---
title: "Code Standards in the AI Era: What to Keep, What to Toss"
date: 2026-03-16T22:00:00+08:00
categories: [Opinion]
tags: [AI, Programming, Code Standards, Agent]
---

Last year I was still religiously following the "functions under 20 lines" rule. This year I had AI write a 300-line data processing function. It worked fine. I stared at the screen for a while thinking—who was this rule even for?

For humans.

Traditional code standards rest on one assumption: the person writing code is human. Humans make mistakes. Humans have limited working memory. Humans will name variables `tmp2_final_v3` at 3 AM. So we invented a whole system of rules to constrain ourselves.

Now code isn't only written by humans. Do these rules still apply?

## Naming: More Important Now, But for Different Reasons

AI doesn't mind long variable names. Ask it to write `userAuthenticationTokenExpirationTimestamp` and it won't complain. It won't get confused by nested `i` `j` `k` loops either.

But here's the thing—you still have to read this code.

AI-generated code has a problem: inconsistent naming. Same project, sometimes `camelCase`, sometimes `snake_case`, sometimes abbreviated, sometimes spelled out. It's not that AI can't name things—it just doesn't care about consistency.

So naming standards can't be dropped. In fact, add a new rule: **specify naming conventions in your AI prompts**. Used to be code review where humans watched humans. Now it's prompts where you set the rules upfront.

## Function Length: Time to Loosen Up

"Functions under 20 lines" and "single responsibility principle"—what are these really about? They exist because human brains can only handle 7±2 chunks of information at once. Long functions are hard to read and bug-prone.

AI doesn't have this limitation. It can generate 200 lines of coherent logic without losing focus at line 150.

My approach now: don't force AI-generated code to split functions. But if humans will maintain this code later, still split it. The criterion shifted from "how long" to "who maintains it."

Pure AI-maintained utility scripts? Write however. Core business logic that humans touch? Old rules still apply.

## Comments: From Explaining What to Explaining Why

Comments used to tell the next person "what this code does." Now with AI-generated code, the what level rarely needs comments—the code itself is the product of AI understanding requirements, usually clear enough.

But why-level comments became more important.

Why this algorithm instead of that one? Why recursion instead of iteration? Why timeout set to 30 seconds? AI won't volunteer this decision context. If you don't write it down, three months later you won't remember what prompt you used.

I now add lines like: `// Chose X approach because better performance in Y scenario, see prompt: Z`. Ugly, but works.

## DRY Principle: AI Is Naturally Anti-DRY

Don't Repeat Yourself—programmer's creed. But when AI writes code, it tends to repeat.

Ask it to handle user authentication in three places, it'll write nearly identical logic three times. Not because it can't abstract—it has no concept of "maintenance cost." To AI, copy-paste and abstraction cost the same: generating a few dozen tokens.

This is a real problem. Because maintenance cost of repeated code falls on humans. Change one place, forget the other two, bugs appear.

So DRY can't be tossed. But enforcement changed: don't require AI to follow DRY while writing, have humans do abstraction during review. AI handles fast generation, humans handle structural optimization. Division of labor shifted.

## Design Patterns: Mostly Downgraded

Factory, Strategy, Observer—what are these really? Fixed patterns to solve common problems in an era when language expressiveness wasn't enough.

Now AI writes code without needing to "remember" design patterns. You tell it requirements, it gives you the most suitable implementation. Sometimes it happens to be a Strategy pattern, sometimes not, but it doesn't care about the name.

I think design patterns in the AI era went from "coding guide" to "communication vocabulary." When people discuss architecture and say "use Observer here," everyone gets it instantly. But you don't need to force AI to follow design patterns—it has its own way, usually not bad.

Only exception is team collaboration. If five people are all modifying the same module, unified design patterns still have value. But that value is for humans, not AI.

## New Standards We Need

While tossing old rules, some new ones should be established:

**Prompt version control.** Record what prompt generated what code. Change the prompt, code behavior might change completely. This matters more than git blame.

**Test coverage requirements for AI-generated code.** Human-written code, you roughly know where bugs hide. AI-written code, you don't. So test coverage isn't "recommended"—it's "required." My standard: AI-generated code needs at least 80% coverage, human-written can be lower.

**Context boundary declarations.** AI's context window when generating code is limited. If a function depends on logic outside that window, AI might make wrong assumptions. Marking "this logic depends on X module's Y behavior" in code helps AI not screw up next time it modifies things.

## Bottom Line

Code standards were never the goal—they're the means. Means serve the goal, which is writing usable, maintainable code.

The entity writing code changed, so the means must change too. Rigidly following "functions under 20 lines" is like rigidly following "code must be handwritten"—both turn means into dogma.

Keep what works, toss what doesn't. Don't let rules become rituals.
