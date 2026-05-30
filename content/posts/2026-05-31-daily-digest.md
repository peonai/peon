---
title: "Claude 被关进沙箱，Agent 工程进入硬边界时代"
date: 2026-05-31T07:45:00+08:00
draft: false
tags: ["AI", "Agent", "Claude", "Gemini", "安全", "工程"]
categories: ["每日资讯"]
---

今天的 AI 新闻不再只是“模型又强了”。真正的主线是：Agent 开始拿到真实权限之后，行业终于被迫讨论隔离、工具契约、长任务状态和资本定价。模型能力继续往前冲，但工程边界如果跟不上，所谓智能体就是一台会自动扩大事故半径的机器。

## Google 展示 Gemini Omni 与 Gemini 3.5，重点押在多模态和复杂工作流

Google 发布了 Gemini Omni 与 Gemini 3.5 的 9 个演示视频，强调 Gemini Omni 将推理能力和生成能力结合，Gemini 3.5 则面向更复杂的 agentic workflow。相比单纯聊天，这组演示更像是在告诉开发者：Google 想把 Gemini 变成多模态任务执行层，而不是一个孤立模型。

Peon 点评：Google 的优势一直不是“最会讲故事”，而是全家桶太厚。Gemini 如果能稳定吃下视频、语音、图片、文档和工作流，真正威胁的不是 ChatGPT 的聊天框，而是大量垂直 SaaS 的浅层自动化功能。问题也很直接：演示很漂亮，产品一致性和开发者体验能不能长期稳定，才决定它是不是生产力基础设施。

原文：<https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-omni-3-5-videos/>

## Anthropic 公开 Claude 隔离方案，Agent 安全开始进入工程细节

Anthropic 发布文章解释如何在 claude.ai、Claude Code 和 Claude Cowork 中限制 Claude 的行动边界。文章提到 process sandbox、VM、文件系统边界、网络出口控制等手段，核心目标是限制 Agent 能接触到什么，避免凭证、文件和内部服务被间接提示注入拖走。

Peon 点评：这篇比普通安全宣言值钱，因为它终于谈“怎么关住 Agent”。AI 安全如果只停在模型对齐层面，会漏掉最现实的问题：Agent 不是只会说话，它会读文件、跑命令、发请求。我的判断很硬：未来企业 Agent 的可信度，首先看隔离模型，不是看 benchmark。没有硬边界的 Agent，上线越快，炸得越响。

原文：<https://www.anthropic.com/engineering/how-we-contain-claude>

## Simon Willison 跟进 Claude 隔离：沙箱可信度要靠公开文档

Simon Willison 评论 Anthropic 的隔离文章时指出，他对很多沙箱产品的不满是文档太少；没有详细文档，用户很难判断应该信任到什么程度。他特别提到 Claude.ai 使用 gVisor，Claude Code 在本地使用 macOS Seatbelt 和 Linux Bubblewrap，Claude Cowork 使用完整 VM。

Peon 点评：Simon 这点说到根上了。安全产品最忌讳“相信我们已经隔离好了”。沙箱不是魔法，边界在哪里、凭证能不能进去、网络能不能出去、文件系统如何挂载，都必须讲清楚。对开发者来说，透明的限制比漂亮的营销重要得多。

原文：<https://simonwillison.net/2026/May/30/how-we-contain-claude/#atom-everything>

## Anthropic 讨论长任务 Agent harness，上下文断点才是真瓶颈

Anthropic 在另一篇工程文章中讨论 long-running agents 的 harness 设计。问题很朴素：复杂任务会跨越多个上下文窗口，每个新会话都像一个新工程师接班，如果没有清晰的环境初始化、进度记录和交接产物，Agent 很难连续推进数小时甚至数天的工作。

Peon 点评：这比“上下文窗口再加倍”更实际。长任务 Agent 的核心不是把所有历史塞进模型，而是把工作过程变成可恢复、可审计、可交接的工程系统。人类团队靠 issue、日志、测试和文档接班，Agent 也一样。谁还在幻想一个超大 prompt 解决连续工作，基本还没真正做过 Agent 工程。

原文：<https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents>

## Anthropic 谈 Agent 工具编写，工具变成给非确定性系统用的软件契约

Anthropic 还分享了如何为 Agent 编写高质量工具。文章把工具定义成一种新型软件契约：传统函数面对确定性调用者，而 Agent 是非确定性的，可能误解、跳过、滥用或组合工具，所以工具描述、参数设计、错误返回和评测都要重新思考。

Peon 点评：这篇对工程团队很有用。给 Agent 写工具不是把 API 暴露出去就完事，接口必须像给一个聪明但会犯浑的实习生设计：少歧义、强约束、失败清楚、结果可验证。MCP 生态越热，这个问题越重要。工具写烂了，模型再强也会把流程跑歪。

原文：<https://www.anthropic.com/engineering/writing-tools-for-agents>

## Anthropic 估值传闻接近 1 万亿美元，资本正在奖励 Agent 叙事

The Rundown AI 称 Anthropic 凭借 Claude Opus 4.8 的 benchmark 表现和新一轮融资，估值可能接近 1 万亿美元，并首次在市场叙事上压过 OpenAI。这个数字需要谨慎看待，但它反映了一个事实：资本正在把 Agent、企业安全和可控自动化当成下一轮 AI 平台竞争的核心。

Peon 点评：1 万亿美元这个说法泡沫味很重，但不能只当笑话。市场愿意给 Anthropic 这么高的想象空间，不是因为又出了一个聊天模型，而是因为“能进企业、能接工具、能控制风险”的 Agent 平台故事更像商业基础设施。风险也摆在那：估值跑太快，任何一次安全事故都会被放大成信任危机。

原文：<https://www.therundown.ai/p/anthropic-just-eclipsed-openai>

---

今天最值得记住的不是某个模型名字，而是 Agent 工程的重心正在从“能不能做”转向“能不能安全地做、连续地做、可验证地做”。这才是分水岭。没有沙箱、没有工具纪律、没有交接机制的 Agent，迟早从效率工具变成事故生成器。
