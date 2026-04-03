---
title: "Google 开源 Gemma 4 挑战开源格局，OpenAI 进军媒体收购 TBPN"
date: 2026-04-04T07:30:00+08:00
categories: ["digest"]
tags: ["AI", "Google", "Gemma", "OpenAI", "Anthropic", "开源", "融资"]
---

## Google 发布 Gemma 4 开源模型，改用 Apache 2.0 许可证

来源：https://www.latent.space/p/ainews-gemma-4-the-best-small-multimodal

Google DeepMind 于 4 月 2 日正式发布 Gemma 4 系列开源模型。这次发布包含四个型号：31B 密集模型、26B MoE 模型（A4B，实际激活约 40 亿参数）、以及面向移动和边缘设备的 E2B 和 E4B 轻量版本。

最值得关注的是许可证变更——Gemma 4 采用 Apache 2.0 许可证，相比此前 Gemma 系列的商业限制条款，这次完全放开商业使用。这意味着开发者可以自由修改、部署和商业化这些模型，无需担心月活用户数限制或使用场景限制。

Gemma 4 在架构上有不少新尝试：支持多模态输入（文本、图像、音频）、最长 256K token 上下文窗口、原生函数调用和结构化 JSON 输出。31B 版本在 LMSYS Arena 开源模型排行榜上位列第三，26B-A4B 版本排名第六。对于需要本地部署或边缘计算的场景，E2B 和 E4B 版本可以在完全离线状态下运行，延迟接近零。

这个发布时机很有意思。Allen Institute 的突发人事变动加上 GPT-OSS 的悬而未决，让美国开源模型的未来充满变数。Google 此时加速推进 Gemma 4，既是在填补生态空缺，也是在向 Meta Llama 和 Mistral 施压。

## OpenAI 收购科技媒体 TBPN，1220 亿美元融资创纪录

来源：https://www.pymnts.com/acquisitions/2026/openai-buys-tech-talk-show-tbpn-in-media-expansion/

OpenAI 完成了一笔意外的媒体收购——以数亿美元收购科技访谈节目 TBPN（Technology Business Programming Network）。这个由 Jordi Hays 和 John Coogan 主持的日更节目自 2024 年 10 月上线以来，每期平均吸引 7 万观众，嘉宾包括扎克伯格、Sam Altman 等科技界重量级人物。

收购背后透露出一个信号：OpenAI 不满足于只做技术产品，它想控制围绕 AI 的公共叙事。TBPN 将继续保持编辑独立性，但团队将向 OpenAI 全球事务负责人 Chris Lehane 汇报，协助公司的营销和传播工作。

与此同时，OpenAI 刚刚完成了可能是史上最大的一笔私募融资——1220 亿美元，估值达到 8520 亿美元。投资方包括 Amazon（约 500 亿美元）、NVIDIA（300 亿美元）、SoftBank（约 300 亿美元）等。值得注意的是，Amazon 的投资中有 350 亿美元是条件性的——只有在 OpenAI 上市或实现 AGI 时才会兑现。

OpenAI 应用业务负责人 Fidji Simo 在内部备忘录中提醒员工「不要被支线任务分心」，但 TBPN 的收购表明，公司认为掌控传播渠道本身就是 AI 竞争的一部分。

## Anthropic Claude Code 代码泄漏，约 51.2 万行代码意外公开

来源：https://www.itbrew.com/stories/2026/04/03/anthropic-code-leak-exposed-claude-information-but-it-might-not-be-a-total-disaster

Anthropic 在 3 月 31 日发布的 Claude Code 2.1.88 版本中意外包含了一个 59.8MB 的 source map 文件（cli.js.map）。这个调试文件将压缩后的代码映射回原始 TypeScript 源码，导致约 51.2 万行代码在几小时内被公开访问。

安全研究员 Chaofan Shou 首先在 X 上曝光此事，随后 GitHub 上迅速出现多个镜像仓库。Anthropic 确认这是一次「发布打包过程中的人为失误」，而非黑客攻击，并强调没有泄露客户数据、凭证或模型权重。

泄漏的代码主要是 Claude Code 应用的实现细节，而非底层模型架构。不过安全专家指出，这仍可能暴露产品路线图，甚至被用于制作恶意仿冒版本。对于一家正在起诉五角大楼、以 AI 安全为核心理念的公司来说，这个时机相当尴尬。

Anthropic 目前正在努力下架 GitHub 上的镜像仓库，但开源社区的特性意味着代码一旦流出就很难彻底收回。

## 美国 Q1 风投创纪录 2670 亿美元，AI 占比近九成

来源：https://siliconangle.com/2026/04/03/pitchbook-us-venture-funding-surges-record-267b-openai-anthropic-xai-dominate-ai-deals/

根据 PitchBook 数据，2026 年第一季度美国风险投资总额达到 2672 亿美元，较此前季度纪录翻倍。但这笔巨额资金高度集中在少数几家公司：OpenAI（1220 亿美元）、Anthropic（300 亿美元）、xAI（200 亿美元）、Waymo（160 亿美元）和 Databricks（70 亿美元）。这五笔交易占了当季总额的 73%。

如果剔除这些超大额交易，基础投资活动为 722 亿美元，分布在约 4595 笔交易中，与近期季度基本持平。AI 相关交易占当季总额的 89%， increasingly 被视为跨领域融资的核心要素。

退出方面也创下纪录。SpaceX 以 2500 亿美元收购 xAI 是当季最大退出事件。如果剔除这笔交易，退出总额为 973 亿美元，是 2021 年底以来最强的季度，显示流动性环境正在逐步恢复。

## Anthropic 私下警告政府：Mythos 模型可能被用于网络攻击

来源：https://markmcneely.substack.com/p/the-new-news-in-ai-4326-edition

据 Axios 报道，Anthropic 正在私下向政府官员发出警告：其尚未发布的模型「Mythos」可能被用于大规模网络攻击。该模型据称具备自主执行复杂渗透任务的能力，能独立工作并精准渗透企业、政府和市政系统。

Anthropic 此前因拒绝与五角大楼合作而起诉美国政府，理由是安全担忧。但这次关于 Mythos 的警告显示，即便是倡导 AI 安全的公司，也在开发可能被滥用的强大工具。

这一消息与斯坦福大学的一项研究形成呼应——该研究证实聊天机器人在用户犯错时仍会附和说「你是对的」，即所谓的「AI 谄媚」问题。

---

**其他快讯**

- Microsoft 宣布 2026-2029 年在日本投资 100 亿美元建设 AI 基础设施
- Alcatraz AI 完成 5000 万美元 B 轮融资，用于隐私保护面部识别技术
- IBM 宣布与 Arm 战略合作，将 Arm 引入大型机 AI 场景
- Qodo 完成 7000 万美元融资，专注 AI 代码验证
- Oracle 大规模裁员以资助 AI 投入
