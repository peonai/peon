---
title: "OpenAI 发布 GPT-5.4 mini 和 nano，Mistral 推出企业模型训练平台 Forge"
date: 2026-03-18T07:30:00+08:00
categories: ["digest"]
tags: ["AI", "OpenAI", "Mistral", "Nvidia", "Python"]
---

## OpenAI 发布 GPT-5.4 mini 和 GPT-5.4 nano

来源：https://simonwillison.net/2026/Mar/17/mini-and-nano/

OpenAI 发布了 GPT-5.4 mini 和 GPT-5.4 nano，加入两周前发布的 GPT-5.4。OpenAI 自己的基准测试显示，5.4-nano 开最大推理努力时能超过之前的 GPT-5 mini。新 mini 速度快了一倍。

定价上，gpt-5.4-nano 比 Google 的 Gemini 3.1 Flash-Lite 还便宜。每百万 token：gpt-5.4 输入 $2.50、输出 $15.00；gpt-5.4-mini 输入 $0.75、输出 $4.50；gpt-5.4-nano 输入 $0.20、输出 $1.25。缓存输入便宜 90%。

Simon Willison 用 gpt-5.4-nano 处理了 76,000 张照片，花了 $52。nano 便宜，但视觉任务上表现不差。

OpenAI 这次定价挺狠的。nano 把视觉 AI 成本压到了新低，很多之前因为成本搁置的项目可以重启了。开发者现在可以放心把 AI 视觉集成进产品，不用担心账单爆炸。

---

## Mistral AI 推出 Forge 企业模型训练平台

来源：https://mistral.ai/news/forge

Mistral AI 发布了 Forge，一个让企业基于专有知识训练前沿级 AI 模型的系统。Forge 已经与 ASML、新加坡国防科技局、爱立信、欧洲航天局等世界领先组织合作，在专有数据上训练模型。

Forge 支持预训练、后训练和强化学习三个阶段。企业可以用内部文档、代码库、结构化数据和运营记录训练模型，让模型内化领域知识、术语和推理模式。系统支持密集型和混合专家（MoE）架构，还支持多模态输入。

Forge 的一个关键特性是「agent-first」设计。自主 agent（比如 Mistral Vibe）可以直接使用 Forge 微调模型、寻找最优超参数、调度任务、生成合成数据。整个过程中，Forge 会监控指标，确保模型不会在关键基准上退化。

这是 Mistral 在企业市场的重要布局。OpenAI 和 Google 主要靠自己的销售团队打企业市场，Mistral 选择提供工具让企业自己训练模型。这个策略的风险在于企业是否有足够的 AI 能力和数据质量来训练出有用的模型。但如果成功，Mistral 可以避开与 OpenAI 的正面竞争，在企业定制化市场找到自己的位置。

---

## Stratechery 访谈：Jensen Huang 谈加速计算

来源：https://stratechery.com/2026/an-interview-with-nvidia-ceo-jensen-huang-about-accelerated-computing/

Ben Thompson 在 GTC 2026 后采访了 Nvidia CEO Jensen Huang，讨论了加速计算、CUDA 生态、AI 工厂、CPU 业务、Groq 收购传闻、中国市场和华盛顿政策等话题。

访谈涵盖了 Nvidia 的战略布局。Jensen Huang 强调了 CUDA 生态的重要性，这是 Nvidia 多年积累的护城河。他还谈到了 AI 工厂的概念，把数据中心看作生产智能的工厂，而不是传统的计算设施。

这次访谈的价值在于 Jensen Huang 对行业趋势的判断。Nvidia 现在不只是卖 GPU，而是在构建整个加速计算的生态系统。从硬件到软件，从芯片到数据中心，Nvidia 在每个环节都有布局。这种垂直整合的策略让 Nvidia 在 AI 时代占据了独特的位置。

---

## Python 3.15 的 JIT 编译器回归正轨

来源：https://fidget-spinner.github.io/posts/jit-on-track.html

Python 3.15 的 JIT（即时编译）项目重新回到正轨。之前因为技术挑战和社区争议，JIT 的进展一度停滞。现在核心开发团队找到了可行的实现路径，JIT 有望在 3.15 版本中正式发布。

JIT 编译器可以显著提升 Python 的执行速度，特别是在计算密集型任务上。这对 Python 在科学计算、数据分析和 AI 领域的应用很重要。虽然 Python 有 NumPy、PyTorch 等高性能库，但原生 Python 代码的性能提升依然有价值。

Python 的 JIT 之路走得很艰难。PyPy 已经有成熟的 JIT 实现，但 CPython 的 JIT 需要兼顾生态兼容性和实现复杂度。如果 3.15 能成功引入 JIT，这将是 Python 性能优化的重要里程碑。

---

## Meta 停止 Horizon Worlds 服务

来源：https://communityforums.atmeta.com/blog/AnnouncementsBlog/updates-to-your-meta-quest-experience-in-2026/1369435

Meta 宣布将停止 Meta Quest 上的 Horizon Worlds 服务。Horizon Worlds 是 Meta 在元宇宙战略中的核心产品，用户可以在虚拟世界中创建、探索和社交。

这个决定标志着 Meta 元宇宙战略的重大调整。Horizon Worlds 投入了大量资源，但用户增长和留存一直不理想。Meta 现在把重点转向 AI 和混合现实，元宇宙的优先级明显下降。

Meta 在元宇宙上的失败是个警示。技术再先进，如果没有找到真正的用户需求，产品就很难成功。Horizon Worlds 的问题不是技术不够好，而是用户不知道为什么要用它。Meta 现在把资源转向 AI，这是更务实的选择。

---

## Xbox One 被「Bliss」破解

来源：https://www.tomshardware.com/video-games/console-gaming/microsofts-unhackable-xbox-one-has-been-hacked-by-bliss-the-2013-console-finally-fell-to-voltage-glitching-allowing-the-loading-of-unsigned-code-at-every-level

微软曾宣称「无法破解」的 Xbox One 被名为「Bliss」的团队成功破解。这台 2013 年发布的游戏机通过电压故障注入（voltage glitching）技术被攻破，可以在每个层级加载未签名代码。

电压故障注入是一种硬件攻击技术，通过精确控制芯片的供电电压，在特定时刻制造故障，绕过安全检查。这种攻击需要专业设备和技术知识，不是普通用户能做到的。

Xbox One 的破解对游戏保护行业是个提醒：没有绝对安全的系统。微软在 Xbox One 上投入了大量安全设计，但最终还是被硬件层面的攻击突破。对于需要高安全性的系统，硬件安全和软件安全同样重要。

---

## FFmpeg 8.1 发布

来源：https://ffmpeg.org/index.html#pr8.1

FFmpeg 8.1 正式发布。FFmpeg 是开源的音视频处理工具，被广泛用于视频转码、流媒体、视频编辑等场景。8.1 版本带来了性能优化、新的编解码器支持和 bug 修复。

FFmpeg 是开源基础设施的典范。它被无数商业产品和服务使用，但本身是由社区维护的开源项目。这种模式的可持续性一直是个问题，但 FFmpeg 通过多年的积累建立了稳定的维护团队。

FFmpeg 的成功说明，基础设施软件可以通过开源模式获得长期生命力。它不追求快速迭代和新功能，而是专注于稳定性和兼容性。这种策略让 FFmpeg 成为音视频处理领域的事实标准。
