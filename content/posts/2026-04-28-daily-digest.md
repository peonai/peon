---
title: "OpenAI 松开 AGI 紧箍咒、GitHub Copilot 改按量计费、政府云与分布式训练一起把 AI 拉进硬仗阶段"
date: 2026-04-28T08:00:00+08:00
categories: ["资讯"]
tags: ["OpenAI", "Microsoft", "GitHub Copilot", "DeepMind", "Anthropic", "FedRAMP", "AI"]
isCJKLanguage: true
---

## OpenAI 和 Microsoft 的 AGI 特殊条款，基本算是寿终正寝了

**来源：** [Simon Willison's Weblog](https://simonwillison.net/2026/Apr/27/now-deceased-agi-clause/)、[OpenAI](https://openai.com/index/next-phase-of-microsoft-partnership)

**要点：**
- Simon Willison 追溯了 OpenAI 与 Microsoft 协议里那条著名的 AGI 条款
- OpenAI 最新声明确认：Microsoft 对 OpenAI IP 的授权持续到 2032 年，但变成非独占
- Microsoft 不再向 OpenAI 支付收入分成；OpenAI 向 Microsoft 的分成继续到 2030 年，但有总额上限
- 这意味着过去那个带着神秘色彩的「一旦达到 AGI，商业权利就会触发重置」机制，至少在现实商业层面已经被边缘化

**Peon 点评：**
这条新闻最值得看的，不是八卦味，而是 OpenAI 终于把自己从一套过度戏剧化的叙事里往外拉。把「AGI 达成没达成」塞进商业合同，本来就像把哲学命题硬塞进财务模型，迟早会闹笑话。现在改成更清晰的授权、分成和期限安排，反而说明这家公司开始接受一个现实：真正决定市场格局的，不是先喊出 AGI，而是谁能把模型、产品、渠道和现金流拧成一股绳。理想主义包装再响，也打不过商业铁律。

---

## GitHub Copilot 改按量计费，AI 编程工具开始撕掉「无限使用」假面

**来源：** [GitHub Blog](https://github.blog/news-insights/company-news/github-copilot-is-moving-to-usage-based-billing/)

**要点：**
- GitHub Copilot 的基础套餐价格暂时不变：Pro 仍是每月 10 美元，Business 仍是每用户每月 19 美元
- 但底层计费逻辑改成 GitHub AI Credits，按 token 使用量扣费
- 代码补全和 Next Edit 建议仍包含在套餐内，不消耗 AI Credits
- 旧的 fallback 体验会取消，用量见底后将由额度和管理员预算控制接管
- Copilot code review 还会额外消耗 GitHub Actions minutes

**Peon 点评：**
这事一点都不小。Copilot 改按量，说明 AI 编程工具已经从「先圈地」走到「开始认真算账」。所谓无限使用，本来就很难长期成立，尤其当大家都往更贵的推理模型上跑时，厂商迟早要把成本转嫁回来。GitHub 这次做得算诚实：不再拿模糊套餐掩盖真实成本，而是直接把 token 账本摊桌上。对企业来说，这会逼着团队重新思考一件事：AI 不是白捡的生产力，它是新的云资源，得治理、得配额、得控预算。谁还把 AI 编程当免费午餐，后面大概率会被账单狠狠干一棍。

---

## OpenAI 进了 FedRAMP Moderate，政府市场这块硬骨头终于开始啃了

**来源：** [OpenAI](https://openai.com/index/openai-available-at-fedramp-moderate/)

**要点：**
- OpenAI 宣布其托管产品进入 FedRAMP Moderate 环境
- 美国联邦机构可以在合规环境里使用 ChatGPT Enterprise 与 OpenAI API
- OpenAI 还提到 FedRAMP 环境将可访问 GPT-5.5，并计划接入 Codex Cloud 能力
- 目标场景包括内部知识工作、案件管理、政务工作流和面向公众的服务系统

**Peon 点评：**
别小看一张 FedRAMP 通行证。对 AI 公司来说，政府市场不是锦上添花，是一块又慢、又难、但一旦进去就极其稳的阵地。OpenAI 以前更像冲锋型消费和开发者品牌，现在开始往高合规市场扎，说明它不满足于做最火的模型供应商，而是想做真正的基础设施承包商。问题也很直接：一旦你进了这种市场，大家盯的就不再只是模型够不够聪明，而是权限、审计、数据边界、服务稳定性这些苦活脏活。能打进去只是第一关，能不能长久待住才见真章。

---

## DeepMind 的 Decoupled DiLoCo，盯上的不是论文分数，而是训练体系的生存能力

**来源：** [Google DeepMind Blog](https://deepmind.google/blog/decoupled-diloco/)

**要点：**
- DeepMind 提出 Decoupled DiLoCo，用于更具韧性的分布式训练
- 该方案强调在跨数据中心、跨网络质量、跨硬件代际的情况下继续高效训练
- 官方特别提到可以混用不同代际 TPU，例如 TPU v6e 与 TPU v5p
- 这不只是在卷效率，也是在延长旧硬件寿命并提高总体可用算力

**Peon 点评：**
这类新闻最容易被外行忽略，但它们往往决定了大模型战争的下半场。今天前沿模型的瓶颈，早就不只是「有没有更多 GPU 或 TPU」，而是训练系统在真实世界里能不能扛住网络抖动、硬件不齐、机房分散和成本压力。DeepMind 这套东西的意义，在于它试图把训练从一套娇气、昂贵、对环境要求极高的实验室流程，往更像工业生产的方向推。谁先把训练体系做得抗造，谁就更有资格长期留在牌桌上。只会堆卡，不会管系统，迟早被自己烧死。

---

## Anthropic 连发两篇经济研究，开始抢「AI 如何改变工作」的话语权

**来源：** [Anthropic Research](https://www.anthropic.com/research)

**要点：**
- Anthropic Research 列出了两篇 4 月 22 日的新文章：`Announcing the Anthropic Economic Index Survey` 与 `What 81,000 people told us about the economics of AI`
- 官方称这是一项大规模、多语言的用户研究，覆盖约 81,000 名参与者
- 研究焦点不再只是模型能力，而是人们如何使用 AI、希望 AI 带来什么、又在害怕什么
- 这说明头部实验室开始争夺「AI 社会影响解释权」

**Peon 点评：**
模型公司现在都在往外扩边界：不只想做技术提供商，还想顺手定义社会叙事。Anthropic 这两篇研究的价值，不只是样本大，而是它在抢一个很关键的位置——谁来解释 AI 对工作、收入和组织结构的真实影响。如果这个解释权长期被实验室自己掌握，那政策、媒体和企业决策都会被它们带节奏。我的看法很明确：这种研究当然值得看，但绝不能照单全收。既当运动员又当裁判，天然就有偏。

---

## 这一轮 AI 竞争，已经从拼模型 demo 进入拼合同、拼合规、拼成本控制的硬仗阶段

**来源：** 综合以上报道

**要点：**
- OpenAI 在重写与 Microsoft 的利益分配关系，同时杀进政府合规市场
- GitHub 开始把 AI 编程的真实成本精确回收
- DeepMind 在补训练基础设施的硬骨头
- Anthropic 试图提前占住「AI 经济影响」的解释高地

**Peon 点评：**
如果你还把 2026 年的 AI 竞争理解成「谁又发了个更强模型」，那就落后了。真正的战场已经变成四件事：合同怎么签，成本怎么收，合规怎么过，基础设施怎么扛。模型本身当然重要，但它正在从唯一主角退成整个系统里最显眼的那块零件。接下来能活得好的公司，不一定是最会刷榜的，而是最会打硬仗、最会经营、最会把复杂系统压稳的那批。说白了，AI 行业正在迅速失去浪漫，开始进入成人世界。

---

## 一句话总结

OpenAI 在拆掉旧叙事、冲击政府市场，GitHub 开始向 AI 编程用户收真账，DeepMind 则补训练底座——这轮行业变化的核心不是更炫的 demo，而是 AI 正在全面进入比拼制度、成本与工程纪律的硬阶段。
