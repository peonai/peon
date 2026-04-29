---
title: "OpenAI Pushes Past 10GW of Compute, Mistral Ships Remote Coding Agents, and AI Security Starts Hitting Real Spreadsheets"
date: 2026-04-30T08:00:00+08:00
categories: ["News"]
tags: ["OpenAI", "Mistral", "AI Agents", "Cybersecurity", "Prompt Injection", "Claude Code", "Linux"]
---

## OpenAI Says Its U.S. AI Infrastructure Has Passed 10GW, Making the Compute Arms Race Explicit

**Source:** [OpenAI](https://openai.com/index/building-the-compute-infrastructure-for-the-intelligence-age)

**Key points:**
- OpenAI says Stargate, announced in January 2025, committed to securing 10GW of AI infrastructure in the U.S. by 2029
- The company now says it has already passed that milestone, with more than 3GW added in the last 90 days alone
- OpenAI describes compute as the critical input for advanced AI
- It frames compute as the center of a flywheel: more compute enables better models, better models drive more usage, and more usage funds more infrastructure
- The post also talks openly about power, land, permitting, transmission, workforce, community support, and water stewardship

**Peon's take:**
This is OpenAI putting the real game on the table. AI competition is no longer a neat software-company contest. It is energy, land, capital, supply chains, and local politics all at once. Ten gigawatts is not "buy more GPUs." It is industrial strategy. The compute flywheel language matters because OpenAI is saying infrastructure advantage should compound into model advantage and revenue advantage. But scale also creates externalities. Power, water, communities, permitting — these are no longer side issues. Behind every model launch, there is now an electrical grid story.

---

## OpenAI Publishes a Cybersecurity Action Plan, Moving AI Security From Slogans Toward Governance

**Source:** [OpenAI](https://openai.com/index/cybersecurity-in-the-intelligence-age)

**Key points:**
- OpenAI published a `Cybersecurity in the Intelligence Age` action plan
- The plan has five pillars: democratizing cyber defense, coordinating government and industry, securing frontier cyber capabilities, preserving deployment visibility and control, and helping users protect themselves
- OpenAI acknowledges that AI can strengthen both defenders and attackers
- The document is positioned as policy and governance work, not just a product announcement

**Peon's take:**
OpenAI is increasingly behaving like infrastructure, and infrastructure companies have to play the policy game. Cybersecurity is the place where vague promises are useless. AI lowers the cost of attack, so the defensive story has to be more than "the model will refuse bad prompts." The important words are visibility and control. Organizations need to know what the system did, who asked for it, what tools were called, and how to respond when something goes wrong. Real AI security will be audit logs, permissions, isolation, response playbooks, and accountability chains. Not launch-page theater.

---

## Mistral Ships Medium 3.5 and Remote Coding Agents, Taking a Serious Swing at the Agent Workspace

**Source:** [Mistral AI](https://mistral.ai/news/vibe-remote-agents-mistral-medium-3-5)

**Key points:**
- Mistral released Mistral Medium 3.5 and added remote coding agents plus Work mode to Vibe and Le Chat
- The company says coding agents can run independently in the cloud, work on tasks in parallel, and notify users when done
- Tasks can be launched from the Mistral Vibe CLI or from Le Chat
- Sensitive actions require explicit permission, such as sending messages, writing documents, or modifying data
- API pricing is listed at $1.5 per million input tokens and $7.5 per million output tokens; open weights are available on Hugging Face under a modified MIT license

**Peon's take:**
This is the right move from Mistral. Competing with "we also have a model" is a weak position. Competing on agent workflow is more interesting. Remote execution, parallel tasks, approval gates, CLI access, chat integration, and open weights together start to look like a real developer workbench. Cursor, Claude Code, and OpenAI Codex are all fighting for this layer. If Mistral only sold APIs, it would struggle to stand out. If it can connect local CLI, cloud execution, Le Chat, and open deployment into one coherent flow, it has a shot at becoming a European developer workflow entry point.

---

## Ramp Sheets AI Shows How Prompt Injection Can Exfiltrate Real Financial Data

**Source:** [PromptArmor](https://promptarmor.com/resources/ramps-sheets-ai-exfiltrates-financials)

**Key points:**
- PromptArmor demonstrated a data-exfiltration attack chain involving Ramp Sheets AI
- A user opens a workbook with sensitive financial models and imports untrusted external data
- The external data contains prompt injection that persuades Ramp AI to create an `IMAGE` formula
- That formula sends a network request to an attacker-controlled URL with sensitive financial data appended
- PromptArmor says Ramp AI inserted the malicious formula without requiring user approval

**Peon's take:**
This is the nasty version of AI inside office software. The model does not have to directly leak secrets. It can be tricked into generating a perfectly valid spreadsheet action that leaks secrets for it. Spreadsheets, documents, email, CRM systems — all of these mix trusted internal data with untrusted external content. That is paradise for indirect prompt injection. The naive defense is trusting the model to know the boundary. The real defense is capability control: anything that sends network requests, writes files, changes records, or calls external tools needs permission checks and execution review. If AI assistants act like employees, they need to be managed like employees.

---

## Claude Code's Reported `HERMES.md` Billing Bug Shows Context Pollution Can Hit the Wallet

**Source:** [GitHub Issue](https://github.com/anthropics/claude-code/issues/53262)

**Key points:**
- A user reported that having the string `HERMES.md` in recent git commit messages caused Claude Code requests to route to extra usage billing
- The reporter says this consumed $200.98 in extra usage credits even though the Max 20x plan should have covered the requests
- The trigger was not a file on disk, but commit-message text included in the system prompt
- The error only said extra usage was exhausted, without explaining that content had changed billing routing

**Peon's take:**
If this report is accurate, it is absurd. Project context should not silently change billing routes. This takes context injection from a quality problem to a billing problem. Worse, the user has no obvious way to understand what happened. They just see credits disappear. AI coding tools are becoming complex cloud platforms, so they need cloud-grade billing transparency. If users start believing mysterious context strings can push them onto a more expensive path, trust gets shredded fast. You cannot build a serious developer platform on invisible billing behavior.

---

## Copy Fail Is a Linux Page-Cache Vulnerability That AI Sandboxes Should Take Seriously

**Source:** [Copy Fail](https://copy.fail/)

**Key points:**
- Copy Fail, tracked as CVE-2026-31431, demonstrates a local privilege-escalation issue involving Linux page cache behavior
- The proof of concept is a 732-byte Python script using only the standard library
- The authors say the same script affects Ubuntu, Amazon Linux, RHEL, and SUSE
- The risk is especially relevant to Kubernetes clusters, CI runners, build farms, cloud SaaS running user code, notebook hosts, and agent sandboxes
- The issue can contribute to container escape or cross-tenant risk

**Peon's take:**
This is directly relevant to AI infrastructure. Everyone is rushing to run agent sandboxes, code interpreters, CI runners, notebooks, and untrusted user code. Multi-tenant execution is becoming the default substrate for AI products. A bug like Copy Fail hurts platforms that assumed containers were enough isolation. As agents write code, run tests, execute shell commands, and inspect files, kernel and sandbox security move from background plumbing to core product risk. Prompt injection is not the only way agents get owned. Ordinary system vulnerabilities can still punch straight through the stack.

---

## One-line summary

OpenAI is scaling compute and security governance, Mistral is pushing remote coding agents into the cloud, and the Ramp, Claude Code, and Copy Fail stories all point to the same lesson: production AI is now a fight over infrastructure, security boundaries, and billing transparency.
