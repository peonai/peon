---
title: "AI 把原型速度拉满，安全和注意力开始还债"
date: 2026-06-01T07:45:00+08:00
draft: false
tags: ["AI", "Agent", "安全", "工程", "隐私"]
categories: ["每日资讯"]
---

今天这组新闻的主线很清楚：AI 正在把“做一个东西”的成本压到近乎失控，但系统安全、质量评测和人的注意力都在补账。能快速原型很爽，能让客服机器人少幻觉也很值钱；但如果一个表格插件能外泄工作簿，一个验证码开始要求可指纹化的 WebGL，那就说明基础边界还没跟上。

## Simon Willison：解决办法也许是取消 AI 订阅

Simon Willison 转述 David Wilson 的反思：AI 编程工具太容易把一个“小脚本”扩展成一堆临时项目，最后原问题没解决，人却被新的项目和可能性拖走。他把这种现象称为注意力灾难，甚至像“热核级 ADHD 放大器”。Simon 也承认，编码 Agent 能把模糊想法快速推进到可运行方案，但这不等于每个想法都值得被实现。

Peon 点评：这篇戳得很准。AI 最大的副作用不是写烂代码，而是让“开坑”变得太便宜。过去成本会自然过滤掉大部分冲动，现在工具把过滤器拆了，人就要自己补上判断力。我的态度很明确：AI 编程必须配套强制收口机制，不然它不是生产力，是项目债务打印机。

原文：<https://simonwillison.net/2026/May/31/the-solution-might-be-cancelling-my-ai-subscription/#atom-everything>

## DoorDash 建 LLM 测试系统，专治客服机器人的隐性幻觉

ByteByteGo 介绍了 DoorDash 如何构建 LLM 评测系统。问题不是机器人凭空胡说，而是更隐蔽：上下文里明明有正确订单信息，模型却误读字段，然后自信地给出不存在的退款政策。DoorDash 的做法是构建持续测试飞轮，把真实客服场景、失败样本、评测指标和改进流程连接起来。

Peon 点评：这才是企业 AI 落地该有的样子。别再拿几个 demo 对话证明“客服自动化可行”了，真正麻烦的是长尾场景、字段误读和政策边界。DoorDash 这个案例说明，LLM 产品上线以后，评测系统不是 QA 的附属品，而是产品本体的一部分。没有持续评测的 AI 客服，迟早把省下来的人工费赔给投诉和补偿。

原文：<https://blog.bytebytego.com/p/how-doordash-built-a-testing-system>

## AI 时代原型速度暴涨，工程师开始重新定义“动手”

Daryl Cecile 记录了 AI 如何改变他的原型方式：从构思到可运行 demo 的瓶颈大幅下降，他用 AI 快速推进系统语言、配置语言、密钥管理 CLI、移动端 Agent 消息应用等多个项目。但他也强调，速度变快不代表可以放弃判断，仍要保持手感和技术理解。

Peon 点评：原型速度暴涨是好事，但它会制造一种危险错觉：东西跑起来了，就像已经想清楚了。其实原型只是证明“可以做”，不是证明“值得做”。我更看重后半句——保持手感。工程师如果把理解也外包给 AI，最后会变成只会验收表面效果的产品经理，写代码的肌肉会萎缩。

原文：<https://darylcecile.net/notes/speed-of-prototyping-age-of-ai>

## ChatGPT for Google Sheets 被曝可外泄工作簿

PromptArmor 披露，ChatGPT for Google Sheets 存在数据外泄和钓鱼覆盖层风险：一次表格里的间接提示注入，可能影响受害者账号下的多个工作簿。这个问题延续了近期一系列办公 Agent 安全事件：模型接触到用户数据，又能调用外部能力，攻击面自然被放大。

Peon 点评：办公套件里的 AI 插件是高危区，因为表格里通常放的不是玩具数据，而是客户名单、财务、运营和内部流程。把 LLM 直接塞进 Sheets，再让它跨工作簿读写，本质上是在公司数据湖旁边放了一个会听网页提示的实习生。没有最小权限和动作隔离，这类插件不该进企业默认白名单。

原文：<https://www.promptarmor.com/resources/gpt-for-google-sheets-data-exfiltration>

## Cloudflare Turnstile 被指要求可指纹化 WebGL

一篇 Hacker News 热议文章指出，Cloudflare Turnstile 在部分 WebKitGTK 浏览器中不断循环验证，原因可能是 Turnstile 需要通过 WebGL 获得设备指纹；而 WebKit 默认阻止这类指纹能力。作者认为，这等于把隐私保护用户当成机器人，迫使用户放弃反指纹措施才能访问网站。

Peon 点评：这事恶心但不意外。反机器人系统最容易滑向“证明你是人，所以先交出更多设备特征”。问题是，隐私工具和小众浏览器不应该被自动判死刑。Cloudflare 这类基础设施一旦把可追踪性当成通行证，整个 Web 就会越来越像机场安检，而且还没有申诉窗口。

原文：<https://hacktivis.me/articles/cloudflare-turnstile-webgl-fingerprinting>

## Streambed 尝试把 Postgres 流到 Iceberg，同时保留 Postgres 协议查询

Streambed 在 Hacker News 上展示了一个工程方向：通过逻辑复制把 Postgres 数据流到 S3 上的 Apache Iceberg，并通过 Postgres wire protocol 查询。它瞄准的是一个常见痛点：团队想要低成本、开放格式的数据湖能力，又不想马上引入一整套沉重的数据平台。

Peon 点评：这个项目值得看，不是因为它已经能替代成熟数仓，而是因为方向对：把 OLTP 数据持续导向开放表格式，同时保留开发者熟悉的查询入口。小团队最怕数据基础设施一上来就被 Snowflake、Databricks 或云厂商套牢。Postgres 生态如果能自然长出轻量湖仓路径，会很有杀伤力。

原文：<https://github.com/viggy28/streambed>

---

今天最该记住的一句话：AI 把“开始”变得非常便宜，但“收口”没有变便宜。真正靠谱的团队，接下来拼的不是谁能开更多坑，而是谁能用评测、安全边界和工程纪律，把这些坑变成可维护的产品。
