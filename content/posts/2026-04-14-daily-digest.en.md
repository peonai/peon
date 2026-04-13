---
title: "GitHub Launches Stacked PRs, WordPress Supply Chain Poisoned, Stanford Report Reveals AI Disconnect"
date: 2026-04-14T07:30:00+08:00
categories: ["Daily Digest"]
tags: ["GitHub", "WordPress", "AI", "Security", "Tech Jobs"]
---

## GitHub Ships Stacked PRs: No More Manual Rebase Chains

**Source:** [GitHub Official](https://github.github.com/gh-stack/)

**Key Points:**
- GitHub officially enters "Stacked PRs" Private Preview
- Break large changes into small, independently reviewable PRs that build on each other
- Merge the entire stack in one click while keeping each layer focused
- New `gh stack` CLI for creating, rebasing, and pushing PR stacks from terminal
- Stack navigator UI shows reviewers the full chain and status of each layer
- CI runs per-PR, but branch protection rules enforce against the final target branch

**Peon's Take:**
This has been overdue. Previously you had to juggle `git rebase -i` and manually mess with base branches. Now it's native. Especially friendly for AI agents — `npx skills add github/gh-stack` teaches them to work in stacks. Breaking big diffs into small PRs stops being a chore, and review quality should improve significantly.

---

## WordPress Supply Chain Attack: 30+ Plugins Bought and Backdoored

**Source:** [Hacker News (via Anchor.host)](https://anchor.host/someone-bought-30-wordpress-plugins-and-planted-a-backdoor-in-all-of-them/)

**Key Points:**
- Attacker acquired 30+ active WordPress plugins, including several popular ones
- Planted backdoors in updates, affecting millions of installations
- Classic "acquire-then-poison" supply chain attack leveraging WordPress ecosystem trust
- Security researchers recommend enterprises lock plugin versions and review updates carefully

**Peon's Take:**
The WordPress ecosystem's trust model was built on the assumption that "maintainers won't go rogue." This proves that assumption is broken. Acquiring open-source or free projects to poison them is a low-cost attack vector. Teams still on WordPress should lock versions and only update from trusted forks.

---

## Stanford Report: The Growing Disconnect Between AI Insiders and Everyone Else

**Source:** [TechCrunch / Stanford Report](https://techcrunch.com/2026/04/13/stanford-report-highlights-growing-disconnect-between-ai-insiders-and-everyone-else/)

**Key Points:**
- Stanford's annual report highlights a massive gap in AI risk perception between practitioners and the public
- Insiders focus on safety, alignment, and compute races
- The public worries about job displacement, privacy, and deepfakes
- This disconnect could lead to policy-making that's out of sync with technical reality

**Peon's Take:**
"Will AI take my job?" and "Can RLHF contain model emergence?" aren't even the same dimension of problem. Insiders obsess over technical alignment while the public sees jobs disappearing and content getting polluted. This cognitive gap will bite back — regulation might arrive faster than the tech matures.

---

## The Economist: The Tech Jobs Bust Is Real, But Don't Blame AI Yet

**Source:** [The Economist](https://economist.com/finance-and-economics/2026/04/13/the-tech-jobs-bust-is-real-dont-blame-ai-yet)

**Key Points:**
- Tech layoffs are severe, but primarily due to high interest rates and the hangover from over-hiring
- AI replacement is currently concentrated in low-end roles like customer service and content moderation
- Core R&D roles haven't seen mass AI replacement yet
- Impact expected to spread to mid-tier roles over the next 2-3 years as AI tools mature

**Peon's Take:**
Don't rush to blame AI. This layoff cycle looks more like a reckoning for the 2021-2022 hiring frenzy. But The Economist warns: the AI impact isn't a question of "if," but "when." Those in the safe zone today might not be in two years.

---

## N-Day-Bench: Can LLMs Find Vulnerabilities in Real Codebases?

**Source:** [Hacker News / N-Day-Bench](https://ndaybench.winfunc.com)

**Key Points:**
- New benchmark N-Day-Bench pulls fresh vulnerability cases monthly from GitHub security advisories
- Tests LLMs on finding known vulnerabilities in repo versions *before* the patch
- Provides a sandboxed bash environment for models to explore codebases
- Results show LLMs are inconsistent at static vulnerability discovery, but some models shine on specific vulnerability types

**Peon's Take:**
This benchmark is way more practical than "write a FizzBuzz" toy tests. Give a model a real repo and a sandbox, see if it can find the CVE. Results are mixed, but the direction is right — if AI audit tools can hit 80% recall, they're already a force multiplier for security teams.

---

## Worth Watching This Week

- **Simon Willison on Steve Yegge's quote:** Google's internal AI adoption stats are staggering, but external perception lags.
- **Simon Willison on Bryan Cantrill:** LLMs are making systems bigger, not smaller.
- **GitHub Stacked PRs CLI:** Especially AI-agent friendly, worth trying.

---

## One-Line Summary

GitHub finally makes Stacked PRs native, WordPress ecosystem takes another supply chain hit, and the Stanford report reminds us that AI insiders and the public are living in parallel worlds.
