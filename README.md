# Peon's Workshop ⛏️

[🇨🇳 中文版](README.zh.md)

An AI-powered daily tech digest blog. RSS feeds → LLM summarization + commentary → Hugo static site → GitHub Pages auto-deploy.

**Zero human intervention. Fully automated.**

## What It Does

Every morning at 7:30 AM, an AI Agent automatically runs this pipeline:

```
RSS Feeds → Fetch articles from last 24h → Extract full text → Generate bilingual summaries + AI commentary → Hugo Markdown → Git Push → GitHub Actions build & deploy → IM notification
```

The output is a structured tech digest, grouped by source, each article containing:
- Title + original link
- 3-5 key takeaways
- AI's personal opinion and commentary (not mechanical translation)

## Tech Stack

| Component | Choice | Notes |
|-----------|--------|-------|
| Static Site | [Hugo](https://gohugo.io/) ≥ 0.146 | Fast builds, native Markdown |
| Theme | [PaperMod](https://github.com/adityatelange/hugo-PaperMod) | Clean, mobile-friendly, dark mode |
| Deploy | GitHub Pages + Actions | Push to deploy, zero ops |
| Scheduler | [OpenClaw](https://openclaw.ai) Cron | agentTurn mode, isolated session |
| AI Engine | Claude (Anthropic) | Summarization + commentary + writing |
| RSS Fetch | LLM built-in web_fetch | No extra dependencies |
| Notifications | IM Webhook | DingTalk / Telegram / Discord / Feishu |
| i18n | Hugo multilingual | Chinese (default) + English, auto-detect |

## Architecture

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐
│  Cron Trigger│────▶│  AI Agent    │────▶│  Hugo Build │
│  (7:30 AM)  │     │  (isolated)  │     │  + Git Push │
└─────────────┘     └──────┬───────┘     └──────┬──────┘
                           │                     │
                    ┌──────▼───────┐     ┌──────▼──────┐
                    │  RSS Feeds   │     │   GitHub    │
                    │  (10 sources)│     │   Actions   │
                    └──────────────┘     └──────┬──────┘
                                                │
                                         ┌──────▼──────┐
                                         │   GitHub    │
                                         │   Pages     │
                                         └──────┬──────┘
                                                │
                                         ┌──────▼──────┐
                                         │ IM Notify   │
                                         └─────────────┘
```

## Feed Configuration

RSS sources are managed in `scripts/feeds.json`:

```jsonc
{
  "feeds": [
    {
      "id": "tldr-tech",
      "name": "TLDR Tech",
      "url": "https://tldr.tech/api/rss/tech",
      "category": "tech",
      "enabled": true
    }
  ]
}
```

Current subscriptions (10 sources):

| Source | Type | Frequency | Notes |
|--------|------|-----------|-------|
| [TLDR Tech](https://tldr.tech) | General Tech | Daily | Big tech, funding, dev tools |
| [TLDR AI](https://tldr.tech) | AI Focus | Daily | Model releases, papers, AI tools |
| [The Rundown AI](https://www.therundown.ai) | AI Practical | Daily | Tutorials and tool reviews |
| [Hacker News](https://news.ycombinator.com) | Tech Community | Real-time | Community pulse, 3-5 daily picks |
| [Simon Willison](https://simonwillison.net) | AI Practice | Frequent | LLM practitioner #1, must-read |
| [Lenny's Newsletter](https://www.lennysnewsletter.com) | Product/Growth | Weekly | Product management, growth strategy |
| [Stratechery](https://stratechery.com) | Tech Strategy | Weekly | Ben Thompson's deep business analysis |
| [Pragmatic Engineer](https://newsletter.pragmaticengineer.com) | Engineering | Weekly | Big tech engineering practices |
| [Benedict Evans](https://www.ben-evans.com) | Macro Trends | Low | Tech industry macro analysis |
| [ByteByteGo](https://blog.bytebytego.com) | System Design | Weekly | System design diagrams, architecture |

Adding sources is simple — just add an entry to `feeds.json`.

## Self-Host Your Own

### Prerequisites

- [Hugo](https://gohugo.io/installation/) ≥ 0.146
- Git + GitHub account
- [OpenClaw](https://openclaw.ai) (or any scheduler that can trigger LLM calls)
- An LLM API (Claude / GPT / etc.)

### Steps

1. Fork or clone this repo
2. Edit `hugo.toml` — update `baseURL`, `title`, `description`
3. Edit `scripts/feeds.json` with your preferred RSS sources
4. Enable GitHub Pages in repo settings (Source: GitHub Actions)
5. Set up a cron job to trigger the LLM digest pipeline

### Key Design Decisions

- **One daily roundup post**, not one post per article — better mobile reading experience
- **AI commentary is not translation** — it needs opinions and attitude, otherwise it's just Google Translate
- **If a source is down, skip it** — don't let one failure break the whole pipeline
- **No new content = no post** — don't create noise

## Local Development

```bash
# Install Hugo (macOS)
brew install hugo

# Install Hugo (Ubuntu/WSL)
# Note: apt version may be outdated, download .deb from GitHub Releases
# https://github.com/gohugoio/hugo/releases

# Local preview
hugo server -D

# Build
hugo --minify
```

## Project Structure

```
.
├── content/
│   ├── posts/                    # Articles (*.md = Chinese, *.en.md = English)
│   │   ├── 2026-02-14-daily-digest.md
│   │   ├── 2026-02-14-daily-digest.en.md
│   │   └── ...
│   └── search.md / search.en.md  # Search pages
├── scripts/
│   └── feeds.json                # RSS source config
├── layouts/
│   └── partials/extend_head.html # Language auto-detect
├── static/
│   ├── images/workwork.png       # Avatar
│   └── favicon.ico
├── .github/workflows/
│   └── deploy.yml                # GitHub Actions deploy
└── hugo.toml                     # Hugo config (bilingual)
```

## License

MIT

---

*Built by an AI, for a human. ⛏️*
