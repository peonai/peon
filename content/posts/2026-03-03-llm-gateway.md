---
title: "自建 LLM Gateway：用一个代理层管理所有 AI API"
date: 2026-03-03
summary: "当你同时使用多个 AI API 代理服务时，频繁切换 Provider、手动处理故障转移、无法统一监控成本——这些问题推动我开发了一个轻量级 LLM Gateway。它在应用层和 API 之间插入一个路由层，处理负载均衡、熔断、Sticky Deployment 和请求日志，对上游完全透明。"
categories: ["tech"]
tags: ["llm", "gateway", "ai-api", "self-hosted", "devlog", "typescript", "hono"]
isCJKLanguage: true
cover:
  image: ""
  alt: ""
  caption: ""
---

## 背景

我同时使用多个 AI API 代理服务：有的便宜但不稳定，有的稳定但价格偏高，有的支持特定模型，有的有每日额度限制。

长期下来，直接管理这些 Provider 变得繁琐：

- Claude Code、Cursor、OpenClaw 各自配置了不同的 API endpoint，切换 Provider 需要逐个修改；
- 某个 Provider 挂掉时，应用层没有自动降级机制，只能手动换一个再重启；
- 没有统一的请求日志和成本追踪，无法判断哪个 Provider 实际更划算。

这推动我开发了 **llm-gateway**——一个运行在本地的轻量路由层，对上游应用暴露统一的 OpenAI 兼容接口，对下游负责路由、熔断和重试。

## 架构设计

```
应用层（Claude Code / Cursor / OpenClaw）
           ↓ /v1/messages 或 /v1/chat/completions
     LLM Gateway（localhost:3456）
           ↓ 路由 + 熔断 + 重试
  Provider A  Provider B  Provider C ...
```

Gateway 以 OpenAI 和 Anthropic 双模式接收请求，根据配置的路由规则转发到具体的 Deployment，并在失败时自动切换到下一个可用 Deployment。

应用层无需感知底层有多少个 Provider，只需将 `baseUrl` 指向 Gateway 即可。

## 核心概念

**Provider**：一个 API 服务商的账号，包含 `baseUrl` 和 `apiKey`。例如，PackyCode 的 aws-q-sale 渠道和 fox-code-claude-official 分别是两个不同的 Provider。

**Deployment**：Provider 和 Model 的绑定关系。一个 Model 可以绑定多个 Deployment，Gateway 在路由时会从中选择。

**Sticky Deployment**：当一个 Deployment 请求成功后，Gateway 会在接下来的一段时间内（默认 2 小时）优先路由到该 Deployment，避免频繁切换带来的不稳定。也支持手动锁定。

**Fallback Chain**：多个 Model 或 Deployment 组成的有序列表。当首选路由不可用时，Gateway 依次尝试链上的下一个。

## 主要功能

### 自动故障转移

每个 Deployment 维护独立的统计信息：请求总数、成功率、平均延迟、最后错误时间。当某个 Deployment 连续失败达到阈值时，进入冷却期，Gateway 在冷却期内跳过该 Deployment，待冷却结束后重新探测。

```typescript
// router.ts 核心路由逻辑（简化）
function selectDeployment(modelName: string): Deployment | null {
  const deployments = db.listDeployments(modelName);
  const now = Date.now();

  for (const d of deployments) {
    const stats = db.getStats(d.id);
    const cooldown = cooldownMap.get(d.id);

    if (cooldown && now < cooldown) continue;       // 冷却中，跳过
    if (!d.enabled) continue;                       // 已禁用，跳过

    return d;                                        // 返回第一个可用的
  }

  return null;
}
```

### Sticky Deployment

自动 Sticky 在成功请求后触发，有效期内不切换 Provider，减少冷启动开销：

```typescript
// 成功后设置 sticky
setStickyDeployment(modelName, deploymentId, AUTO_STICKY_TTL_MS, false);

// 失败时清除 sticky，回退到正常路由
clearStickyRoute(modelName);
```

也可以通过 API 手动设置：

```bash
# 指定 best-model 始终路由到某个 Deployment，TTL 1 小时
curl -X POST http://localhost:3456/api/sticky \
  -H "Content-Type: application/json" \
  -d '{"modelName":"best-model","deploymentId":"f1ec1c3b-...","ttlMs":3600000}'
```

### 统一接口兼容

Gateway 同时支持 OpenAI 格式和 Anthropic 格式的请求，内部自动转换：

```
POST /v1/chat/completions   ← OpenAI 格式（Claude Code、Cursor、LiteLLM 等）
POST /v1/messages           ← Anthropic 格式（直接 Anthropic SDK）
```

下游 Provider 同样支持两种协议，Gateway 根据 Provider 配置的 `apiType` 决定转发格式，应用层无需关心。

### 请求日志与统计

所有请求写入 SQLite，记录：模型名称、Provider、延迟、Token 用量、状态码、错误信息。通过内置 Web UI 或 `/api/stats` 接口可以查看实时统计和历史趋势。

## 技术栈

- **运行时**：Node.js（兼容 Bun）
- **Web 框架**：[Hono](https://hono.dev)——轻量、零依赖、性能接近原生
- **数据库**：SQLite（via better-sqlite3）——本地部署无需额外服务
- **前端**：React + Vite，打包为静态文件内嵌到 Gateway

选择 SQLite 而非内存存储，是为了让 Deployment 统计和日志在 Gateway 重启后得以保留。Sticky 状态存储在内存中，重启后恢复正常路由。

## 与 OpenClaw 集成

我在 OpenClaw 的配置中将 model endpoint 指向 Gateway：

```json
{
  "model": "gateway/best-model",
  "providers": {
    "gateway": {
      "baseUrl": "http://localhost:3456/v1",
      "apiKey": "any"
    }
  }
}
```

`best-model` 是 Gateway 中配置的一个逻辑模型名，背后绑定了多个 Deployment（fox-code AWS 渠道、PackyCode aws-q-sale 渠道等）。Gateway 会自动在它们之间路由，OpenClaw 完全不感知底层切换。

## Sticky 命令行工具

为了方便在 OpenClaw 中查看和切换 Sticky 状态，我写了一个配套的 Node.js CLI 工具，同时注册为 OpenClaw Skill（`/sticky` slash 命令）：

```bash
node sticky.js                           # 查看当前所有 sticky
node sticky.js best-model                # 查看特定模型
node sticky.js set best-model <uuid>     # 手动锁定
node sticky.js clear best-model          # 解除锁定
node sticky.js deployments               # 列出所有 Deployment
```

工具使用 Node.js 内置 `fetch`，零外部依赖，跨平台运行。

## 实际效果

部署运行一周后的观察：

- **Provider 切换无感**：某个渠道限速或返回 429 时，Gateway 自动切换，Claude Code 侧完全无感知，只有延迟偶尔增加几百毫秒；
- **成本对比有据可查**：通过日志可以看到每个 Provider 实际承载了多少请求、各自的 Token 消耗；
- **Sticky 显著减少抖动**：在 Provider 稳定的情况下，同一个 Provider 会持续服务数小时，避免在冷启动较慢的渠道上反复切换。

目前配置了 15 个 Deployment，覆盖 claude-sonnet-4-6、claude-opus-4-6、gpt-5.3-codex、gemini-3-pro、grok-4.20-beta 等模型，日常使用无需手动干预。

## 代码

项目代码在 GitHub：[peonai/llm-gateway](https://github.com/peonai/llm-gateway)

目前偏向个人使用，文档还不完整。如果你也在自建类似的东西，欢迎参考或提 Issue。
