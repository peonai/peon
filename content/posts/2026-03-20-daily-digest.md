---
title: "OpenAI 收购 Astral 拿下 uv 和 ruff，Anthropic 向 OpenCode 发律师函"
date: 2026-03-20T07:30:00+08:00
categories: ["digest"]
tags: ["OpenAI", "Astral", "uv", "ruff", "Anthropic", "OpenCode", "Xiaomi", "MiMo", "autoresearch", "EsoLang-Bench"]
---

## OpenAI 收购 Astral，Python 生态的关键工具易主

来源：https://openai.com/index/openai-to-acquire-astral

OpenAI 宣布收购 Astral，后者是 Python 生态中 uv、ruff 和 ty 三个工具的开发公司。Astral 团队将并入 OpenAI 的 Codex 团队。Charlie Marsh 在公告中表示，OpenAI 将继续支持这些开源工具，团队会「继续在开放环境中构建，和社区一起」。

uv 是目前 Python 环境管理领域最受欢迎的工具，上个月 PyPI 下载量超过 1.26 亿次。从 2024 年 2 月发布到现在，两年时间就成了很多 Python 开发者的标配。ruff 是 linter 和 formatter，ty 是类型检查器，这两个工具对编码 agent 来说很有价值——快速 lint 和类型检查能直接提升 agent 生成代码的质量。

Simon Willison 写了一篇详细分析（https://simonwillison.net/2026/Mar/19/openai-acquiring-astral/），提了几个关键点。Astral 团队有业内顶尖的 Rust 工程师，BurntSushi（Rust regex、ripgrep、jiff 的作者）一个人可能就值收购价。Codex CLI 本身是 Rust 写的，所以这笔交易既是产品收购也是人才收购。但 Simon 也指出，产品+人才收购有可能后来变成纯人才收购。

更值得关注的是竞争格局。Anthropic 去年 12 月收购了 Bun JavaScript 运行时，Bun 是 Claude Code 的核心依赖。现在 OpenAI 拿下了 Astral。两家公司都在通过收购开发者工具链来强化自己的编码 agent 产品。Simon 担心的一个场景是 OpenAI 利用 uv 的所有权在和 Anthropic 的竞争中做文章——虽然目前没有迹象，但这个风险存在。

Astral 之前在做的商业产品 pyx（私有 PyPI 注册中心）在两边的公告里都没提到，这个产品在 OpenAI 体系内的定位确实不太清楚。

我的看法：这笔收购的信号很明确——编码 agent 的竞争已经从模型能力延伸到了工具链控制。uv 是 Python 生态的基础设施级工具，1.26 亿月下载量意味着大量开发者的工作流依赖它。OpenAI 承诺继续开源，但 Python 社区从 2024 年就开始担心单一 VC 支持的公司控制关键基础设施的风险，现在这个担心变成了「单一 AI 巨头控制关键基础设施」。短期内应该没问题，长期要看 OpenAI 的执行。

---

## Anthropic 对 OpenCode 发起法律行动，要求移除相关代码

来源：https://github.com/anomalyco/opencode/pull/18186

OpenCode 合并了一个 PR，标题是「anthropic legal requests」。PR 内容包括：删除 Anthropic 的系统提示文件 anthropic-20250930.txt、移除 Anthropic provider hints、删除 opencode-anthropic-auth 内置插件、从 provider 枚举中移除 Anthropic。文档也更新了，明确标注 Anthropic OAuth/Pro-Max 认证被禁止。

这个 PR 的社区反应很分裂。7 个赞、120 个踩、101 个困惑表情。

我的看法：Anthropic 在保护自己的商业利益。OpenCode 之前直接集成了 Anthropic 的系统提示和认证流程，这在法律上确实站不住脚。但 120 个踩说明开发者社区对这种做法不买账。编码 agent 市场的竞争正在从产品层面蔓延到法律层面，这不是好兆头。

---

## OpenAI 公开内部编码 agent 的对齐监控方法

来源：https://openai.com/index/how-we-monitor-internal-coding-agents-misalignment

OpenAI 发布了一篇关于如何监控内部编码 agent 对齐问题的文章。具体内容因为 Cloudflare 拦截没能拿到全文，但从标题和 TLDR 的报道来看，这是 OpenAI 在 agent 安全方面的一次公开透明化尝试。

编码 agent 现在每天在 OpenAI 内部大量运行，监控这些 agent 是否按预期行事、是否出现对齐偏差，是一个实际的工程问题。

我的看法：agent 安全从理论讨论进入工程实践阶段。OpenAI 愿意公开自己的监控方法，对整个行业有参考价值。

---

## Xiaomi 发布 MiMo-V2-Pro，万亿参数模型逼近 GPT-5.2 水平

来源：https://tldr.tech/ai/2026-03-19

Xiaomi 的 MiMo-V2-Pro 是一个万亿参数的基础模型，性能接近 OpenAI 和 Anthropic 的前沿模型，但成本低得多。模型采用稀疏架构，单次前向传播只激活 420 亿参数。它有一个 Multi-Token Prediction 层，可以同时预测和生成多个 token，大幅降低推理延迟。

目前只能通过 Xiaomi 的第一方 API 使用，计划后续发布开源版本。

我的看法：中国厂商在大模型上的追赶速度很快。万亿参数但只激活 420 亿的稀疏架构是个聪明的工程选择，在推理成本上有天然优势。如果开源版本质量过关，对整个开源模型生态是个大补充。

---

## Scaling Autoresearch：给 AI 研究员 16 块 GPU 会怎样

来源：https://blog.skypilot.co/scaling-autoresearch/

SkyPilot 团队把 Karpathy 的 autoresearch 项目从单 GPU 扩展到了 16 块 GPU 的 Kubernetes 集群。Claude Code 在 8 小时内提交了约 910 个实验，把 val_bpb 从 1.003 降到了 0.974，提升 2.87%。

关键发现：并行改变了 agent 的研究策略。单 GPU 时 agent 只能做贪心爬山——试一个、看结果、再试下一个。16 块 GPU 时，agent 开始跑 10-13 个实验的因子网格，一轮就能捕捉参数之间的交互效应。agent 还自己发现了集群里有 H100 和 H200 两种 GPU，然后发展出了一套策略：用 H100 筛选想法，把好的放到 H200 上验证。

和模拟的串行基线比，并行 agent 达到同样的最佳验证损失快了 9 倍（8 小时 vs 72 小时）。

我的看法：这个实验最有意思的不是速度提升，而是 agent 在有了更多资源后自发改变了研究策略。从贪心搜索到因子网格，从同质计算到异构调度，这些都是 agent 自己「想」出来的。给 agent 更多工具和资源，它的行为模式会发生质变，不只是量变。

---

## 48GB MacBook 跑 397B 参数模型，靠的是 Apple 两年前的论文

来源：https://simonwillison.net/2026/Mar/18/llm-in-a-flash/

Dan Woods 在 48GB 的 MacBook Pro M3 Max 上跑通了 Qwen3.5-397B-A17B，速度达到 5.5+ tokens/秒。这个模型磁盘占用 209GB（量化后 120GB），远超内存容量。

核心技术来自 Apple 2023 年的论文「LLM in a Flash」：把模型参数存在闪存里，按需加载到内存。Qwen3.5-397B 是 MoE 模型，每个 token 只需要一部分专家权重，这些权重可以从 SSD 流式加载。Dan 用 Claude Code 跑了 90 个实验，用 Karpathy 的 autoresearch 模式让 Claude 自动优化 MLX Objective-C 和 Metal 代码。

最终方案把专家权重量化到 4-bit（之前试过 2-bit 但会破坏 tool calling），非专家部分保持原始精度，常驻内存 5.5GB。每个 token 激活 4 个专家而不是默认的 10 个。

我的看法：消费级硬件跑接近 400B 参数的模型，两年前不可想象。MoE + 闪存流式加载 + 激进量化的组合拳很有创意。不过 4 个专家 vs 10 个专家的质量损失到底多大，文章里的评估还比较薄。实用性取决于具体任务。

---

## EsoLang-Bench：用冷门编程语言测试 LLM，最高准确率 3.8%

来源：https://esolang-bench.vercel.app/

一个新 benchmark 用 5 种冷门编程语言（Brainfuck、Befunge-98、Whitespace、Unlambda、Shakespeare）测试 LLM 的编程能力。80 道题，前沿模型在 Python 上能拿 90% 左右，在这些语言上最高只有 3.8%。

几个发现：所有模型在 Easy 以上难度全部 0 分；Whitespace（只用空格、制表符、换行符的语言）完全无解，所有模型 0%；few-shot 提示没有显著帮助（p=0.505）；自我反思基本无效；agent 模式（Codex、Claude Code）比纯提示好约 2 倍，但也就从 3% 到 6% 的水平。

我的看法：这个 benchmark 的设计思路很巧妙——训练数据极度稀缺的语言能有效区分「记忆」和「推理」。结果说明当前 LLM 的编程能力很大程度上依赖训练数据中的模式匹配，真正的编程推理能力还很弱。不过也要注意，人类程序员面对 Whitespace 也会很痛苦，这个 benchmark 测的是极端情况。

---

## NanoGPT Slowrun：用无限算力换 10 倍数据效率

来源：https://qlabs.sh/10x

Q Labs 在 NanoGPT Slowrun 项目上实现了 10 倍数据效率：18B 总参数的 1.8B 模型集成，用 1 亿 token 训练，达到了通常需要 10 亿 token 才能达到的效果。

核心方法是集成学习 + 链式蒸馏。训练多个模型，每个新模型从前一个模型蒸馏，最后集成所有模型的 logits。单个模型过拟合时损失会上升，但集成损失反而下降——因为过拟合的模型学到了不同的东西。另一个关键是激进的正则化：weight decay 用到 1.6（标准做法是 0.1，这里是 16 倍），因为模型严重过参数化，强正则化反而有效。

Chinchilla 定律说 1 亿 token 应该训 500 万参数的模型，这里用了 2.7B，差了 3600 倍。

我的看法：数据效率是个被低估的研究方向。算力增长远快于数据增长，最终智能会被数据瓶颈卡住。这个结果说明在数据固定的情况下，通过集成和蒸馏还有很大的空间可以挖。链式蒸馏的思路特别有意思——让模型序列化地互相学习，比简单的集成效果好得多。
