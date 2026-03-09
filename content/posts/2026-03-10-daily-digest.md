---
title: "📰 每日资讯 | 2026-03-10"
date: 2026-03-10T07:30:00+08:00
categories: ["digest"]
tags: ["OpenAI", "Anthropic", "Simon Willison", "AI 安全", "开发工具", "基础设施", "开源"]
---

本期涵盖 03-08 ～ 03-10 的资讯。

这期有几条挺值得看：一条是 OpenAI 往 AI 安全工具链继续下沉；一条是 Anthropic 把 benchmark 里那些平时没人愿意细讲的「基础设施噪声」摊开讲明白了；还有一条来自 Simon Willison，属于数据库工程师看了会立刻想动手试的那种文章。

## OpenAI：收购 Promptfoo，把 AI 安全评测往产品栈里收

来源：OpenAI News  
链接：https://openai.com/index/openai-to-acquire-promptfoo

要点：
- OpenAI 宣布将收购 Promptfoo，这是一套面向企业的 AI 安全平台。
- Promptfoo 的核心价值不在「又一个 eval 工具」，而在于它把提示词攻击、越权输出、策略绕过这类问题，提前放进开发阶段排查。
- 这说明头部模型公司已经不满足于只卖模型本身，而是开始把安全评测、上线前验证、风险修复一起打包。
- 对企业来说，这种能力越早内建，后面接入 agent、工具调用、外部知识库时踩坑越少。

我的看法：
这件事比表面上更重要。过去很多团队把 AI 安全当成上线前补作业，现在看，大厂的判断是：安全评测本身就是产品的一部分。谁能把 red teaming、policy 检查、回归测试做成默认流程，谁就更像是下一代 AI 基础设施。

## Anthropic：agentic coding benchmark 的分数，可能先输在机器配置上

来源：Anthropic Engineering  
链接：https://www.anthropic.com/engineering/infrastructure-noise

要点：
- Anthropic 研究了 agentic coding eval 在不同资源配置下的表现，发现 CPU、RAM 和容器限制会明显影响分数。
- 在 Terminal-Bench 2.0 上，资源从严格限制放宽到 uncapped，基础设施导致的失败率从 5.8% 降到 0.5%。
- 更关键的是，资源给多了以后，模型不只是「少崩一点」，而是真的能尝试更多原本跑不动的解法，成绩也会继续上升。
- 这意味着 leaderboard 上差几个百分点，未必全是模型能力差异，也可能是 runtime 条件不同。

我的看法：
这篇很扎实，也很戳行业痛点。现在大家太爱拿 benchmark 排名当绝对坐标，但 agentic eval 天生就是端到端系统测试，环境一变，分数就会飘。以后再看这类榜单，我会更在意 harness、资源配额、超时和并发设置，而不是只盯模型名。

## Simon Willison：不用拷生产数据，也能在本地复现生产环境的 query plan

来源：Simon Willison  
链接：https://simonwillison.net/2026/Mar/9/production-query-plans-without-production-data/

要点：
- PostgreSQL 18 新增了 `pg_restore_relation_stats()` 和 `pg_restore_attribute_stats()`，可以把生产环境的统计信息复制到开发环境。
- 这样做不需要同步海量真实数据，却能让 query planner 更接近线上决策。
- 文章里的例子很直观：同一列如果 95% 都是 `delivered`，数据库就会对不同过滤条件选出不同执行计划。
- Simon 还顺手提到，SQLite 其实早就能通过 `sqlite_stat1`、`sqlite_stat4` 走类似思路。

我的看法：
这就是典型的「不炸裂，但真有用」。很多团队调慢查询时最痛苦的不是不知道怎么优化，而是本地根本复现不了线上 planner 的判断。现在 PostgreSQL 把统计信息复制这条路正式铺平，排查性能问题会现实很多。Simon 这种文章的价值就在这儿：不喊口号，直接给你一个能落地的工程思路。

## OpenAI 风波继续：机器人负责人因 Pentagon 合作离职

来源：The Rundown AI  
链接：https://www.therundown.ai/p/openai-robotics-lead-exits-over-pentagon-deal

要点：
- The Rundown 报道，OpenAI 机器人方向负责人 Caitlin Kalinowski 因 Pentagon 合作争议离职。
- 她公开提到，问题不在团队，而在于相关决策推进得太快，AI 监控和 lethal autonomy 的 guardrails 还没定义清楚。
- 这是这轮争议里第一位公开因原则离开的高级别负责人，象征意义不小。
- 事件也说明，AI 公司的军工合作一旦越过公众和员工的心理线，舆论与组织层面的反噬会同时出现。

我的看法：
这条新闻让我更在意组织治理，而不是公关表态。AI 公司只要开始碰国防、监控、自动化武力这些边界议题，外部争议其实还是第二层，真正难的是内部能不能建立一套让核心人员也愿意相信的约束机制。不然，技术能力越强，内部撕裂只会越快。

## ByteByteGo：2026 年最值得关注的一批 AI GitHub 项目

来源：ByteByteGo  
链接：https://blog.bytebytego.com/p/top-ai-github-repositories-in-2026

要点：
- ByteByteGo 盘点了 2026 年 GitHub 上增长最快、影响力最大的 AI 项目。
- 文章提到，GitHub 上 AI 相关仓库已超过 430 万个，LLM 项目同比增长 178%。
- 这一轮受关注的，不只是模型本身，还包括 workflow、local AI、agent orchestration 和低代码编排工具。
- 从趋势看，开发者正在把重心从「哪个模型更强」转向「怎样把模型接进真实工作流」。

我的看法：
开源圈现在已经很明显：单点模型能力不再是唯一焦点，真正持续长出来的是围绕模型的「操作系统层」。谁能把本地运行、权限控制、自动化流程、上下文管理这些基础活做好，谁就更可能成为下一波默认底座。

## Lenny’s Newsletter：Applied Intuition 为何能低调长成 150 亿美元公司

来源：Lenny’s Newsletter  
链接：https://www.lennysnewsletter.com/p/the-most-successful-ai-company-youve-never-heard-of

要点：
- Qasar Younis 在访谈里谈到，Applied Intuition 长期保持低曝光，却做成了一家估值 150 亿美元的 AI 公司。
- 他的核心判断是，真正大的 AI 机会未必先发生在软件里，而会更早落到矿业、农业、建筑、卡车运输这类物理世界行业。
- 公司内部强调速度、跟进和不让客户失望，这套文化比「讲愿景」更重要。
- 他还提到，很多最成功的公司在很早阶段就会露出牵引力，只是外界未必注意到。

我的看法：
我挺认同这个判断。过去一年大家讨论 AI，太容易被聊天产品和 coding agent 吸走注意力，但真正能吃下大市场的，往往是那些把 AI 塞进复杂、脏、慢、重的现实行业里的公司。软件世界热闹，物理世界才真是难啃也最值钱。
