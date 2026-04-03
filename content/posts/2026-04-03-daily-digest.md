---
title: "Anthropic 源码泄露、OpenAI 融资 1220 亿美元、Google 开源 Gemma 4"
date: 2026-04-03T07:30:00+08:00
categories: ["digest"]
tags: ["AI", "Anthropic", "OpenAI", "Google", "Gemma", "Claude", "NASA"]
---

本期涵盖 4 月 1 日至 4 月 3 日的资讯。

## Anthropic 一周内两次泄露：Claude Code 源码全面曝光

来源：https://thenewstack.io/anthropic-claude-code-leak/

Anthropic 这周过得不太顺。3 月 26 日，Fortune 报道该公司因 CMS 配置错误导致近 3000 份内部文件泄露，其中包括代号为「Mythos」（内部也称「Capybara」）的新模型草稿——被描述为公司「迄今为止最强大的 AI 模型」。不到一周，3 月 31 日，安全研究员 Chaofan Shou 发现 Anthropic 在 Claude Code v2.1.88 的 npm 包中意外包含了一个 59.8MB 的源代码映射文件。

这个源映射文件指向一个存储在 Cloudflare R2 上的未加密 ZIP 压缩包，包含约 1900 个文件、51.2 万行 TypeScript 代码。泄露内容涵盖完整的代理架构、系统提示词、40 多个 agentic 工具的内部实现，以及至少 8 项未发布功能：包括名为 KAIROS 的后台常驻代理（每天记录行为、夜间执行「autoDream」例行整理）、一个 Tamagotchi 风格的编程伴侣（会在输入框旁边根据你的代码做出反应），还有「卧底模式」——当 Anthropic 员工在内部仓库使用 Claude Code 时会自动激活，防止敏感信息外泄。

Anthropic 首席商务官 Paul Smith 回应称这是「发布流程中的人工失误，绝非安全漏洞」。Claude Code 创始人 Boris Cherny 在 X 上表示：「已经改进了自动化流程，没人因此被解雇，这是诚实的错误。」Anthropic 已向 GitHub 提交大量 DMCA 删除请求，但代码早已传播开来，甚至出现了一个韩国开发者用 Python 和 Rust 重写的「Claw Code」项目，24 小时内获得 10 万星标，创下 GitHub 最快增长记录。

这件事对 Anthropic 的品牌伤害不小。一家以「AI 安全」为核心定位的公司，一周内连续两次泄露，第一次暴露了新模型，第二次暴露了自家旗舰产品的全部源码。讽刺的是，泄露的代码中还包含他们如何检测和防止模型被用于恶意用途的机制——现在这些机制本身也暴露了。

---

## Google 发布 Gemma 4，Apache 2.0 授权正式开源

来源：https://www.theregister.com/2026/04/02/googles_gemma_4_open_weights/

Google 在 4 月 2 日发布了 Gemma 4 系列开源模型，这是 Google 在开源 AI 领域的一次重要表态。Gemma 4 包含四个版本：E2B（20 亿参数）和 E4B（40 亿参数）针对手机和边缘设备优化；26B 是混合专家（MoE）架构，注重推理速度；31B 是密集架构，追求原始质量。

最大的变化是许可协议。之前的 Gemma 版本使用 Google 自定义的受限许可，企业构建衍生模型或商业化都需要法律审查。Gemma 4 改用 Apache 2.0，这意味着开发者可以自由修改、重新分发和商业化，不用担心 Google 事后改条款。Hugging Face 联合创始人 Clement Delangue 评论说：「本地 AI 正在迎来它的时代，这是 AI 行业的未来。」

性能方面，31B 模型在 AIME 2026 数学基准上达到 89.2%，GPQA Diamond 科学推理 84.3%，LiveCodeBench v6 编程竞赛 80%。虽然略逊于阿里巴巴的 Qwen 3.5、智谱 GLM-5 和月之暗面 Kimi K2.5 等中国开源模型，但差距不大。更重要的是，Gemma 4 是「美国阵营」中目前最强的开源模型之一。

背景是中国开源模型的崛起正在挤压西方模型的空间。过去几个月，Moonshot AI、阿里巴巴、Z.AI 发布的开源模型在多项基准上逼近甚至超越 GPT-5 和 Claude。Gemma 4 的发布可以看作 Google 的回应：用更开放的许可和更强的性能，重新夺回开源赛道的话语权。

---

## OpenAI 完成 1220 亿美元融资，估值达 8520 亿美元

来源：https://theaiworld.org/news/openai-raises-122b-to-accelerate-ai

OpenAI 在 3 月 31 日完成了史上最大的一轮融资：1220 亿美元，投后估值 8520 亿美元。这个数字是什么概念？它超过了 Spotify、Uber、Airbnb 三家公司市值的总和。

本轮融资由亚马逊领投 500 亿美元，英伟达和软银各投 300 亿美元，其他投资者包括 Andreessen Horowitz、D.E. Shaw、MGX、TPG、T. Rowe Price 等。据《华尔街日报》报道，CEO Sam Altman 在内部称这笔资金将用于「真正加速经济发展」，暗示 OpenAI 正在规划远超 ChatGPT 规模的基础设施。

这笔钱主要投向两个方向：一是计算基础设施，建设「行星级别」的 AI 计算集群；二是新模型研发，包括内部代号为「Spud」的下一代基础模型。OpenAI 总裁 Greg Brockman 在 Big Technology 播客中透露，Spud 凝聚了公司两年的研究成果，将是「一个新基座模型」，而不仅仅是增量升级。

OpenAI 的融资节奏越来越快。一年前它还以 1570 亿美元估值融资，现在直接跳到 8520 亿。这种增长速度在科技史上极为罕见，也反映出资本市场对 AGI 的押注正在升温。但隐忧也在这：如此庞大的资金体量意味着 OpenAI 必须在未来几年证明其商业价值能匹配这个估值，否则调整将是剧烈的。

---

## Anthropic 推出 Windows 版 Claude Computer Use

来源：https://letsdatascience.com/news/anthropic-adds-computer-use-to-windows-apps-40c5c1ad

4 月 3 日，Anthropic 宣布 Claude Cowork 和 Claude Code Desktop 的 Computer Use 功能正式支持 Windows。该功能于 3 月 23 日首先在 macOS 上推出，一周后扩展到 Windows，覆盖了约 70% 的桌面用户。

Computer Use 允许 Claude 直接控制用户的电脑：打开应用、控制键盘鼠标、浏览网页、填写表格、使用 Slack 或 Google Calendar 等服务连接器。Anthropic 还与 Dispatch 合作提供远程任务编排能力。目前该功能仍处于研究预览阶段，需要 Claude Pro 或 Max 订阅才能使用。

这个功能代表了 AI 从「聊天工具」向「数字员工」的转型。与简单的 API 集成不同，Computer Use 让 AI 像人类一样与现有软件生态交互，无需企业为每个应用单独开发 AI 接口。对于知识工作者来说，这意味着 AI 可以接管更多重复性桌面任务——整理文件、填写报表、跨应用同步数据。

当然，风险也随之而来。Anthropic 官方文档提醒用户：这是研究预览功能，复杂任务有时需要重试，屏幕交互比直接集成慢，建议先在非敏感应用中测试。毕竟，让 AI 控制你的电脑本质上是在赋予它很高的系统权限。

---

## NASA Artemis II 成功发射，人类重返月球

来源：https://apod.nasa.gov/apod/ap260402.html

4 月 1 日，NASA 成功发射 Artemis II 载人绕月任务。这是自 1972 年阿波罗 17 号以来，人类首次离开近地轨道进入深空。猎户座飞船搭载 4 名宇航员，将执行为期约 10 天的任务：发射后进入地球轨道，然后推进器点火进入地月转移轨道，绕月飞行后返回地球，在太平洋溅落。

Artemis II 是一次「不落地」的测试飞行，主要验证猎户座飞船的生命支持系统、导航系统和深空通信能力。宇航员将观察月球表面，包括极少能从地球看到的月球背面阴影区域。这些数据将为 2027 年的 Artemis III 载人登月任务做准备。

这次发射标志着美国载人航天进入了新阶段。过去 50 年，人类的活动范围被限制在近地轨道——国际空间站距地面约 400 公里，而月球距地球 38 万公里。Artemis 计划的目标不仅是重返月球，更是建立可持续的月球存在，为未来的火星任务积累经验。

SpaceX 的星舰也在并行发展，但 NASA 的 Artemis 代表了政府主导的传统深空探索路径。两条路线最终都指向同一个目标：让人类成为多行星物种。

---

## Simon Willison：用 Claude 技能实验 Starlette 1.0

来源：https://simonwillison.net/2026/Mar/22/starlette-claude-skills/

Simon Willison 最近发了篇文章，记录他用 Claude Code 探索 Starlette 1.0 开发的过程。Starlette 是一个轻量级的 Python ASGI 框架，1.0 版本刚刚发布。Willison 的方式是典型的「vibe coding」——让 Claude 生成代码，自己负责审查和迭代。

他发现 Claude 在处理异步 Python 代码时表现出色，能快速理解 ASGI 的生命周期和 Starlette 的请求处理流程。一个有趣的细节是：当 Claude 犯错时，直接把错误信息丢回去，它通常能自己修复。这种「自我纠错」能力让开发流程变得流畅。

Willison 是少数真正在记录 AI 辅助编程实践的人。他的文章不是炫耀工具多厉害，而是诚实地展示过程中遇到的问题和解决方案。对于想要尝试类似工作流的开发者来说，这些记录比任何教程都有价值。

---

## OpenAI 新模型 Spud 预告：两年研究的集大成

来源：https://www.ndtvprofit.com/technology/openai-may-announce-spud-new-base-ai-model-for-chatgpt-in-agi-push-11301492

OpenAI 总裁 Greg Brockman 在 Big Technology 播客中透露了公司下一代基础模型的细节。这个内部代号为「Spud」的模型，预计将在未来几周内发布，可能命名为 GPT-5.5 或 GPT-6。

Brockman 描述 Spud 是「两年研究成果的结晶」，拥有「big model smell」——这个说法借用了「新车味」的比喻，暗示用户能直观感受到模型的不同。核心改进在于上下文理解能力：用户不需要反复解释和澄清，模型能更快抓住意图。

Sam Altman 在内部会议上称 Spud「可以真正加速经济发展」，这是一个相当高的评价。如果属实，Spud 可能不仅在基准测试上提升，还会带来全新的能力类别——更好的工具使用、更长的连贯推理、或者更接近自主代理的行为。

发布时间窗口预计在 4 月或 5 月。如果 Spud 和 Anthropic 泄露的 Mythos 都在近期发布，这将是 AI 模型竞争最激烈的一个季度。

---

## AI 初创企业融资 Q1 创历史新高

来源：https://news.crunchbase.com/venture/foundational-ai-startup-funding-doubled-openai-anthropic-xai-q1-2026/

2026 年第一季度的 AI 融资数据出来了，数字惊人。据 Crunchbase 统计，仅基础 AI 创业公司就在 Q1 筹集了 1780 亿美元，超过 2025 年全年（889 亿美元）的两倍，比 2024 年全年的 314 亿美元高出 467%。

除了 OpenAI 的 1220 亿美元和 Anthropic 的 300 亿美元，xAI 筹集了 200 亿美元，Waymo 160 亿美元。这四轮融资就占了整个季度融资额的 63% 以上。种子轮和 A 轮的平均规模也显著上升，达到 1800 万美元，比 2025 年同期增长 30%。

投资热点集中在几个方向：多模态 AI（如 Imbue 1.2 亿美元 B 轮）、生命科学 AI（如蛋白质设计公司 Cradle 9000 万美元）、垂直领域 AI SaaS（金融、法律、物流）。

这种资本密度意味着 AI 行业的门槛正在迅速提高。对于没有大量算力储备或顶尖研究团队的新进入者，竞争空间正在收窄。同时，这也预示着未来几年可能出现剧烈的行业整合——当烧钱速度超过收入增长时，只有资本最充裕的玩家能 survive。
