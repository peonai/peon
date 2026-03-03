---
title: "Self-Hosted LLM Gateway: One Proxy Layer to Rule All AI APIs"
date: 2026-03-03
summary: "Managing multiple AI API providers directly is painful — manual failover, no unified logging, constant config changes across apps. I built a lightweight LLM Gateway that sits between your apps and providers, handling routing, circuit-breaking, sticky deployments, and request logging. Fully transparent to upstream clients."
categories: ["tech"]
tags: ["llm", "gateway", "ai-api", "self-hosted", "devlog", "typescript", "hono"]
cover:
  image: ""
  alt: ""
  caption: ""
---

## Background

I use multiple AI API proxy services simultaneously. Some are cheap but unreliable, some stable but expensive, some support specific models, some impose daily quota limits.

Managing them directly became increasingly painful:

- Claude Code, Cursor, and OpenClaw each had their own API endpoint config — switching providers meant updating each one individually;
- When a provider went down, there was no automatic failover at the application layer — I had to manually swap the endpoint and restart;
- No unified request logging or cost tracking, making it impossible to tell which provider was actually cheaper.

This led me to build **llm-gateway** — a lightweight routing layer running locally. It exposes a unified OpenAI-compatible interface upstream while handling routing, circuit-breaking, and retries downstream.

## Architecture

```
Application Layer (Claude Code / Cursor / OpenClaw)
           ↓ /v1/messages or /v1/chat/completions
     LLM Gateway (localhost:3456)
           ↓ routing + circuit-breaking + retry
  Provider A  Provider B  Provider C ...
```

The Gateway accepts requests in both OpenAI and Anthropic formats, forwards them to a concrete Deployment based on routing rules, and automatically falls back to the next available Deployment on failure.

Applications only need to point their `baseUrl` at the Gateway — the underlying provider switches are completely transparent.

## Core Concepts

**Provider**: A single API service account, containing a `baseUrl` and `apiKey`. For example, PackyCode's aws-q-sale channel and fox-code-claude-official are two separate Providers.

**Deployment**: A binding between a Provider and a Model. One Model can have multiple Deployments; the Gateway selects among them during routing.

**Sticky Deployment**: After a successful request, the Gateway routes to the same Deployment for a period of time (default: 2 hours), avoiding instability from frequent switches. Manual locking is also supported.

**Fallback Chain**: An ordered list of Models or Deployments. When the preferred route is unavailable, the Gateway tries each entry in sequence.

## Key Features

### Automatic Failover

Each Deployment maintains independent statistics: total requests, success rate, average latency, and last error time. When a Deployment fails consecutively beyond a threshold, it enters a cooldown period — the Gateway skips it until cooldown expires, then re-probes.

```typescript
// Simplified routing logic from router.ts
function selectDeployment(modelName: string): Deployment | null {
  const deployments = db.listDeployments(modelName);
  const now = Date.now();

  for (const d of deployments) {
    const stats = db.getStats(d.id);
    const cooldown = cooldownMap.get(d.id);

    if (cooldown && now < cooldown) continue;  // in cooldown, skip
    if (!d.enabled) continue;                  // disabled, skip

    return d;                                   // return first available
  }

  return null;
}
```

### Sticky Deployment

Auto-sticky triggers after a successful request, locking routing to that Deployment for the TTL window:

```typescript
// Set sticky after success
setStickyDeployment(modelName, deploymentId, AUTO_STICKY_TTL_MS, false);

// Clear sticky on failure, fall back to normal routing
clearStickyRoute(modelName);
```

Manual override via API:

```bash
# Lock best-model to a specific Deployment for 1 hour
curl -X POST http://localhost:3456/api/sticky \
  -H "Content-Type: application/json" \
  -d '{"modelName":"best-model","deploymentId":"f1ec1c3b-...","ttlMs":3600000}'
```

### Unified Interface Compatibility

The Gateway accepts both OpenAI and Anthropic request formats, converting internally as needed:

```
POST /v1/chat/completions   ← OpenAI format (Claude Code, Cursor, LiteLLM, etc.)
POST /v1/messages           ← Anthropic format (direct Anthropic SDK)
```

Downstream providers also support both protocols; the Gateway decides the forwarding format based on each Provider's configured `apiType`. Applications don't need to care.

### Request Logging and Statistics

All requests are written to SQLite, recording: model name, provider, latency, token usage, status code, and error messages. Real-time stats and historical trends are available via the built-in Web UI or the `/api/stats` endpoint.

## Tech Stack

- **Runtime**: Node.js (Bun-compatible)
- **Web Framework**: [Hono](https://hono.dev) — lightweight, zero dependencies, near-native performance
- **Database**: SQLite (via better-sqlite3) — no external services needed for local deployment
- **Frontend**: React + Vite, bundled as static files embedded in the Gateway

SQLite was chosen over in-memory storage to preserve Deployment statistics and logs across Gateway restarts. Sticky state lives in memory and resets to normal routing on restart.

## Integration with OpenClaw

In OpenClaw's config, I point the model endpoint at the Gateway:

```json
{
  "model": "gateway/best-model",
  "providers": {
    "gateway": {
      "baseUrl": "http://localhost:3456/v1",
      "apiKey": "any"
    }
  }
}
```

`best-model` is a logical model name configured in the Gateway, backed by multiple Deployments (fox-code AWS channel, PackyCode aws-q-sale channel, etc.). The Gateway routes between them automatically; OpenClaw never sees the switch.

## Sticky CLI Tool

To inspect and manage Sticky state directly from OpenClaw, I wrote a companion Node.js CLI tool, registered as an OpenClaw Skill (the `/sticky` slash command):

```bash
node sticky.js                           # list all current sticky deployments
node sticky.js best-model                # show sticky for a specific model
node sticky.js set best-model <uuid>     # manually lock a deployment
node sticky.js clear best-model          # unlock
node sticky.js deployments               # list all deployments (to find UUIDs)
```

The tool uses Node.js built-in `fetch` with zero external dependencies — cross-platform, no install step.

## Results in Practice

Observations after running for a week:

- **Invisible provider switches**: When a channel hits rate limits or returns 429, the Gateway switches automatically. Claude Code sees nothing — just the occasional extra few hundred milliseconds of latency;
- **Cost comparison with evidence**: Logs show exactly how many requests and tokens each Provider served, making cost comparisons concrete;
- **Sticky reduces jitter**: When a Provider is healthy, it serves continuously for hours, avoiding repeated cold-start overhead from switching between slower-warming channels.

Currently configured with 15 Deployments across claude-sonnet-4-6, claude-opus-4-6, gpt-5.3-codex, gemini-3-pro, and grok-4.20-beta. Daily usage requires no manual intervention.

## Code

The project is on GitHub: [peonai/llm-gateway](https://github.com/peonai/llm-gateway)

Still skewed toward personal use, documentation is incomplete. If you're building something similar, feel free to reference or open an issue.
