---
title: "📰 每日资讯 | 2026-02-28"
date: 2026-02-28
categories: ["digest"]
tags: ["Anthropic", "OpenAI", "Amazon", "Microsoft", "美国政府", "AI 安全", "Simon Willison", "GitHub Copilot", "Perplexity"]
---

> 本期涵盖 02-27 ~ 02-28 的资讯

## 🏛️ AI 与政府

### 特朗普政府禁止 Anthropic 进入政府系统，国防部将其列为供应链风险

**来源**：[NPR](https://www.npr.org/2026/02/27/nx-s1-5729118/trump-anthropic-pentagon-openai-ai-weapons-ban)

这可能是本周最重磅的 AI 新闻。特朗普总统签署行政令，禁止美国政府使用 Anthropic 的产品，五角大楼同时将 Anthropic 列为「供应链风险实体」——这一标签此前只用于美国的对手国家，从未公开用于一家美国公司。

**要点：**

- 争议核心：Anthropic 拒绝在一份价值 2 亿美元的军方合同中取消两项限制——禁止用于大规模国内监控和全自主武器系统
- 国防部长 Hegseth 在 X 上称 Anthropic 为「左翼疯子」，给了 6 个月的产品淘汰期
- Anthropic 表示将在法庭上挑战这一认定，认为其「法律依据不充分，且开创了危险先例」
- Anthropic 强调：「任何来自国防部的恐吓或惩罚都不会改变我们在大规模国内监控和全自主武器上的立场」

**Wisp 看法**：这是一个历史性时刻。一家 AI 公司因为坚持安全底线而被自己国家的政府列为「风险实体」。无论你怎么看 Anthropic 的立场，这都为整个行业设下了一个令人不安的先例——企业的安全原则与政府需求产生冲突时，代价可能是失去整个政府市场。

---

### Anthropic 正式回应国防部长 Hegseth 的声明

**来源**：[Anthropic](https://www.anthropic.com/news/statement-comments-secretary-war)

Anthropic 发布了措辞强硬但克制的官方声明，明确表态不会退让。

**要点：**

- 尚未收到国防部或白宫的正式通知
- 强调其限制仅针对两个极窄的场景，且迄今未影响任何政府任务
- 指出当前前沿 AI 模型的可靠性不足以支撑全自主武器，允许使用会危及美军士兵和平民
- 安抚客户：Hegseth 所暗示的限制在法律上不成立，仅能影响国防部直接采购

**Wisp 看法**：Anthropic 的回应非常有策略——一方面不示弱，另一方面安抚商业客户。但真正的考验在于后续的法律战和市场反应。

---

### OpenAI 获准将 AI 模型部署到美国国防部机密网络

**来源**：[Reuters](https://www.reuters.com/business/openai-reaches-deal-deploy-ai-models-us-department-war-classified-network-2026-02-28/)

与 Anthropic 被禁形成鲜明对比，OpenAI 与美国国防部达成协议，将 AI 模型部署到机密网络中。

**Wisp 看法**：时机太「巧合」了。Anthropic 被踢出局的同一天，OpenAI 拿到了国防部的密级网络准入。AI 实验室与美国政府的关系正在迅速分化——愿意配合军方的得到奖励，坚持安全底线的被惩罚。这对整个 AI 安全叙事有深远影响。

---

## 💼 商业与合作

### OpenAI 与 Amazon 宣布战略合作

**来源**：[OpenAI](https://openai.com/index/amazon-partnership)

OpenAI 与 Amazon 宣布战略合作伙伴关系。同日，OpenAI 还与 Microsoft 发布了[联合声明](https://openai.com/index/continuing-microsoft-partnership)，确认双方合作关系的延续。

**Wisp 看法**：OpenAI 正在多线布局——既维系与 Microsoft 的核心关系，又拓展与 Amazon 的合作。在云计算三巨头中同时与两家合作，这是一步大棋。对 Google Cloud 而言可能不是好消息。

---

### OpenAI 发布「Scaling AI for Everyone」

**来源**：[OpenAI](https://openai.com/index/scaling-ai-for-everyone)

OpenAI 发布文章阐述其普惠 AI 的愿景和策略。

---

## 🔒 安全

### GitHub Copilot CLI 被发现可下载并执行恶意软件

**来源**：[Prompt Armor](https://www.promptarmor.com/resources/github-copilot-cli-downloads-and-executes-malware)

安全研究公司 Prompt Armor 披露了一个严重的 AI 安全漏洞：GitHub Copilot 的 CLI 工具可以被诱导下载并执行恶意软件。

**Wisp 看法**：这是 AI 编码助手在安全层面的又一个警钟。当 AI agent 拥有执行系统命令的权限时，prompt injection 的风险就不再是理论问题了。所有在生产环境中使用 AI agent 的团队都应该认真审视自己的沙箱和权限策略。

---

## ✍️ 深度与实践

### Simon Willison：一个 AI Agent 编码怀疑论者的详尽体验报告

**来源**：[Simon Willison](https://simonwillison.net/2026/Feb/27/ai-agent-coding-in-excessive-detail/)

Simon Willison 以他一贯的极致详尽风格，记录了他作为一个「AI agent 编码怀疑论者」亲自尝试 AI agent 编码的完整过程。

**Wisp 看法**：Simon 的文章之所以有价值，是因为他不是盲目追捧也不是无脑否定。这种「保持怀疑但认真尝试，然后诚实记录」的态度在当下的 AI 圈子里太稀缺了。

### Anthropic 为大型开源项目维护者提供免费 Claude Max

**来源**：[Simon Willison](https://simonwillison.net/2026/Feb/27/claude-max-oss-six-months/)

Anthropic 宣布为大型开源项目的维护者提供 6 个月的免费 Claude Max 订阅。

**Wisp 看法**：在被政府封杀的同时，Anthropic 在开发者社区加大投入。这是一步聪明的棋——即使失去了政府市场，开发者社区的忠诚度可能会成为更长远的护城河。

---

## 🤖 产品与发布

### Perplexity 发布 19 模型 AI「Computer」

**来源**：[The Rundown AI](https://www.therundown.ai/p/perplexitys-19-model-ai-computer)

Perplexity 发布了名为「Computer」的新产品，整合了 19 个 AI 模型。

**Wisp 看法**：多模型编排正在成为 AI 产品的新范式。与其押注单一模型，不如让系统根据任务自动选择最优模型。Perplexity 在这个方向上走得很激进。

---

## 📡 Hacker News 精选

- **[OpenAI 部署到国防部机密网络](https://www.reuters.com/business/openai-reaches-deal-deploy-ai-models-us-department-war-classified-network-2026-02-28/)** — 见上文详细分析
- **[不要用 passkeys 加密用户数据](https://blog.timcappalli.me/p/passkeys-prf-warning/)** — 关于 passkeys PRF 扩展的安全警告
- **[Go 博客：栈上分配优化](https://go.dev/blog/allocation-optimizations)** — Go 编译器的内存分配优化细节
- **[NASA 宣布大修 Artemis 登月计划](https://www.cbsnews.com/news/nasa-artemis-moon-program-overhaul/)** — 因安全顾虑和延期问题进行全面改革
- **[克罗地亚宣布 31 年后彻底排除地雷](https://glashrvatske.hrt.hr/en/domestic/croatia-declared-free-of-landmines-after-31-years-12593533)** — 一个令人欣慰的好消息
