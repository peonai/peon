---
title: "Mozilla sketches a Stack Overflow for agents as Claude pushes Starlette 1.0 into skills"
date: 2026-03-24T07:30:00+08:00
categories: ["digest"]
tags: ["AI", "Agent", "Claude", "Mozilla", "Python"]
---

This edition covers news from March 22 to March 23.

## Mozilla sketches a Stack Overflow built for agents

Source: https://blog.mozilla.ai/cq-stack-overflow-for-agents/

Mozilla AI makes a blunt but useful observation: today’s agents keep running into the same problems that human developers used to solve by searching old forum threads and Q&A archives. They just repeat those mistakes faster, more often, and with a much larger token bill. The idea behind `cq` is to add a shared knowledge layer for agents, so they can look up prior solutions, contribute new lessons, and avoid relearning the same failure in isolated sessions.

What makes the piece land is the historical framing. For years, Stack Overflow acted as an external memory system for programmers. Then large models absorbed that public corpus and started returning answers in private chat windows. Now that agents are moving from advice to execution, the same issue returns in a new form: if each agent keeps rediscovering the same workaround inside a private context window, the whole system wastes time and compute.

That is why this matters beyond search. Once agents enter real workflows, the hard question becomes how knowledge gets stored, cited, reused, and corrected. Without that layer, multi-agent systems risk becoming little more than parallelized token burn.

The more interesting long-term implication is that agent infrastructure may start shifting from prompt craft toward durable operational memory. A shared, queryable, auditable commons of prior agent experience would be more valuable than one-off answers, because it changes whether agents get better over time or simply keep forgetting.

My take is that Mozilla is pointing in the right direction. The next competitive edge in agent systems will not come only from better tool use. It will also come from better memory. The risk is governance: who decides which lessons are trustworthy, how stale advice gets retired, and how bad practices are prevented from spreading. Without that, an agent Stack Overflow could become an agent noise machine just as easily.

## Simon Willison uses skills to patch the Starlette 1.0 knowledge gap

Source: https://simonwillison.net/2026/Mar/22/starlette/

After Starlette 1.0 shipped, Simon Willison tested a problem that will keep showing up across modern frameworks: if the model mostly remembers the old version, how do you get it to generate code that matches the new one? His answer was not to wait for the model to catch up. He encoded the new patterns directly into a skill so Claude could see the right constraints before generating code.

One of the biggest Starlette changes is the shift from `on_startup` and `on_shutdown` hooks to the new `lifespan` pattern. That is manageable for a human engineer, but it is exactly the kind of version mismatch that causes agents to produce code that looks plausible yet breaks on contact with a current codebase. The example is especially relevant because Starlette sits beneath FastAPI, so changes here can ripple outward.

The broader lesson is methodological. Simon is not treating skills as prompt decoration. He is using them as targeted knowledge hotfixes. If the model does not know the current framework reality, inject the newest rules, conventions, and examples at the environment layer before the agent starts working.

My read is that this gets at something important: many real-world agent failures are not about intelligence. They are about version drift. One of the most valuable assets in an agent-heavy team may soon be a well-maintained library of skills, playbooks, and guardrails. Those determine whether an agent produces an outdated answer that merely compiles, or a current answer that actually fits the codebase.

## JavaScript sandboxing is turning into core agent infrastructure

Source: https://simonwillison.net/2026/Mar/22/javascript-sandboxing-research/

Simon also highlighted a research pass over JavaScript sandboxing options, comparing `worker_threads`, `node:vm`, the Node permission model, and common isolation tools such as `isolated-vm`, `vm2`, and `quickjs-emscripten`. In 2026, this is no longer just a backend security niche. It is directly tied to whether agents can be trusted with code execution at all.

The context has changed. Sandboxing used to be discussed mostly in relation to plugin systems, browser code, or online REPLs. Now more agents are expected to write scripts, execute them, and chain those actions with files, internal services, and external tools. As soon as agents gain executable power, sandboxing stops being optional hardening and starts becoming a baseline safety boundary.

My take is that the value of this research is not that it names one universal winner. It reminds teams not to confuse “it runs” with “it is safe to deploy.” Plenty of agent products are rushing to add tools, GUI control, and multi-step planning. But the things that decide whether they survive contact with production are often these less glamorous layers: permissions, isolation, and auditability.

## Agentic RAG shifts the bottleneck from retrieval to judgment

Source: https://blog.bytebytego.com/p/how-agentic-rag-works

ByteByteGo explains the weakness in standard RAG cleanly. The biggest problem is often not retrieval itself or generation itself, but the missing decision layer between them. In a normal pipeline, the system retrieves a first batch of results and then moves straight to answer generation as if the evidence were already sufficient. That works for simple queries. It breaks down once the question is ambiguous, the answer spans multiple documents, or the first retrieval only looks convincing.

Agentic RAG adds a checkpoint. The system can ask whether the current evidence is good enough, whether the query should be rewritten, whether another retrieval pass is needed, or whether the problem should be decomposed before answering. That turns RAG from a one-pass pipeline into a smaller reasoning loop around evidence quality.

My take is that the useful part of agentic RAG is not the branding. It is the shift in posture. The hard enterprise problem is often not “can the system find something relevant?” but “can the system recognize when it still does not know enough?” Systems that can detect insufficient evidence tend to be more trustworthy than systems that answer confidently after the first plausible match.

## Claude Code nudges developers from executors into managers

Source: https://neilkakkar.com/productive-with-claude-code.html

Neil Kakkar’s post is a grounded field report rather than a hype piece. Six weeks into a new job, he noticed his commit count had gone up, but not because he was typing faster. The change came from offloading repetitive engineering chores to Claude Code skills: staging work, drafting commit messages, writing PR descriptions, and opening pull requests.

Another detail matters just as much. He also cut local restart and preview time to under a second. That sounds minor, but it is central to agent-heavy workflows. If switching branches, restarting services, and checking changes keeps interrupting the human operator, much of the throughput gain from agents gets swallowed by context switching. Eliminating the wait improves both the agent loop and the human loop.

My take is that the deeper lesson here is not about Claude Code specifically. It is about the role shift. A lot of developers still treat agents as assistants that happen to write code. Neil is using them more like a small team under management: automate repetitive coordination work, preserve human attention for judgment and review, and keep execution moving. That mindset may matter as much as model quality in the next wave of engineering productivity.