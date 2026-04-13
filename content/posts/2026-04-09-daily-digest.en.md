---
title: "Anthropic Launches Project Glasswing Zero-Day Scanning, Partners with Google and Broadcom for Gigawatt Compute"
date: 2026-04-09T07:30:00+08:00
categories: ["digest"]
tags: ["AI", "Anthropic", "Project Glasswing", "Google", "OpenAI", "Meta"]
---

This issue covers news from April 5 to April 8, 2026.

## Anthropic Launches Project Glasswing, Claude Mythos Discovers Thousands of Zero-Day Vulnerabilities

Source: https://www.anthropic.com/glasswing

Anthropic unveiled Project Glasswing, a security initiative developed in partnership with major tech companies. Claude Mythos Preview autonomously identified thousands of zero-day vulnerabilities across major operating systems and browsers. These capabilities will be used to detect and fix security vulnerabilities at scale. Anthropic plans to develop safeguards and broaden industry cooperation to address security challenges in the AI era.

This marks an important milestone for AI in cybersecurity. Previous security work relied primarily on manual penetration testing and rule-based engines—AI can now discover vulnerabilities autonomously, improving efficiency by an order of magnitude. The key question is whether this capability could be misused maliciously. Anthropic's choice to open-source part of this capability in exchange for industry cooperation is a delicate balance to strike.

## Anthropic Partners with Google and Broadcom for Multiple Gigawatts of Next-Generation Compute

Source: https://www.anthropic.com/news/google-broadcom-partnership-compute

Anthropic has signed an agreement with Google and Broadcom for multiple gigawatts of next-generation TPU capacity, expected to come online starting in 2027. This capacity is necessary to serve Anthropic's exponential user growth and will enable Claude to define the frontier of AI development. The vast majority of the new compute will be sited in the United States.

This signals a new phase in the AI compute arms race. Google's TPUs combined with Broadcom's chip design expertise and Anthropic's models directly targets the Microsoft + OpenAI compute alliance. While 2027 may seem distant, the timeline is reasonable given data center construction cycles.

## OpenAI Tests Next-Generation Image V2 Model

Source: https://www.testingcatalog.com/openai-tests-next-gen-image-v2-model-on-chatgpt-and-lm-arena/

OpenAI is testing its next-generation Image V2 model on ChatGPT and LM Arena, offering three variants for evaluation. Early tests show improvements in UI design rendering, prompt adherence, and compositional understanding. The test results will influence OpenAI's competitive position against Google in the image generation space.

The image generation赛道 is becoming increasingly crowded. With OpenAI's Sora not yet widely available and Google having the Veo series, Image V2 adds another contender. The key variable is whether this will be opened to developers via API or continue along the conservative Playground-only approach.

## Google Develops Jules V2, Coding Agent Capable of Managing Higher-Level Goals

Source: https://www.testingcatalog.com/google-prepares-jules-v2-agent-capable-of-taking-bigger-tasks/

Google is developing Jules V2 (codenamed Jitro), a coding agent designed to autonomously manage high-level development goals rather than specific tasks. Launching via waitlist, it aims to redefine AI software development by shifting focus from task-based commands to KPI-driven outcomes. This approach may benefit teams handling large codebases, but faces challenges of unpredictable changes and trust issues.

The shift from "executing specific tasks" to "managing higher-level goals" represents an important paradigm leap for AI programming agents. The difficulty lies not in technology, but in how humans learn to trust AI's architectural decisions.

## Zhipu GLM-5.1 Achieves SOTA on SWE-Bench Pro

Source: https://z.ai/blog/glm-5.1

Zhipu released GLM-5.1, its flagship model for agentic engineering. The model achieves state-of-the-art performance on SWE-Bench Pro. Built to stay effective on agent tasks over much longer horizons than previous generations, it can sustain optimization over hundreds of rounds and thousands of tool calls. The model breaks complex problems down, runs experiments, reads results, and identifies blockers with real precision.

Chinese AI companies are catching up in the agent赛道. GLM-5.1's long-horizon task capability is a differentiator—most models "lose their way" on complex tasks, and maintaining contextual coherence is the key.

## Meta Will Open-Source Some New Models

Source: https://sherwood.news/tech/report-some-of-metas-new-ai-models-will-eventually-be-open-source/

Meta is close to releasing new AI models, with some to be eventually released under an open-source license. Meta plans to focus on the consumer market rather than enterprise. The company previously embraced open-source AI with its Llama models, and CEO Mark Zuckerberg has written a manifesto declaring open-source AI as the future. The company will pursue a hybrid strategy of proprietary and open-source models going forward.

Llama 4 should be coming soon. The hybrid strategy signals Meta's intent to please both the open-source community and enterprise market. This puts indirect pressure on Anthropic and OpenAI—the higher the quality of open-source models, the harder it becomes to justify paying for proprietary alternatives.

## Cursor Releases Warp Decode, MoE Inference Throughput Improved 1.8x

Source: https://cursor.com/blog/warp-decode

Cursor's Warp Decode is a kernel design that reorganizes MoE (Mixture of Experts) inference around output neurons instead of experts. It achieves approximately 1.8x higher throughput and improved numerical accuracy on Blackwell GPUs.

The inference efficiency war is heating up. Anthropic optimizes through model architecture, OpenAI through large-scale deployment, Cursor through low-level system optimization—different companies are attacking the problem at different layers. For end users, this means better experiences and lower costs.