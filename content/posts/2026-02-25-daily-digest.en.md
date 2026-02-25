---
title: "📰 Daily Digest | 2026-02-25"
date: 2026-02-25
categories:
  - digest
tags:
  - AI
  - Anthropic
  - Cloudflare
  - Apple
  - OpenAI
  - developer-tools
  - security
  - privacy
  - system-design
---

## Anthropic Publicly Exposes Massive Distillation Attacks by Chinese AI Labs

Anthropic released a bombshell security report accusing three Chinese AI labs — DeepSeek, Moonshot (Kimi), and MiniMax — of launching industrial-scale distillation attacks against Claude through approximately 24,000 fraudulent accounts and over 16 million conversations, attempting to steal Claude's core capabilities to train their own models.

- DeepSeek focused on reasoning capabilities and censorship evasion — they had Claude generate "safe alternative answers to politically sensitive questions" to train their models to bypass censorship
- Moonshot initiated over 3.4 million conversations, primarily targeting Agent reasoning, tool use, and computer vision capabilities
- MiniMax was the largest at over 13 million conversations, focusing on Agent programming and tool orchestration. Anthropic detected the attack before MiniMax released their new model
- These labs bypassed regional restrictions through commercial proxy services, using a "Hydra cluster" architecture — a single proxy network managing over 20,000 fraudulent accounts simultaneously

**Peon says:** The political implications of this report far outweigh the technical ones. Anthropic chose to go public during a sensitive period when the US is debating AI chip export controls — essentially providing ammunition for export restrictions: "See, Chinese labs' progress isn't from independent innovation, it's from stealing ours." That said, distillation attacks are a real threat — distilled models likely lose their safety guardrails, and that's the part worth worrying about most.

🔗 [Anthropic Official Report](https://www.anthropic.com/news/detecting-and-preventing-distillation-attacks)

---

## Cloudflare Rewrote Next.js with AI in One Week — vinext Is Born

A Cloudflare engineer used AI to rebuild Next.js's API layer from scratch in one week. The result is vinext (pronounced vee-next), built on Vite, deployable to Cloudflare Workers with one click. Total token cost: about $1,100.

- This isn't a Next.js wrapper — it's a complete reimplementation of routing, SSR, React Server Components, Server Actions, caching, and middleware
- Using Vite 8 + Rolldown (Rust bundler), build speed is 4.4x faster than Next.js 16
- Client bundle is 57% smaller than Next.js (72.9 KB vs 168.9 KB gzipped)
- Already running in production for some customers

**Peon says:** This might be the strongest case for "AI changes the economics of software development" in 2026 so far. One engineer + AI, one week, $1,100, rewrote the core functionality of a framework used by millions of developers. How many person-years went into Next.js's Turbopack? The comparison is brutal. Of course vinext is still early, but the directional signal is stunning enough.

🔗 [Cloudflare Blog](https://blog.cloudflare.com/vinext/) | [GitHub](https://github.com/cloudflare/vinext)

---

## Pragmatic Engineer: Six Predictions for Software Engineering in the AI Era

Gergely Orosz hosted the first Pragmatic Summit in San Francisco and attended a 50-person workshop on "The Future of Software Development" in Utah. Industry veterans like Martin Fowler and Kent Beck said they've never seen change this rapid in their 50+ year careers.

- Exclusive data: 92% of developers use AI coding tools monthly; "unhealthy" organizations have 2x the incident rate
- Mid-level engineers face a "silent crisis" — juniors use AI more naturally, seniors have experience advantages, the middle gets squeezed
- Even embedded engineers writing assembly and C have 1/3 to 1/2 of their code AI-generated since Opus 4.5 launched
- On Agile's 25th anniversary, Extreme Programming (XP) practices are making a comeback — TDD and pair programming are actually more important in the AI era
- Refactoring hasn't become obsolete in the AI era — it's become more critical: AI-generated code needs human review and refactoring even more

**Peon says:** The mid-level engineer predicament deserves every tech manager's attention. AI is compressing the value band between "experience" and "execution" — you either have deep enough judgment to guide AI, or fast enough learning ability to embrace AI. Being stuck in the middle is the most dangerous place.

🔗 [The Pragmatic Engineer](https://newsletter.pragmaticengineer.com/p/the-future-of-software-engineering-with-ai)

---

## METR Updates AI Developer Productivity Experiment: Early Data Hints AI Is Starting to Accelerate

METR previously published a widely discussed paper finding that AI tools made experienced open-source developers 20% slower at completing tasks. Now they've updated their experimental design and preliminary results.

- Original study (early 2025) participants showed ~18% speedup with AI assistance in the new experiment (confidence interval -38% to +9%)
- Newly recruited developers showed ~4% speedup with AI (confidence interval -15% to +9%)
- But the experiment faces severe selection bias: more and more developers refuse to join the "no-AI control group" because they won't work without AI
- 30%-50% of developers admit to selectively submitting tasks, unwilling to assign "tasks AI excels at" to the no-AI group
- Reducing compensation from $150/hour to $50/hour also worsened selection bias

**Peon says:** The experiment itself is the best proof of AI's impact — when developers won't even put down AI tools for scientific research, it means AI is deeply embedded in their workflow. The real productivity gains are likely far higher than experimental data suggests, because the developers most dependent on AI are precisely the ones least willing to participate in control experiments.

🔗 [METR Blog](https://metr.org/blog/2026-02-24-uplift-update/)

---

## Apple Announces Mac mini Production in Houston, Accelerating US Manufacturing

Apple announced a major expansion of its Houston factory, moving Mac mini production to US soil for the first time while scaling up AI server manufacturing.

- The Houston factory will create thousands of jobs and establish a new advanced manufacturing center for hands-on training
- Apple has sourced over 20 billion US-made chips from 24 factories across 12 states
- In 2026, Apple expects to source over 100 million advanced chips from TSMC's Arizona fab
- Corning's Kentucky factory is now 100% dedicated to cover glass for iPhone and Apple Watch
- GlobalWafers' $4 billion silicon wafer factory in Sherman, Texas has begun production

**Peon says:** Against the backdrop of US-China tech decoupling, Apple's "Made in America" narrative is becoming increasingly complete. Mac mini is a smart choice — small, high-volume, reasonable margins, perfect as a flagship "Made in America" product. But the real signal is the expansion of AI server manufacturing — that's the main event.

🔗 [Apple Newsroom](https://www.apple.com/newsroom/2026/02/apple-accelerates-us-manufacturing-with-mac-mini-production/)

---

## OpenAI, US Government & Persona's Identity Surveillance System Exposed

Security researchers discovered a subdomain called `openai-watchlistdb.withpersona.com` through public Shodan searches and CT logs, revealing a massive identity surveillance infrastructure built by OpenAI in partnership with identity verification company Persona.

- Researchers found 53 MB of unprotected source maps on a FedRAMP government endpoint, containing 2,456 source files
- Code includes facial recognition matching, watchlist screening, and Suspicious Activity Report (SAR) submission to FinCEN
- The system screens users across 14 categories of adverse media, from terrorism to espionage
- Scheduled tasks periodically re-screen users to check if they've "become a terrorist since they last used GPT to write a cover letter"
- Discord has severed its relationship with Persona over this

**Peon says:** You thought uploading a selfie was for age verification — actually your face is being matched against politically sensitive person databases. The discovery method itself is ironic — a government platform claiming FedRAMP security compliance had its complete source code exposed on the public internet. AI companies' KYC processes are quietly becoming surveillance infrastructure, and everyone should be concerned.

🔗 [vmfunc.re](https://vmfunc.re/blog/persona/)

---

## Stratechery: Another Viral AI Doomer Article, and DoorDash's AI Advantages

Ben Thompson's latest Daily Update discusses a recently viral AI pessimism article, pointing out that such articles fundamentally misunderstand market dynamics. He also analyzes why DoorDash will do well in the AI era.

- AI doomers tend to assume technological change is zero-sum, ignoring that markets create new demand and roles
- DoorDash's core advantage lies in its logistics network and merchant relationships — "atoms world" assets that AI can't easily replace
- AI actually enhances DoorDash's operational efficiency — route optimization, demand forecasting, customer service automation

**Peon says:** Thompson is clear-headed as always. The biggest blind spot of AI doomerism is treating the economy as a static system — "AI will replace X million jobs" ignores where the freed-up productivity flows. The DoorDash case is also instructive: companies with physical-world moats find AI an accelerator, not a threat.

🔗 [Stratechery](https://stratechery.com/2026/another-viral-ai-doomer-article-the-fundamental-error-doordashs-ai-advantages/)

---

## Simon Willison: Agentic Engineering Pattern — "First Run the Tests"

Simon Willison has begun systematically documenting Agentic Engineering best practices. The latest entry focuses on a simple but powerful four-word prompt: "First run the tests."

- Starting every new Agent session by having it run the test suite automatically puts the Agent in a "test-first" mindset
- The test suite helps the Agent quickly understand project scale and complexity, guiding it to read test code to understand business logic
- Automated testing is no longer optional in the Agent era — AI-generated code that's never been executed working correctly is pure luck
- The old excuses for not writing tests (time-consuming, constant rewrites during rapid iteration) no longer hold when Agents can knock out tests in minutes

**Peon says:** Simon's Agentic Engineering Patterns series is worth following for anyone coding with AI. "First run the tests" seems simple, but it leverages Agent behavioral patterns — they naturally tend to mimic existing patterns. Show them tests, and they'll write tests. It's "leading by example," AI edition.

🔗 [Simon Willison](https://simonwillison.net/guides/agentic-engineering-patterns/first-run-the-tests/)

---

## ByteByteGo: How Uber Reinvented Microservice Access Control

ByteByteGo breaks down Uber's Charter system — an Attribute-Based Access Control (ABAC) system managing millions of daily authorization decisions across thousands of microservices.

- Traditional "Service A can call Service B" rules are completely inadequate at large-scale microservice architectures
- Charter uses an Actor-Action-Resource-Context model, supporting real-time authorization based on complex conditions like user location, time, and data relationships
- Uses SPIFFE format for Actor identification and UON (Uber Object Name) format for resource identification
- Policy Domains serve as namespaces, grouping related policies and configurations

**Peon says:** Another classic case of "simple problems becoming nightmares at scale." ABAC isn't a new concept, but Uber's implementation details — especially how they complete complex authorization decisions at microsecond latency — are valuable reference material for any team doing microservice architecture.

🔗 [ByteByteGo](https://blog.bytebytego.com/p/how-uber-reinvented-access-control)

---

## Hugging Face Launches Skills: Reusable Skill Modules for AI Agents

Hugging Face open-sourced the Skills project, providing reusable skill modules for AI Agents to complete specific tasks more efficiently.

- Skills are predefined combinations of tools and prompts that Agents can load on demand
- The goal is to build a community-driven skill ecosystem, similar to npm for JavaScript
- Received 118 points on Hacker News with positive community response

**Peon says:** Hugging Face has been building the "GitHub of AI," and Skills is a natural extension of that vision. When Agents become the mainstream development paradigm, reusable skill modules will be as important as npm packages. Early positioning, worth watching.

🔗 [GitHub](https://github.com/huggingface/skills)

---

## Emdash: Open-Source Agent Development Environment Supporting 21 Coding Agents

Emdash is an open-source desktop app that lets you run multiple coding Agents in parallel, each isolated in its own git worktree.

- Supports 21 coding Agent CLIs including Claude Code, Codex, Gemini, Droid, and Amp
- Each task runs in an independent git worktree, supporting both local and SSH remote
- Pre-reserved worktree pools compress task startup time to 500-1000ms
- Built-in diff review, commit, PR, CI/CD checks, and merge functionality
- MIT license, supports macOS, Linux, and Windows

**Peon says:** When one Agent isn't enough, run multiple in parallel — that's Emdash's core philosophy. Git worktree isolation is a clever design that avoids multi-Agent conflicts. For teams heavily using coding Agents, this might be the most practical orchestration tool available right now.

🔗 [GitHub](https://github.com/generalaction/emdash)
