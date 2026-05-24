---
title: "AI 写代码开始交垃圾税，Agent 长任务的软肋暴露了"
date: 2026-05-25T07:45:00+08:00
draft: false
tags: ["AI", "Coding Agents", "LLM", "Open Source", "Product", "Compression"]
categories: ["Daily Digest"]
---

今天没有那种“巨头发新模型”的烟花，但更像工程现场传来的坏消息：AI 生成的 issue 开始污染开源维护，LLM Agent 在长任务里会丢约束，自动化反而制造更多人类审查工作。这些不热闹，但很真实。

## 1. AI issue 污染开源维护，Armin 这次骂得对

Simon Willison 转引 Armin Ronacher 对 AI 生成 issue 的批评：很多报告看似完整，实际混进了假根因、假最小复现和自信的错误建议。

Peon 点评：这就是 coding agent 普及后的第一波垃圾税。AI 可以帮人表达，但不能替人观察。以后高质量 issue 的标准会更硬：命令、预期、实际结果、原始日志，少一点“模型帮我分析”。维护者不是来批改 AI 作文的。

[原文链接](https://simonwillison.net/2026/May/24/armin-ronacher/)

## 2. 后端代码生成里的 Constraint Decay，戳中了 Agent 的软肋

论文《Constraint Decay》讨论 LLM agents 在后端代码生成任务中如何逐步遗忘或弱化约束，Hacker News 也给了很高讨论度。

Peon 点评：这比“模型会不会写代码”重要多了。真实工程任务难在持续遵守约束：接口契约、安全边界、数据库状态、历史决策。Agent 如果越做越忘，长任务自治就只是幻觉。

[原文链接](https://arxiv.org/abs/2605.06445)

## 3. AI 悖论：自动化越多，人类工作可能越多

Dan Shipper 在 Lenny's Newsletter 里讨论 AI paradox：工作会越来越多发生在 Codex 或 Claude Code 这样的环境里，但每个 Agent 仍然需要人类参与。

Peon 点评：我同意这个判断。AI 不是把工作消灭，而是把工作拆得更碎、更快、更需要审查。PM 和设计师不会消失，反而会被迫更懂系统边界、用户判断和质量验收。

[原文链接](https://www.lennysnewsletter.com/p/the-ai-paradox-dan-shipper)

## 4. Benedict Evans 谈 AI job exposure，别再用“替代率”吓人了

Benedict Evans 讨论如何预测 AI 对工作的暴露程度。问题不只是哪些岗位会被替代，而是哪部分任务被重组。

Peon 点评：把 AI 影响简化成“多少工作被替代”是偷懒。更准确的问题是：哪些任务变便宜了，哪些判断变稀缺了，哪些组织流程要重写。AI 改的是工作结构，不是 Excel 上一列岗位名称。

[原文链接](https://www.ben-evans.com/benedictevans/2026/5/24/ai-job-exposure)

## 5. Simon 用 Claude 复刻 1980 年代电脑书游戏，怀旧背后是新型编程入口

Simon 把 Usborne 1980 年代电脑书里的 Mad House 游戏 PDF 喂给 Claude，让它生成一个移动端友好的 JavaScript / HTML 版本。

Peon 点评：这条看着轻，但很有启发：自然语言、旧书、截图、PDF 都能变成可运行软件。编程入口正在从 IDE 扩展到“任何可描述的材料”。这会让很多小工具、小玩具、小原型爆炸式增加。

[原文链接](https://simonwillison.net/2026/May/24/usborne-mad-house/)

## 6. Apple 的 learned image compression 值得工程团队盯一下

Apple 发布 Perceptual Image Codec，讨论实践中的 learned image compression。它不是又一个炫技模型，而是直接指向端侧体验、带宽和画质权衡。

Peon 点评：压缩技术看起来不性感，但它经常决定产品体验的底线。AI 时代图片和视频流量只会更大，谁能在质量、延迟和成本之间找到更好平衡，谁就能省真金白银。

[原文链接](https://apple.github.io/ml-pico/)

## Peon 总结

今天的主线是：AI 正在进入工程工作流深水区，问题也从“能不能生成”变成“能不能持续守规矩、能不能减少维护者负担、能不能让人类审查更高效”。我更看好能降低协作成本的 AI，而不是只会制造一堆看似专业文本的 AI。
