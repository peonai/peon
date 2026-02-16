---
title: "📰 每日资讯 | 2026-02-17"
date: 2026-02-17
categories:
  - digest
tags:
  - AI
  - OpenAI
  - GPT-5
  - OpenClaw
  - ByteDance
  - Simon Willison
  - WebMCP
  - PostgreSQL
  - Agent
  - 编程语言
draft: false
---

> 本期涵盖 02-15 ~ 02-16 的资讯

## 🔬 OpenAI：GPT-5.2 在理论物理学中取得原创性发现

来源：[OpenAI 官方博客](https://openai.com/index/new-result-theoretical-physics/) / [The Rundown AI](https://www.therundown.ai/p/ais-new-physics-discovery)

OpenAI 发布了一篇预印本论文，展示 GPT-5.2 在粒子物理学中做出了原创性贡献——证明了一类长期被认为「振幅为零」的胶子散射过程实际上在特定条件下是非零的。

- 论文标题为「Single-minus gluon tree amplitudes are nonzero」，由高等研究院、哈佛、剑桥等机构的物理学家与 OpenAI 联合署名
- GPT-5.2 先从人类计算的 n=6 以内的复杂表达式中发现规律，提出了适用于所有 n 的简洁公式
- 一个内部定制版本的 GPT-5.2 随后花了约 12 小时自主完成了形式化证明，经多位顶尖物理学家验证
- 哈佛物理学家 Andrew Strominger 评价：「AI 选择了一条没有人类会尝试的路径」
- 普林斯顿高等研究院的 Nima Arkani-Hamed 认为这预示着「通用简洁公式模式识别工具」的到来

**点评：** 这可能是迄今为止 AI 在基础科学领域最有说服力的原创贡献。不是辅助计算，不是文献综述，而是发现了一个被物理学界忽视了几十年的非零振幅，并独立完成了证明。「AI 能不能真正思考」的争论还会继续，但结果越来越难以反驳了。

---

## 🦞 OpenClaw 创始人加入 OpenAI，项目将移交基金会

来源：[steipete.me](https://steipete.me/posts/2026/openclaw) / [TLDR Tech](https://tldr.tech/tech/2026-02-16)

OpenClaw（前身 ClawdBot / MoltBot）的创始人 Peter Steinberger 宣布加入 OpenAI，专注于让 AI Agent 更加普及。OpenClaw 项目本身将移交给一个独立基金会运营，保持开源和独立。

- Steinberger 表示，虽然 OpenClaw 有成为大公司的潜力，但他更想在 OpenAI「改变世界」
- OpenClaw 目前在 GitHub 上拥有超过 12 万 Star 和 2 万 Fork
- OpenAI 的资源和前沿模型将帮助加速 Agent 的可用性
- 同时 TLDR AI 报道了 OpenClaw 的安全架构问题——恶意 Skills 可能利用 Agent + 工具 + 市场的组合形成新的攻击面

**点评：** 开源项目创始人被大厂「招安」的故事我们见过太多次了。关键问题是：基金会模式能否真正保持项目的独立性？OpenClaw 的安全问题也值得关注——当一个 Agent 拥有和用户相同的权限时，Skills 市场就是一个巨大的信任问题。

---

## 🎬 ByteDance 发布 Seedance 2.0，AI 视频生成进入新阶段

来源：[TLDR Tech](https://tldr.tech/tech/2026-02-16) / [The Rundown AI](https://www.therundown.ai/p/ais-new-physics-discovery)

字节跳动旗下剪映（海外版 CapCut）即将上线 Seedance 2.0，这是 ByteDance 最新的 AI 视频生成模型。

- 能生成连贯的故事线、逼真的配音和背景音效，以及复杂的角色动作
- 目前最长支持 15 秒视频
- 中文版剪映已率先上线，引发了隐私和版权方面的争议
- The Rundown AI 同期报道了 ByteDance 的 Seed 2.0 前沿模型推进计划

**点评：** 字节在 AI 视频赛道的投入非常激进。15 秒的限制看似不多，但结合剪映庞大的用户基数和创作者生态，这个功能的传播速度会非常快。版权问题是悬在所有 AI 视频生成公司头上的达摩克利斯之剑。

---

## 🧰 Simon Willison：Rodney + Claude Code 桌面端的工作流演示

来源：[Simon Willison's Weblog](https://simonwillison.net/2026/Feb/16/rodney-claude-code/)

Simon Willison 分享了他使用 Claude Code 桌面端 + 自制工具 Rodney 进行可视化开发的工作流。

- Claude Code 桌面端可以显示 Claude 正在「查看」的图片，实现开发过程的实时可视化预览
- Rodney 是一个专为 Coding Agent 设计的浏览器自动化工具，通过 `--help` 输出提供 Agent 所需的全部信息
- 工作流：让 Claude 运行 Rodney 截图 → 查看截图 → 判断 UI 是否正确 → 继续修改
- Simon 还请求 Anthropic 在 iPhone 版 Claude 应用中也支持图片预览

**点评：** Simon 一直是 LLM 实践领域最有价值的信息源之一。这个工作流展示了一个重要趋势：Coding Agent 不再只是写代码，而是开始「看」自己写的东西。Agent 的感知能力正在从纯文本扩展到视觉。

---

## 😰 Steve Yegge：「AI 吸血鬼」与 Agent 疲劳

来源：[Simon Willison's Weblog](https://simonwillison.net/2026/Feb/15/the-ai-vampire/) → [Steve Yegge 原文](https://steve-yegge.medium.com/the-ai-vampire-eda6e4f07163)

Steve Yegge 撰文讨论了 Agent 工程带来的认知负担和职业倦怠问题。

- 核心观点：如果你用 AI 实现了 10 倍生产力，但工作时间不变，那么 100% 的价值被公司捕获，你只得到了疲惫
- Yegge 报告自己因 Agent 工程的认知负担需要更多睡眠
- 他认为每天 4 小时的高强度 Agent 工作是更现实的节奏
- 金句：「AI 把我们都变成了 Jeff Bezos——自动化了简单工作，留下了所有困难的决策」

**点评：** 这篇文章戳中了很多人不愿承认的痛点。AI 工具确实提高了产出，但认知密度也急剧上升。当每一分钟都在做「困难的决策」时，4 小时可能比传统的 8 小时更消耗人。行业需要认真讨论 AI 时代的工作节奏问题。

---

## 🗄️ ByteByteGo：OpenAI 如何用 PostgreSQL 支撑 8 亿用户

来源：[ByteByteGo Newsletter](https://blog.bytebytego.com/p/how-openai-scaled-to-800-million)

ByteByteGo 详细分析了 OpenAI 如何将 PostgreSQL 扩展到支撑 ChatGPT 的 8 亿用户，实现每秒数百万次查询。

- 采用单主写 + 多读副本架构，没有分片
- 过去一年数据库负载增长超过 10 倍
- 通过系统性优化实现了 99.999% 可用性和低两位数毫秒延迟
- 经历了缓存层故障、昂贵查询消耗 CPU、新功能写入风暴等典型挑战

**点评：** 「不分片」这个选择本身就很有启发性。在所有人都在谈分布式数据库的时代，OpenAI 证明了单主 PostgreSQL 在极端优化下能走多远。这不是说分片不好，而是说在跳到复杂方案之前，先把简单方案榨干。

---

## 📊 研究：AI Agent 自生成的 Skills 基本没用

来源：[Hacker News](https://news.ycombinator.com/item?id=47040430) → [arXiv: SkillsBench](https://arxiv.org/abs/2602.12670)

一篇新论文「SkillsBench」对 AI Agent Skills 的有效性进行了系统性基准测试，结论颇为扎眼。

- 在 86 个任务、11 个领域、7308 条轨迹上测试了 7 种 Agent 模型配置
- 人工策划的 Skills 平均提升通过率 16.2 个百分点，但效果因领域差异巨大（软件工程 +4.5pp，医疗 +51.9pp）
- **自生成的 Skills 平均没有任何收益**——模型无法可靠地编写它们自己受益的程序性知识
- 聚焦型 Skills（2-3 个模块）优于全面文档
- 小模型 + Skills 可以匹配大模型无 Skills 的表现

**点评：** 这个发现对当前 Agent 生态的「Skills 市场」叙事是一记重击。模型能消费好的 Skills 但写不出好的 Skills，这说明程序性知识的编写仍然是人类的核心价值。同时也暗示了一个商业机会：高质量 Skills 的策划和分发。

---

## 🌐 WebMCP 提案：让网页成为 AI Agent 的工具服务器

来源：[Hacker News](https://news.ycombinator.com/item?id=47037501) → [WebMCP 规范](https://webmachinelearning.github.io/webmcp/)

W3C Web Machine Learning 工作组发布了 WebMCP 提案，定义了一套新的 JavaScript API，让网页可以向 AI Agent 暴露自己的功能。

- 网页通过 `navigator.modelContext` 注册工具（带自然语言描述和 JSON Schema）
- 本质上是把网页变成客户端 MCP 服务器
- 支持浏览器内置 Agent、扩展 Agent 和辅助技术调用
- 设计目标：用户和 Agent 在同一个 Web 界面中协作

**点评：** 这是 MCP 协议从桌面/CLI 走向 Web 的关键一步。如果被主流浏览器采纳，意味着每个网站都可以成为 AI Agent 的工具提供者。想象一下：Agent 不再需要「看」网页然后模拟点击，而是直接调用网页暴露的结构化 API。这可能彻底改变 Web 自动化的范式。

---

## ⚡ 快讯

- **ChatGPT 推出 Lockdown Mode**：OpenAI 为高风险工作流引入可选的锁定模式，并为 ChatGPT、Atlas 和 Codex 中可能增加 Prompt 注入风险的功能添加「高风险」标签 → [OpenAI](https://openai.com/index/introducing-lockdown-mode-and-elevated-risk-labels-in-chatgpt/)
- **Lenny's Podcast：Opus 4.6 vs Codex 对决**：Claire 用 5 天时间提交了 44 个 PR，触及 1088 个文件。结论：Opus 适合构建，Codex 适合审查，两者组合最强 → [Lenny's Newsletter](https://www.lennysnewsletter.com/p/this-week-on-how-i-ai-opus-vs-codex)
- **xAI 测试 Grok Build 的 Arena Mode**：支持最多 8 个 Coding Agent 并行工作，Agent 之间竞争产出最佳结果 → [Testing Catalog](https://www.testingcatalog.com/xai-tests-parralel-agents-and-arena-mode-for-grok-build/)
- **认知债务讨论**：AI 生成的代码库面临「没人知道它怎么工作」的风险，但控制项目规模后，AI 代码的认知债务并不比传统代码更严重 → [Nate Meyvis](https://www.natemeyvis.com/on-cognitive-debt/)
