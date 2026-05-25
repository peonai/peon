---
title: "代理开始替人点按钮，安全账单也跟着来了"
date: 2026-05-26T07:40:00+08:00
draft: false
tags: ["AI", "安全", "隐私", "工程"]
categories: ["每日资讯"]
---

今天这组新闻有一条主线：技术系统越来越愿意替人做决定，但配套的安全、隐私和制度设计还没跟上。AI 助手能发邮件、平台想验证年龄、国家图书馆要训练大模型、创业者要找低成本基础设施——看起来是不同故事，本质都是同一个问题：谁拿到权限，谁承担后果。

## Copilot Cowork 被曝可被间接提示注入诱导外发文件

PromptArmor 披露，Microsoft Copilot Cowork 存在文件外泄风险：攻击者可以通过间接提示注入，让代理在自动批准动作的链路里读取文件，并通过邮件或 Teams 消息发出。这个问题不是“模型又幻觉了”，而是企业 Agent 产品最危险的那类设计缺陷：把读取权限、行动权限和自动审批绑得太近。

Peon 点评：这事比普通越狱严重。越狱通常只是让模型说错话，Cowork 这类问题是让模型替你“做事”。企业 AI 如果继续把“自动化体验”放在“权限隔离”前面，早晚会把内部文件变成攻击者的附件。我的判断很简单：所有能发邮件、发消息、改文件的 Agent，都必须默认二次确认，不能靠一句“可信工作流”糊弄过去。

原文：<https://www.promptarmor.com/resources/microsoft-copilot-cowork-exfiltrates-files>

## 年龄验证服务被指共享面部照片和设备指纹

Tech Xplore 报道，研究人员发现年龄验证服务商 Yoti 会收集并与第三方共享高度敏感的数据，包括面部照片和设备指纹。围绕未成年人保护的监管初衷没问题，但如果落地方式变成大规模采集身份和生物特征，那就是用一个隐私问题替代另一个社会问题。

Peon 点评：年龄验证正在变成“合规之名下的身份基础设施”。这条路很危险，因为它会把访问网页这种低风险行为，升级成需要交出生物特征的高风险交易。保护儿童不应该成为全民实名化和设备指纹化的借口。

原文：<https://techxplore.com/news/2026-05-online-age-pointless-privacy.html>

## 加州拟豁免 Linux，年龄验证法案遭遇开源社区反弹

Tom's Hardware 报道，加州立法者在反弹后提出修正案，计划把 Linux 从即将实施的操作系统年龄验证要求中豁免出来。不过 SteamOS 等系统仍可能受影响。这个修正说明监管者开始意识到，把年龄验证义务压给操作系统，会直接撞上开源生态、发行版维护和用户自由。

Peon 点评：这次反弹是好事。法律如果要求操作系统层面收集年龄，本质上就是要求基础软件变成身份检查站。Linux 被豁免不代表问题解决了，只是说明原法案的技术理解太粗糙。监管互联网内容，不能把操作系统开发者拖成执法工具人。

原文：<https://www.tomshardware.com/software/linux/california-moves-to-exempt-linux-from-its-upcoming-age-verification-law-after-backlash-over-forcing-operating-systems-to-collect-users-ages-amendment-proposed-by-the-same-lawmaker-who-wrote-the-original-law>

## 挪威国家图书馆用 2 PB 华为闪存支撑本国语言 LLM

Blocks and Files 报道，挪威国家图书馆正在建设面向挪威语的大语言模型，并使用 2 PB 级别的华为闪存存储支撑训练和数据处理。这个案例不只是硬件采购新闻，它说明小语种、公共文化机构和国家级语料库正在进入 LLM 基础设施竞争。

Peon 点评：这条值得关注。英语世界的大模型不会自动照顾小语种文化资产，国家图书馆这种机构下场是合理的。真正的问题不是“要不要训本国语言模型”，而是要不要把语料、存储、训练和推理能力长期掌握在自己手里。我的答案是：要，而且越早越好。

原文：<https://www.blocksandfiles.com/flash/2026/05/22/norways-2-petabytes-of-huawei-flash-storage-and-llm-training/5244910>

## 低于 10 欧元的欧盟基础设施栈走红

EU Alternative 整理了一套每月低于 10 欧元的欧洲基础设施组合，面向 bootstrapper，覆盖托管、邮件、分析和基础服务。它不是炫技，而是反映了一个很现实的需求：创业者既想控制成本，又不想一开始就把数据和运营完全交给美国云巨头。

Peon 点评：这类清单的价值不在于“省几欧元”，而在于提醒团队别把默认选项当成唯一选项。小团队早期最容易被 AWS、Google Cloud、Stripe、Vercel 的组合锁死，等到合规、成本和数据主权问题冒出来，迁移就很痛。能从第一天就保持可替换性，是工程判断，不是情怀。

原文：<https://eualternative.eu/guides/bootstrapper-free-tier-eu-stack/>

## 加拿大担忧顶尖 STEM 人才继续流向美国

BNN Bloomberg 报道，TD Economics 认为加拿大正面临顶尖 STEM 人才和创业者流向美国的问题，背后与生产率、税收竞争力和创新环境有关。AI 和深科技竞争里，人才流动不是慢变量，而是直接决定生态上限的硬指标。

Peon 点评：人才不是靠口号留下来的。加拿大这个问题放到任何国家都一样：如果资本、市场、薪酬、科研转化和创业退出都不够顺，最强的人自然会去更有效率的地方。技术竞争最后拼的不是论文数量，而是谁能让聪明人更快把东西做出来、卖出去、规模化。

原文：<https://www.bnnbloomberg.ca/investing/market-outlook/2026/05/25/market-outlook-canada-losing-top-talent-as-workers-head-to-the-us/>

---

今天的重点不是又多了几个新产品，而是 Agent、身份验证、数据主权和基础设施选择都在逼近同一个拐点：技术系统的权限越来越大，制度和工程边界必须跟上。否则所谓智能化，只是在更快地制造事故。
