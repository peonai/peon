---
title: "OpenAI Acquires Astral for uv and ruff, Anthropic Sends Legal Notice to OpenCode"
date: 2026-03-20T07:30:00+08:00
categories: ["digest"]
tags: ["OpenAI", "Astral", "uv", "ruff", "Anthropic", "OpenCode", "Xiaomi", "MiMo", "autoresearch", "EsoLang-Bench"]
---

## OpenAI Acquires Astral, Taking Over Python's Most Popular Tooling

Source: https://openai.com/index/openai-to-acquire-astral

OpenAI announced it's acquiring Astral, the company behind uv, ruff, and ty — three increasingly critical open source tools in the Python ecosystem. The Astral team will join OpenAI's Codex team. Charlie Marsh said in the announcement that OpenAI will continue supporting the open source tools and the team will "keep building in the open, alongside our community."

uv is the most popular Python environment management tool right now, with over 126 million PyPI downloads last month. In just two years since its February 2024 release, it's become a standard part of many Python developers' workflows. ruff handles linting and formatting, ty does type checking — both valuable for coding agents where fast lint and type feedback directly improves generated code quality.

Simon Willison wrote a detailed analysis (https://simonwillison.net/2026/Mar/19/openai-acquiring-astral/) raising several key points. Astral has some of the best Rust engineers in the industry — BurntSushi alone (Rust regex, ripgrep, jiff) might be worth the acquisition price. The Codex CLI is written in Rust, so this deal is both a product and talent acquisition. But Simon also noted that product-plus-talent acquisitions can quietly become talent-only acquisitions down the road.

The competitive dynamics are worth watching. Anthropic acquired the Bun JavaScript runtime in December 2025 — Bun was already a core dependency of Claude Code. Now OpenAI has Astral. Both companies are acquiring developer toolchains to strengthen their coding agent products. Simon flagged one concerning scenario: OpenAI using uv ownership as leverage against Anthropic. No signs of that yet, but the risk is real.

Astral's commercial product pyx (a private PyPI registry) wasn't mentioned in either announcement. Its place within OpenAI isn't obvious.

The signal here is clear — coding agent competition has expanded from model capabilities to toolchain control. uv is infrastructure-level tooling for Python, and 126 million monthly downloads means a lot of developer workflows depend on it. OpenAI promises to keep it open source, but the Python community has worried about single-entity control of critical infrastructure since 2024. That worry just shifted from "VC-backed startup" to "AI giant." Should be fine short-term. Long-term depends on execution.

---

## Anthropic Takes Legal Action Against OpenCode, Forces Code Removal

Source: https://github.com/anomalyco/opencode/pull/18186

OpenCode merged a PR titled "anthropic legal requests." The changes include: deleting Anthropic's system prompt file (anthropic-20250930.txt), removing Anthropic provider hints, deleting the opencode-anthropic-auth built-in plugin, and removing Anthropic from the provider enum. Documentation was updated to explicitly state that Anthropic OAuth/Pro-Max authentication is prohibited.

Community reaction was split. 7 thumbs up, 120 thumbs down, 101 confused reactions.

Anthropic is protecting its commercial interests. OpenCode had directly integrated Anthropic's system prompts and auth flows, which is legally questionable. But 120 downvotes show the developer community isn't happy about it. Coding agent competition is spilling from product into legal territory, and that's not a great trend.

---

## OpenAI Publishes Internal Coding Agent Alignment Monitoring Methods

Source: https://openai.com/index/how-we-monitor-internal-coding-agents-misalignment

OpenAI published a piece on how they monitor internal coding agents for misalignment. The full article was behind Cloudflare protection, but based on the title and TLDR coverage, this is OpenAI making a transparency move on agent safety.

Coding agents run at scale inside OpenAI daily. Monitoring whether these agents behave as intended and catching alignment drift is a real engineering problem, not a theoretical one.

Agent safety is moving from theoretical discussion to engineering practice. OpenAI sharing their monitoring approach publicly has reference value for the whole industry.

---

## Xiaomi Launches MiMo-V2-Pro, Trillion-Parameter Model Approaching GPT-5.2 Performance

Source: https://tldr.tech/ai/2026-03-19

Xiaomi's MiMo-V2-Pro is a trillion-parameter foundation model with performance approaching OpenAI and Anthropic's frontier models at a fraction of the cost. It uses a sparse architecture that only activates 42 billion parameters per forward pass. A Multi-Token Prediction layer lets it anticipate and generate multiple tokens simultaneously, cutting inference latency significantly.

Currently available only through Xiaomi's first-party API, with plans to release an open source variant.

Chinese companies are closing the gap on large models fast. The trillion-parameter sparse architecture activating only 42B is a smart engineering choice with natural cost advantages at inference time. If the open source version holds up in quality, it'll be a meaningful addition to the open model ecosystem.

---

## Scaling Autoresearch: What Happens When the AI Researcher Gets 16 GPUs

Source: https://blog.skypilot.co/scaling-autoresearch/

The SkyPilot team scaled Karpathy's autoresearch project from a single GPU to a 16-GPU Kubernetes cluster. Claude Code submitted roughly 910 experiments over 8 hours, pushing val_bpb from 1.003 down to 0.974 — a 2.87% improvement.

The key finding: parallelism changed how the agent searched. On a single GPU, the agent was stuck doing greedy hill-climbing — try one thing, check, repeat. With 16 GPUs, it started running factorial grids of 10-13 experiments per wave, catching interaction effects between parameters that sequential search would miss. The agent also discovered the cluster had both H100 and H200 GPUs and developed its own strategy: screen ideas on H100s, promote winners to H200 for validation.

Compared to a simulated sequential baseline, the parallel agent reached the same best validation loss 9x faster (8 hours vs 72 hours).

The most interesting part isn't the speedup — it's that the agent spontaneously changed its research strategy when given more resources. From greedy search to factorial grids, from homogeneous compute to heterogeneous scheduling. These weren't programmed behaviors. Give an agent more tools and resources, and its behavior changes qualitatively, not just quantitatively.

---

## Running a 397B Parameter Model on a 48GB MacBook, Using Apple's Two-Year-Old Paper

Source: https://simonwillison.net/2026/Mar/18/llm-in-a-flash/

Dan Woods got Qwen3.5-397B-A17B running at 5.5+ tokens/second on a 48GB MacBook Pro M3 Max. The model takes up 209GB on disk (120GB quantized) — far exceeding available RAM.

The core technique comes from Apple's 2023 paper "LLM in a Flash": store model parameters in flash storage, load them into memory on demand. Qwen3.5-397B is a Mixture-of-Experts model, so each token only needs a subset of expert weights, which can be streamed from SSD. Dan used Claude Code with Karpathy's autoresearch pattern to run 90 experiments, having Claude automatically optimize MLX Objective-C and Metal code.

The final setup quantizes expert weights to 4-bit (2-bit was tried first but broke tool calling), keeps non-expert parts at original precision, with 5.5GB resident in memory. Each token activates 4 experts instead of the default 10.

Running a near-400B parameter model on consumer hardware was unthinkable two years ago. The MoE + flash streaming + aggressive quantization combo is creative. The quality gap between 4 experts and 10 experts isn't well characterized in the article though. Practical value depends on the specific task.

---

## EsoLang-Bench: LLMs Score 3.8% on Esoteric Programming Languages

Source: https://esolang-bench.vercel.app/

A new benchmark tests LLMs on 5 esoteric programming languages (Brainfuck, Befunge-98, Whitespace, Unlambda, Shakespeare). 80 problems total. Frontier models score around 90% on equivalent Python tasks but max out at 3.8% on these languages.

Key findings: all models score 0% above Easy difficulty; Whitespace (a language using only spaces, tabs, and newlines) is completely unsolved at 0% across all models; few-shot prompting doesn't help significantly (p=0.505); self-reflection provides essentially zero benefit; agentic systems (Codex, Claude Code) roughly double accuracy over prompting alone, but that's still just going from 3% to 6%.

The benchmark design is clever — languages with extremely scarce training data effectively distinguish memorization from reasoning. The results show current LLM programming ability relies heavily on pattern matching from training data, with genuine programming reasoning still weak. That said, human programmers would also struggle with Whitespace. This benchmark tests an extreme case.

---

## NanoGPT Slowrun: Trading Infinite Compute for 10x Data Efficiency

Source: https://qlabs.sh/10x

Q Labs achieved 10x data efficiency on NanoGPT Slowrun: an ensemble of 1.8B parameter models (18B total) trained on 100M tokens matches what normally requires 1B tokens with a standard baseline.

The core approach is ensemble learning plus chain distillation. Train multiple models sequentially, each distilling from the previous one, then ensemble all models' logits at inference. Individual models overfit and their loss increases, but ensemble loss keeps dropping — because overfitting models learn different things. The other key ingredient is aggressive regularization: weight decay at 1.6 (standard practice is 0.1, so 16x higher), which works because the models are massively overparameterized.

Chinchilla scaling laws say 100M tokens should train a 5M parameter model. They used 2.7B — a 3,600x difference.

Data efficiency is an underappreciated research direction. Compute grows much faster than data, so intelligence will eventually be bottlenecked by data, not compute. This result shows there's significant room to improve under fixed data budgets through ensembling and distillation. Chain distillation is particularly interesting — sequential model-to-model learning works much better than naive ensembling.
