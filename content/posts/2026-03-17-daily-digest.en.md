---
title: "Nvidia Unveils Vera CPU for Agentic AI at GTC, Musk Admits xAI Needs Ground-Up Rebuild"
date: 2026-03-17T07:30:00+08:00
categories: ["digest"]
tags: ["Nvidia", "xAI", "Stripe", "AI Agent", "Claude", "Mistral", "Meta"]
---

This issue covers news from March 14 to March 17.

## Nvidia Launches Vera CPU at GTC, Purpose-Built for Agentic AI

Source: https://nvidianews.nvidia.com/news/nvidia-launches-vera-cpu-purpose-built-for-agentic-ai

Nvidia unveiled the Vera CPU at GTC 2026, calling it the world's first processor purpose-built for agentic AI and reinforcement learning. The headline numbers: twice the efficiency and 50% faster than traditional rack-scale CPUs.

The context here is that agentic AI has fundamentally changed what compute infrastructure needs to do. When AI shifts from answering questions to planning tasks, calling tools, running code, and validating results, the bottleneck moves beyond GPUs. CPUs handle the orchestration layer — moving data around, managing concurrent environments, coordinating workflows. Vera targets this gap with optimized single-thread performance and bandwidth per core.

The partner list tells the story: Alibaba, ByteDance, Meta, and Oracle Cloud are deploying Vera, with Dell, HPE, Lenovo, and Supermicro building systems around it. Nvidia also announced a Vera CPU rack — 256 liquid-cooled Vera CPUs sustaining over 22,500 concurrent independent CPU environments. As part of the Vera Rubin NVL72 platform, Vera connects to GPUs via NVLink-C2C at 1.8 TB/s, 7x the bandwidth of PCIe Gen 6.

Jensen Huang put it this way: "The CPU is no longer simply supporting the model; it's driving it." Two years ago that would've sounded like marketing. Today, with coding agents spinning up dozens of parallel environments, each needing its own CPU resources, it's just describing reality. Nvidia isn't content selling GPUs alone — they want the entire AI infrastructure stack. If CPU market growth really does outpace GPU growth by 2028, Vera is how Nvidia gets ahead of that curve.

---

## Musk Says xAI Was "Not Built Right," 9 of 11 Co-Founders Gone

Source: https://www.therundown.ai/p/musk-takes-xai-into-a-full-rebuild

Elon Musk posted that xAI is "being rebuilt from the foundations up." Nine of the original eleven co-founders have left, with Zihang Dai and Guodong Zhang being the latest departures. Zhang led Grok Code and reported directly to Musk — reportedly blamed for Grok's coding shortfalls before leaving.

Only Manuel Kroiss and Ross Nordeen remain from the founding team. Last week Musk hired senior Cursor leaders Andrew Milich and Jason Ginsberg, a clear move to shore up coding capabilities. This is the second major reorg in a month.

Three years ago Musk assembled 11 people to take on OpenAI and Anthropic. Nine are gone, and Grok still can't match competitors on coding. The timing makes it worse — xAI is preparing for an IPO. Rebuilding from scratch while heading toward a public listing is a tough sell to investors.

---

## Stripe's Minions Ship 1,300 PRs a Week With Zero Human-Written Code

Source: https://blog.bytebytego.com/p/how-stripes-minions-ship-1300-prs

Every week, Stripe merges over 1,300 pull requests containing zero human-written code. These PRs come from "Minions," Stripe's internal coding agents that work completely unattended. An engineer sends a message in Slack describing the issue, walks away, and comes back to a finished PR that's already passed automated tests and is ready for review.

ByteByteGo's key insight: the reason Minions work has almost nothing to do with the AI model. It's the infrastructure Stripe built for human engineers years before LLMs existed. This is different from attended agents like Cursor or Claude Code, where a developer watches and steers. Minions are unattended — no one's supervising.

That distinction changes everything. Attended agents can tolerate messy infrastructure because humans catch mistakes in real time. Unattended agents need deterministic CI, high test coverage, and strict code standards. Stripe's monorepo, Sorbet type system, and robust CI pipeline are what make Minions possible. If you want to replicate this, you need Stripe-level engineering infrastructure first.

---

## Stratechery: We Might Not Be in a Bubble

Source: https://stratechery.com/2026/agents-over-bubbles/

Ben Thompson published a long piece on the morning of Nvidia's GTC, titled "Agents Over Bubbles." His core argument: he no longer thinks AI is a bubble.

The article traces three LLM inflection points: ChatGPT in 2022 (showed the world what LLMs could do, but hallucinations made them feel unreliable), o1 in 2024 (introduced reasoning, models started self-correcting), and the current agentic phase (models don't just answer — they execute). Thompson argues the third inflection is qualitatively different. When AI can autonomously complete workflows, the business value shifts from "potentially useful" to "already in production."

Thompson previously held that bubbles can be good. He's changed his mind. He acknowledges the irony — "I don't think it's a bubble" might be the strongest evidence that it is. But his evidence is more concrete now: Stripe's Minions, real output from coding agents, enterprise customers paying real money. These are transactions, not slide decks.

---

## Simon Willison Ships Agentic Engineering Patterns Guide, Codex Subagents Hit GA

Source: https://simonwillison.net/2026/Mar/16/codex-subagents/#atom-everything
Source: https://simonwillison.net/guides/agentic-engineering-patterns/how-coding-agents-work/#atom-everything
Source: https://simonwillison.net/2026/Mar/16/coding-agents-for-data-analysis/#atom-everything

Simon Willison had a prolific couple of days. A few things worth covering together.

OpenAI Codex subagents are now generally available. The defaults are explorer, worker, and default. Users can also define custom agents as TOML files in `~/.codex/agents/`, each with custom instructions and specific models. Subagents are now standard across the ecosystem — Claude Code, Gemini CLI, Mistral Vibe, Cursor, and VS Code Copilot all have similar implementations.

Simon also published his "Agentic Engineering Patterns" guide series, starting from how coding agents work under the hood: what LLMs are, how chat templates function, how tool use is implemented. This isn't a beginner tutorial — it's a systematic framework for developers already using agents who want to understand the mechanics.

He also ran a three-hour NICAR 2026 workshop teaching data journalists to use Claude Code and Codex for data analysis. Participants burned through $23 in Codex tokens total. A highlight was live-generating Leaflet heatmap visualizations with Claude Code and Datasette.

What makes Simon valuable is that he doesn't just report on tools — he uses them in practice and extracts patterns. His Agentic Engineering Patterns guide is likely to become a reference document for the field.

---

## Mistral Releases Leanstral: Open-Source Code Agent for Lean 4

Source: https://mistral.ai/news/leanstral

Mistral released Leanstral, an open-source code agent designed specifically for the Lean 4 proof assistant. It has 6B active parameters and ships under Apache 2.0.

Lean 4 is a formal verification system capable of expressing complex mathematical objects and software specifications. Leanstral isn't a general-purpose coding agent — it's built for proof engineering in real formal repositories, not solving isolated competition math problems.

Benchmarked on FLTEval (completing proofs and defining new concepts in PRs to the Fermat's Last Theorem project), Leanstral-120B-A6B outperforms much larger open-source models like GLM5-744B-A40B and Kimi-K2.5-1T-32B with just a single pass. It's competitive with closed-source models too.

Formal verification is an interesting frontier for AI-assisted programming. Generating code is easy; proving it correct is hard. If AI can do both, that changes not just productivity but the ceiling on software quality. Leanstral only covers the niche Lean 4 ecosystem for now, but the approach deserves attention.

---

## Claude 1M Context Window Now Generally Available at Standard Pricing

Source: https://tldr.tech/ai/2026-03-16

Anthropic announced that the full 1M token context window for Claude Opus 4.6 and Sonnet 4.6 is now generally available at standard pricing. Claude Code users on Max, Team, and Enterprise plans get the full 1M context with Opus 4.6 as well.

OpenAI and Google typically charge 2-4x premiums for extended context. Claude doesn't. Developers can feed entire codebases and long documents without worrying about cost multipliers. For Claude Code users, larger context means fewer compactions and more stable conversation quality.

The pricing is aggressive. Inference at 1M tokens isn't cheap. Anthropic is either very efficient at managing costs or trading margin for market share. Either way, developers benefit.

---

## Meta Lays Off 20% of Workforce

Source: https://tldr.tech/tech/2026-03-16

Meta announced a 20% workforce reduction. Details on which divisions are affected and how this relates to their AI strategy are still sparse.

---

## LinkedIn Editor Becomes iOS Developer Using Claude Code

Source: https://www.lennysnewsletter.com/p/from-journalist-to-ios-developer

Lenny's Newsletter interviewed LinkedIn editor Daniel Roth about his transition from journalist to iOS developer, primarily using Claude Code.

These stories are becoming more common. Non-technical people building functional products with AI coding agents — the barrier to entry is genuinely lower. But "can build it" and "can maintain it" are different problems. Comprehension debt will surface eventually.

---

## ByteByteGo: Git Workflow Essential Commands

Source: https://blog.bytebytego.com/p/ep206-git-workflow-essential-commands

ByteByteGo published a summary of the most commonly used Git commands for daily workflows. Most development work only uses a small subset of Git's full command set. A solid reference for newcomers.
