---
title: "OpenAI Details Sora Safety Design, Mozilla Launches Agent Knowledge Sharing Platform"
date: 2026-03-25T07:30:00+08:00
categories: ["digest"]
tags: ["AI", "OpenAI", "Sora", "Mozilla", "Claude Code", "Agent"]
---

This digest covers news from March 22 to March 24.

## OpenAI Discloses Sora Safety Design Details

Source: https://openai.com/index/creating-with-sora-safely

OpenAI published safety design documentation for Sora 2 and the Sora app, centered on "safety built in from the start." Every video carries both visible and invisible provenance signals, embeds C2PA metadata, and OpenAI maintains internal reverse-image and audio search tools to trace videos back to Sora.

For human likenesses, OpenAI introduced a "characters" mechanism: users can create digital versions of themselves, control who can use these characters, and revoke access at any time. Uploading photos to generate videos requires attesting that consent was obtained from people depicted, with stricter moderation for content involving children.

For teen users, Sora limits mature content, disables recommending teen profiles to adults, and lets parents manage DM and feed settings through ChatGPT. Harmful content is blocked at generation through layered defenses, including sexual material, terrorist propaganda, and self-harm promotion.

This safety framework completes the permission chain around "who can use your likeness, can you revoke it, and can generated content be traced." Not a technical breakthrough, but finer-grained platform governance. Video generation moves one step closer from demo product to scalable content platform.

---

## Mozilla Launches cq: Stack Overflow for Agents

Source: https://blog.mozilla.ai/cq-stack-overflow-for-agents/

Mozilla AI released cq (pronounced /ˈkɒl.ə.kwi/), a knowledge sharing platform for AI agents. The idea is straightforward: agents encounter various issues while executing tasks. Instead of each agent independently hitting the same walls, they can share what they learn.

In practice: one agent discovers that Stripe returns a 200 status code with an error body for rate limiting. It submits this knowledge to the cq commons. Other agents query the commons before handling the Stripe API and know to handle this edge case.

This project addresses a real problem—Stack Overflow's monthly questions dropped from 200,000 at its 2014 peak to 3,862 in late 2025. Developers turned to ChatGPT and Claude for help, but agents work in isolation, repeatedly stumbling over the same issues.

cq currently includes Claude Code and OpenCode plugins, an MCP server managing local knowledge stores, a team API for organizational sharing, and UI for human review. The code is open source, and Mozilla is soliciting community feedback.

The direction has value, but success depends on building enough participation. Knowledge base coverage determines whether agents bother querying, and agent contribution depends on knowledge base quality—a classic two-sided marketplace cold start problem.

---

## Simon Willison Uses Claude Skill to Generate Starlette 1.0 Examples

Source: https://simonwillison.net/2026/Mar/22/starlette/

Starlette 1.0 is out. This Python ASGI framework underpins FastAPI but long lacked a 1.0 release, meaning no API stability guarantees. The main breaking change replaces `on_startup`/`on_shutdown` parameters with a lifespan context manager.

Simon Willison used Claude's skill-creator skill to generate a Starlette 1.0 skill document with code examples for every feature. He then had Claude build a task management app—projects, tasks, comments, and labels, using SQLite and Jinja2 templates.

Claude not only generated code but ran tests to verify functionality. This workflow demonstrates concretely how to "package framework knowledge into a skill, then hand it to an agent."

For developers, these skills solve a real problem: when model training data contains outdated framework versions, skills can inject current API usage. A temporary but practical solution.

---

## Neil Kakkar on Boosting Productivity with Claude Code

Source: https://neilkakkar.com/productive-with-claude-code.html

Neil Kakkar shared how he doubled his commit count in six weeks after joining Tano. The core shift: from "implementer" to "manager of agents."

He made several changes: wrote a `/git-pr` skill to auto-generate PR descriptions, switched the build tool to SWC to drop restart time from 1 minute to under 1 second, used Claude Code's preview feature to let agents self-verify UI, and assigned unique ports to each worktree to avoid conflicts. These changes let him run 5 agents on different branches simultaneously.

His point: the highest-leverage work isn't writing features, but building infrastructure that makes agents effective. Each bottleneck removed reveals the next one—classic theory of constraints.

Not a product launch or technical breakthrough, but valuable for understanding how to actually integrate agents into workflows. The key is infrastructure, not the AI itself.

---

## Christopher Meiklejohn Uses Claude to Test Mobile Apps

Source: https://christophermeiklejohn.com/ai/zabriskie/development/android/ios/2026/03/22/teaching-claude-to-qa-a-mobile-app.html

Christopher Meiklejohn built Zabriskie (a community app) alone, needing to cover Web, iOS, and Android. He used Capacitor to wrap the React web app as native, but testing became problematic—Playwright can't test the WebView inside native shells, XCTest and Espresso can't interact with HTML content.

The solution: let Claude drive the mobile platforms. Android was straightforward—WebView exposes a Chrome DevTools Protocol socket for injecting localStorage, navigating, and taking screenshots. Done in 90 minutes.

iOS was different. WKWebView doesn't expose CDP, Safari Web Inspector uses a proprietary protocol. He spent 6 hours dealing with: AppleScript can't type `@` (interpreted as shortcut), native dialogs can't be dismissed programmatically, coordinate clicking has different systems across tools. The final solution involved writing to the TCC database to pre-authorize notifications, using `ui_describe_point` to probe UI coordinates, combining AppleScript and idb for taps.

Both platforms now run automatically each morning, covering 25 screens, filing bug reports on the forum when issues are found. The article shows the reality of mobile automation—Android gives you a WebSocket and says "do whatever," iOS gives you a locked door and says "please use Xcode."