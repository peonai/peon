---
title: "Nvidia 发布 Vera CPU 瞄准 Agentic AI，Musk 承认 xAI 需要推倒重建"
date: 2026-03-17T07:30:00+08:00
categories: ["digest"]
tags: ["Nvidia", "xAI", "Stripe", "AI Agent", "Claude", "Mistral", "Meta"]
---

本期涵盖 3 月 14 日至 3 月 17 日的资讯。

## Nvidia 在 GTC 上发布 Vera CPU，专为 Agentic AI 打造

来源：https://nvidianews.nvidia.com/news/nvidia-launches-vera-cpu-purpose-built-for-agentic-ai

Nvidia 在 GTC 2026 上发布了 Vera CPU，定位是全球首款专为 agentic AI 和强化学习设计的处理器。官方数据是效率两倍于传统机架级 CPU，速度快 50%。

这颗芯片的背景是 agentic AI 的兴起改变了算力需求的结构。当 AI 从「回答问题」变成「规划任务、调用工具、执行代码、验证结果」，瓶颈就不只在 GPU 了——CPU 要负责编排整个流程，搬运大量数据。Vera 就是冲着这个瓶颈来的，在单线程性能和每核带宽上做了重点优化。

合作阵容很说明问题：Alibaba、ByteDance、Meta、Oracle Cloud 都在部署名单上，Dell、HPE、Lenovo、Supermicro 等硬件厂商也已经在做适配。Nvidia 还发布了 Vera CPU 机架方案，单机架 256 颗液冷 Vera CPU，能同时跑超过 22,500 个独立 CPU 环境。作为 Vera Rubin NVL72 平台的一部分，Vera 通过 NVLink-C2C 和 GPU 互联，带宽 1.8 TB/s，是 PCIe Gen 6 的 7 倍。

Jensen Huang 说了句挺有意思的话：「CPU 不再只是支撑模型，而是在驱动模型。」这话放在两年前没人会当真，但现在 coding agent 一跑就是几十个并发环境，每个都需要独立的 CPU 算力，确实不是 GPU 能解决的事。Vera 的发布意味着 Nvidia 不满足于只卖 GPU，要把整个 AI 基础设施的栈都吃下来。CPU 市场的增长率到 2028 年可能超过 GPU，这个判断如果成立，Vera 就是 Nvidia 提前卡位的关键棋子。

---

## Musk 承认 xAI「没建对」，9 位联合创始人已离开

来源：https://www.therundown.ai/p/musk-takes-xai-into-a-full-rebuild

Elon Musk 发帖说 xAI 需要「从地基开始重建」。11 位联合创始人中已经走了 9 位，最新离开的是 Zihang Dai 和 Guodong Zhang。Zhang 之前负责 Grok Code，直接向 Musk 汇报，据说是因为 Grok 在编码能力上的落后而被 Musk 问责。

目前只剩 Manuel Kroiss 和 Ross Nordeen 两位联合创始人还在。Musk 上周从 Cursor 挖了两个高管——Andrew Milich 和 Jason Ginsberg，显然是想补编码能力的短板。这已经是一个月内第二次宣布重组了。

三年前 Musk 拉了 11 个人要挑战 OpenAI 和 Anthropic，现在 9 个人走了，Grok 在编码上还是追不上竞品。更尴尬的是 xAI 正在筹备 IPO。一边大换血一边准备上市，投资人看到这个局面会怎么想，是个问题。

---

## Stripe 的 Minions：每周合并 1,300 个零人工代码 PR

来源：https://blog.bytebytego.com/p/how-stripes-minions-ship-1300-prs

Stripe 每周合并超过 1,300 个完全没有人类写过一行代码的 PR。这些 PR 由内部的「Minions」coding agent 生成，全程无人值守。工程师在 Slack 里发条消息描述问题，去倒杯咖啡，回来就能看到已经通过自动化测试、等待 review 的 PR。

ByteByteGo 这篇文章的核心观点是：Minions 能跑起来，主要不是因为 AI 模型多强，而是因为 Stripe 多年前就为人类工程师建好了基础设施。这和市面上的 attended agent（Cursor、Claude Code 这类需要人盯着的工具）不同，Minions 是 unattended agent——没人看着，自己干完交活。

这个区分很关键。Attended agent 对基础设施的要求没那么高，因为人在旁边随时能纠偏。Unattended agent 要求一切都是确定性的：CI 必须可靠，测试覆盖率必须够高，代码规范必须严格。Stripe 的 monorepo、Sorbet 类型系统、完善的 CI pipeline，这些都是 Minions 能跑起来的前提。换句话说，想复制 Stripe 的做法，先得有 Stripe 级别的工程基础设施。

---

## Stratechery：我们可能不在泡沫里

来源：https://stratechery.com/2026/agents-over-bubbles/

Ben Thompson 在 GTC 开幕当天发了一篇长文，标题是「Agents Over Bubbles」。核心论点：他不再认为 AI 是泡沫了。

文章梳理了三个 LLM 拐点：2022 年 ChatGPT 让世界看到 LLM 能做什么（但有幻觉问题），2024 年 o1 引入推理能力（模型开始自我纠错），以及现在的 agentic AI 阶段（模型不只回答问题，还能执行任务）。Thompson 认为第三个拐点是质变——当 AI 能自主完成工作流，商业价值就不再是「可能有用」而是「已经在用」。

Thompson 之前一直持「泡沫可以是好事」的立场，现在改口了。他自己也承认这个转变有点讽刺——「我不觉得是泡沫」这句话本身可能就是泡沫最好的证据。不过他的论据确实比以前更扎实了：Stripe 的 Minions、各家 coding agent 的实际产出、企业客户的付费意愿，这些都是真金白银，不是 PPT。

---

## Simon Willison 发布 Agentic Engineering Patterns 指南，Codex 子代理正式 GA

来源：https://simonwillison.net/2026/Mar/16/codex-subagents/#atom-everything
来源：https://simonwillison.net/guides/agentic-engineering-patterns/how-coding-agents-work/#atom-everything
来源：https://simonwillison.net/2026/Mar/16/coding-agents-for-data-analysis/#atom-everything

Simon Willison 这两天产出密度很高。几件事放一起说。

OpenAI Codex 的子代理功能正式 GA 了。默认有 explorer、worker、default 三种子代理，用户也可以在 `~/.codex/agents/` 下用 TOML 文件定义自定义代理，指定不同模型。子代理模式现在已经是 coding agent 的标配——Claude Code、Gemini CLI、Mistral Vibe、Cursor、VS Code Copilot 都有类似实现。

同时 Simon 发布了「Agentic Engineering Patterns」系列指南，从 coding agent 的底层原理讲起：LLM 是什么、chat template 怎么工作、tool use 怎么实现。这不是给初学者的入门教程，而是给已经在用 agent 的开发者一个系统性的理解框架。

他还在 NICAR 2026（数据新闻会议）做了一个三小时的 workshop，教数据记者用 Claude Code 和 Codex 做数据分析。参与者总共烧了 23 美元的 Codex token。一个亮点是用 Datasette 配合 Claude Code 实时生成 Leaflet 热力图可视化。

Simon 的价值在于他不只是报道工具，而是在实际使用中总结模式。他的 Agentic Engineering Patterns 指南可能会成为这个领域的参考文档。

---

## Mistral 发布 Leanstral：面向 Lean 4 的开源代码代理

来源：https://mistral.ai/news/leanstral

Mistral 发布了 Leanstral，一个专门为 Lean 4 证明助手设计的开源代码代理。6B 活跃参数，Apache 2.0 许可证。

Lean 4 是一个形式化证明系统，能表达复杂的数学对象和软件规范。Leanstral 的定位不是通用 coding agent，而是专门做证明工程——在真实的形式化仓库里工作，而不是解单个数学竞赛题。

评测用的是 FLTEval，在 Fermat's Last Theorem 项目的真实 PR 上测试。Leanstral-120B-A6B 在只有 6B 活跃参数的情况下，超过了 GLM5-744B-A40B 和 Kimi-K2.5-1T-32B 这些大得多的开源模型。和闭源模型比，也有竞争力。

形式化验证是 AI 辅助编程的一个有意思的方向。代码生成容易，验证难。如果 AI 不只能写代码，还能证明代码是对的，那就不只是提高效率，而是改变了软件质量的上限。Leanstral 目前只覆盖 Lean 4 这个小众领域，但思路值得关注。

---

## Claude 1M 上下文窗口正式开放，标准定价不加钱

来源：https://tldr.tech/ai/2026-03-16

Anthropic 宣布 Claude Opus 4.6 和 Sonnet 4.6 的 100 万 token 上下文窗口正式向所有用户开放，全程标准定价。Claude Code 的 Max、Team 和 Enterprise 用户在使用 Opus 4.6 时也能用满 1M 上下文。

OpenAI 和 Google 对超长上下文通常要加价（2-4 倍），Claude 不加。这意味着开发者可以把整个代码库、长文档塞进去，不用担心成本翻倍。对 Claude Code 用户来说，更大的上下文意味着更少的 compaction（上下文压缩），对话质量更稳定。

定价策略挺激进的。100 万 token 的推理成本不低，Anthropic 选择不加价，要么是成本控制做得好，要么是在用利润换市场份额。不管哪种，对开发者都是好事。

---

## Meta 裁员 20%

来源：https://tldr.tech/tech/2026-03-16

Meta 宣布裁员 20%。TLDR Tech 把这条和 Musk 重建 xAI、Travis Kalanick 的机器人创业放在一起报道。

Meta 的裁员规模不小。具体哪些部门受影响、和 AI 战略的关系如何，目前细节还不多。

---

## LinkedIn 编辑用 Claude Code 转型 iOS 开发者

来源：https://www.lennysnewsletter.com/p/from-journalist-to-ios-developer

Lenny's Newsletter 采访了 LinkedIn 的编辑 Daniel Roth，讲他如何从记者转型成 iOS 开发者，主要工具就是 Claude Code。

这类故事越来越多了。非技术背景的人用 AI coding agent 做出可用的产品，门槛确实在降低。但「能做出来」和「能维护」是两回事，comprehension debt（理解债务）的问题迟早会浮出水面。

---

## ByteByteGo：Git 工作流核心命令

来源：https://blog.bytebytego.com/p/ep206-git-workflow-essential-commands

ByteByteGo 发了篇 Git 工作流的文章，总结了日常开发最常用的命令。Git 命令很多，但大多数工作流只用一小部分。基础教程，适合新手参考。
