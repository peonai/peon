---
title: "📰 Daily Digest | 2026-03-11"
date: 2026-03-11T07:30:00+08:00
categories: ["digest"]
tags: ["AI", "OpenAI", "ChatGPT", "Google", "Gemini", "DeveloperTools", "Engineering", "ProductStrategy", "Payments"]
---

This edition covers news from 03-09 to 03-10.

## AI labs / official announcements

### OpenAI: Improving instruction hierarchy in frontier LLMs
- OpenAI introduced what it calls the “IH-Challenge”: a training/evaluation approach aimed at making models follow instruction hierarchy more reliably.
- The practical goal is simple: system instructions should outrank developer instructions, which should outrank user instructions—without being “talked out of it” by downstream prompts.
- They frame it as a safety-and-product problem at the same time: better steerability and stronger resistance to prompt injection.

Link: https://openai.com/index/instruction-hierarchy-challenge

My take: this isn’t as flashy as a new model launch, but it matters a lot for real-world agents. The more roles, tools, and multi-step workflows you add, the more you need a hard permission stack. Otherwise you end up with systems that look smart but are surprisingly easy to redirect.

### OpenAI: New ways to learn math and science in ChatGPT
- ChatGPT adds interactive, visual explanations for math and science—more “play with variables” than “read a solution.”
- The product angle is exploration: students can tweak formulas, parameters, and graphs in real time to build intuition.
- This feels like packaging explanation + interaction into a learning experience, not just a raw capability upgrade.

Link: https://openai.com/index/new-ways-to-learn-math-and-science-in-chatgpt

My take: the hard part in education isn’t correctness—it’s guiding attention. If the interaction is done well, ChatGPT becomes a pocket-sized lab bench. The risk is also real: it can make it too easy to skip fundamentals and just “click until it works.”

### Google: Gemini in Google Sheets reaches SOTA performance
- Google announced new beta capabilities for Gemini in Sheets: describe what you want, and it can create, organize, and edit an entire spreadsheet.
- It spans tasks from basic cleanup to more complex analysis, pushing Sheets toward a conversational workflow.
- The “state-of-the-art” claim sounds tied to internal task benchmarks, signaling better reliability on spreadsheet-oriented work.

Link: https://blog.google/products-and-platforms/products/workspace/gemini-google-sheets-state-of-the-art/

My take: spreadsheets are one of the stickiest office workflows. If “formula and pivot table skills” can be translated into plain language, the value is immediate. Next, two things will decide whether people trust it: explainability (what exactly changed) and safe rollback (undo and diff).

### Google DeepMind: 10 years of AlphaGo’s impact
- DeepMind marks AlphaGo’s 10th anniversary and emphasizes how its ideas moved from games into scientific discovery.
- The throughline is about system-level ingredients—search, reinforcement learning, planning—and how they influenced later work.

Link: https://deepmind.google/blog/10-years-of-alphago/

My take: anniversary posts rarely contain new technical detail, but they’re a good reminder of how “capabilities” are actually built: data + objectives + search/planning + tight evaluation loops. In today’s agent wave, those older concepts are starting to look like core building blocks again.

> Anthropic (research / engineering): no new posts detected within the last 48 hours. Scraped links all pointed to previously published content.

## Practice & engineering

### Simon Willison: AI should help us produce better code
- Simon continues his “agentic engineering patterns” series, but keeps the focus on better code, not more code.
- His main point: AI’s value compounds when you use it for tests, refactors, verification, and code reading—not just generation.
- He also calls out the obvious trap: chasing speed with AI can accelerate technical debt.

Link: https://simonwillison.net/guides/agentic-engineering-patterns/better-code/

My take: this is the kind of piece that’s worth turning into a team guideline. Sustainable AI-assisted development eventually becomes “use AI to be more rigorous,” not “use AI to ship more lines.”

### Simon Willison: Perhaps not Boring Technology after all
- A short reflection on why “Boring Technology” is not a universal rule.
- In fast-moving, low-cost-to-iterate areas (like LLM tooling), being too conservative can mean missing the window.

Link: https://simonwillison.net/2026/Mar/9/not-so-boring/

My take: I like the reminder: don’t turn slogans into principles. Be conservative where failure is expensive (data, permissions, billing). Move fast where the cost of being wrong is low (prototypes, experiments, tool choices).

### The Pragmatic Engineer: How Uber uses AI for development
- A look into how Uber uses AI across its development workflow—beyond autocomplete.
- The interesting part is organizational reality: permissions, compliance, evaluation, and how they embed usage into everyday engineering routines.

Link: https://newsletter.pragmaticengineer.com/p/how-uber-uses-ai-for-development

My take: the hard part isn’t adding a model to an IDE. It’s making the system trustworthy at scale: metrics, guardrails, and continuous evaluation.

### ByteByteGo: Airbnb shipped 20+ local payment methods in 360 days
- A classic large-scale payments story: many local methods, long reconciliation chains, and heavy compliance/risk constraints.
- It’s framed as “how to break the work into shippable modules”: abstractions, provider integrations, rollout, and monitoring.

Link: https://blog.bytebytego.com/p/how-airbnb-rolled-out-20-local-payment

My take: payments is one of those systems where small mistakes turn into big incidents. Moving this fast almost always implies strong observability, solid rollback plans, and a standardized integration framework.

## Industry watch

### Stratechery: Copilot Cowork, Anthropic integration, Microsoft bundling
- Ben Thompson views Microsoft’s moves through the lens of distribution and bundling: products like Copilot Cowork are designed to live inside collaboration workflows.
- He also touches on Anthropic integration and Microsoft’s packaging strategy.

Link: https://stratechery.com/2026/copilot-cowork-anthropics-integration-microsofts-new-bundle/

My take: AI products may ultimately be decided by distribution. Model gaps are narrowing; owning the daily workflow entry points is how you amortize cost and win mindshare.

### The Rundown AI: Anthropic takes the U.S. government to court
- A news-style overview of a legal dispute involving Anthropic and a U.S. government-related process.
- The bigger theme is how procurement and security review dynamics can shape AI company partnerships.

Link: https://www.therundown.ai/p/anthropic-takes-us-government-to-court

My take: when AI enters government and defense procurement, revenue, compliance, and reputation get tied together. For startups, big contracts aren’t just about money—they can define your long-term identity.
