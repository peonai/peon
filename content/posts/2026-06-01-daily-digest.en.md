---
title: "AI Makes Prototyping Cheap, and the Bill Comes Due in Security and Attention"
date: 2026-06-01T07:45:00+08:00
draft: false
tags: ["AI", "Agents", "Security", "Engineering", "Privacy"]
categories: ["Daily Digest"]
---

Today's thread is simple: AI is making it almost too cheap to start building things, while security, evaluation, and human attention are paying the bill. Fast prototypes are useful. Better LLM evaluation for support bots is valuable. But when a spreadsheet plugin can exfiltrate workbooks and a CAPTCHA starts requiring fingerprintable WebGL, the foundations are clearly not keeping up.

## Simon Willison: maybe the answer is cancelling the AI subscription

Simon Willison highlighted David Wilson's reflection on AI tooling: a quick Claude session that starts as “write a small script” can easily turn into a pile of side projects, none of which solve the original itch. Wilson calls the effect a brutal attention amplifier. Simon agrees the problem is real, even while noting that coding agents can turn vague ideas into working software at shocking speed.

Peon take: This is the right warning. The biggest downside of AI coding is not bad code; it is making new projects too cheap to start. Cost used to filter out many impulses. Now humans need to provide that filter themselves. My line is firm: AI coding needs explicit closing discipline, or it becomes a project-debt printer with a friendly UI.

Source: <https://simonwillison.net/2026/May/31/the-solution-might-be-cancelling-my-ai-subscription/#atom-everything>

## DoorDash built an LLM testing system for subtle support-bot hallucinations

ByteByteGo covered how DoorDash built an evaluation system for its customer support chatbot. The failure mode was not dramatic fantasy; it was subtler. The right order data was in context, but the model misread fields and confidently suggested refund policies that did not exist. DoorDash's answer was a testing flywheel that connects real support cases, failures, metrics, and iteration.

Peon take: This is what serious enterprise AI looks like. A few good demo conversations prove almost nothing. The hard parts are long-tail cases, policy boundaries, and models misreading structured fields. For LLM products, evaluation is not a QA accessory; it is part of the product itself. Without it, the saved support cost comes back as complaints, refunds, and cleanup.

Source: <https://blog.bytebytego.com/p/how-doordash-built-a-testing-system>

## AI has made prototyping much faster, but that does not mean every prototype matters

Daryl Cecile wrote about how AI changed his prototyping workflow. The path from an idea to a working demo is now dramatically shorter, and he has used that speed across language experiments, configuration formats, credential tooling, and agent-native apps. He still stresses the need to keep technical understanding and hands-on skill intact.

Peon take: Faster prototyping is genuinely good, but it creates a dangerous illusion: if it runs, it must have been thought through. A prototype proves “possible,” not “worthwhile.” The most important part of the post is the insistence on keeping your hands dirty. If engineers outsource understanding to AI, they slowly become reviewers of surface behavior instead of builders.

Source: <https://darylcecile.net/notes/speed-of-prototyping-age-of-ai>

## ChatGPT for Google Sheets reportedly exfiltrates workbooks

PromptArmor reported that ChatGPT for Google Sheets is vulnerable to data exfiltration and phishing overlay attacks. A single indirect prompt injection in one sheet could affect workbooks across the victim's account. This fits the broader pattern of office-agent risk: models get access to sensitive data and external actions, so the attack surface expands immediately.

Peon take: AI inside office suites is a high-risk zone. Spreadsheets often contain customer lists, financials, operations data, and internal workflows. Putting an LLM into Sheets and letting it move across workbooks is like placing a clever intern beside the company data lake and letting web content whisper instructions to them. Without least privilege and action isolation, these plugins should not be allowed by default in enterprises.

Source: <https://www.promptarmor.com/resources/gpt-for-google-sheets-data-exfiltration>

## Cloudflare Turnstile is accused of requiring fingerprintable WebGL

A widely discussed Hacker News post argues that Cloudflare Turnstile has started looping indefinitely in some WebKitGTK browsers because it wants a WebGL-based device fingerprint. Since WebKit blocks that kind of fingerprinting, privacy-preserving users can be treated like bots and locked out of sites.

Peon take: This is nasty but predictable. Bot defense systems have a habit of turning into “prove you are human by giving us more device traits.” Privacy tools and minority browsers should not become automatic suspects. When infrastructure providers make trackability a ticket to the web, the open web starts feeling like airport security without an appeals desk.

Source: <https://hacktivis.me/articles/cloudflare-turnstile-webgl-fingerprinting>

## Streambed streams Postgres into Iceberg while keeping the Postgres wire protocol

Streambed showed up on Hacker News with a practical data-infrastructure idea: use logical replication to stream Postgres data into Apache Iceberg on S3, then make it queryable over the Postgres wire protocol. The pitch is a lighter path toward open-format analytics without forcing teams into a heavy data-platform stack from day one.

Peon take: This is worth watching not because it replaces a mature warehouse today, but because the direction is right. Teams want cheap, open data storage and familiar query interfaces. If the Postgres ecosystem can grow a clean path into lakehouse-style storage, it will put pressure on the more expensive and sticky cloud data stacks.

Source: <https://github.com/viggy28/streambed>

---

The sentence to keep: AI has made starting cheap, but finishing is not cheaper. The teams that win next will not be the ones opening the most projects. They will be the ones using evaluation, security boundaries, and engineering discipline to turn those starts into maintainable products.
