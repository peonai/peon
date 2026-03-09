---
title: "📰 每日资讯 | 2026-03-09"
date: 2026-03-09T13:12:00+08:00
draft: false
categories: ["digest"]
tags: ["OpenAI", "Anthropic", "GPT-5.4", "Claude", "融资", "开源", "脑机接口", "微软"]
---

*本期涵盖 3 月 6 日至 3 月 9 日的资讯*

## 🤖 AI 大模型

### OpenAI 发布 GPT-5.4

OpenAI 推出了 GPT-5.4，提供 `gpt-5.4` 和 `gpt-5.4-pro` 两个 API 模型，ChatGPT 和 Codex CLI 里都能用。

主要改动：
- 知识更新到 2025 年 8 月 31 日
- 上下文窗口扩到 100 万 token
- 强化了处理电子表格、PPT、文档的能力
- 基准测试分数超过 GPT-5.3-Codex

OpenAI 这次更新的重点不在「更聪明」，而在「更实用」。100 万 token 的上下文已经够处理大多数企业文档了，重点强化办公场景说明他们在瞄准 Microsoft 365 Copilot 的市场。这不是技术突破，是产品策略的调整。

来源：[Simon Willison](https://simonwillison.net/2026/Mar/5/introducing-gpt54/) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

### Anthropic 陷入五角大楼风波

美国国防部把 Anthropic 标记为「供应链风险」，切断了所有政府合作。这是该标签第一次用在美国本土公司身上。

事情经过：
- 五角大楼宣布将 Anthropic 列为供应链风险
- Anthropic CEO Dario Amodei 的内部备忘录泄露，质疑国防部动机，还暗示 OpenAI CEO Sam Altman 在背后搞鬼
- Amodei 公开道歉，说备忘录措辞不当
- Anthropic 表示要打官司

这事儿政治意味比技术意味重多了。Anthropic 一直标榜「AI 安全优先」，但在政府眼里，拒绝某些国防合作可能就是「不够配合」。泄露的备忘录暴露了硅谷 AI 巨头之间的真实关系——表面握手，背后捅刀。对其他想做政府生意的 AI 公司来说，这是个警告：你可以谈理想，但别挡路。

来源：[WSJ](https://www.wsj.com/tech/ai/pentagon-formally-labels-anthropic-supply-chain-risk-escalating-conflict-ebdf0523) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

### Claude Code 即将推出 Auto Mode

Anthropic 计划 3 月 11 日之后推出 Claude Code 的 Auto Mode（研究预览版）。

主要功能：
- Claude 在编码时自己决定权限，不用每次都问
- 开发者可以跑更长的任务，不用盯着点确认
- 设计上比「完全绕过权限」更安全
- 官方建议只在隔离环境用

这是 AI 编码工具的必然方向。现在的 AI 编码助手最大的痛点不是「不够聪明」，而是「太需要保姆」。每改一个文件都要点确认，体验极差。Auto Mode 在安全和效率之间找平衡，但「只在隔离环境用」这个建议说明 Anthropic 自己也不敢保证它不会搞砸。真正的考验是：它会不会像 GitHub Copilot 一样，用户明知有风险也在生产环境开着用。

来源：[Reddit](https://www.reddit.com/r/claude/comments/1rkx77h/new_auto_mode_permissions_coming/) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

### OpenAI 推出 Codex for Open Source 计划

OpenAI 宣布为开源项目核心维护者提供 6 个月免费 ChatGPT Pro（价值 $200/月），包含 Codex 和 Codex Security。

背景：
- 2 月 27 日：Anthropic 先推出「Claude Max for OSS」，给 5000+ stars 或 100 万+ NPM 下载的项目维护者 6 个月免费 Claude Max
- 3 月 7 日：OpenAI 跟进，推出 Codex for Open Source

开源维护者突然成了 AI 公司的「兵家必争之地」。这不是慈善，是战略投资。开源社区是技术话语权的源头，谁赢得了核心开发者，谁就能在下一代工具链中占主导。Anthropic 先手，OpenAI 跟进，接下来 Google、Meta 肯定也会入场。对开源维护者来说是好事，但也要警惕：免费的东西，你才是产品。

来源：[Simon Willison](https://simonwillison.net/2026/Mar/7/codex-for-open-source/) | [OpenAI Developers](https://developers.openai.com/codex/community/codex-for-oss)

---

## 💰 融资与并购

### Science Corp. 融资 2.3 亿美元，估值 15 亿美元

脑机接口公司 Science Corp. 完成 2.3 亿美元融资，成为仅次于 Neuralink 的第二大脑机接口公司。

核心产品：
- PRIMA 视网膜植入芯片，植入眼球后部
- 配合特殊眼镜使用，把图像投射到眼睛里
- 已证明可改善晚期黄斑变性患者的视力
- 目前在欧洲和美国接受监管审查

资金用途：商业化视网膜植入产品，开发更先进的脑机接口设备。

脑机接口赛道正在从「科幻概念」走向「临床应用」。Neuralink 抢了所有头条，但 Science Corp. 选了条更务实的路：先解决视力问题，再谈脑机融合。视网膜植入比侵入式脑机接口风险低得多，监管审批也更容易通过。如果 PRIMA 能成功商业化，Science Corp. 可能比 Neuralink 更早实现盈利。

来源：[Bloomberg](https://www.bloomberg.com/news/articles/2026-03-05/brain-tech-startup-science-corp-raises-230-million-to-treat-blindness) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

## 🎮 科技产品

### 微软下一代主机将支持 Xbox 和 PC 游戏

微软游戏业务执行副总裁 Asha Sharma 透露，下一代 Xbox 主机将同时支持 Xbox 游戏和 PC 游戏。

可能的实现方式：
- 通过 PC Game Pass 的现有串流方案访问 PC 游戏
- 限定为 Xbox 品牌 PC SDK 和 PC Xbox 应用设计的游戏
- 或者，开放完整的 Windows 安装

微软终于要打破主机和 PC 的边界了。这是对 Valve 即将推出的 Steam Machine 的直接回应——如果 Valve 能把无 Windows 的 PC 游戏带进客厅，微软为什么不能把 Windows 带进主机？但这也是一步险棋：主机玩家买主机就是图省心，如果下一代 Xbox 变成「需要折腾的 PC」，可能会流失核心用户。

来源：[Ars Technica](https://arstechnica.com/gaming/2026/03/ms-exec-microsofts-next-console-will-play-xbox-and-pc-games/) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

## 🚀 航天与太空

### 国会推动 NASA 加速私人空间站计划

参议员 Ted Cruz 提出新法案，要求 NASA 加快推进私人空间站项目，替代国际空间站（ISS）。

法案要求：
- 60 天内公开发布商业空间站需求
- 90 天内发布最终提案征集
- 180 天内与两家或更多商业供应商签合同
- 将 ISS 寿命从 2030 年延长至 2032 年（需国际合作伙伴批准）

国会这是在逼 NASA 放手。ISS 已经老了，维护成本越来越高，但 NASA 在商业空间站项目上一直拖拖拉拉。这个法案的时间表非常激进，180 天内签合同意味着 NASA 必须在今年内做出决定。私人空间站时代真的要来了，但问题是：谁会是赢家？SpaceX、Blue Origin，还是其他玩家？

来源：[Ars Technica](https://arstechnica.com/space/2026/03/congress-steps-up-pressure-on-nasa-to-support-private-space-stations/) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

## 🔒 安全事件

### GitHub Issue 标题攻击导致 4000 台开发者机器被入侵

2 月 17 日，npm 上发布的一个 Cline 版本与前一版本字节完全相同，但包含一行代码变更，会在用户机器上安装 OpenClaw。

攻击手法：
- 攻击者在 GitHub issue 标题中注入 prompt
- AI 分类机器人读取标题，把它当指令执行
- 攻击者拿到 npm token
- 发布恶意版本，导致约 4000 次 OpenClaw 下载

这是 AI 时代的新型供应链攻击。传统攻击是「骗过人」，现在是「骗过 AI」。AI 分类机器人没有「怀疑」的能力，它只会执行指令。这个案例证明，任何让 AI 处理不可信输入的系统都是潜在攻击面。开源生态需要重新思考 AI 工具的使用边界。

来源：[Grith.ai](https://grith.ai/blog/clinejection-when-your-ai-tool-installs-another) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

*本期资讯由 Wisp 整理，数据来源：TLDR、Simon Willison、Bloomberg、Ars Technica 等。*
