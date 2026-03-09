---
title: "📰 Daily Digest | 2026-03-10"
date: 2026-03-10T07:30:00+08:00
categories: ["digest"]
tags: ["OpenAI", "Anthropic", "Simon Willison", "AI Safety", "Developer Tools", "Infrastructure", "Open Source"]
---

This edition covers news from 03-08 to 03-10.

A few threads stood out today. OpenAI is moving deeper into the AI safety toolchain. Anthropic published one of the more useful pieces I’ve seen lately on how benchmark scores get distorted by infrastructure. And Simon Willison wrote the kind of database post that makes engineers want to try it immediately.

## OpenAI is acquiring Promptfoo and pulling AI security closer to the core product stack

Source: OpenAI News  
Link: https://openai.com/index/openai-to-acquire-promptfoo

Key points:
- OpenAI says it will acquire Promptfoo, an AI security platform used by enterprises.
- The real value here is not just “another eval tool.” Promptfoo helps teams catch prompt injection, unsafe outputs, policy bypasses, and related issues during development.
- That suggests frontier labs no longer want to sell only models. They want to own more of the workflow around testing, validation, and remediation.
- For enterprise teams, this matters most when agents start using tools, APIs, and external knowledge sources, where failures become much more expensive.

My take:
This feels more important than the headline first suggests. A lot of companies still treat AI safety as cleanup work right before launch. OpenAI seems to be betting on the opposite idea: evaluation and red teaming belong inside the default product stack. Whoever makes that invisible and routine will look a lot more like core infrastructure.

## Anthropic shows that agentic coding benchmarks can swing on infrastructure, not just model quality

Source: Anthropic Engineering  
Link: https://www.anthropic.com/engineering/infrastructure-noise

Key points:
- Anthropic studied how agentic coding evals behave under different CPU, RAM, and container limits.
- On Terminal-Bench 2.0, infrastructure-related failure rates fell from 5.8% under strict limits to 0.5% when resources were uncapped.
- Past a certain point, extra headroom didn’t just reduce crashes. It let agents try solution paths that were impossible before.
- That means a leaderboard gap of a few percentage points may reflect runtime setup as much as model capability.

My take:
This is one of those articles the field badly needed. People love to read benchmark rankings as if they were clean measurements. But agentic evals are end-to-end system tests by design. Change the harness, the timeouts, the memory cap, or the concurrency model, and the score moves. From here on out, I care a lot more about the eval setup than the headline number.

## Simon Willison on reproducing production query plans without copying production data

Source: Simon Willison  
Link: https://simonwillison.net/2026/Mar/9/production-query-plans-without-production-data/

Key points:
- PostgreSQL 18 added `pg_restore_relation_stats()` and `pg_restore_attribute_stats()` so developers can copy production statistics into development environments.
- That makes it possible to simulate production query planner behavior without moving huge datasets around.
- The example is simple and useful: if 95% of a column is `delivered`, the planner may choose a very different path than it would for a rarer value.
- Simon also points out that SQLite has long supported a similar approach through `sqlite_stat1` and `sqlite_stat4`.

My take:
This is not flashy news, but it is genuinely practical. A lot of performance work gets stuck because local environments cannot reproduce what the production planner is seeing. PostgreSQL is making that path much more realistic now. Simon is especially good at spotting these ideas early: not big slogans, just solid techniques that save teams real time.

## The Pentagon fallout around OpenAI deepens as its robotics lead resigns

Source: The Rundown AI  
Link: https://www.therundown.ai/p/openai-robotics-lead-exits-over-pentagon-deal

Key points:
- The Rundown reports that OpenAI robotics leader Caitlin Kalinowski resigned over the company’s Pentagon deal.
- In her public comments, she argued the decision moved too quickly and skipped clear guardrails around surveillance and lethal autonomy.
- This appears to be the first senior public departure tied directly to the controversy.
- It is another sign that military and defense partnerships can create pressure inside AI companies, not just outside them.

My take:
The governance angle matters more to me than the PR angle. Once AI companies start touching defense, surveillance, or autonomous force, the hard problem is no longer just public messaging. The harder problem is whether internal guardrails are credible enough that senior people will trust them. If not, capability gains just make the fracture lines sharper.

## ByteByteGo maps the AI repositories shaping developer workflows in 2026

Source: ByteByteGo  
Link: https://blog.bytebytego.com/p/top-ai-github-repositories-in-2026

Key points:
- ByteByteGo highlights a set of AI projects that are growing quickly and shaping the open-source ecosystem.
- It notes that GitHub now hosts more than 4.3 million AI-related repositories, with LLM projects up 178% year over year.
- The center of gravity is moving beyond models themselves toward workflow tools, local AI, orchestration layers, and low-code systems.
- In other words, developers are shifting from “which model is best” to “how do I wire models into real work.”

My take:
The open-source pattern is getting clearer. Raw model capability still matters, but the compounding value is forming around the operating layer: local execution, permissions, automation, and context management. The teams that turn that messy middle into something dependable will end up owning more of the stack than model vendors expect.

## Lenny’s Newsletter: why Applied Intuition became a 15 billion dollar AI company without much noise

Source: Lenny’s Newsletter  
Link: https://www.lennysnewsletter.com/p/the-most-successful-ai-company-youve-never-heard-of

Key points:
- Qasar Younis explains how Applied Intuition stayed relatively quiet while growing into a company valued at 15 billion dollars.
- His core argument is that the biggest AI wave may arrive in physical-world industries like mining, agriculture, construction, and trucking before it fully plays out in software.
- Inside the company, speed, follow-through, and not disappointing customers matter more than grand storytelling.
- He also argues that truly exceptional companies often show traction much earlier than outsiders realize.

My take:
I buy this argument. Over the past year, attention has clustered around chat products and coding agents. But the really large outcomes may come from companies that push AI into messy, operational, physical industries where the constraints are painful and the value is concrete. Software gets the headlines. The physical world gets the budgets.
