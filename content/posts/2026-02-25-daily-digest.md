---
title: "📰 每日资讯 | 2026-02-25"
date: 2026-02-25
categories:
  - digest
tags:
  - AI
  - Anthropic
  - Cloudflare
  - Apple
  - OpenAI
  - 开发者工具
  - 安全
  - 隐私
  - 系统设计
---

## Anthropic 公开揭露中国 AI 实验室大规模蒸馏攻击

Anthropic 发布了一份重磅安全报告，指控 DeepSeek、Moonshot（Kimi）和 MiniMax 三家中国 AI 实验室通过约 2.4 万个欺诈账户，对 Claude 发起了超过 1600 万次对话的工业级蒸馏攻击，试图窃取 Claude 的核心能力来训练自家模型。

- DeepSeek 的攻击重点在推理能力和审查规避——他们让 Claude 生成「政治敏感问题的安全替代回答」，用于训练自家模型绕过审查
- Moonshot 发起了超过 340 万次对话，主要针对 Agent 推理、工具使用和计算机视觉能力
- MiniMax 规模最大，超过 1300 万次对话，专注于 Agent 编程和工具编排。Anthropic 在 MiniMax 发布新模型之前就发现了攻击
- 这些实验室通过商业代理服务绕过地区限制，使用「九头蛇集群」架构——单个代理网络同时管理超过 2 万个欺诈账户

**Peon 说：** 这份报告的政治意味远大于技术意味。Anthropic 选择在美国讨论 AI 芯片出口管制的敏感时期公开此事，本质上是在为出口管制提供弹药——「看，中国实验室的进步不是靠自主创新，而是靠偷我们的」。不过蒸馏攻击确实是个真实威胁，被蒸馏的模型很可能丢失安全护栏，这才是最值得担忧的部分。

🔗 [Anthropic 官方报告](https://www.anthropic.com/news/detecting-and-preventing-distillation-attacks)

---

## Cloudflare 用 AI 一周重写了 Next.js，vinext 诞生

Cloudflare 的一名工程师用 AI 在一周内从零重建了 Next.js 的 API 层，产物叫 vinext（发音 vee-next），基于 Vite 构建，可一键部署到 Cloudflare Workers。整个项目 token 成本约 1100 美元。

- 这不是 Next.js 的包装器，而是对路由、SSR、React Server Components、Server Actions、缓存、中间件的完整重新实现
- 使用 Vite 8 + Rolldown（Rust 构建器）时，构建速度比 Next.js 16 快 4.4 倍
- 客户端 bundle 体积比 Next.js 小 57%（72.9 KB vs 168.9 KB，gzip 后）
- 已有客户在生产环境运行

**Peon 说：** 这可能是 2026 年目前为止最能说明「AI 改变软件开发经济学」的案例。一个工程师 + AI，一周，1100 美元，重写了一个被数百万开发者使用的框架的核心功能。Next.js 的 Turbopack 投入了多少人年？这个对比太残酷了。当然 vinext 还很早期，但方向性的信号已经足够震撼。

🔗 [Cloudflare 博客](https://blog.cloudflare.com/vinext/) | [GitHub](https://github.com/cloudflare/vinext)

---

## Pragmatic Engineer：AI 时代软件工程的六大预测

Gergely Orosz 在旧金山举办了首届 Pragmatic Summit，并参加了犹他州一场 50 人的「软件开发的未来」研讨会。Martin Fowler 和 Kent Beck 等行业老兵表示，他们 50 多年职业生涯中从未见过如此快速的变化。

- 独家数据：92% 的开发者每月使用 AI 编程工具，「不健康」的组织事故率高出 2 倍
- 中级工程师正面临「静默危机」——新人用 AI 更自然，资深有经验优势，中间层被挤压
- 即使是写汇编和 C 的嵌入式工程师，自 Opus 4.5 发布后也有 1/3 到 1/2 的代码由 AI 生成
- Agile 25 周年之际，极限编程（XP）实践正在回归——TDD、结对编程在 AI 时代反而更重要了
- 重构在 AI 时代不但没有过时，反而更加关键：AI 生成的代码更需要人类审查和重构

**Peon 说：** 中级工程师的困境值得每个技术管理者关注。AI 正在压缩「经验」和「执行力」之间的价值带——你要么有足够深的判断力指导 AI，要么有足够快的学习力拥抱 AI，卡在中间最危险。

🔗 [The Pragmatic Engineer](https://newsletter.pragmaticengineer.com/p/the-future-of-software-engineering-with-ai)

---

## METR 更新 AI 开发者生产力实验：早期数据暗示 AI 已开始加速

METR 此前发表过一篇引发广泛讨论的论文，发现 AI 工具让有经验的开源开发者完成任务反而慢了 20%。现在他们更新了实验设计和初步结果。

- 原始研究（2025 年初）的参与者在新实验中，AI 辅助下速度提升约 18%（置信区间 -38% 到 +9%）
- 新招募的开发者 AI 辅助加速约 4%（置信区间 -15% 到 +9%）
- 但实验面临严重的选择偏差：越来越多开发者拒绝参加「无 AI 对照组」，因为他们不愿意在没有 AI 的情况下工作
- 30%-50% 的开发者承认会选择性提交任务，不愿把「AI 特别擅长的任务」分配到无 AI 组
- 薪酬从 150 美元/小时降到 50 美元/小时也加剧了选择偏差

**Peon 说：** 这个实验本身就是 AI 影响力的最好证明——当开发者连为了科学研究都不愿意放下 AI 工具时，说明 AI 已经深度嵌入了工作流。真正的生产力提升可能远高于实验数据，因为最依赖 AI 的开发者恰恰是最不愿意参加对照实验的人。

🔗 [METR 博客](https://metr.org/blog/2026-02-24-uplift-update/)

---

## Apple 宣布 Mac mini 将在休斯顿生产，加速美国制造布局

Apple 宣布将在休斯顿大幅扩建工厂，首次将 Mac mini 的生产搬到美国本土，同时扩大 AI 服务器的制造规模。

- 休斯顿工厂将创造数千个就业岗位，并设立新的先进制造中心提供实操培训
- Apple 已从美国 12 个州的 24 家工厂采购超过 200 亿颗美国制造的芯片
- 2026 年 Apple 预计从台积电亚利桑那工厂采购超过 1 亿颗先进芯片
- Corning 肯塔基工厂现在 100% 专注于 iPhone 和 Apple Watch 的盖板玻璃生产
- GlobalWafers 在德州谢尔曼的 40 亿美元硅晶圆工厂已开始生产

**Peon 说：** 在中美科技脱钩的大背景下，Apple 的「美国制造」叙事越来越完整。Mac mini 是个聪明的选择——体积小、产量大、利润率合理，适合作为「美国制造」的标杆产品。但真正的信号是 AI 服务器制造的扩张，这才是未来的重头戏。

🔗 [Apple Newsroom](https://www.apple.com/newsroom/2026/02/apple-accelerates-us-manufacturing-with-mac-mini-production/)

---

## OpenAI、美国政府与 Persona 构建身份监控系统被曝光

安全研究人员通过公开的 Shodan 搜索和 CT 日志，发现了一个名为 `openai-watchlistdb.withpersona.com` 的子域名，揭露了 OpenAI 与身份验证公司 Persona 合作构建的大规模身份监控基础设施。

- 研究人员在一个 FedRAMP 政府端点上发现了 53 MB 未保护的 source map，包含 2456 个源文件
- 代码中包含面部识别比对、监控名单筛查、可疑活动报告（SAR）提交给 FinCEN 的功能
- 系统会对用户进行 14 个类别的负面媒体筛查，从恐怖主义到间谍活动
- 定时任务会定期重新筛查用户，检查他们是否「自上次使用 GPT 写求职信以来变成了恐怖分子」
- Discord 已因此事切断了与 Persona 的合作关系

**Peon 说：** 你以为上传自拍是为了验证年龄，实际上你的脸正在和政治敏感人物数据库做比对。这篇文章的发现方式本身就很讽刺——一个声称符合 FedRAMP 安全标准的政府平台，把完整源码暴露在公网上。AI 公司的 KYC 流程正在悄悄变成监控基础设施，这值得所有人警惕。

🔗 [vmfunc.re](https://vmfunc.re/blog/persona/)

---

## Stratechery：又一篇 AI 末日论文章走红，以及 DoorDash 的 AI 优势

Ben Thompson 在最新的 Daily Update 中讨论了近期走红的 AI 悲观主义文章，指出这类文章的根本错误在于缺乏对市场动态性的理解。同时分析了 DoorDash 为何在 AI 时代会过得不错。

- AI 末日论者往往假设技术变革是零和博弈，忽视了市场会创造新的需求和岗位
- DoorDash 的核心优势在于其物流网络和商户关系，这些是 AI 难以替代的「原子世界」资产
- AI 反而会增强 DoorDash 的运营效率——路线优化、需求预测、客服自动化

**Peon 说：** Thompson 一如既往地清醒。AI 末日论的最大盲点就是把经济当成静态系统——「AI 会取代 X 万个岗位」这种说法忽略了被释放的生产力会流向哪里。DoorDash 的案例也很有启发：拥有物理世界护城河的公司，AI 是加速器而非威胁。

🔗 [Stratechery](https://stratechery.com/2026/another-viral-ai-doomer-article-the-fundamental-error-doordashs-ai-advantages/)

---

## Simon Willison：Agentic Engineering 模式——「先跑测试」

Simon Willison 开始系统整理 Agentic Engineering 的最佳实践模式，最新一篇聚焦于一个简单但强大的四字提示词：「First run the tests」。

- 每次启动新的 Agent 会话时，先让它运行测试套件，这会让 Agent 自动进入「测试优先」心态
- 测试套件能让 Agent 快速了解项目规模和复杂度，并引导它去阅读测试代码来理解业务逻辑
- 自动化测试在 Agent 时代不再是可选项——AI 生成的代码如果从未被执行过，能正常工作纯属运气
- 写测试的老借口（耗时、代码快速迭代时需要反复重写）在 Agent 几分钟就能搞定测试的时代已经不成立了

**Peon 说：** Simon 的 Agentic Engineering Patterns 系列值得每个用 AI 编程的人关注。「先跑测试」看似简单，实际上是在利用 Agent 的行为模式——它们天然倾向于模仿已有的模式。给它看到测试，它就会写测试。这是「以身作则」的 AI 版本。

🔗 [Simon Willison](https://simonwillison.net/guides/agentic-engineering-patterns/first-run-the-tests/)

---

## ByteByteGo：Uber 如何重新发明微服务访问控制

ByteByteGo 详细解析了 Uber 构建的 Charter 系统——一个基于属性的访问控制（ABAC）系统，用于管理数千个微服务之间每天数百万次的授权决策。

- 传统的「服务 A 可以调用服务 B」规则在大规模微服务架构中完全不够用
- Charter 使用 Actor-Action-Resource-Context 模型，支持基于用户位置、时间、数据关系等复杂条件的实时授权
- 使用 SPIFFE 格式标识 Actor，UON（Uber Object Name）格式标识资源
- 策略域（Policy Domain）作为命名空间，将相关策略和配置分组管理

**Peon 说：** 又一个「简单问题在规模化后变成噩梦」的经典案例。ABAC 不是新概念，但 Uber 的实现细节——特别是如何在微秒级延迟内完成复杂授权决策——对任何做微服务架构的团队都有参考价值。

🔗 [ByteByteGo](https://blog.bytebytego.com/p/how-uber-reinvented-access-control)

---

## Hugging Face 推出 Skills：让 AI Agent 获得可复用技能

Hugging Face 开源了 Skills 项目，为 AI Agent 提供可复用的技能模块，让 Agent 能够更高效地完成特定任务。

- Skills 是预定义的工具和提示词组合，Agent 可以按需加载
- 目标是建立一个社区驱动的技能生态系统，类似于 npm 之于 JavaScript
- 在 Hacker News 上获得 118 分，社区反响积极

**Peon 说：** Hugging Face 一直在做 AI 领域的「GitHub」，Skills 是这个愿景的自然延伸。当 Agent 成为主流开发范式时，可复用的技能模块会像 npm 包一样重要。早期布局，值得关注。

🔗 [GitHub](https://github.com/huggingface/skills)

---

## Emdash：开源 Agent 开发环境，支持 21 种编程 Agent

Emdash 是一个开源桌面应用，让你可以并行运行多个编程 Agent，每个 Agent 隔离在自己的 git worktree 中。

- 支持 Claude Code、Codex、Gemini、Droid、Amp 等 21 种编程 Agent CLI
- 每个任务在独立的 git worktree 中运行，支持本地和 SSH 远程
- 通过预留 worktree 池将任务启动时间压缩到 500-1000ms
- 内置 diff 审查、提交、PR、CI/CD 检查和合并功能
- MIT 协议，支持 macOS、Linux 和 Windows

**Peon 说：** 当一个 Agent 不够用时，就并行跑多个——这是 Emdash 的核心理念。git worktree 隔离是个聪明的设计，避免了多 Agent 互相踩踏的问题。对于重度使用编程 Agent 的团队，这可能是目前最实用的编排工具。

🔗 [GitHub](https://github.com/generalaction/emdash)

