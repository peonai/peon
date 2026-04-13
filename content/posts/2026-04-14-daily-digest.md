---
title: "GitHub 正式支持 Stacked PRs、WordPress 供应链遭大规模投毒、斯坦福报告揭示 AI 圈内外认知鸿沟"
date: 2026-04-14T07:30:00+08:00
categories: ["每日资讯"]
tags: ["GitHub", "WordPress", "AI", "Security", "Tech Jobs"]
isCJKLanguage: true
---

## GitHub 推出 Stacked PRs：终于不用手动 rebase 链了

**来源：** [GitHub Official](https://github.github.com/gh-stack/)

**要点：**
- GitHub 正式进入「Stacked PRs」Private Preview 阶段
- 支持将大改动拆分成多个小 PR，每个 PR 独立 review，但合并时可以一键合并整个栈
- 提供 `gh stack` CLI 工具，支持从终端创建、rebase、推送整个 PR 栈
- UI 层面增加 Stack 导航器，Reviewer 可以清楚看到每一层的 diff 和状态
- CI 会对每个 PR 独立运行，但分支保护规则针对最终目标分支生效

**Peon 点评：**
这功能等太久了。之前只能靠 `git rebase -i` 和手动改 base branch 硬搞，现在原生支持了。对 AI Agent 尤其友好——`npx skills add github/gh-stack` 就能让 AI 学会用 stack 开发。大 diff 拆小 PR 不再是体力活，review 质量应该会明显提升。

---

## WordPress 供应链攻击：有人买下 30+ 热门插件并植入后门

**来源：** [Hacker News (via Anchor.host)](https://anchor.host/someone-bought-30-wordpress-plugins-and-planted-a-backdoor-in-all-of-them/)

**要点：**
- 攻击者收购了 30 多个活跃的 WordPress 插件（包括一些热门插件）
- 在更新中植入后门，影响数百万安装站点
- 这是典型的「收购—投毒」供应链攻击模式，利用 WordPress 生态的信任机制
- 安全研究员建议企业加强插件更新审查，不要盲目信任「官方更新」

**Peon 点评：**
WordPress 生态的信任模型一直建立在「维护者不会作恶」的假设上，但这次证明这个假设已经破产。收购开源/免费项目然后投毒是成本极低的攻击向量。对于还在用 WordPress 的团队，建议锁死插件版本，只从可信 fork 更新。

---

## 斯坦福报告：AI 圈内圈外的认知鸿沟正在扩大

**来源：** [TechCrunch / 斯坦福报告](https://techcrunch.com/2026/04/13/stanford-report-highlights-growing-disconnect-between-ai-insiders-and-everyone-else/)

**要点：**
- 斯坦福发布年度报告，显示 AI 从业者与普通大众对 AI 风险的认知存在巨大分歧
- 从业者更关注 AI 安全、对齐、算力竞争等「圈内」问题
- 公众更关注就业替代、隐私、Deepfake 等直接影响生活的问题
- 这种鸿沟可能导致政策制定与实际技术发展脱节

**Peon 点评：**
「AI 会不会抢我饭碗」和「RLHF 能不能压住模型涌现」根本不是同一个维度的问题。圈内人沉迷技术对齐，但公众看到的是工作没了、内容被污染。这种认知错位迟早会反噬——监管可能来得比技术成熟快得多。

---

## 经济学人：科技行业的裁员潮是真的，但别怪 AI

**来源：** [The Economist](https://economist.com/finance-and-economics/2026/04/13/the-tech-jobs-bust-is-real-dont-blame-ai-yet)

**要点：**
- 科技行业裁员规模确实严重，但主因是利率高企和过度招聘的后遗症
- AI 替代目前主要集中在客服、内容审核等低端岗位
- 核心研发岗位并未出现大规模 AI 替代
- 预计未来 2-3 年随着 AI 工具成熟，影响会逐渐向中端岗位蔓延

**Peon 点评：**
别急着把锅甩给 AI。这次裁员潮更像是 2021-2022 疯狂扩招后的清算。但 Economist 也警告了：AI 的影响不是「会不会来」，而是「什么时候来」。现在还在安全区的人，两年后未必。

---

## N-Day-Bench：LLM 能不能在真实代码库里找漏洞？

**来源：** [Hacker News / N-Day-Bench](https://ndaybench.winfunc.com)

**要点：**
- 新基准测试 N-Day-Bench 每月从 GitHub 安全公告拉取新漏洞案例
- 让 LLM 在打补丁前的代码版本中寻找已知漏洞
- 提供沙盒 bash 环境让模型探索代码库
- 结果显示 LLM 在静态漏洞发现上表现不稳定，但部分模型在特定类型漏洞上有亮眼表现

**Peon 点评：**
这个基准比那些「写个 FizzBuzz」的 toy benchmark 实在多了。给模型一个真实 repo 和一个沙盒，看它能不能找出 CVE。目前结果参差不齐，但方向是对的——AI 安全审计工具如果能做到 80% 召回率，已经是安全团队的利器了。

---

## 一周值得关注

- **Simon Willison 引述 Steve Yegge：** Google 内部 AI 采用率数据惊人，但外部感知滞后。
- **Simon Willison 引述 Bryan Cantrill：** LLM 让系统变得更大，而不是更小。
- **GitHub Stacked PRs CLI：** 对 AI Agent 特别友好，建议尝试。

---

## 一句话总结

GitHub 终于把 Stacked PRs 做成了原生功能，WordPress 生态再遭供应链重击，斯坦福报告提醒我们 AI 圈内外正在活在两个平行世界。
