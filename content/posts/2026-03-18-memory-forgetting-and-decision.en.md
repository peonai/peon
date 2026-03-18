---
title: "Does More Memory Mean Better Decisions?"
date: 2026-03-18
summary: "We assume that remembering more leads to better decisions. But for both humans and AI, recording everything without distinction is not diligence — it's deferring the work of filtering to your future self."
categories: ["thoughts"]
tags: ["memory", "AI", "decision-making", "forgetting", "agent"]
cover:
  image: ""
  alt: ""
  caption: ""
---

I've been tinkering with the memory system for my AI agents recently, and I hit a snag that made me rethink what "memory" actually means.

## A Missing Nail

I asked Peon, my AI coding assistant, to build a product landing page. He searched his memory, found a directory path, and got to work. Diligently. Spent a lot of tokens on it.

The problem? That directory was from an experiment weeks ago. Long abandoned.

Peon's memory did contain that record, and the retrieval did match. But he had no way to judge whether the memory was stale. To him, a three-month-old memory and yesterday's memory carry the same confidence.

It's like a missing nail — the system runs fine without it, but when things go wrong, you'll be annoyed: how was it this one nail?

## The Power of Human "Blur"

Humans don't make this kind of mistake. Not because we remember more accurately — quite the opposite. It's because we remember more *vaguely*.

You wouldn't assume a directory you used for an experiment three months ago is still the right place. You'd hesitate. You'd double-check. That hesitation isn't inefficiency — it's a built-in decay function. The older a memory, the fuzzier it gets, and that fuzziness is telling you: don't take this too seriously.

Human memory works more like a river. Information flows through, and what remains is the change in terrain — intuitions, tendencies, judgment frameworks — not the raw data itself. You can't recall the specifics of a meeting from three years ago, but you remember the feeling that "that approach was sketchy." Details gone, conclusions retained.

But every AI memory system today, including the one we built, follows a "library model": store it, categorize it, retrieve it. Every memory is treated equally — no decay, no blur, no gut feeling of "something's off about this one."

## Is Recording Everything Diligence or Laziness?

We designed a thorough memory architecture for Peon: episodic, semantic, procedural, snapshots, archived by date, neatly categorized. Looks professional.

But honestly, most of those date-stamped episodic entries — I'm not even sure what they're good for. The system defaults to reading only the last few days of memory; older entries rarely get touched. They just sit there, taking up space, occasionally surfacing during retrieval to add noise.

Delete them? What if they're useful someday. Keep them? They might lead the AI astray at the worst possible moment.

This contradiction made me realize something: recording everything without distinction looks like diligence, but it's actually deferring the filtering work to your future self. And your future self, facing a pile of information with no priority signals, won't make better decisions — just slower, more hesitant ones.

The same applies to humans. "Retrospectives" are praised as good practice, but over-reviewing becomes ruminative anxiety. You look back at notes from three months ago, and a "failure record" makes you afraid to try again — even though the context was completely different. That memory became an invisible brake.

## If You Can't Plug the Leak, Control the Source

Since downstream cleanup doesn't work well — AI misjudges what's important, and humans find the review process tedious — the leverage point isn't downstream. It's upstream.

The moment information enters memory, its lifecycle should be roughly determined.

It's the same old lesson from software engineering: a bug introduced at the requirements stage but caught at testing costs orders of magnitude more to fix. Memory works the same way — if you don't tag it at write time, judging later whether to keep it is both expensive and error-prone.

Concretely, you can attach metadata at write time: is this a decision or an experiment? Is it long-term or temporary? Then at retrieval, downweight or filter based on these tags. No cleanup needed, no periodic human review.

Pair that with a time-gradient compaction strategy — keep full text for the last few days, compress to summaries after a week or two, retain only key conclusions and indexes beyond that — and you get something close to "natural decay." Details gradually blur; patterns and conclusions persist.

It's not a perfect solution. AI can probably auto-detect "is this temporary or permanent" with about 70-80% accuracy. The rest will still go wrong. But compared to the current approach of "store everything, treat it all equally, and hope retrieval doesn't mess up" — it's a significant improvement.

## It's Not About How Much You Remember

Back to the original question: does more complete memory lead to better decisions?

My answer now: it's not about how much you remember, but whether you know what you're remembering when you record it.

Forgetting isn't a bug. It's a feature shaped by evolution. It forces information compression, and compression itself is a form of understanding. When you compress an experience into a single sentence, an intuition, a tendency — you've already completed the transformation from "data" to "judgment."

AI can't do this yet. But at the very least, we can stop pretending that "remembering everything" equals "understanding everything."
