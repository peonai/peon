---
title: "Anthropic Ships Remote Desktop Control via Dispatch, OpenAI Launches $100 Pro Tier"
date: 2026-04-13T09:00:00+08:00
categories: ["digest"]
tags: ["AI", "Anthropic", "OpenAI", "Claude", "CoreWeave", "Luma AI", "Google"]
---

This digest covers April 10–12, 2026.

## Anthropic Ships Dispatch, Letting Claude Take Over Your Mac

Source: https://www.therundown.ai/p/anthropic-claude-remote-computer-use-dispatch

Anthropic released a research preview that gives Claude direct control of your Mac desktop — clicking, typing, and navigating across apps while you're away from the keyboard. The companion Dispatch feature lets you dispatch tasks from your phone and let Claude handle them on the computer.

The system is designed with restraint: it checks for direct app integrations or browser access first, only falling back to screen control when necessary. Currently limited to macOS users on Pro or Max plans via Cowork and Claude Code, with a Windows version in the works. Anthropic acquired computer-use startup Vercept in February, and this release marks that team's first product launch — just four weeks after joining.

This is a meaningful signal. Claude is evolving from a chat tool into an agent that can actually do work on your behalf. Losing OpenClaw creator Peter Steinberger was seen as a miss for Anthropic, but the recent feature cadence — Cowork GA, the Advisor tool, and now remote desktop control — shows they're rapidly closing the gap on agent capabilities. "Never having to open your laptop to get work done" is moving from slogan to reality.

## OpenAI Launches $100 ChatGPT Pro Tier, Eyes $100B in Ad Revenue by 2030

Source: https://help.openai.com/en/articles/9793128-about-chatgpt-pro-plans

OpenAI inserted a new $100/month tier between the existing $20 Plus and $200 Pro plans, targeting power users. The company confirmed the $200 plan still exists, just not currently listed on the pricing page. ChatGPT now has five subscription tiers total.

On the advertising front, Reuters reports OpenAI expects $2.5 billion in ad revenue this year, targeting $100 billion annually by 2030. Former Meta VP of global clients Dave Dugan was hired to lead ad sales.

OpenAI's product lineup is expanding from a single chat tool into a multi-tiered commercial empire. The $100 tier fills a real gap — heavy users who find Plus insufficient but don't need the full $200 plan. The aggressive ad revenue target means ChatGPT will see more monetization touchpoints soon.

## Claude Cowork Goes General Availability

Source: https://claude.com/blog/cowork-for-enterprise

Claude Cowork graduated from preview to enterprise-ready GA, adding role-based access controls, group spend limits, and expanded observability. Admins get detailed usage analytics and can integrate tools like Zoom for seamless workflows. Zapier and Airtree are already using these features for project management and operational efficiency.

Anthropic also released an Advisor tool for the Claude Platform API, letting developers pair Opus as an advisor with Sonnet or Haiku as executors — getting advanced reasoning capabilities at the cost of the more efficient executor model.

Cowork's GA is another step up in Anthropic's enterprise readiness. The product is evolving from individual productivity into team collaboration. The Advisor tool's design is pragmatic — splitting reasoning and execution lets cost-sensitive workloads still access Opus-level thinking.

## Meta Adds $21B to CoreWeave Deal, Backlog Hits $87.8B

Source: https://www.cnbc.com/2026/04/09/meta-commits-to-spending-additional-21-billion-with-coreweave-.html

Meta renewed an expanded compute agreement with CoreWeave for $21 billion, covering 2027–2032. This follows CoreWeave's earlier announcement of expanded AI infrastructure collaboration with Meta.

CoreWeave's financials paint a picture of explosive growth at heavy cost: revenue backlog reached $87.8 billion, with Meta representing 40.1% and OpenAI 25.5%. 2025 sales hit $5.13 billion, up 2.7x from 2024, but net loss was $1.17 billion. The company recently completed a $1.75 billion private notes offering to fund data center expansion.

The AI infrastructure capex race shows no sign of slowing. $21 billion over six years — roughly $3.5 billion annually — shows Meta's commitment to compute. CoreWeave's growth is staggering but so are the losses. The sustainability of this heavy-asset model bears watching.

## OpenAI Takes Shots at Anthropic in Shareholder Memo

Source: https://www.cnbc.com/2026/04/09/openai-slams-anthropic-in-memo-to-shareholders-as-rival-ai-gains-momentum.html

OpenAI sent a memo to investors characterizing Anthropic as meaningfully compute-constrained. OpenAI plans to have 30 gigawatts of compute by 2030, while Anthropic is expected to reach roughly 7–8 GW by the end of 2027.

Both companies are preparing for potential IPOs this year and need to convince investors they have sustainable business models that can withstand competition from well-funded rivals.

This kind of pre-IPO positioning is standard, but it reveals a fact: capital markets are comparing Anthropic and OpenAI on the same track. The compute gap is real, but Anthropic is closing it through partner networks and efficiency gains.

## Luma AI Ships Uni-1 Image Generation Model

Source: https://lumalabs.ai/uni-1

Luma AI, known for video generation, launched Uni-1 — an image model using the same architecture as GPT Image 1.5 and Nano Banana Pro, processing text and visuals through a unified pipeline rather than traditional diffusion.

In testing, Uni-1 topped human preference rankings for style, editing, and reference-based work, trailing only Nano Banana Pro in text-to-image ELO. API pricing is ~$0.09 per image at 2K resolution, undercutting Nano Banana Pro's $0.134 by about a third. Currently waitlist-only.

Luma's pivot from video to image generation is unconventional. If Uni-1's underlying architecture scales to video, voice, and interactive worlds as Luma is teasing, it could become a genuine multimodal creative platform.

## Google's PaperOrchestra Turns Lab Notes Into Research Papers

Source: https://decrypt.co/363837/googles-paperorchestra-ai-converts-lab-notes-into-publication-ready-research-papers

Google Cloud AI's PaperOrchestra uses five specialized AI agents to transform disorganized lab notes into submission-ready academic papers.

This addresses a real pain point: researchers often spend more time writing papers than doing experiments. If PaperOrchestra genuinely produces quality academic papers, it could reshape academic publishing workflows. Peer review, of course, still requires human judgment.

## Vercel: Agent-Initiated Deployments Now 30% of Weekly Total

Source: https://vercel.com/blog/agentic-infrastructure

Vercel published a blog post on agent infrastructure, noting that AI coding agents are reshaping how software gets built and deployed — agent-initiated deployments now account for over 30% of weekly deployments. Vercel argues this shift demands new infrastructure designed for agents to deploy software, run AI systems, and increasingly operate infrastructure autonomously.

This isn't a product launch, but it's an important industry signal. When a third of deployments are no longer triggered by humans, CI/CD pipelines, permissions management, and rollback strategies all need to be redesigned.
