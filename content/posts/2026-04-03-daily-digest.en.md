---
title: "Anthropic Source Code Leak, OpenAI Raises $122B, Google Open-Sources Gemma 4"
date: 2026-04-03T07:30:00+08:00
categories: ["digest"]
tags: ["AI", "Anthropic", "OpenAI", "Google", "Gemma", "Claude", "NASA"]
---

This issue covers news from April 1 to April 3.

## Anthropic's Rough Week: Claude Code Source Code Fully Exposed

Source: https://thenewstack.io/anthropic-claude-code-leak/

Anthropic has had a difficult week. On March 26, Fortune reported that a CMS configuration error exposed nearly 3,000 internal files, including a draft announcement for a new model codenamed "Mythos" (internally also called "Capybara"), described as the company's "most capable AI model to date." Less than a week later, on March 31, security researcher Chaofan Shou discovered that Anthropic had accidentally included a 59.8MB source map file in the Claude Code v2.1.88 npm package.

This source map pointed to an unencrypted ZIP archive stored on Cloudflare R2, containing approximately 1,900 files and 512,000 lines of TypeScript code. The leaked content covered the complete agent architecture, system prompts, internal implementations of 40+ agentic tools, and at least 8 unreleased features: including a background agent called KAIROS that logs actions daily and runs a nightly "autoDream" routine, a Tamagotchi-style coding companion that reacts to your code beside the input box, and an "Undercover Mode" that automatically activates when Anthropic employees use Claude Code on internal repositories to prevent sensitive information leakage.

Anthropic's Chief Commercial Officer Paul Smith responded that this was "human error in the release process, absolutely not a security breach." Claude Code creator Boris Cherny stated on X: "We've improved the automation, no one was fired, it was an honest mistake." Anthropic has submitted numerous DMCA takedown requests to GitHub, but the code had already spread widely. A South Korean developer even rewrote the core architecture in Python and Rust as "Claw Code," hitting 100,000 stars within 24 hours—a GitHub growth record.

The incident is damaging to Anthropic's brand. A company built on "AI safety" suffered two leaks in one week—first exposing a new model, then exposing the complete source code of its flagship product. Ironically, the leaked code included mechanisms for detecting and preventing malicious use of the model—and now those mechanisms are also exposed.

---

## Google Releases Gemma 4 Under Apache 2.0 License

Source: https://www.theregister.com/2026/04/02/googles_gemma_4_open_weights/

Google released the Gemma 4 series of open-weight models on April 2, marking a significant statement in the open-source AI space. Gemma 4 includes four variants: E2B (2B parameters) and E4B (4B parameters) optimized for phones and edge devices; 26B is a Mixture-of-Experts (MoE) architecture focused on inference speed; and 31B is a dense architecture optimized for raw quality.

The biggest change is the license. Previous Gemma versions used Google's custom restrictive license, requiring legal review for derivative models or commercial use. Gemma 4 switches to Apache 2.0, meaning developers can freely modify, redistribute, and commercialize without worrying about Google changing terms later. Hugging Face co-founder Clement Delangue commented: "Local AI is having its moment, this is the future of the AI industry."

In terms of performance, the 31B model achieves 89.2% on the AIME 2026 mathematics benchmark, 84.3% on GPQA Diamond scientific reasoning, and 80% on LiveCodeBench v6 programming competition. While slightly behind Chinese open models like Alibaba's Qwen 3.5, Zhipu AI's GLM-5, and Moonshot AI's Kimi K2.5, the gap is small. More importantly, Gemma 4 is one of the strongest open models in the "Western camp" currently available.

The context is the rise of Chinese open models squeezing Western alternatives. Over the past few months, Moonshot AI, Alibaba, and Z.AI have released open models approaching or surpassing GPT-5 and Claude on multiple benchmarks. Gemma 4 represents Google's response: reclaiming open-source leadership through more permissive licensing and stronger performance.

---

## OpenAI Completes $122 Billion Funding Round at $85.2B Valuation

Source: https://theaiworld.org/news/openai-raises-122b-to-accelerate-ai

OpenAI completed the largest funding round in history on March 31: $122 billion at an $85.2 billion post-money valuation. To put this in perspective: this exceeds the combined market caps of Spotify, Uber, and Airbnb.

The round was led by Amazon with $50 billion, with Nvidia and SoftBank each contributing $30 billion. Other investors include Andreessen Horowitz, D.E. Shaw, MGX, TPG, T. Rowe Price, and others. According to The Wall Street Journal, CEO Sam Altman told employees this funding would be used to "really accelerate the economic economy," suggesting OpenAI is planning infrastructure far beyond ChatGPT's current scale.

The money is primarily directed at two areas: computing infrastructure to build "planetary-scale" AI compute clusters, and new model development including a next-generation base model internally codenamed "Spud." OpenAI President Greg Brockman revealed on the Big Technology podcast that Spud represents two years of research and will be "a new base model," not just an incremental upgrade.

OpenAI's funding pace is accelerating. A year ago it raised at a $157 billion valuation; now it has jumped to $85.2 billion. This growth rate is rare in tech history and reflects capital markets warming to AGI bets. But concerns exist: such massive funding means OpenAI must prove commercial value matching this valuation in the coming years, or the correction will be severe.

---

## Anthropic Launches Windows Support for Claude Computer Use

Source: https://letsdatascience.com/news/anthropic-adds-computer-use-to-windows-apps-40c5c1ad

On April 3, Anthropic announced that Computer Use in Claude Cowork and Claude Code Desktop is now available on Windows. The feature launched on macOS on March 23 and expanded to Windows a week later, covering approximately 70% of desktop users.

Computer Use allows Claude to directly control users' computers: opening applications, controlling keyboard and mouse, browsing the web, filling forms, using service connectors like Slack or Google Calendar. Anthropic has also partnered with Dispatch for remote task orchestration. The feature remains in research preview and requires Claude Pro or Max subscription.

This capability represents AI's transformation from "chat tool" to "digital employee." Unlike simple API integrations, Computer Use lets AI interact with existing software ecosystems like humans, without enterprises needing to develop separate AI interfaces for each application. For knowledge workers, this means AI can take over more repetitive desktop tasks—organizing files, filling reports, syncing data across applications.

Risks come with this capability. Anthropic's documentation warns: this is a research preview, complex tasks sometimes need retrying, screen interaction is slower than direct integration, and testing on non-sensitive applications is recommended. After all, letting AI control your computer essentially grants it significant system privileges.

---

## NASA Artemis II Successfully Launches, Humanity Returns to the Moon

Source: https://apod.nasa.gov/apod/ap260402.html

On April 1, NASA successfully launched the Artemis II crewed lunar flyby mission. This is humanity's first venture beyond low-Earth orbit since Apollo 17 in 1972. The Orion spacecraft carries 4 astronauts on a roughly 10-day mission: entering Earth orbit after launch, then firing thrusters for lunar transfer, looping around the Moon, and returning to Earth for a Pacific Ocean splashdown.

Artemis II is a "touch-free" test flight primarily validating Orion's life support systems,