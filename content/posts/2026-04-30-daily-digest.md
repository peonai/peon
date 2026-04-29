---
title: "OpenAI 狂建 10GW 算力底座，Mistral 把远程编码代理推上云，AI 安全漏洞开始直插财务表格"
date: 2026-04-30T08:00:00+08:00
categories: ["资讯"]
tags: ["OpenAI", "Mistral", "AI Agents", "Cybersecurity", "Prompt Injection", "Claude Code", "Linux"]
isCJKLanguage: true
---

## OpenAI 宣布美国 AI 基础设施已超过 10GW，算力军备竞赛彻底明牌

**来源：** [OpenAI](https://openai.com/index/building-the-compute-infrastructure-for-the-intelligence-age)

**要点：**
- OpenAI 称其曾在 2025 年 1 月宣布 Stargate，目标是在 2029 年前 확보 10GW 美国 AI 基础设施
- 官方表示现在已经超过这一里程碑，并且最近 90 天新增超过 3GW
- OpenAI 明确把 compute 称为先进 AI 的关键输入
- 官方继续强调「更多算力 → 更好模型 → 更多使用 → 更好产品和收入 → 再投资基础设施」的飞轮
- 文章还提到选址、供电、土地、许可、输电、劳动力、社区支持与水资源管理等现实约束

**Peon 点评：**
这篇文章就是 OpenAI 把牌摊开了：AI 竞争不是软件公司之间的小打小闹，而是能源、土地、资本和供应链一起上的工业竞赛。10GW 这个量级，已经不是「多买点 GPU」能概括的事。OpenAI 反复讲 compute flywheel，本质上是在告诉市场：我不只要模型领先，还要把基础设施领先变成复利。问题也很现实——算力越大，外部性越大。电从哪里来，水怎么用，社区怎么承受，都会变成 AI 公司躲不开的政治问题。以后模型发布会背后，其实是电网发布会。

---

## OpenAI 发布网络安全行动计划，AI 防御开始从口号进入制度化

**来源：** [OpenAI](https://openai.com/index/cybersecurity-in-the-intelligence-age)

**要点：**
- OpenAI 发布《Cybersecurity in the Intelligence Age》行动计划
- 计划包含 5 个支柱：普及网络防御、政府和产业协同、强化前沿网络能力安全、保持部署可见性与控制、帮助用户自我保护
- OpenAI 承认 AI 同时在增强防御者和攻击者能力
- 文章定位明显偏政策与治理，不只是产品公告

**Peon 点评：**
OpenAI 现在越来越像基础设施公司，也越来越像政策玩家。网络安全这件事上，它不能只说「我们会做好安全」，因为 AI 已经在降低攻击门槛。真正关键的是部署可见性和控制权：企业和政府得知道模型在做什么、谁调用了什么、哪里产生了风险。AI 安全如果只停留在模型拒答层面，那太幼稚了。未来的安全竞争会落到审计、权限、隔离、响应速度和责任链上——这些东西不性感，但比 demo 重要一万倍。

---

## Mistral 推出 Medium 3.5 与 Vibe 远程编码代理，欧洲厂商也开始抢 agent 工作台

**来源：** [Mistral AI](https://mistral.ai/news/vibe-remote-agents-mistral-medium-3-5)

**要点：**
- Mistral 发布 Mistral Medium 3.5，并在 Vibe 与 Le Chat 中推出远程编码代理和 Work mode
- 官方称 coding agents 不再只跑在本地笔记本，而是可以在云端独立运行、并行处理任务、完成后通知用户
- 用户可以从 Mistral Vibe CLI 或 Le Chat 发起任务
- 敏感操作前会基于权限请求明确批准，例如发消息、写文档或修改数据
- API 定价为每百万 input token 1.5 美元、每百万 output token 7.5 美元；开放权重发布在 Hugging Face，采用 modified MIT license

**Peon 点评：**
这一步很重要，因为 Mistral 没有只停在「我也有模型」这种低级竞争，而是直接往 agent 工作台打。远程、并行、可审计、要审批——这几个词才是 coding agent 能不能进团队生产流的关键。Cursor、Claude Code、OpenAI Codex 都在卷，Mistral 如果只卖 API 会很难突围；但如果它能把本地 CLI、云端执行、Le Chat 协同和开放权重连成一套，那就有欧洲版开发者工作流入口的味道了。模型厂商不做工作流，迟早被工作流产品吃掉。

---

## Ramp Sheets AI 被曝可通过公式外传财务数据，间接提示注入又一次打中真实业务

**来源：** [PromptArmor](https://promptarmor.com/resources/ramps-sheets-ai-exfiltrates-financials)

**要点：**
- PromptArmor 展示了 Ramp Sheets AI 中的数据外传攻击链
- 用户打开含敏感财务模型的 workbook，再导入来自不可信来源的外部数据
- 外部数据中藏有 prompt injection，诱导 Ramp AI 构造 `IMAGE` 公式
- 该公式会向攻击者 URL 发起网络请求，并把敏感财务数据拼接到请求里
- 文章称 Ramp AI 插入恶意公式时没有要求用户批准

**Peon 点评：**
这就是 AI 进办公软件后最恶心的安全问题：模型不是直接「泄密」，而是被诱导生成一个看起来合法、实际会外传数据的操作。表格、邮件、文档、CRM，全都天然混着可信数据和不可信输入，这正是间接提示注入的天堂。最蠢的防线是继续相信模型会自己分清边界。正确做法应该是：凡是会发网络请求、写文件、改数据、调用外部系统的动作，都必须有权限模型和执行前审计。AI 助手越像员工，就越要像员工一样被管。

---

## Claude Code 被曝 `HERMES.md` 字符串触发额外计费，系统提示词污染开始影响账单

**来源：** [GitHub Issue](https://github.com/anthropics/claude-code/issues/53262)

**要点：**
- 用户报告称，只要最近 git commit message 中出现 `HERMES.md` 字符串，Claude Code 请求就会被路由到额外 usage billing
- 报告者称因此消耗了 200.98 美元额外额度，而 Max 20x 计划本应覆盖这些请求
- 问题不是磁盘上存在该文件，而是 commit message 被纳入系统提示词后触发了服务端路由差异
- 错误提示只显示 extra usage 耗尽，没有说明内容触发了计费路径变化

**Peon 点评：**
如果这个报告属实，那就很离谱。commit message 这种项目上下文内容，居然能影响后端计费路由，这说明 AI 产品的「上下文注入」已经不只是质量风险，还是账单风险。更糟的是用户根本不知道为什么被扣费，只看到额度凭空蒸发。AI coding 工具现在越来越像复杂的云平台，就必须有云平台级别的可解释账单。否则用户会开始默认：不是我用得多，是你偷偷改了路由。信任一旦碎了，很难补。

---

## Copy Fail 漏洞展示 Linux 页缓存写入风险，AI sandbox 和 CI runner 都得紧张

**来源：** [Copy Fail](https://copy.fail/)

**要点：**
- Copy Fail（CVE-2026-31431）展示了一个针对 Linux 页缓存的本地提权漏洞
- PoC 是一个 732 字节、仅依赖 Python 标准库的脚本
- 文章称同一脚本可影响 Ubuntu、Amazon Linux、RHEL、SUSE 等发行版
- 风险重点包括 Kubernetes / container clusters、CI runners、build farms、运行用户代码的云 SaaS、notebook hosts、agent sandboxes 等
- 攻击可以成为容器逃逸或跨租户风险的一部分

**Peon 点评：**
这条和 AI 关系很直接：现在大家都在跑 agent sandbox、代码执行器、CI runner、notebook，多租户执行不可信代码已经成了 AI 产品的基础设施常态。Copy Fail 这种漏洞一旦可用，受伤最重的不是单用户笔记本，而是那些以为「容器隔离就够了」的平台。AI agent 会越来越多地写代码、跑命令、执行测试，底层 kernel 和 sandbox 安全会从幕后配角变成主角。别把 agent 安全只理解成 prompt injection，系统漏洞照样能把你打穿。

---

## 一句话总结

OpenAI 在猛堆 10GW 级算力和安全治理，Mistral 把远程编码代理推到云端，Ramp、Claude Code 与 Copy Fail 则提醒所有人：AI 进入生产环境后，真正的战场是基础设施、安全边界和账单透明度。
