---
title: "Anthropic 推出 Project Glasswing 零日漏洞扫描计划，联合 Google、Broadcom 建设千兆瓦算力"
date: 2026-04-09T07:30:00+08:00
categories: ["digest"]
tags: ["AI", "Anthropic", "Project Glasswing", "Google", "OpenAI", "Meta"]
---

本期涵盖 4 月 5 日至 4 月 8 日的资讯。

## Anthropic 推出 Project Glasswing，Claude Mythos 发现数千零日漏洞

来源：https://www.anthropic.com/glasswing

Anthropic 发布了 Project Glasswing，这是一项与主要科技公司合作的安全计划。Claude Mythos Preview 自动发现了主流操作系统和浏览器中的数千个零日漏洞。这些能力将被用于大规模检测和修复安全漏洞。Anthropic 计划开发保障措施，并扩大行业合作范围，以应对 AI 时代的安全挑战。

这是 AI 在网络安全领域应用的重要里程碑。之前的安全工作主要依赖人工渗透测试和规则引擎，AI 现在可以自主发现漏洞，效率提升了一个数量级。关键问题是，这个能力是否会被恶意使用——Anthropic 选择开源部分能力来换取行业合作，这个平衡并不容易把握。

## Anthropic 联合 Google、Broadcom 建设多个千兆瓦下一代算力

来源：https://www.anthropic.com/news/google-broadcom-partnership-compute

Anthropic 与 Google 和 Broadcom 签署协议，获得多个千兆瓦的新一代 TPU 容量，预计 2027 年开始上线。这个容量对于服务 Anthropic 指数级增长的用户群至关重要，也将使 Claude 能够在 AI 开发的前沿保持领先地位。新算力的绝大部分将部署在美国境内。

这标志着 AI 算力竞争进入新阶段。Google 的 TPU + Broadcom 的芯片设计能力 + Anthropic 的模型，这个组合剑指 Microsoft + OpenAI 的算力联盟。2027 年看似遥远，但考虑到数据中心建设周期，这个时间表是合理的。

## OpenAI 测试新一代 Image V2 模型

来源：https://www.testingcatalog.com/openai-tests-next-gen-image-v2-model-on-chatgpt-and-lm-arena/

OpenAI 正在 ChatGPT 和 LM Arena 上测试其下一代 Image V2 模型，提供了三个变体供测试。早期测试显示在 UI 设计渲染、提示词跟随和组合理解方面有改进。测试结果将影响 OpenAI 在图像生成领域与 Google 竞争的地位。

图像生成赛道正在变得拥挤。OpenAI 的 Sora 尚未大规模开放，Google 有 Veo 系列，现在 Image V2 又来了。关键变量是：这次是否会对开发者开放 API，还是继续走 Playground 试用的保守路线。

## Google 开发 Jules V2，能处理更大任务的代码代理

来源：https://www.testingcatalog.com/google-prepares-jules-v2-agent-capable-of-taking-bigger-tasks/

Google 正在开发 Jules V2（代号 Jitro）代码代理，设计目标是自主管理高层开发目标而非具体任务。通过等待列表发布，它旨在将 AI 软件开发的关注点从基于任务的命令转向 KPI 驱动的成果。这个方法可能对处理大型代码库的团队有益，但面临不可预测的变更和信任问题。

从「执行具体任务」到「管理高层目标」，这是 AI 编程代理的重要范式跃迁。难度不在于技术，而在于人类如何信任 AI 做出的架构决策。

## 智谱 GLM-5.1 在 SWE-Bench Pro 达到 SOTA

来源：https://z.ai/blog/glm-5.1

智谱发布了 GLM-5.1，这是其面向代理工程的旗舰模型。该模型在 SWE-Bench Pro 上达到了最先进性能。模型设计为在比前代更长的视野内保持代理任务有效性，可以持续数百轮和数千次工具调用进行优化。模型能够分解复杂问题、运行实验、读取结果并精确识别障碍。

中国 AI 公司正在 Agent 赛道追赶。GLM-5.1 的长程任务处理能力是一个差异化点——大多数模型在复杂任务上会「迷失」，能够保持上下文连贯性是关键。

## Meta 部分新模型将开源

来源：https://sherwood.news/tech/report-some-of-metas-new-ai-models-will-eventually-be-open-source/

Meta 即将发布新 AI 模型，部分模型最终将按开源许可发布。Meta 计划专注于消费者市场而非企业市场。公司此前通过 Llama 模型拥抱开源 AI，CEO 马克·扎克伯格已撰写宣言宣称开源 AI 是未来。公司将采用专有模型和开源模型的混合策略。

Llama 4 应该快了。混合策略意味着 Meta 在开源社区和企业市场两头讨好的意图。这对 Anthropic 和 OpenAI 是间接压力——开源模型质量越高，付费模型的差异化越难。

## Cursor 发布 Warp Decode，MoE 推理吞吐量提升 1.8 倍

来源：https://cursor.com/blog/warp-decode

Cursor 的 Warp Decode 是一种核心设计，将 MoE（混合专家）推理围绕输出神经元而非专家进行重组。它在 Blackwell GPU 上实现了约 1.8 倍的更高吞吐量和改进的数值精度。

推理效率战争正在进行。Anthropic 靠模型架构优化，OpenAI 靠大规模部署，Cursor 靠底层系统优化——不同公司在不同层级发力。对终端用户来说，这意味着更好的体验和更低的成本。