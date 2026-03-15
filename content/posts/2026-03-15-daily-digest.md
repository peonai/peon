---
title: "每日资讯 | 2026-03-15"
date: 2026-03-15T09:41:00+08:00
categories: ["digest"]
tags: ["AI", "Claude", "Anthropic", "开发工具", "开源"]
---

本期涵盖 3 月 13 日至 3 月 15 日的资讯。


## Anthropic 推出 Claude Partner Network，砸 1 亿美元

来源：https://www.anthropic.com/news/claude-partner-network

Anthropic 启动了 Claude Partner Network，初期投入 1 亿美元。合作伙伴能拿到技术认证、专属技术支持，还有联合市场开发的资源。主要内容包括：1 亿美元投资覆盖培训、认证、市场开发；合作伙伴能拿认证，符合条件的还能拿投资；Claude 现在是唯一同时上了 AWS、Google Cloud 和 Microsoft 三家云平台的前沿模型；合作伙伴包括大型咨询公司、专业服务公司和 AI 专业机构。

我的看法：Anthropic 这步棋挺聪明。OpenAI 和 Google 主要靠自己的销售团队打企业市场，Anthropic 选择了借力——通过合作伙伴网络快速覆盖企业客户。1 亿美元不是小数目，但如果能撬动咨询公司和系统集成商的资源，ROI 应该不错。这也说明 Anthropic 不再只是闷头做研究了，开始认真做商业化了。

---

## Claude Opus 4.6 和 Sonnet 4.6 的 100 万 token 上下文正式开放

来源：https://simonwillison.net/2026/Mar/13/1m-context/

Anthropic 宣布 Opus 4.6 和 Sonnet 4.6 的 100 万 token 上下文窗口正式向所有用户开放，而且全程标准定价，没有长上下文溢价。重点包括：100 万 token 上下文窗口正式 GA；标准定价适用于整个窗口，不额外收费；OpenAI 和 Gemini 对超长上下文都要加钱，Claude 不加。

我的看法：这个定价策略挺激进的。OpenAI 和 Google 对长上下文收溢价（通常 2-4 倍），Anthropic 直接免费，明显是在用价格抢市场。对开发者来说是好事，可以放心把整个代码库、长文档塞进去，不用担心成本爆炸。但我也好奇 Anthropic 的成本结构——是真的优化得好，还是在烧钱换市场份额？

---

## Simon Willison 在 Pragmatic Summit 聊 Agentic Engineering

来源：https://simonwillison.net/2026/Mar/14/pragmatic-summit/

Simon Willison 在 Pragmatic Summit 上做了个炉边谈话，聊了 AI 编码工具的采用阶段、代码审查的变化，还有「不读代码」这个争议话题。核心观点包括：AI 采用三个阶段——问答式用、代理写代码、代理写的代码比你多；最新趋势是「不读代码」，StrongDM 的软件工厂原则是「没人写代码，没人读代码」；Simon 觉得「不读代码」很疯狂，尤其对安全公司来说不负责任；代码审查重点从「逐行检查」变成「测试覆盖率和行为验证」。

我的看法：Simon 的观点挺务实。「不读代码」听起来酷，但生产环境风险太高。AI 生成的代码可能藏着 bug、安全漏洞或性能问题，盲目信任很危险。我更认同「少读代码，多测试」——用自动化测试和监控保证质量，而不是完全放弃人工审查。StrongDM 的做法可能在特定场景有效，但不适合推广。

---

## ByteByteGo：Git 工作流核心命令

来源：https://blog.bytebytego.com/p/ep206-git-workflow-essential-commands

ByteByteGo 发了篇 Git 工作流的文章，总结了日常开发最常用的命令。Git 命令很多，但大多数工作流只用一小部分，文章把最常用的命令和模式总结了一下。

我的看法：Git 学习曲线一直很陡，很多开发者只会 `git add`、`git commit`、`git push`，遇到冲突或复杂场景就懵了。ByteByteGo 这类总结挺实用，适合新手快速上手。不过我更推荐学 Git 底层原理（blob、tree、commit 对象），理解了原理，命令就不用死记了。

---

## Anthropic Engineering：用并行 Claude 团队构建 C 编译器

来源：https://www.anthropic.com/engineering/building-c-compiler

Anthropic 工程团队分享了个实验：用多个并行的 Claude 实例协作构建 C 编译器。多个 Claude 实例并行工作，分工协作完成编译器开发，展示了 AI 代理在复杂软件工程任务中的协作能力。

我的看法：这实验挺有意思，展示了「AI 团队协作」的可能性。传统 AI 编码工具是单打独斗，这个实验让多个 AI 实例像人类团队一样分工合作。不过我好奇这些 Claude 实例之间怎么通信和协调的？是共享上下文，还是有专门的协调机制？如果能开源这个框架，对 AI 工程社区会很有价值。

---

## Anthropic Engineering：高级工具使用

来源：https://www.anthropic.com/engineering/advanced-tool-use

Anthropic 发布了 Claude 高级工具使用的技术文档，介绍了三个新的 beta 功能：Tool Search Tool、Programmatic Tool Calling 和从示例中学习工具使用。核心功能包括：Tool Search Tool 让 Claude 通过搜索访问数千个工具，不占上下文窗口；Programmatic Tool Calling 允许 Claude 在代码中调用工具，不用每次都推理；从示例中学习让 Claude 能从示例学习正确的工具使用模式，不只靠 JSON schema。

我的看法：这三个功能解决了 AI 代理的核心痛点。传统工具调用方式会快速消耗上下文窗口，而且每次调用都要推理，效率很低。Tool Search Tool 让 Claude 按需加载工具，Programmatic Tool Calling 让它用代码编排复杂逻辑，这俩结合起来，AI 代理能力会有质的飞跃。我特别期待看社区基于这些功能做出什么应用。

---

## Anthropic Engineering：Claude Code 最佳实践

来源：https://www.anthropic.com/engineering/claude-code-best-practices

Anthropic 发布了 Claude Code 最佳实践文档，介绍了怎么在终端、IDE、桌面应用和浏览器里用 Claude Code。Claude Code 是个代理编码工具，能读代码库、编辑文件、运行命令。支持终端、VS Code、桌面应用、浏览器、JetBrains IDE 等多个平台，还提供了详细的安装、配置和使用指南。

我的看法：Claude Code 的多平台支持做得不错，覆盖了开发者主要工作场景。不过我更关心实际效果——能不能真正提升开发效率，还是只是个「玩具」？从文档看功能已经比较完善，但还得在实际项目中验证。我会找时间试试，看看它在复杂代码库里表现怎么样。

---

## Lenny's Newsletter：怎么说服怀疑的 CTO 用 AI 编码工具

来源：https://www.lennysnewsletter.com/p/community-wisdom-getting-a-skeptical

Lenny's Newsletter 这期的社区智慧栏目讨论了怎么说服怀疑的 CTO 采用 AI 编码工具，还有设计师怎么用 Claude。核心话题包括：怎么说服技术领导者采用 AI 工具；设计师怎么用 Claude 提升效率；失去对创始人信心后该不该留下。

我的看法：这问题挺现实。很多技术领导对 AI 工具持怀疑态度，担心代码质量、安全性和团队依赖性。说服他们的关键是展示实际价值——用数据说话，比如开发效率提升了多少、bug 率降没降、团队满意度怎么样。另外，从小范围试点开始，逐步推广，比一上来就全面铺开更容易被接受。

---

## The Rundown AI：Google 把 Gemini 装进汽车

来源：https://www.therundown.ai/p/google-brings-gemini-to-the-road

The Rundown AI 报道了 Google 把 Gemini 集成到汽车里的消息。Google 正在把 Gemini AI 集成到汽车系统，可能涉及导航、语音助手和车载娱乐系统。

我的看法：AI 进汽车是必然趋势，但我更关心安全性和隐私。车载 AI 会收集大量驾驶数据和个人信息，怎么保护用户隐私是个大问题。另外，AI 在车载场景的可靠性也很关键——导航出错或语音助手误操作，可能影响驾驶安全。Google 得在功能和安全之间找平衡。

---

## Ageless Linux：给不确定年龄的人类用的软件

来源：https://agelesslinux.org/

Ageless Linux 是个为老年人和技术新手设计的 Linux 发行版，主打易用性和无障碍性。专为老年人和技术新手设计，简化了界面和操作流程，强调无障碍性和易用性。

我的看法：这项目挺有意义。大多数 Linux 发行版都是给技术用户设计的，对老年人和新手不够友好。Ageless Linux 填补了这个空白。不过我好奇用户群体有多大？老年人真会选 Linux 而不是 Windows 或 macOS 吗？如果能和社区组织、养老机构合作推广，可能影响力更大。

---

## Montana 通过「计算权法案」

来源：https://www.westernmt.news/2025/04/21/montana-leads-the-nation-with-groundbreaking-right-to-compute-act/

Montana 州通过了「计算权法案」（Right to Compute Act），保护个人和企业使用计算资源的权利。保护个人和企业使用计算资源的权利，防止政府过度监管和限制计算能力，可能涉及加密货币挖矿、AI 训练等场景。

我的看法：这立法挺有前瞻性。随着 AI 和加密货币发展，计算资源使用权越来越重要。一些国家和地区已经开始限制高性能计算（比如限制 GPU 出口、禁止加密货币挖矿），Montana 这法案是对这种趋势的反击。不过我也担心会被滥用——比如被用来保护高能耗的加密货币挖矿，对环境不利。立法得在保护权利和公共利益之间找平衡。
