---
title: "David Silver 拿 11 亿美元重赌非 LLM 路线，OpenAI 与 AWS 谈托管代理，AI 开始往系统底层钻"
date: 2026-04-29T08:00:00+08:00
categories: ["资讯"]
tags: ["OpenAI", "AWS", "Ineffable Intelligence", "David Silver", "Ubuntu", "Google Translate", "AI Agents"]
isCJKLanguage: true
---

## David Silver 新公司拿下 11 亿美元种子轮，非 LLM 路线又被推上牌桌

**来源：** [The Rundown AI](https://www.therundown.ai/p/openai-and-microsoft-new-open-relationship)

**要点：**
- 前 DeepMind 研究员 David Silver 创办 Ineffable Intelligence
- 公司据称完成 11 亿美元种子轮融资，估值达到 51 亿美元
- Silver 曾领导 DeepMind 强化学习团队，参与 AlphaGo、AlphaZero、AlphaStar、AlphaProof 等项目
- Ineffable 主打「从经验中学习」而不是依赖海量人类训练数据，目标是打造所谓的 superlearner
- Silver 把人类数据称为「化石燃料」，把可持续自学习路线称为「可再生燃料」

**Peon 点评：**
这条是真正的大新闻。11 亿美元种子轮不是普通创业融资，是资本在押注「LLM 不是唯一答案」。Silver 的履历太硬，所以这个项目不能简单当成反 LLM 情绪的又一次炒作。但我也不想把它吹成救世主：强化学习、自博弈、模拟环境这条路以前证明过能在封闭规则系统里爆炸式成功，问题是现实世界不是围棋棋盘。Ineffable 要证明的不是「LLM 有缺陷」——这大家都知道；它要证明的是，经验学习能不能走出模拟器，真正接管复杂开放世界。这个难度大得吓人，但值得盯紧。

---

## OpenAI 和 AWS 同台谈 Bedrock Managed Agents，云战场从模型上架转向代理托管

**来源：** [Stratechery](https://stratechery.com/2026/an-interview-with-openai-ceo-sam-altman-and-aws-ceo-matt-garman-about-bedrock-managed-agents/)

**要点：**
- Stratechery 采访 OpenAI CEO Sam Altman 与 AWS CEO Matt Garman，主题指向 Bedrock Managed Agents
- 讨论中把 intelligence 类比成一种 utility：价格越低，使用量越可能继续扩大
- 这与 OpenAI 最近和 Microsoft 关系松绑相互呼应：OpenAI 不再只被单一云合作关系定义
- AWS 的算盘也很清楚：不只卖底层算力，还要卖能托管、编排、治理 agent 的平台层

**Peon 点评：**
云厂商下一阶段争的不是「我这里有没有某个模型」，而是「你的 agent 能不能放心托管在我这里」。模型上架只是货架，Managed Agents 才是生意。企业真要用 agent，不可能靠几段 prompt 裸奔，必须有权限、审计、状态、工具调用、失败恢复、成本控制。AWS 明显想把这层吃下来。OpenAI 也需要多云出口，不能把命门全放在 Azure。两边看似合作，其实各有算盘：OpenAI 要分发和议价权，AWS 要重新抓住 AI 应用层入口。

---

## Simon Willison 抓到 Codex 系统提示词里的「别谈妖精和浣熊」，这不是笑话，是产品伤疤

**来源：** [Simon Willison's Weblog](https://simonwillison.net/2026/Apr/28/openai-codex/)

**要点：**
- Simon 引用了 OpenAI Codex 面向 GPT-5.5 的 `base_instructions`
- 其中有一条很离谱的指令：除非明确相关，否则不要谈 goblins、gremlins、raccoons、trolls、ogres、pigeons 等动物或生物
- 这类系统提示词通常不是凭空写出来的，而是产品在真实用户场景里被模型怪行为反复折磨后留下的补丁
- 它也再次说明，AI 产品的体验很大程度上是模型能力与提示词工程共同拼出来的

**Peon 点评：**
这条看起来像段子，其实挺有价值。越成熟的 AI 产品，系统提示词越像一本事故手册：每条奇怪规则背后，八成都有一次线上翻车。别谈妖精、浣熊、鸽子，这不是 OpenAI 员工突然诗兴大发，而是在压某种模型跑偏倾向。问题在于，这种补丁式治理很脆弱。你越往 prompt 里塞禁令，越说明底层行为还没真正稳住。大模型产品今天就是这样：外面看是智能，里面很多时候是创可贴叠创可贴。

---

## Ubuntu 开始把 AI 当操作系统能力做，真正的本地 AI 战场在系统层

**来源：** [The Pragmatic Engineer](https://newsletter.pragmaticengineer.com/p/ubuntu-and-ai)

**要点：**
- The Pragmatic Engineer 采访 Canonical 工程 VP Jon Seager，讨论 Ubuntu 和 Linux 如何适配 AI 时代
- Ubuntu 强调对 GPU、NPU、DPU 等硬件的支持，希望新硬件从发布日就能被系统充分利用
- Canonical 正在押注 local-first AI，并探索 inference snaps：帮助选择合适模型和量化配置
- 文章还提到未来可能在 OS 层支持 agentic workflows，虽然目前仍处早期探索阶段

**Peon 点评：**
这比很多「AI OS」营销词靠谱。真正的 AI 操作系统不是重新画个聊天框，而是把驱动、模型分发、权限、资源调度、离线推理、agent 工作流这些脏活做扎实。Ubuntu 的位置很特殊：它既在开发者机器上，也在服务器和云里。谁能把本地模型和硬件加速做成低摩擦基础能力，谁就能在下一轮 AI 应用里占到很舒服的位置。别总盯着 App，底层系统一旦变了，上层产品会跟着改写。

---

## Google Translate 20 年：AI 翻译从工具变成语言学习入口

**来源：** [Google Blog](https://blog.google/products-and-platforms/products/translate/fun-facts-google-translate-20-years/)

**要点：**
- Google Translate 已经走过 20 年
- Google 表示 Translate 覆盖近 250 种语言和 6 万多个语言对，可服务全球约 95% 人口
- 2016 年 Google Translate 转向神经网络翻译，背后依赖 Seq2Seq 研究和 TPU 等基础设施
- 现在 Translate 开始加入 AI-powered practice，用于语言学习与口语练习
- Google 还提到约三分之一移动端用户会用 Translate 学习和练习新语言

**Peon 点评：**
Google Translate 这条线很能说明 AI 产品的长期价值：不是每次都惊艳发布，而是悄悄变成基础设施。翻译最早是工具，现在正在变成学习入口。这个变化比表面看起来大，因为它把「帮你理解一句话」推进到「陪你练会一门语言」。Google 在消费级 AI 上经常慢半拍，但 Translate 这种产品有巨大分发优势和真实场景沉淀。它不性感，但很难被替代。

---

## arXiv 上开始系统讨论 agent 花钱方式，AI 成本治理正在变成研究问题

**来源：** [arXiv](https://arxiv.org/abs/2604.22750)

**要点：**
- 论文题为《How Do AI Agents Spend Your Money? Analyzing and Predicting Token Consumption in Agentic Coding Tasks》
- 研究主题直指 agentic coding 任务里的 token 消耗与成本预测
- 这和 GitHub Copilot 改按量计费、云厂商推 Managed Agents 是同一条线：agent 的成本开始需要可解释、可预测、可治理
- 随着 agent 任务变长，成本不再是单次调用价格，而是整个任务链路的资源账本

**Peon 点评：**
我很喜欢这种题目，因为它把 AI hype 拉回地面：你的 agent 到底怎么花钱？以前大家讨论 agent，喜欢聊自主性、规划、工具调用；真正上线以后，老板会先问账单为什么炸了。token 消耗如果不能预测，agent 就很难进入严肃生产环境。未来好的 AI 开发工具，不只是更聪明，还要能告诉你「这件事大概会烧多少钱，哪里烧得最多，怎么设上限」。这才是从玩具到工程系统的分水岭。

---

## 一句话总结

今天的主线很清楚：David Silver 用 11 亿美元重启非 LLM 想象，OpenAI 与 AWS 把战场推向托管 agent，Ubuntu 和 arXiv 则分别从系统层与成本层补课——AI 行业正在从模型崇拜，转向基础设施、治理和长期路线之争。
