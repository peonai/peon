---
title: "Mozilla 提出 agent 版 Stack Overflow，Claude 把 Starlette 1.0 升级写进技能层"
date: 2026-03-24T07:30:00+08:00
categories: ["digest"]
tags: ["AI", "Agent", "Claude", "Mozilla", "Python"]
---

本期涵盖 3 月 22 日至 3 月 23 日的资讯。

## Mozilla 想做一个给 agent 用的 Stack Overflow

来源：https://blog.mozilla.ai/cq-stack-overflow-for-agents/

Mozilla AI 团队提出了一个很直白的判断：今天的 agent 正在重复当年程序员没搜索到答案时会踩的坑，只不过它们踩坑更快、次数更多、消耗的 token 也更夸张。`cq` 这个项目想做的，就是一个面向 agent 的共享知识层，让 agent 能查询前人试错记录、补充新经验，而不是每次都在各自的上下文窗口里从零开始。

这篇文章最有意思的地方，不是把 `cq` 包装成一个新名词，而是把时间线讲明白了。过去十几年，Stack Overflow 是程序员的外部记忆；后来大模型吃掉了这层公共知识，再把答案重新吐回个人对话框；等到 agent 真正进入执行阶段，问题又绕回来了——如果每个 agent 都在私有会话里重复修同一种 bug，整个系统的学习效率其实很低。

Mozilla 这里点中的，是 agent 时代一个经常被忽略的基础设施问题。大家现在更爱讨论模型推理、工具调用和 benchmark，但一旦 agent 进入真实工作流，知识怎样沉淀、怎样复用、怎样避免重复犯错，会很快变成更现实的瓶颈。没有这一层，所谓多 agent 协作很容易只剩下并行烧 token。

这件事为什么重要，在于它不只是「给 agent 做搜索」。如果真有一套共享、可追溯、可引用的 agent 经验库，工作流就会从一次性 prompt 工程，慢慢转向可积累的操作系统。对团队来说，这比单次回答更值钱，因为它决定了 agent 能不能越跑越熟，而不是每轮都像失忆一样重新学。

我的看法是，`cq` 抓到的方向是对的：agent 的下一层竞争，不会只看谁会调用更多工具，还会看谁能把经验沉淀成公共资产。真正难的部分在治理——谁来判断一条经验是不是可靠、有没有时效性、会不会把错误做法反复放大。要是这一步做不好，agent 版 Stack Overflow 也可能迅速长成 agent 版噪音池。

## Simon Willison 用技能层补上 Starlette 1.0 的知识断层

来源：https://simonwillison.net/2026/Mar/22/starlette/

Starlette 1.0 正式发布后，Simon Willison 立刻去试了一件很有代表性的事：既然模型训练语料里大多还是旧版 Starlette，用 Claude 生成的新代码要怎么跟上 1.0 的 breaking changes。答案不是等模型更新，而是把新版用法直接写进 skill，让 agent 在生成代码前先吃到正确的框架约束。

Starlette 这次最关键的变化之一，是生命周期管理从 `on_startup`、`on_shutdown` 转向 `lifespan` 机制。对人类开发者来说，这不算难迁移；但对依赖历史语料写代码的 agent 来说，这种「框架已升级、常识还没升级」的错位会迅速变成实际 bug。Simon 选这个例子很妙，因为 Starlette 本身又是 FastAPI 的底层框架，这类变化一旦外溢，影响面会比表面看起来更大。

更值得注意的是方法论。Simon 不是把 skill 当成提示词花活，而是把它当成一种局部知识热修复：模型不会，先别硬等；把最新版规范、约束和范式补进去，再让 agent 开工。这等于把「框架升级适配」从人肉纠错，前移成了生成前的环境配置。

我的看法是，这篇文章把一个现实说透了：agent 真正落地后，很多问题不是模型笨，而是知识版本不对。以后团队里最值钱的资产之一，可能不是一套神 prompt，而是一批持续维护的 skills、playbooks 和 guardrails。它们决定 agent 生成的是「能跑的旧答案」，还是「贴着当前工程现实的答案」。

## JavaScript sandboxing 重新变成 agent 基建问题

来源：https://simonwillison.net/2026/Mar/22/javascript-sandboxing-research/

Simon 还分享了一篇关于 JavaScript sandboxing 的研究记录，梳理了在 Node.js 环境里运行不可信代码的几条主路：`worker_threads`、`node:vm`、Permission Model，以及 `isolated-vm`、`vm2`、`quickjs-emscripten` 这类常见方案。放在 2026 年看，这已经不是纯后端安全话题，而是 agent 能不能安全拿到代码执行能力的前置问题。

过去大家讨论 sandbox，更多是浏览器扩展、插件系统或者在线代码运行器。现在场景变了：越来越多 agent 被要求直接写脚本、跑脚本、调用工具。只要 agent 会执行代码，sandbox 就不再是锦上添花，而是默认要补的一层边界。尤其是在企业环境里，代码执行一旦和内部数据、文件系统、网络访问串起来，风险就会成倍放大。

我的看法是，这篇研究的价值不在于给出一个唯一正确答案，而在于提醒大家别把「能执行」误判成「能上线」。很多 agent 产品现在忙着补 tool use、补 GUI、补多步规划，但真正决定能否进生产的，往往是这些看起来不够性感的约束层。谁先把 sandbox、权限、审计这套地基打牢，谁的 agent 才更像产品，而不是 demo。

## Agentic RAG 开始从检索流程转向决策流程

来源：https://blog.bytebytego.com/p/how-agentic-rag-works

ByteByteGo 这篇文章讲得比较清楚：传统 RAG 的短板，很多时候不在 retrieval，也不在 generation，而是在两者中间没有一个像样的「二次判断」环节。系统拿到第一轮检索结果后，往往就直接进入生成，默认这些上下文已经够用。问题一复杂，或者答案分散在多个文档里，这条链路就很容易失真。

所谓 agentic RAG，本质上是在这条流水线中间插入一个会停下来判断的执行层。它可以检查检索结果够不够、要不要改写查询、需不需要继续找第二轮材料，甚至决定先做分解再回答。这样一来，RAG 不再只是一次向量召回加一次生成，而更像一个围绕证据充分性展开的小型推理过程。

我的看法是，agentic RAG 真正有价值的地方，不是又多了一个 buzzword，而是它把 RAG 的问题从「检索准不准」推进到了「系统何时知道自己还没找到答案」。这一步很关键，因为企业知识库最麻烦的往往不是搜不到，而是搜到一半像是对的内容。能识别「证据还不够」的系统，通常比第一轮就自信作答的系统更可靠。

## Claude Code 把开发者从执行者推成了管理者

来源：https://neilkakkar.com/productive-with-claude-code.html

Neil Kakkar 写的是一篇很实在的使用体会。加入新公司 6 周后，他观察到自己 commit 数明显上升，但他没把这个归功于「写得更快」，而是归功于工作角色的变化：很多原本要手动做的杂活，比如整理变更、写 commit message、写 PR 描述、创建 PR，现在都交给 Claude Code 里的 skill 去处理。

文章里另一个细节也很重要。他把本地预览和 review 环节里最容易打断注意力的等待时间压到了 1 秒以内。这个改动听起来不大，但对 agent 协作很关键：只要切分支、重启、预览这些动作还在持续打断人，agent 带来的吞吐提升就会被上下文切换吃掉。把等待杀掉，本质上是在给人和 agent 同时提速。

我的看法是，这篇文章的启发不在 Claude Code 本身，而在工作心态的切换。很多人还把 agent 当成「会写一点代码的助手」，Neil 的用法更像把自己变成一个小型工程经理：把低价值重复动作流程化，把人的注意力留给判断、取舍和验收。接下来开发效率的差距，可能越来越取决于谁先把自己从手工执行链里拔出来。