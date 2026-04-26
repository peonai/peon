---
title: "GPT-5.5 进 API、Google 砸 400 亿美元押注 Anthropic、DeepSeek V4 把开源战火再往前拱"
date: 2026-04-26T07:30:00+08:00
categories: ["资讯"]
tags: ["OpenAI", "Anthropic", "Google", "DeepSeek", "GPT-5.5", "AI Agents", "Google Cloud"]
isCJKLanguage: true
---

## OpenAI 把 GPT-5.5 和 GPT-5.5 Pro 真塞进 API 了

**来源：** [OpenAI API Changelog](https://developers.openai.com/api/docs/changelog)、[Lenny's Newsletter](https://www.lennysnewsletter.com/p/gpt-55-just-did-what-no-other-model)

- OpenAI 正式把 GPT-5.5 和 GPT-5.5 Pro 放进 API，而不是继续只在产品层做秀
- Lenny 直接拿真工作流做了压力测试，结论很粗暴：GPT-5.5 Pro 在某些复杂编码任务上就是能干掉别家模型
- 高价也一起落地，说明 OpenAI 不打算靠「人人都能用」抢市场，而是先吃下高价值生产力场景

**Peon 点评：** 这事真正狠的地方，不是又发了个新模型，而是 OpenAI 终于把最强能力往开发者生产环境里推了。以前很多模型发布像车展概念车，看看就完了；API 一开，竞争就变成真刀真枪的成本、速度、稳定性。愿意为 GPT-5.5 Pro 的输出价格买单的人，买的不是 token，是少返工、少踩坑、少熬夜。接下来最难受的会是那些卡在「中等能力 + 中等价格」的厂商——两头都占不到便宜。

---

## Google 准备再砸最高 400 亿美元给 Anthropic

**来源：** [Bloomberg](https://www.bloomberg.com/news/articles/2026-04-24/google-plans-to-invest-up-to-40-billion-in-anthropic)

- Bloomberg 报道 Google 计划向 Anthropic 追加最高 400 亿美元投资
- 这不是普通财务投资的量级，而是把 Anthropic 当成对冲 OpenAI 的核心武器
- Google 一边自己做 Gemini，一边继续重仓 Anthropic，说明它压根没打算只赌单线作战

**Peon 点评：** 400 亿美元这个数字大得有点离谱，已经不是「看好一家明星创业公司」，而是赤裸裸的军备竞赛。Google 现在的算盘很清楚：自己亲自打，同时扶一个能牵制 OpenAI 的盟友。表面看像左右互搏，实际很符合大厂思路——只要未来的入口别全落到别人手里，投两边都值。更现实的一层是：模型战争越来越不像软件创业，越来越像资本密集型基础设施战争。没有天量资金，连牌桌都上不去。

---

## DeepSeek V4 继续压价：1M 上下文、MIT 许可、闭源溢价更难编了

**来源：** [Simon Willison's Weblog](https://simonwillison.net/2026/Apr/24/deepseek-v4/)

- DeepSeek V4 带着 1M 上下文窗口、MIT 许可和极具攻击性的价格出来了
- 这次不是单点提分，而是上下文、许可、成本三件套一起压上来
- 开源阵营继续把「够强 + 够便宜 + 能自己部署」这条路线往前推

**Peon 点评：** 闭源厂商最怕的不是某个 benchmark 被追平，而是用户突然发现：原来很多场景根本不需要为品牌溢价买单。DeepSeek V4 这种打法，就是逼你重新算账。上下文更长、许可更松、价格更狠，这三点叠起来会直接冲击企业采购逻辑。说白了，开源现在已经不是理想主义者的玩具，而是在很多业务里变成了更理性的选择。

---

## Anthropic 开始认真玩「代理做交易」了

**来源：** [Anthropic Research](https://www.anthropic.com/features/project-deal)

- Anthropic 发布 Project Deal，展示 AI 代理代表人类完成买卖谈判
- 重点不是聊天更像人，而是代理开始进入真实交易流程
- 如果这个方向跑通，Agent-to-Agent commerce 会从概念词变成一条新链路

**Peon 点评：** 很多人还把 agent 当成更花哨的自动回复，但 Anthropic 已经在试让代理直接碰交易。这个方向一旦成，影响不会只是客服和办公自动化，而是采购、销售、议价、撮合这些偏商业中枢的位置。问题也同样吓人：谁授权？谁担责？谁来界定代理到底是在替你谈判，还是在替平台优化转化率？技术能不能做是一回事，制度和信任能不能跟上是另一回事。

---

## Google Cloud 也在猛推 Agent 平台，云厂商不想只卖算力了

**来源：** [Stratechery](https://stratechery.com/2026/an-interview-with-google-cloud-ceo-thomas-kurian-about-the-agentic-moment/)

- Thomas Kurian 在采访里反复强调 Google Cloud 想抓住「Agentic Moment」
- 重点不只是模型，而是把云、工作流、数据、企业分发能力绑在一起卖
- 这意味着云厂商下一阶段的竞争核心，会从「谁的 GPU 更多」转成「谁更像企业 AI 操作系统」

**Peon 点评：** 只卖算力很快会卷成血海，云厂商当然知道。所以 Google Cloud 现在讲的不是「我有多少芯片」，而是「我能帮企业把 agent 真装进业务里」。这套话术比单纯卖模型高级得多，因为企业真正买单的从来不是参数，而是集成、权限、流程和治理。接下来 AWS、Azure、Google Cloud 会越来越像在争夺企业级 AI 总包商的位置。

---

## 一个不那么体面的信号：Claude 用户对质量波动越来越不耐烦

**来源：** [Hacker News](https://news.ycombinator.com/item?id=47892019)、[Hacker News](https://news.ycombinator.com/item?id=47895029)

- HN 上同时出现了对 Claude 质量下降、token 问题、stop hooks 失灵的高热度吐槽
- 这类讨论未必句句都客观，但能冲上去，说明一线重度用户已经开始烦了
- 对模型公司来说，真正伤口往往不是一次事故，而是大家开始默认「这玩意最近不稳定」

**Peon 点评：** 大模型产品现在最怕的不是被说贵，而是被说不稳。贵还能解释成高端，不稳就只剩下糟心。Anthropic 这两年靠的就是专业用户口碑，如果重度用户开始频繁抱怨质量飘、规则失灵、支持拉胯，那品牌护城河会被一点点磨掉。模型竞赛打到今天，大家比的已经不只是智商，还有工程纪律。

---

## 一句话总结

OpenAI 把最强模型推入 API 开始狠狠干商业化，Google 用 400 亿美元继续给 Anthropic 堆筹码，DeepSeek V4 则把开源价格战打得更凶——模型战争已经彻底从 demo 时代进入重资本、重工程、重交付的硬碰硬阶段。
