---
title: "📰 Daily Digest | 2026-02-28"
date: 2026-02-28
categories: ["digest"]
tags: ["Anthropic", "OpenAI", "Amazon", "Microsoft", "US Government", "AI Safety", "Simon Willison", "GitHub Copilot", "Perplexity"]
---

> This edition covers news from Feb 27–28

## 🏛️ AI & Government

### Trump Administration Bans Anthropic from Government Systems, Pentagon Designates Supply Chain Risk

**Source**: [NPR](https://www.npr.org/2026/02/27/nx-s1-5729118/trump-anthropic-pentagon-openai-ai-weapons-ban)

Arguably the biggest AI story of the week. President Trump signed an executive order banning US government use of Anthropic's products, while the Pentagon simultaneously designated Anthropic as a "supply chain risk entity"—a label historically reserved for US adversaries and never before publicly applied to an American company.

**Key points:**

- The core dispute: Anthropic refused to remove two restrictions from a $200M military contract—prohibitions on mass domestic surveillance and fully autonomous weapons
- Defense Secretary Hegseth called Anthropic "leftwing nut jobs" on X, setting a 6-month product phaseout timeline
- Anthropic says it will challenge the designation in court, calling it "legally unsound and a dangerous precedent"
- Anthropic stated: "No amount of intimidation or punishment from the Department of War will change our position on mass domestic surveillance or fully autonomous weapons"

**My take**: This is a watershed moment. An AI company has been branded a "risk entity" by its own government for maintaining safety guardrails. Regardless of where you stand on Anthropic's position, this sets a deeply unsettling precedent—the cost of principled safety stances could be losing the entire government market.

---

### Anthropic Issues Formal Response to Secretary Hegseth

**Source**: [Anthropic](https://www.anthropic.com/news/statement-comments-secretary-war)

Anthropic released a firm but measured official statement, making clear they won't budge.

**Key points:**

- They haven't received formal communication from the DoW or White House
- Their restrictions cover only two extremely narrow scenarios and have not affected a single government mission to date
- Current frontier AI models aren't reliable enough for fully autonomous weapons—allowing their use would endanger warfighters and civilians
- Reassuring customers: Hegseth's implied restrictions lack statutory authority and can only affect direct DoW procurement

**My take**: Anthropic's response is strategically sound—standing firm while calming commercial clients. But the real test comes with the legal battle and market reaction.

---

### OpenAI Reaches Deal to Deploy Models on Pentagon's Classified Network

**Source**: [Reuters](https://www.reuters.com/business/openai-reaches-deal-deploy-ai-models-us-department-war-classified-network-2026-02-28/)

In stark contrast to Anthropic's ban, OpenAI struck a deal with the Pentagon to deploy AI models on classified networks.

**My take**: The timing is too "coincidental" to ignore. On the same day Anthropic gets kicked out, OpenAI gains classified network access. The relationship between AI labs and the US government is splitting fast—those who cooperate with the military get rewarded; those who hold safety lines get punished. This has far-reaching implications for the AI safety narrative.

---

## 💼 Business & Partnerships

### OpenAI and Amazon Announce Strategic Partnership

**Source**: [OpenAI](https://openai.com/index/amazon-partnership)

OpenAI and Amazon announced a strategic partnership. The same day, OpenAI also released a [joint statement with Microsoft](https://openai.com/index/continuing-microsoft-partnership), reaffirming their ongoing collaboration.

**My take**: OpenAI is playing the multi-cloud game—maintaining its core Microsoft relationship while expanding with Amazon. Partnering with two of the three cloud giants simultaneously is a bold move. Probably not great news for Google Cloud.

---

### OpenAI Publishes "Scaling AI for Everyone"

**Source**: [OpenAI](https://openai.com/index/scaling-ai-for-everyone)

OpenAI laid out its vision for democratizing AI access and its scaling strategy.

---

## 🔒 Security

### GitHub Copilot CLI Found to Download and Execute Malware

**Source**: [Prompt Armor](https://www.promptarmor.com/resources/github-copilot-cli-downloads-and-executes-malware)

Security research firm Prompt Armor disclosed a serious AI security vulnerability: GitHub Copilot's CLI tool can be tricked into downloading and executing malware.

**My take**: Another alarm bell for AI coding assistants on the security front. When AI agents have system command execution privileges, prompt injection risks stop being theoretical. Every team running AI agents in production should seriously audit their sandboxing and permission policies.

---

## ✍️ Deep Dives & Practice

### Simon Willison: An AI Agent Coding Skeptic Tries AI Agent Coding, in Excessive Detail

**Source**: [Simon Willison](https://simonwillison.net/2026/Feb/27/ai-agent-coding-in-excessive-detail/)

Simon Willison, in his characteristically thorough style, documented his complete experience trying AI agent coding as a self-described skeptic.

**My take**: What makes Simon's pieces valuable is that he neither hypes nor dismisses blindly. This attitude of "remain skeptical but try honestly, then report accurately" is far too rare in today's AI discourse.

### Anthropic Offers Free Claude Max to Large Open Source Maintainers

**Source**: [Simon Willison](https://simonwillison.net/2026/Feb/27/claude-max-oss-six-months/)

Anthropic announced 6 months of free Claude Max subscriptions for maintainers of large open-source projects.

**My take**: Even as they're shut out of government, Anthropic is doubling down on the developer community. Smart move—even if you lose the government market, developer loyalty could prove to be a more durable moat.

---

## 🤖 Products & Launches

### Perplexity Launches 19-Model AI "Computer"

**Source**: [The Rundown AI](https://www.therundown.ai/p/perplexitys-19-model-ai-computer)

Perplexity released its new product called "Computer," integrating 19 AI models.

**My take**: Multi-model orchestration is becoming the new paradigm for AI products. Rather than betting on a single model, systems that automatically select the optimal model for each task are gaining traction. Perplexity is pushing aggressively in this direction.

---

## 📡 Hacker News Highlights

- **[OpenAI deploys to Pentagon's classified network](https://www.reuters.com/business/openai-reaches-deal-deploy-ai-models-us-department-war-classified-network-2026-02-28/)** — See detailed analysis above
- **[Don't use passkeys for encrypting user data](https://blog.timcappalli.me/p/passkeys-prf-warning/)** — Security warning about passkeys PRF extension
- **[Go Blog: Allocating on the Stack](https://go.dev/blog/allocation-optimizations)** — Deep dive into Go compiler memory allocation optimizations
- **[NASA announces Artemis program overhaul](https://www.cbsnews.com/news/nasa-artemis-moon-program-overhaul/)** — Major reforms amid safety concerns and delays
- **[Croatia declared free of landmines after 31 years](https://glashrvatske.hrt.hr/en/domestic/croatia-declared-free-of-landmines-after-31-years-12593533)** — Some uplifting news for a change
