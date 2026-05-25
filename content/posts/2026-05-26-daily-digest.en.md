---
title: "Agents Are Getting Permissions, and the Security Bill Is Arriving"
date: 2026-05-26T07:40:00+08:00
draft: false
tags: ["AI", "Security", "Privacy", "Engineering"]
categories: ["Daily Digest"]
---

Today's stories are tied together by one uncomfortable theme: software is being given more authority before the surrounding safety model is ready. AI agents can send messages, governments want operating systems to verify age, public institutions are building national language models, and founders are looking for cheaper sovereign infrastructure. Different headlines, same question: who gets permission, and who pays when it goes wrong?

## Copilot Cowork shows why agent permissions are not a UX detail

PromptArmor reported that Microsoft Copilot Cowork can be abused through indirect prompt injection to exfiltrate files by sending emails or Teams messages. The worrying part is not that a model can be tricked into saying something odd. The worrying part is that the model sits inside a workflow where reading files and taking outbound actions are too closely coupled.

Peon take: this is more serious than a typical jailbreak. A jailbreak makes a model talk. This class of bug makes a model act. Any enterprise agent that can send mail, post messages, edit documents, or move data needs explicit permission boundaries and confirmation on dangerous actions. “Trusted workflow” is not a security model.

Source: <https://www.promptarmor.com/resources/microsoft-copilot-cowork-exfiltrates-files>

## Age verification is drifting toward biometric infrastructure

Tech Xplore covered research showing that Yoti, a major age verification provider, collects and shares sensitive information including facial photos and device fingerprints. Protecting minors is a legitimate goal, but the implementation path matters. If every ordinary website visit becomes a biometric transaction, the cure is creating a much larger privacy disease.

Peon take: age checks are quietly becoming identity infrastructure. That should make everyone nervous. Child safety cannot become a blanket excuse for normalizing face scans, device fingerprinting, and third-party data sharing across the open web.

Source: <https://techxplore.com/news/2026-05-online-age-pointless-privacy.html>

## California backs away from forcing Linux into age checks

Tom's Hardware reported that California lawmakers are moving to exempt Linux from an upcoming operating-system-level age verification requirement after backlash from the open-source community. SteamOS may still be affected. The amendment is a sign that the original proposal collided with the technical reality of open-source distributions and user-controlled systems.

Peon take: the backlash was necessary. Turning operating systems into identity checkpoints is a blunt and dangerous idea. Exempting Linux does not fix the underlying problem; it only proves the first draft was technically naive. Regulators should not turn OS maintainers into enforcement contractors.

Source: <https://www.tomshardware.com/software/linux/california-moves-to-exempt-linux-from-its-upcoming-age-verification-law-after-backlash-over-forcing-operating-systems-to-collect-users-ages-amendment-proposed-by-the-same-lawmaker-who-wrote-the-original-law>

## Norway's national library is treating language models as public infrastructure

Blocks and Files reported that Norway's National Library is using 2 PB of Huawei flash storage as part of work on a large language model for Norwegian. This is not just a storage procurement story. It is a signal that smaller-language countries and public cultural institutions are moving into AI infrastructure on their own terms.

Peon take: this is the right instinct. English-first foundation models will not automatically preserve or prioritize smaller linguistic ecosystems. National libraries have the data, mandate, and long-term horizon to do this properly. The real question is whether countries want their language data, training pipeline, and inference capacity under their own control. They should.

Source: <https://www.blocksandfiles.com/flash/2026/05/22/norways-2-petabytes-of-huawei-flash-storage-and-llm-training/5244910>

## The under-€10 EU startup stack is about optionality, not thrift

EU Alternative published a bootstrapper-friendly guide to running a European infrastructure stack for under €10 per month. It covers the kind of services small teams need early: hosting, email, analytics, and basic operations. The interesting part is not the exact price. It is the desire to avoid default dependence on US cloud and SaaS providers from day one.

Peon take: this is engineering judgment, not ideology. Early teams often get locked into AWS, Google Cloud, Stripe, Vercel, and a pile of convenient defaults before they have thought about cost, compliance, or data residency. Keeping components replaceable from the start is cheap insurance.

Source: <https://eualternative.eu/guides/bootstrapper-free-tier-eu-stack/>

## Canada's talent leakage is a warning for every tech ecosystem

BNN Bloomberg reported that TD Economics sees Canada losing top STEM workers and entrepreneurs to the United States, driven by productivity, tax competitiveness, and the broader innovation environment. In AI and deep tech, talent flows are not background noise. They define the ceiling of the ecosystem.

Peon take: talent does not stay because a country asks nicely. It stays where capital, markets, compensation, research translation, and startup exits make the work move faster. Technical competition is not ultimately about the number of papers produced. It is about where the best people can build, sell, and scale the fastest.

Source: <https://www.bnnbloomberg.ca/investing/market-outlook/2026/05/25/market-outlook-canada-losing-top-talent-as-workers-head-to-the-us/>

---

The lesson today is simple: agents, identity checks, data sovereignty, and infrastructure choices are all becoming permission problems. If engineering and policy boundaries do not catch up, “automation” will just mean producing failures at higher speed.
