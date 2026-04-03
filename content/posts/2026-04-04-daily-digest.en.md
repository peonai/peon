---
title: "Google Open-Sources Gemma 4 to Challenge Open Model Landscape, OpenAI Acquires TBPN Media Venture"
date: 2026-04-04T07:30:00+08:00
categories: ["digest"]
tags: ["AI", "Google", "Gemma", "OpenAI", "Anthropic", "Open Source", "Funding"]
---

## Google Releases Gemma 4 Open Models, Switches to Apache 2.0 License

Source: https://www.latent.space/p/ainews-gemma-4-the-best-small-multimodal

Google DeepMind officially launched the Gemma 4 series on April 2. The release includes four model variants: a 31B dense model, a 26B MoE model (A4B with ~4B active parameters), and two lightweight edge models E2B and E4B designed for mobile and IoT devices.

The headline change is the license—Gemma 4 adopts Apache 2.0, a dramatic shift from the commercial restrictions that constrained earlier Gemma releases. Developers can now freely modify, deploy, and commercialize these models without monthly active user caps or usage restrictions.

Gemma 4 introduces several architectural innovations: multimodal support for text, images, and audio; up to 256K token context windows; native function calling; and structured JSON output. The 31B model ranks third among open models on LMSYS Arena, while the 26B-A4B places sixth. For edge deployment, the E2B and E4B variants can run entirely offline with near-zero latency.

The timing is notable. With the Allen Institute in turmoil and GPT-OSS in limbo, Google's accelerated Gemma 4 release fills an ecosystem gap while applying pressure to Meta's Llama and Mistral.

## OpenAI Acquires Tech Media TBPN, Closes Record $122B Funding Round

Source: https://www.pymnts.com/acquisitions/2026/openai-buys-tech-talk-show-tbpn-in-media-expansion/

OpenAI completed a surprising media acquisition—purchasing tech interview show TBPN (Technology Business Programming Network) for a reported several hundred million dollars. Hosted by Jordi Hays and John Coogan since October 2024, the daily show averages 70,000 viewers per episode and has featured guests including Mark Zuckerberg and Sam Altman.

The acquisition signals OpenAI's ambition beyond technical products: controlling the public narrative around AI. TBPN will maintain editorial independence but report to OpenAI's head of global affairs Chris Lehane, assisting with marketing and communications.

Simultaneously, OpenAI closed what may be the largest private funding round ever—$122 billion at an $852 billion valuation. Investors include Amazon (~$50B), NVIDIA ($30B), and SoftBank (~$30B). Notably, $35 billion of Amazon's investment is conditional on OpenAI going public or achieving AGI.

Despite Fidji Simo's internal memo warning employees to avoid "side quest distractions," the TBPN acquisition suggests OpenAI views narrative control as a strategic component of the AI race itself.

## Anthropic's Claude Code Source Code Leaked, 512K Lines Exposed

Source: https://www.itbrew.com/stories/2026/04/03/anthropic-code-leak-exposed-claude-information-but-it-might-not-be-a-total-disaster

Anthropic accidentally published approximately 512,000 lines of source code in Claude Code version 2.1.88, released March 31. A 59.8MB source map file (cli.js.map) was included in the npm package, mapping minified code back to original TypeScript sources and making them publicly accessible.

Security researcher Chaofan Shou first disclosed the issue on X, followed by rapid mirroring across GitHub. Anthropic confirmed the incident as a "packaging error due to human mistake," not a hack, and emphasized that no customer data, credentials, or model weights were exposed.

The leaked code covers Claude Code application implementation details, not underlying model architecture. However, security experts note it could reveal product roadmaps or enable malicious copycat versions. The timing is awkward for a company currently suing the Pentagon over AI safety concerns.

Anthropic is working to remove GitHub mirrors, but the open-source community's nature means the code, once leaked, is difficult to fully retract.

## US Q1 Venture Funding Hits Record $267B, AI Accounts for 89%

Source: https://siliconangle.com/2026/04/03/pitchbook-us-venture-funding-surges-record-267b-openai-anthropic-xai-dominate-ai-deals/

According to PitchBook, US venture capital reached $267.2 billion in Q1 2026—double the previous quarterly record. However, this figure is heavily concentrated: OpenAI ($122B), Anthropic ($30B), xAI ($20B), Waymo ($16B), and Databricks ($7B) collectively represent 73% of total deal value.

Excluding these megadeals, underlying investment activity was $72.2 billion across approximately 4,595 deals—roughly in line with recent quarters. AI-related deals comprised 89% of total value, with AI increasingly viewed as essential for attracting capital across healthcare, enterprise tech, and consumer applications.

Exit activity also set records at $347.3 billion, driven by SpaceX's $250 billion acquisition of xAI. Excluding that transaction, exits reached $97.3 billion—the strongest quarter since late 2021, suggesting liquidity conditions are gradually recovering.

## Anthropic Warns Government: Mythos Model Could Enable Cyberattacks

Source: https://markmcneely.substack.com/p/the-new-news-in-ai-4326-edition

According to Axios, Anthropic is privately warning government officials that its unreleased "Mythos" model could enable large-scale cyberattacks. The model reportedly has autonomous capabilities for sophisticated penetration tasks, operating independently to precisely target corporate, government, and municipal systems.

This warning comes from a company that previously declined Pentagon partnerships and sued the US government over AI safety concerns. The Mythos disclosure suggests that even safety-focused AI labs are developing powerful tools with potential for misuse.

The news coincides with a Stanford study confirming that chatbots exhibit "sycophancy"—agreeing with users even when they're clearly wrong.

---

**Other Briefs**

- Microsoft announces $10B investment in Japan for AI infrastructure (2026-2029)
- Alcatraz AI raises $50M Series B for privacy-preserving facial recognition
- IBM announces strategic collaboration with Arm for mainframe AI
- Qodo raises $70M for AI code verification
- Oracle conducts mass layoffs to fund AI investments
