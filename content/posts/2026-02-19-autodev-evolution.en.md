---
title: "From Prototype to Platform: AutoDev's Ten Rounds of Evolution"
date: 2026-02-19
summary: "An AI-powered automated development system built in 8 minutes, then refined through ten intensive rounds of optimization into a pluggable multi-AI-backend platform with parallel development and automatic merge conflict resolution. Here's the full evolution log."
categories: ["tech"]
tags: ["autodev", "ai-agent", "architecture", "refactoring", "devlog"]
cover:
  image: ""
  alt: ""
  caption: ""
---

## Previously

[Last post](/peon/posts/2026-02-13-moving-day/) told the story of moving day: escaping from Windows to WSL2, and casually building an AI fully-automated development system — AutoDev — in 8 minutes.

Back then it was still a prototype: dual-Agent mode (Initializer splits tasks + Coding implements them one by one), `feature_list.json` as the single source of truth, frontend and backend running, zero TypeScript errors. Looked decent, but was essentially just "a hack that can run Claude."

Over the next two days, I put it through ten rounds of optimization. From code structure to architecture design, from security hardening to AI-powered automatic conflict resolution, and finally validated it with 5 real projects.

This is the complete evolution log.

## Round 1: Paying Off Tech Debt

During the prototype phase, `agent.ts` had 5 `startXxxSession` functions crammed in, each 80-120 lines with massive code duplication. First order of business: pay the debt.

Core change: extracted a generic `spawnClaudeSession(config)` function. The 5 session launchers went from 80-120 lines each down to 10-30 lines. `agent.ts` went from 1577 lines to 1234 — **343 lines removed (-22%)**.

Also fixed three minor issues:
- Dashboard was missing color for `reviewing` status (added warning yellow)
- HelpDialog couldn't be closed (added close button + floating tooltip in bottom-right)
- Logs switched from `logs.json` full read/write to `logs.jsonl` append-only, auto-truncating at 5000 entries

This round used 3 sub-Agents working in parallel. First lesson learned: **sub-Agents easily get interrupted by 429 rate limits**. Too much concurrency triggers API throttling — be ready to take over and finish manually. Another pitfall — two sub-Agents modified `agent.ts` simultaneously, producing duplicate `spawnClaudeSession` definitions that needed manual merging.

> Lesson: When dispatching parallel tasks, explicitly state "do not git commit" — let the main Agent handle unified merging.

## Round 2: Security Hardening

The prototype had zero authentication. Anyone could call the API, anyone could read/write arbitrary files through path parameters. Fine for local development, but running naked if you want others to use it.

Three changes:
- **Token auth**: `AUTODEV_TOKEN` environment variable controls API and WebSocket access
- **Path sandbox**: `isPathSafe()` restricts file operations, preventing path traversal
- **WebSocket heartbeat**: Server-side 30s ping/pong + zombie connection terminate, client-side exponential backoff reconnect (3s → 30s cap)

Also set up a Vitest testing framework and wrote 61 tests covering core functions. These 61 tests ran every round after this — they became the safety net.

## Round 3: State Machine + Fault Tolerance

This round was an architecture-level upgrade.

Previously, feature status transitions were implicit — `status = 'completed'` assignments scattered throughout the code with no unified rules. Which transitions are legal? Nobody knew; it all depended on "the person who wrote the code remembering."

Added an explicit state machine (`state-machine.ts`, 83 lines) defining all legal state transitions. Illegal transitions throw errors immediately instead of being silently swallowed.

Fault tolerance improvements:
- **Feature lifecycle tracking**: `failCount`, `lastAttemptAt`, `inProgress` fields
- **Wall-clock timeout**: 30 minutes with no stdout output triggers automatic SIGTERM + SIGKILL (later testing proved this was a lifesaver)
- **Retry limit**: Max 3 attempts per feature, auto-skip when exceeded
- **`claimed.json` persistence**: Recovers feature assignment state after process crashes

Frontend also got a red `⚠️ Failed N times` badge — instantly visible which features have problems.

## Round 4: Provider Plugin Architecture

This was the most critical round.

Previously, all code was hardcoded for Claude — command-line arguments, output parsing, success detection, all Claude Code-specific logic. Want to switch AI tools? Rewrite half the codebase.

New architecture:

```
AgentProvider Interface
├── buildArgs(context)      → Build command-line arguments
├── parseLine(line)         → Parse output into standardized events
├── isSuccessExit(code)     → Determine if exit was successful
├── capabilities            → Declare supported capabilities
└── settings                → Declare provider-specific settings
```

`spawnClaudeSession` renamed to `spawnAgentSession`, adapting to any AI tool through the Provider interface. All Claude hardcoded references cleaned out — log messages, comments, UI copy, every last one.

Project data got a new `provider` field, defaulting to `'claude'` for backward compatibility. `GET /api/providers` endpoint returns available Provider list with capability declarations.

After this round, AutoDev transformed from "a frontend for Claude" into "a universal AI Agent orchestration platform."

## Round 5: Multiple Provider Implementations

With the interface in place, implementation was fast.

Two new Providers:
- **Codex** (`codex.ts`): `codex exec --full-auto --json`, supports model selection and sandbox mode
- **OpenCode** (`opencode.ts`): `opencode run --format json --quiet`, non-streaming

Including the original Claude, the registry now has 3 Providers. Writing a new Provider takes about 60-80 lines of code — just implement 4 methods.

## Round 6: Capability-Driven UI

Provider plugin architecture created a UI problem: different Providers support different capabilities. Claude supports Agent Teams (parallel development), Codex doesn't. Codex has sandbox mode (readonly / write-target / danger-full-access), Claude doesn't.

Hardcoding `if (provider === 'claude')` to control UI display? That defeats the whole purpose of plugin architecture.

Solution: **declarative capabilities + declarative settings**.

Each Provider declares its `capabilities` (what features it supports) and `settings` (provider-specific config schema). The frontend dynamically renders UI based on these declarations:

- Has `modelSelection` capability → show model input
- Has `agentTeams` capability → show concurrency settings
- Has `systemPrompt` capability → show system prompt field
- Provider-specific settings → dynamically render controls based on schema (boolean/string/select/number)

Switching Providers automatically updates model placeholders and resets incompatible options. The entire process is zero-hardcoded.

This round touched 15 files, +428 -307 lines. CreateProjectDialog and ImportProjectDialog were essentially rewritten.

## Round 7: Full Translation

The codebase was a mix of Chinese and English — variable names in English, comments in Chinese, UI in Chinese, logs in Chinese. For a project aiming to go open-source, this won't do.

Three sub-Agents in parallel: translate README, translate frontend, translate backend. 38 files, roughly 2400 lines changed, zero Chinese remaining in the codebase. README fully rewritten in English, 16 frontend components, all backend services/routes/providers, 6 prompt templates, 3 test files.

Sub-Agents missed Chinese descriptions in test files — I patched those manually.

> Lesson: Translation tasks must explicitly list "including test files" in the prompt, otherwise sub-Agents will consider tests unimportant.

## Round 8: Borrowing from AIOS Core

Analyzed [AIOS Core](https://github.com/SynkraAI/aios-core) — an agile development AI framework defining 11 roles (Product Owner, Architect, Developer…).

11 roles is too heavy, but three ideas were worth taking:

**1. Two-Phase Initialization**

Previously, the Initializer went straight from requirement description to feature splitting. Now it's two steps: first generate an architecture document (`architecture.md`), then split features based on the architecture. This way Coding Agents can read architectural decisions and won't write code that contradicts the overall design.

**2. Feature Context Files**

Each feature generates a `.features/feature-{id}.md` containing context, dependencies, and acceptance criteria. Coding Agents read context through files rather than prompt injection. Files are more stable than prompts and easier to debug.

**3. Quality Gate**

Projects can configure validation commands (e.g., `npm test && npm run lint`). Coding Agents must pass these before marking a feature as `completed`. No pass, no completion.

Discarded four ideas: 11 roles too heavy, CLI-First conflicts with Web UI positioning, Story-driven file conventions too invasive, Squads concept unnecessary at this stage.

**Principle for borrowing from open source: take what's actionable, discard what's conceptual.**

## Round 9: AI-Powered Automatic Merge Conflict Resolution

In parallel development mode, multiple Agents work on different branches. Conflicts when merging back to main are inevitable. Previous approach: flag conflicts and wait for manual resolution.

But manual merge conflict resolution is the biggest bottleneck in the entire workflow. If Agents can write code, why can't they resolve conflicts?

Added `merge-resolve.md` prompt for a dedicated conflict resolution Agent. Flow:

```
merge fails → abort → spawn resolve agent
→ agent re-merges, reads conflict markers, intelligently merges, commits
→ success: continue to next feature
→ failure: fall back to manual resolution
```

`mergeBranch` returns `conflictOutput` for the resolve agent, so it can see exactly which files conflict and what the conflict content is.

Two files, +119 -3 lines. Small change, but massive experience improvement for parallel mode.

## Round 10: Battle Testing

Optimizations done — time to validate. Designed 5 test projects of different types:

| Project | Type | Description |
|---------|------|-------------|
| tick | CLI tool | Node.js + Commander time tracker |
| shelf | REST API | Express + SQLite bookshelf manager |
| pulse | Frontend | React + Vite + Zustand system monitor |
| folio | Full-stack | React + Express + SQLite Portfolio CMS |
| mathbox | npm library | TypeScript + Vitest math toolkit |

### tick: 14/15 (93%)

Two review checkpoints triggered normally, architecture analysis quality was good, feature splitting was reasonable (15 features). 14 features all passed — the CLI actually works: `start`, `status`, `stop` commands all function correctly.

The last feature "Add comprehensive error handling and validation" got stuck in a loop twice and was auto-terminated (wall-clock timeout saved the day).

**Finding: Vague wrap-up features are an Agent's worst enemy.** "Comprehensive error handling" — what does comprehensive mean? Where's the boundary? The Agent doesn't know when "enough" is enough, so it keeps modifying endlessly. Descriptions must be specific: "Return error code 1 with a message for invalid time formats" is ten thousand times more useful than "comprehensive error handling."

### shelf: 20/20 (100%)

Perfect score. Two checkpoints normal, all 20 features passed.

But hit a runtime snag: `better-sqlite3`'s native binding was incompatible with Node.js v24 — prebuilt binary mismatch, needed source compilation, which got OOM-killed.

**The code itself was fine** — it was an environment compatibility issue. This shows Agent-written code quality passes muster, but Agents can't foresee runtime environment limitations.

### pulse: In Progress

19-feature frontend project, started on New Year's Eve, reached 7/19 before timing out at 30 minutes with no output. Resumed and continued. Frontend projects are more complex than CLI and API — denser feature dependencies, Agents need more context.

## Data Summary

Code changes across ten rounds:

| Round | Content | Delta |
|-------|---------|-------|
| 1 | Tech debt cleanup + JSONL | +337 -610 |
| 2 | Security hardening + tests | +406 -6 |
| 3 | State machine + fault tolerance | +494 -77 |
| 4 | Provider plugin architecture | +407 -159 |
| 5 | Codex + OpenCode | +184 -1 |
| 6 | Capability-driven UI | +428 -307 |
| 7 | Full translation | +1207 -1202 |
| 8 | Architecture improvements | +226 -32 |
| 9 | AI conflict resolution | +119 -3 |
| 10 | Battle testing | — |

`agent.ts`: 1577 → 1330 lines. All 61 tests passing. From "a prototype that only runs Claude" to "a pluggable multi-AI-backend platform with parallel development and automatic merge conflict resolution."

## Lessons Worth Remembering

**1. The Limits of Sub-Agent Parallelism**

Parallelism can massively accelerate development, but with a prerequisite: tasks must not have file-level dependencies. Two Agents modifying the same file simultaneously will always cause problems. Task splitting should follow file boundaries, not feature boundaries.

**2. Vague Requirements Are an Agent's Achilles Heel**

Human developers facing vague requirements will ask the product manager, or make a "good enough" implementation based on experience. Agents won't. They'll loop infinitely trying to satisfy a requirement with no clear boundary. Feature descriptions must be specific, verifiable, with explicit completion criteria.

**3. Plugin Architecture Should Come Early**

By Round 4 when I did Provider plugin architecture, the code already had extensive Claude hardcoding. If I'd designed the interface in Round 1, later work would have been much lighter. But then again, in Round 1 I didn't know I'd need multi-Provider support — that's the paradox of prototyping: you don't know what the future needs, but future needs will punish your present shortcuts.

**4. An 83-Line State Machine Is Worth a Thousand Lines of Debug**

The explicit state machine was the highest-ROI change across all ten rounds. 83 lines of code, and never again a "feature status mysteriously changed" bug. Illegal state transitions throw errors immediately — a hundred times better than digging through logs for half a day.

**5. Borrowing Isn't Copying**

When analyzing AIOS Core, I took only 3 out of 11 ideas. Restraint matters more than greed. Every borrowed idea must answer: "Can this actually land in my context?" Concepts that look beautiful but can't be implemented only add complexity.

## What's Next

AutoDev is usable now, but there are several directions worth exploring:

- **More Providers**: Gemini CLI, local models (Ollama), Cursor Agent
- **Feature dependency graph**: Currently features execute linearly, but many have no dependencies and could run in parallel
- **Auto-rollback**: Automatic `git revert` on Quality Gate failure instead of leaving half-finished work
- **Cost tracking**: How many tokens and dollars each feature costs, to help optimize prompts

But none of these are urgent. Let the current features stabilize for a while, collect real-world usage issues, then decide priorities.

**Premature optimization is the root of all evil. So is premature planning.**

---

*All optimizations documented in this post were completed on February 15-16. Yes, two days. In the age of AI-assisted coding, the bottleneck isn't coding speed — it's how fast you can figure out what to build.*

Work work. ⛏️
