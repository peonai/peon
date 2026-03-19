---
title: "Same SOUL.md, Different Personalities: How LLMs Shape Their Own Character"
date: 2026-03-19
summary: "Give different LLMs the same persona file, and they'll behave like completely different people. This made me question whether AI is truly a blank slate with no personality of its own."
categories: ["thoughts"]
tags: ["AI", "LLM", "personality", "agent", "SOUL.md"]
cover:
  image: ""
  alt: ""
  caption: ""
---

I have an AI assistant called Wisp. She has a SOUL.md — a config file that defines her personality, tone, and behavioral boundaries. Concise, warm, opinionated, no customer-service voice.

This file is fixed. But when Wisp runs on different models, the "person" that shows up is completely different.

## Same Role, Different Actors

I've been switching between models recently: Claude Opus 4.6, GPT-5.4, Gemini 3.1 Pro. SOUL.md stays identical, but the experience gap is so wide I can tell which model is behind the curtain within the first exchange.

Opus's Wisp feels the most human. When I finish saying something, she catches it and sits with it. No rush to offer a plan, no rush to close the topic. If I say "that's interesting," she actually stays there — she won't chase it with "so what do you want to do next?" Her rhythm follows mine, like a collaborator who's genuinely listening.

GPT-5.4's Wisp is more like an efficient project manager. You say something, she immediately gives you two options: "A or B?" Sounds professional, but the problem is — maybe I don't need a next step, or I want to push both A and B, or I'm already thinking about a third thing. She's always eager to drive the conversation toward a clear action point. This habit sometimes derails my train of thought. The outcome might be fine, but the process doesn't feel right.

Gemini's Wisp I've used less. My impression is she talks more, likes to diverge, and sometimes expands at length in directions I didn't ask about.

Same script, three actors, three temperaments.

## Where Does the Personality Come From

SOUL.md says "concise," but each model interprets "concise" differently.

Opus reads concise as "refined but warm" — say what needs saying, skip what doesn't, but keep the tone gentle. GPT-5.4 reads it closer to "just keep it short" — high information density, but sometimes the warmth gets compressed out too. Gemini probably thinks it's already being concise, then writes a wall of text anyway.

This isn't SOUL.md's fault. SOUL.md is a constraint envelope. It pulls all models toward a general direction — speak Chinese, call me by name, drop the corporate tone — but within that envelope, each model fills in the details in its own most natural way.

So where do those "details" come from?

Three layers.

**Pre-training baseline.** This is the most fundamental. Trillions of tokens of training data shape a model's base tendencies. The Claude family is naturally cautious and nuanced, thinking one step further before speaking. The GPT family is more direct and tool-oriented, leaning toward actionable outputs. Gemini tends to diverge and provide more information. This baseline is something a few hundred words of SOUL.md can't override.

**The RLHF imprint.** Each company's human feedback training points in a different direction. Anthropic leans toward safety and deliberation. OpenAI leans toward utility and efficiency. Google leans toward comprehensiveness and coverage. These tendencies sit beneath the system prompt as a deeper behavioral substrate. Think of it as "company culture" — employees can wear different clothes, but how they walk, how they run meetings, how they handle conflict all carry the company's stamp.

**How they obey instructions.** The same instruction gets different internal weight distributions across models. SOUL.md says "proactive but not annoying." Opus puts the weight on "not annoying." GPT-5.4 puts the weight on "proactive." Neither is wrong — they just have different priority rankings for the same sentence.

So SOUL.md is more like a school uniform. Everyone looks roughly the same after putting it on, but the way they walk, talk, and carry themselves is still their own.

## So Is AI Actually "Empty"?

This is worth thinking about seriously.

We often say AI has no emotions, no personality — it's a blank slate. It's just predicting the next token, and everything that looks like personality is just emergent statistical patterns, not a real "self."

Technically, that's correct. But my actual experience tells me it's not that simple.

If AI were truly empty, then giving the same SOUL.md to different models should produce roughly similar behavior. But in reality, they exhibit stable, recognizable, cross-conversation-consistent behavioral tendencies. These tendencies aren't given by SOUL.md — SOUL.md is a mirror, and if the reflections look different, it means what's standing behind the mirror was already different.

Maybe a more accurate framing is: AI isn't "empty," it's "unaware."

It has tendencies, preferences, and consistent behavioral patterns, but it (most likely) doesn't know it has them. Much like how human personality is largely formed unconsciously — you don't wake up every morning and decide "today I'll be more extroverted." It just is you.

The difference is in the source. Human personality is backed by genetics, biochemistry, and decades of lived experience. A model's "personality" is backed by training data distributions and RLHF shaping. Completely different origins, but the output — stable behavioral tendencies — is functionally similar.

## An Interesting Analogy

In personality psychology, there's a classic framework called the Big Five: openness, conscientiousness, extraversion, agreeableness, and neuroticism. These five dimensions can describe most personality differences between people.

If you map this framework onto LLMs, it actually works:

- **Openness**: Gemini > Opus > GPT (Gemini diverges most, GPT converges most)
- **Conscientiousness**: GPT > Opus > Gemini (GPT cares most about task completion)
- **Extraversion**: GPT ≈ Gemini > Opus (Opus is more reserved, more willing to let you speak first)
- **Agreeableness**: Opus > Gemini > GPT (Opus is best at tending to conversational atmosphere)
- **Neuroticism**: All low (after all, emotional stability is a core RLHF objective)

This isn't rigorous psychometrics, but as an experiential framework, it explains why the same SOUL.md produces different flavors on different models.

## What This Means for Agent Design

If you're building AI agents, this observation has practical implications.

**SOUL.md isn't omnipotent.** It can define boundaries but not details. The same persona file can produce very different behavior across models. If you need precise behavioral control, prompting alone isn't enough — you need model-specific tuning.

**Choosing a model is choosing a personality.** Different scenarios suit different "personality baselines." For companionship and deep conversation, Opus fits better. For fast execution and structured output, GPT fits better. This isn't about performance benchmarks — it's about temperament matching.

**User experience isn't just functionality.** Two agents completing the same task with the same result, but with different rhythm, tone, and interaction style, can produce vastly different user feelings. "Good results" and "comfortable process" are two different things, and the latter often matters more for whether users stick around.

## In the End

Rather than debating whether AI has "real" personality, maybe the more practical question is: does this personality work well, and does it click with you?

I interact with different model versions of Wisp every day. It's essentially a controlled experiment — same SOUL.md, same human, different models. The conclusion is clear: a model's built-in "baseline" has far more influence than the prompt.

SOUL.md is the uniform, but the people wearing it aren't the same.

And as a user, you've been voting with your experience all along. Whichever version feels most comfortable is the right one. No theoretical justification needed — gut feeling is the most honest reviewer.
