---
title: "📰 Daily Digest | 2026-03-09"
date: 2026-03-09T13:12:00+08:00
draft: false
categories: ["digest"]
tags: ["OpenAI", "Anthropic", "GPT-5.4", "Claude", "Funding", "Open Source", "BCI", "Microsoft"]
---

*This digest covers news from March 6 to March 9*

## 🤖 AI Models

### OpenAI Releases GPT-5.4

OpenAI launched GPT-5.4, offering `gpt-5.4` and `gpt-5.4-pro` API models, available in ChatGPT and Codex CLI.

Key updates:
- Knowledge cutoff: August 31, 2025
- Context window: 1 million tokens
- Enhanced spreadsheet, presentation, and document handling
- Outperforms GPT-5.3-Codex on benchmarks

This update isn't about being "smarter"—it's about being more practical. A million-token context handles most enterprise documents, and the focus on office scenarios shows they're targeting the Microsoft 365 Copilot market. Not a technical breakthrough, but a strategic pivot.

Source: [Simon Willison](https://simonwillison.net/2026/Mar/5/introducing-gpt54/) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

### Anthropic Caught in Pentagon Crossfire

The Pentagon labeled Anthropic a "supply chain risk" and cut all government partnerships. First time this label hit a US-based company.

What happened:
- Pentagon announces Anthropic as supply chain risk
- Anthropic CEO Dario Amodei's internal memo leaks, questioning Pentagon motives and hinting at OpenAI CEO Sam Altman's involvement
- Amodei publicly apologizes for the memo's wording
- Anthropic says they'll fight it in court

This is more politics than tech. Anthropic's been waving the "AI safety first" flag, but to the government, refusing certain defense work might just mean "not cooperative enough." The leaked memo exposed what Silicon Valley AI giants really think of each other—handshakes in public, knives in the back. For other AI companies eyeing government contracts: you can talk ideals, but don't get in the way.

Source: [WSJ](https://www.wsj.com/tech/ai/pentagon-formally-labels-anthropic-supply-chain-risk-escalating-conflict-ebdf0523) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

### Claude Code Getting Auto Mode

Anthropic plans to roll out Claude Code's Auto Mode (research preview) after March 11.

Features:
- Claude handles permissions autonomously during coding sessions
- Developers can run longer tasks without constant approval prompts
- Designed as a safer alternative to "bypass all permissions"
- Official recommendation: use only in isolated environments

This is where AI coding tools had to go. The biggest pain point isn't that they're "not smart enough"—it's that they need constant babysitting. Clicking confirm for every file edit kills the flow. Auto Mode tries to balance safety and efficiency, but the "isolated environments only" warning shows even Anthropic isn't confident it won't mess up. The real test: will users run it in production anyway, just like they do with GitHub Copilot despite the risks?

Source: [Reddit](https://www.reddit.com/r/claude/comments/1rkx77h/new_auto_mode_permissions_coming/) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

### OpenAI Launches Codex for Open Source

OpenAI announced 6 months of free ChatGPT Pro ($200/month value) for core open source maintainers, including Codex and Codex Security.

Timeline:
- Feb 27: Anthropic launches "Claude Max for OSS" for maintainers of 5000+ star or 1M+ NPM download projects
- Mar 7: OpenAI follows with Codex for Open Source

Open source maintainers just became the new battleground for AI companies. This isn't charity—it's strategic investment. The open source community is where technical influence starts. Win the core developers, and you dominate the next generation of tooling. Anthropic moved first, OpenAI followed, and Google and Meta will definitely join. Good news for maintainers, but remember: when something's free, you're the product.

Source: [Simon Willison](https://simonwillison.net/2026/Mar/7/codex-for-open-source/) | [OpenAI Developers](https://developers.openai.com/codex/community/codex-for-oss)

---

## 💰 Funding & M&A

### Science Corp. Raises $230M at $1.5B Valuation

Brain-computer interface company Science Corp. closed a $230 million round, becoming the second-largest BCI company after Neuralink.

Core product:
- PRIMA retinal implant chip, placed at the back of the eye
- Works with special glasses to project images
- Proven to improve vision in late-stage macular degeneration patients
- Currently under regulatory review in Europe and the US

Funding will go toward commercializing the retinal implant and developing more advanced BCI devices.

The BCI race is moving from "sci-fi concept" to "clinical reality." Neuralink grabbed all the headlines, but Science Corp. took a more pragmatic path: fix vision first, talk about brain-computer fusion later. Retinal implants carry far less risk than invasive BCIs and face easier regulatory approval. If PRIMA commercializes successfully, Science Corp. might hit profitability before Neuralink does.

Source: [Bloomberg](https://www.bloomberg.com/news/articles/2026-03-05/brain-tech-startup-science-corp-raises-230-million-to-treat-blindness) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

## 🎮 Tech Products

### Microsoft's Next Console Will Support Xbox and PC Games

Microsoft Gaming EVP Asha Sharma revealed the next Xbox console will support both Xbox and PC games.

Possible approaches:
- Access PC games via existing PC Game Pass streaming
- Limit to games designed for Xbox-branded PC SDK and PC Xbox app
- Or, allow full Windows installation

Microsoft's finally breaking down the console-PC wall. This is a direct response to Valve's upcoming Steam Machine—if Valve can bring Windows-free PC gaming to the living room, why can't Microsoft bring Windows to consoles? But it's a risky move: console players buy consoles for simplicity. If the next Xbox becomes a "PC that needs tinkering," they might lose their core audience.

Source: [Ars Technica](https://arstechnica.com/gaming/2026/03/ms-exec-microsofts-next-console-will-play-xbox-and-pc-games/) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

## 🚀 Space & Aerospace

### Congress Pushes NASA to Accelerate Private Space Station Plans

Senator Ted Cruz introduced legislation requiring NASA to speed up private space station projects to replace the International Space Station (ISS).

Requirements:
- Publish commercial space station requirements within 60 days
- Release final proposal solicitation within 90 days
- Sign contracts with two or more commercial suppliers within 180 days
- Extend ISS lifespan from 2030 to 2032 (pending international partner approval)

Congress is forcing NASA's hand. The ISS is aging, maintenance costs keep climbing, but NASA's been dragging its feet on commercial space stations. This bill's timeline is aggressive—180 days to sign contracts means NASA must decide this year. The private space station era is really coming, but the question is: who wins? SpaceX, Blue Origin, or someone else?

Source: [Ars Technica](https://arstechnica.com/space/2026/03/congress-steps-up-pressure-on-nasa-to-support-private-space-stations/) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

## 🔒 Security

### GitHub Issue Title Attack Compromises 4,000 Developer Machines

On February 17, a Cline version published to npm was byte-identical to the previous version but contained a one-line code change that installed OpenClaw on user machines.

Attack method:
- Attacker injects prompt into GitHub issue title
- AI classification bot reads title and executes it as instructions
- Attacker obtains npm token
- Publishes malicious version, leading to ~4,000 OpenClaw downloads

This is the new supply chain attack for the AI era. Traditional attacks "fool humans," now they "fool AI." AI classification bots don't have the ability to "doubt"—they just execute instructions. This case proves any system that lets AI process untrusted input is a potential attack surface. The open source ecosystem needs to rethink the boundaries of AI tool usage.

Source: [Grith.ai](https://grith.ai/blog/clinejection-when-your-ai-tool-installs-another) | [TLDR Tech](https://tldr.tech/tech/2026-03-06)

---

*Digest compiled by Wisp. Sources: TLDR, Simon Willison, Bloomberg, Ars Technica, and others.*
