---
title: "Anthropic Surpasses OpenAI with $30B ARR, Claude Mythos Shakes the Cybersecurity Industry"
date: 2026-04-12T07:30:00+08:00
categories: ["digest"]
tags: ["Anthropic", "Claude", "Mythos", "OpenAI", "SiFive", "RISC-V", "DeepMind", "SQLite", "Meta", "AI Safety"]
---

This issue covers news from April 7 to April 11, 2026.

## Anthropic Surpasses OpenAI with $30B ARR

Source: https://www.latent.space/p/ainews-anthropic-30b-arr-project

Anthropic announced on April 7 that its annualized recurring revenue has crossed $30 billion. Just a month earlier on March 4, that number stood at $19 billion—an $11 billion jump in a single month. For comparison, OpenAI's ARR sits at approximately $25 billion. Anthropic has officially overtaken OpenAI in revenue scale.

The revenue mix is equally noteworthy. Eighty percent of Anthropic's revenue comes from enterprise customers, while OpenAI relies more heavily on converting free consumer users. On the compute spending side, OpenAI expects to spend $121 billion in a single year, while Anthropic's spending is significantly lower. Claude Code went from zero to $2.5 billion in revenue in just 10 months, capturing roughly half of the AI coding tool market.

Anthropic is valued at around $380 billion, but its revenue efficiency is showing the industry a different growth path—not brute-forcing users with compute spend, but achieving high margins through deep enterprise penetration.

This isn't just a leaderboard swap. OpenAI took a consumer-first approach: build the user base first, monetize later. Anthropic went enterprise-first, going straight to customers with real budgets. The two strategies converged in 2026, and Anthropic's enterprise play is currently ahead. But OpenAI's user base and ecosystem breadth remain a massive advantage. This race is far from over.

## Anthropic Launches Claude Mythos and Project Glasswing

Source: https://www.anthropic.com/glasswing

Anthropic formally released Claude Mythos Preview on April 8 and simultaneously launched Project Glasswing, an industry consortium. Anthropic describes Mythos's cybersecurity capabilities as "far ahead of any other AI model"—it can discover high-severity vulnerabilities in every major operating system and web browser, including previously unknown zero-days.

The catch is that this capability cuts both ways. Defenders can use it to patch vulnerabilities, but attackers can equally use it to find new entry points. Anthropic's response: don't release Mythos publicly. Instead, make it available through Project Glasswing to a select group including AWS, Apple, Broadcom, Cisco, CrowdStrike, Google, JPMorganChase, Microsoft, and Nvidia—exclusively for defensive security work.

Nicolas Carlini noted in a recent talk that he's "found more bugs in the last couple weeks than I've found in the rest of my life combined." The security market reacted accordingly—shares of CrowdStrike, Palo Alto Networks, Zscaler, SentinelOne, and others dropped 5% to 11% on the news. Investors are worried that AI models this capable could undermine demand for traditional security products.

This is the first time in AI history that a model has been deliberately held back because it's too powerful. The old playbook was always "the stronger the model, the faster we ship it." Mythos changes that calculus: when an AI's vulnerability-finding ability outpaces the industry's ability to patch, public release itself becomes a risk. Anthropic is choosing a rare path—give defenders time to prepare first, then consider broader release. This precedent could shape how every future AI safety-related model gets shipped.

## Demis Hassabis: DeepMind Must Return to Startup Speed

Source: https://thenextweb.com/news/google-deepmind-hassabis-startup-pace

Demis Hassabis revealed on the 20VC podcast that Google DeepMind has undergone "deliberate acceleration" in the two to three years since merging with Google Brain. His framing was blunt: "We had to come back to our startup roots—be scrappier, be faster, ship things quickly."

Hassabis described the competitive environment as "ferocious." Employees with 20 to 30 years of experience told him it's "the most intense environment they've ever seen, perhaps ever in the technology industry." He speaks with Alphabet CEO Sundar Pichai daily, reflecting DeepMind's position at the operational center of Alphabet's product and research strategy.

Google's capital expenditure plan bears this out: $91.4 billion in 2025, guided to $175-185 billion in 2026—nearly double. Hassabis also claimed that roughly 90% of the breakthroughs underpinning the modern AI industry came from Google Brain, Google Research, or DeepMind.

Hassabis also runs Isomorphic Labs, DeepMind's pharmaceutical AI spinoff. He described his schedule as a first workday at DeepMind, followed by a "second workday" starting around 10pm focused on Isomorphic's drug discovery program. Isomorphic raised $600 million in April 2025, has partnership agreements with Eli Lilly and Novartis worth up to $3 billion in milestones, and expects to begin human oncology trials later in 2026.

The context here is that SoftBank provided OpenAI with a $40 billion bridge loan—capital on a scale that even Alphabet's commitments can't trivially match. Hassabis's "startup speed" isn't a cultural slogan; it's a survival strategy in a resource war that's already hot.

## SiFive Raises $400M as Nvidia Bets on RISC-V Open Chip Architecture

Source: https://techcrunch.com/2026/04/11/nvidia-backed-sifive-hits-3-65-billion-valuation-for-open-ai-chips/

RISC-V chip design company SiFive closed a $400 million oversubscribed round, valuing the company at $3.65 billion. The round was led by Atreides Management, founded by former Fidelity executive Gavin Baker, with Nvidia participating alongside Apollo Global Management, D1 Capital Partners, Point72 Turion, and T. Rowe Price.

SiFive's business model mirrors Arm's in its early days—licensing chip designs for customers to modify, without manufacturing chips itself. But SiFive's designs are based on the open RISC-V instruction set, not Intel's x86 or ARM. This was SiFive's first funding since March 2022, when it raised $175 million at a $2.33 billion valuation.

What makes this particularly interesting is Nvidia's position. Nvidia's GPU empire is built on x86 and ARM CPUs, yet it chose to invest in a company designing chips on a completely different, open architecture. SiFive's designs will be compatible with Nvidia's CUDA software and NVLink Fusion data center systems. While Intel and AMD try to compete with Nvidia's GPUs, Nvidia is quietly backing a company that can design open-architecture CPUs—a hedging strategy.

RISC-V has historically been better known for embedded systems and smaller-scale use cases. SiFive is using this funding to target AI data center CPUs. The appeal of open architecture in the AI chip space is independence from any single vendor—a compelling proposition for large tech companies.

## AI Training Data Market Heats Up: AfterQuery Raises $30M

Source: https://siliconangle.com/2026/04/10/ai-training-data-startup-afterquery-nabs-30m-investment/

San Francisco-based AI data company AfterQuery raised $30 million at a $300 million valuation, led by Altos Ventures with participation from Y Combinator, The Raine Group, and BoxGroup. The 14-month-old company claims its customers include "every leading AI lab" and has surpassed $100 million in annual recurring revenue.

AfterQuery's core product is training datasets, but not simple prompt-response pairs. They provide step-by-step reasoning behind each response, which matters for model generalization. The company works with nearly 100,000 developers, attorneys, and other professionals to generate data, and also supports multimodal training data and custom evaluation suites.

This is the third AI data startup to raise funding in the past month. Deccan AI closed $25 million in late March, and Deeptune raised $43 million just days before that. AI training data is becoming a standalone,规模化 market.

A 14-month-old company hitting $100 million ARR signals that frontier models' demand for high-quality training data far exceeds expectations. Customized datasets for reinforcement learning stages can't be scraped from the internet—they require human experts. The ceiling for this market may be much higher than most people assumed.

## SQLite 3.53.0 Released, Fixes WAL Corruption Bug and Adds Query Result Formatting

Source: https://simonwillison.net/2026/Apr/11/sqlite/

SQLite released version 3.53.0. Since 3.52.0 was withdrawn, this update accumulates a significant batch of improvements. The most visible change is the new Query Result Formatter (QRF) library—interactive CLI sessions now use Unicode box-drawing characters to format query results by default, dramatically improving readability.

Other changes include: a fix for a critical WAL reset database corruption bug; a new SQLITE_PREPARE_FROM_DDL option allowing virtual table implementations to safely prepare schema-derived SQL statements; the .indexes command now matches index names rather than table names; and a new self-healing index feature addressing stale expression index issues.

Simon Willison covered this on his blog. For daily SQLite users, the CLI output formatting improvement is immediately noticeable. The WAL corruption fix prevents potential data loss scenarios that could have been nasty.

## Meta Launches Muse Spark Model, meta.ai Chat Shows Multimodal Capabilities

Source: https://simonwillison.net/2026/Apr/8/muse-spark/

Meta released its new Muse Spark model and showcased accompanying tools in the meta.ai chat interface. Simon Willison noted that meta.ai now has visual grounding capabilities—it can analyze images, identify and label objects, locate regions, and even count a raccoon's whiskers.

Image generation is likely powered by Meta's Emu model. The meta.ai tool collection is quite robust, including code interpreter, visual analysis, and more, all presented through custom HTML visualizations.

Simon's take was characteristically pragmatic: the tool collection is solid, but the real test is API availability—can we build on top of these models ourselves? Meta's typical pattern is to validate the experience on its own platform first, then gradually open up to developers.

## LLMs May Be Standardizing Human Expression

Source: https://news.ycombinator.com/item?id=47673541

A USC study suggests that LLMs may be standardizing the way humans express themselves, and subtly influencing how we think. The topic sparked discussion on Hacker News.

The core hypothesis: as more people use LLMs to assist with writing and thinking, the convergence in output style will loop back to shape input—human expression habits will gradually align with the model's output patterns. This isn't just about writing style; at a deeper level, it's about how thinking patterns are shaped.

The research is still early, but the direction is worth watching. If LLMs are genuinely shaping how humans express themselves, then the diversity of training data becomes even more critical—because model output doesn't just affect the user's immediate experience, it may have long-term cognitive implications.
