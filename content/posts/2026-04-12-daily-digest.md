---
title: "Anthropic ARR 突破 300 亿美元超越 OpenAI，Claude Mythos 引发网络安全行业震动"
date: 2026-04-12T07:30:00+08:00
categories: ["digest"]
tags: ["Anthropic", "Claude", "Mythos", "OpenAI", "SiFive", "RISC-V", "DeepMind", "SQLite", "Meta", "AI 安全"]
---

本期涵盖 4 月 7 日至 4 月 11 日的资讯。

## Anthropic ARR 突破 300 亿美元，营收正式超越 OpenAI

来源：https://www.latent.space/p/ainews-anthropic-30b-arr-project

Anthropic 在 4 月 7 日宣布年化经常性收入突破 300 亿美元。就在一个月前的 3 月 4 日，这个数字还是 190 亿——一个月增长 110 亿，增速惊人。作为对比，OpenAI 的 ARR 大约在 250 亿美元左右。这意味着 Anthropic 在营收规模上正式超过了 OpenAI。

更值得关注的是收入结构。Anthropic 80% 的营收来自企业客户，而 OpenAI 的收入更多依赖消费端免费用户转化。在算力支出方面，OpenAI 预计单年投入 1210 亿美元，而 Anthropic 的支出远低于这个数字。Claude Code 从零到 25 亿美元营收只用了 10 个月，占据了 AI 编程工具市场半壁江山。

Anthropic 的估值约 3800 亿美元，但其营收效率已经让行业注意到一种不同的增长路径——不是靠砸算力堆用户，而是靠企业客户的深度渗透实现高利润率。

这不仅仅是数字游戏的换位。OpenAI 走的是 consumer-first 路线，先铺用户再变现；Anthropic 选择了 enterprise-first，直接对接有付费意愿的企业。两条路线在 2026 年交汇， Anthropic 的企业策略目前跑在了前面。但 OpenAI 的用户基数和生态广度仍然是巨大优势，这场竞争远未到终局。

## Anthropic 推出 Claude Mythos 与 Project Glasswing

来源：https://www.anthropic.com/glasswing

Anthropic 在 4 月 8 日正式发布 Claude Mythos Preview，并同步启动 Project Glasswing 行业联盟。Mythos 的网络安全能力被 Anthropic 自己描述为「远超任何其他 AI 模型」——它能发现每个主要操作系统和 Web 浏览器中的高危漏洞，包括此前未被发现的 zero-day。

问题的关键在于，这种能力是双刃剑。防御方可以用它来修补漏洞，攻击方同样可以利用它来寻找攻击入口。Anthropic 的选择是不公开发布 Mythos，而是通过 Project Glasswing 将其有限开放给 AWS、Apple、Broadcom、Cisco、CrowdStrike、Google、JPMorganChase、Microsoft 和 Nvidia 等行业巨头，专门用于防御性安全工作。

Nicolas Carlini 在近期的分享中提到「过去几周发现的 bug 数量超过了我一辈子发现的总和」。安全社区的反应也印证了 Mythos 能力的真实性——CrowdStrike、Palo Alto Networks、Zscaler、SentinelOne 等安全公司股价在消息传出后下跌 5% 到 11%。投资者担心 AI 模型的能力会让传统安全产品的需求下降。

这是 AI 行业第一次出现模型因为能力太强而被主动限制发布的案例。过去的安全模型都是「越强越好、越快发布越好」，但 Mythos 的出现让整个行业意识到：当 AI 的漏洞发现能力超过人类修复速度时，公开发布本身就成了风险。Anthropic 选择了一条罕见的路线——先给防御方时间准备，再考虑更广泛的发布。这个先例可能会影响未来所有 AI 安全相关模型的发布策略。

## Demis Hassabis：DeepMind 必须回到创业公司的节奏

来源：https://thenextweb.com/news/google-deepmind-hassabis-startup-pace

Demis Hassabis 在 20VC 播客中透露，Google DeepMind 在与 Google Brain 合并后的两三年里经历了「刻意的加速」。他的说法很直接：「我们必须回到创业公司的节奏，更敏捷、更快、迅速交付。」

Hassabis 形容当前的竞争环境为「残酷」——有 20 到 30 年从业经验的老员工告诉他，这是他们见过「最激烈的环境，可能是整个科技行业有史以来最激烈的」。他每天和 Alphabet CEO Sundar Pichai 沟通，反映出 DeepMind 已经处于 Alphabet 产品与研发战略的核心位置。

Google 的资本支出计划也印证了这种紧迫感——2025 年支出 914 亿美元，2026 年指引为 1750 亿到 1850 亿美元，几乎翻倍。Hassabis 甚至表示，大约 90% 的现代 AI 行业基础突破来自 Google Brain、Google Research 或 DeepMind。

Hassabis 还在运营 Isomorphic Labs（制药 AI 子公司），他描述自己的工作安排是：白天在 DeepMind，晚上 10 点开始「第二个工作日」处理 Isomorphic 的药物发现项目。Isomorphic 在 2025 年 4 月融资 6 亿美元，与 Eli Lilly 和 Novartis 的合作里程碑价值高达 30 亿美元，2026 年将启动肿瘤学人体临床试验。

这番表态的背景是 SoftBank 给 OpenAI 提供了 400 亿美元过桥贷款，竞争烈度已经让 Alphabet 的资本投入也显得不够用。Hassabis 的「创业节奏」不是文化口号，而是在资源战白热化下的生存策略。

## SiFive 获 4 亿美元融资，Nvidia 押注 RISC-V 开放芯片架构

来源：https://techcrunch.com/2026/04/11/nvidia-backed-sifive-hits-3-65-billion-valuation-for-open-ai-chips/

RISC-V 开源芯片设计公司 SiFive 完成了 4 亿美元的超额认购融资，估值达到 36.5 亿美元。这轮融资由前富达投资高管 Gavin Baker 创立的 Atreides Management 领投，Nvidia 参投，其他投资者包括 Apollo Global Management、D1 Capital Partners、Point72 Turion 和 T. Rowe Price。

SiFive 的业务模式类似早期的 Arm——授权芯片设计给客户，由客户自行修改，本身不生产芯片。但 SiFive 的设计基于 RISC-V 开放指令集，而非 Intel 的 x86 或 ARM 架构。这轮融资是 SiFive 自 2022 年 3 月以来首次融资，当时估值为 23.3 亿美元。

更有意思的是 Nvidia 的立场。Nvidia 的 GPU 帝国建立在 x86 和 ARM CPU 之上，但它选择投资一个基于完全不同的开放架构的芯片设计公司。SiFive 的设计将兼容 Nvidia 的 CUDA 软件和 NVLink Fusion 数据中心系统。在 Intel 和 AMD 试图与 Nvidia GPU 竞争的同时，Nvidia 在背后投资了一个可以设计开放架构 CPU 的公司——这是一种对冲策略。

RISC-V 过去更多用于嵌入式系统等小规模场景，但 SiFive 正在用这笔资金进军 AI 数据中心的 CPU 市场。开放架构在 AI 芯片领域的意义在于摆脱对特定供应商的依赖，这对大型科技公司来说吸引力很大。

## AI 训练数据市场升温：AfterQuery 完成 3000 万美元融资

来源：https://siliconangle.com/2026/04/10/ai-training-data-startup-afterquery-nabs-30m-investment/

旧金山 AI 数据公司 AfterQuery 完成了 3000 万美元融资，估值 3 亿美元，由 Altos Ventures 领投，Y Combinator、The Raine Group 和 BoxGroup 参投。这家成立仅 14 个月的公司声称其客户包括「所有领先的 AI 实验室」，年收入已超过 1 亿美元。

AfterQuery 的核心产品是训练数据集，但不只是简单的 prompt-response 对。他们提供每个回答背后的逐步推理过程，这对模型的泛化能力很重要。他们拥有近 10 万名开发者、律师等专业人士来生成数据，还支持多模态训练数据和定制评估套件。

这是过去一个月内第三家获得融资的 AI 数据公司。Deccan AI 在 3 月底融资 2500 万美元，Deeptune 更早几天完成 4300 万美元融资。AI 训练数据正在成为一个独立的、规模化的市场。

一个 14 个月的公司能做到 1 亿美元 ARR，说明前沿模型对高质量训练数据的需求远超预期。尤其是强化学习阶段所需的定制化数据集，几乎无法通过公开爬取获得，必须依靠人工专家团队。这个赛道的天花板可能比我们想象的要高得多。

## SQLite 3.53.0 发布，修复 WAL 损坏 bug 并新增查询结果格式化

来源：https://simonwillison.net/2026/Apr/11/sqlite/

SQLite 发布了 3.53.0 版本。由于 3.52.0 被撤回，这次更新包含了大量积累的功能改进。最引人注目的是新增的 Query Result Formatter（QRF）库，CLI 交互式会话现在默认使用 Unicode 框线字符来格式化查询结果，大幅提升了可读性。

其他改进包括：修复了一个关键的 WAL 重置导致的数据库损坏 bug；新增 SQLITE_PREPARE_FROM_DDL 选项允许虚拟表实现安全地准备从数据库 schema 派生的 SQL 语句；.indexes 命令的模式参数现在匹配索引名而非表名；新增自修复索引功能，解决表达式索引过期问题。

Simon Willison 在博客中标注了这一发布。对于每天使用 SQLite 的开发者来说，CLI 输出格式化的改善是立即可感知的体验提升。WAL 损坏 bug 的修复则避免了潜在的数据丢失风险。

## Meta 推出 Muse Spark 模型，meta.ai 聊天工具展示多模态能力

来源：https://simonwillison.net/2026/Apr/8/muse-spark/

Meta 发布了新模型 Muse Spark，并在 meta.ai 聊天界面中展示了配套的工具集。Simon Willison 注意到 meta.ai 现在具备视觉定位能力——可以分析图像、识别并标注对象、定位区域、甚至数出浣熊的胡须数量。

图像生成可能由 Meta 的 Emu 模型驱动。meta.ai 的工具集合相当强大，包括代码解释器、视觉分析等功能，都通过自定义 HTML 可视化呈现给用户。

Simon Willison 的评论很务实：工具集合虽然不错，但真正的考验是 API 开放程度——我们能否在这些模型之上构建自己的应用。Meta 一贯的做法是先在自己的平台上验证体验，再逐步开放给开发者。

## LLM 可能正在标准化人类表达方式

来源：https://news.ycombinator.com/item?id=47673541

USC 的一项研究指出，LLM 可能正在标准化人类的表达方式，并微妙地影响我们的思维方式。Hacker News 上引发了讨论。

这个话题的核心假设是：当越来越多人使用 LLM 辅助写作和思考时，输出风格的趋同会反过来塑造输入——人类的表达习惯会逐渐向模型的输出风格靠拢。这不仅仅是写作风格的问题，更深层的是思维模式的影响。

目前的研究还处于早期阶段，但这个方向值得持续关注。如果 LLM 确实在塑造人类的表达方式，那么模型训练数据的选择和多样性就变得格外重要——因为模型的输出不仅影响用户当下的使用体验，还可能对长期的认知模式产生影响。
