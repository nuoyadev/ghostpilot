<div align="center">

![Lumi Banner](banner.png)

# Lumi — AI Social Media Autopilot

[![License: MIT](https://img.shields.io/badge/license-MIT-purple?style=flat-square)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.10+-blue?style=flat-square&logo=python)](https://python.org)
[![Playwright](https://img.shields.io/badge/playwright-latest-green?style=flat-square&logo=playwright)](https://playwright.dev)
[![LLM](https://img.shields.io/badge/LLM-Claude%20%7C%20GPT--4-orange?style=flat-square)](https://anthropic.com)
[![Status](https://img.shields.io/badge/status-active-brightgreen?style=flat-square)]()
[![Zero API Cost](https://img.shields.io/badge/Twitter%20API-%240-success?style=flat-square)]()

**Post on Twitter/X and Instagram automatically. No API fees. No manual work. Just results.**

Built by [@nuoyadev](https://github.com/nuoyadev) — Because building is more important than posting about building.

</div>

---

## What is Lumi?

**Lumi** is an AI-powered social media autopilot that runs silently in the background and posts for you every single day, while you focus on what actually matters: building.

It uses LLMs (Claude / GPT-4) to generate platform-native content from your ideas, projects, and GitHub activity, then uses Playwright to post directly via the browser — completely free, no API keys required for posting.

```
Your projects → Lumi AI → Twitter/X post ✓
                        → Instagram caption ✓
                        → Scheduled & done ✓
```

---

## Features

| Feature | Description |
|---|---|
| 🤖 AI Content Generation | Claude or GPT-4 generates engaging posts from your GitHub activity |
| 🌐 Browser-Based Posting | Playwright posts via browser — zero API cost for Twitter/Instagram |
| ⏰ Smart Scheduling | GitHub Actions runs on cron — fully automated, 24/7 |
| 🎯 Platform-Native | Different tone and format for Twitter vs Instagram |
| 🔄 Multi-Platform | Twitter/X + Instagram in one pipeline |
| 🛡️ Safe and Private | No third-party services, runs entirely in your GitHub repo |

---

## Architecture

```
GitHub Actions (cron)
       ↓
content_generator.py
  ├── Fetch GitHub activity / topic ideas
  ├── Call Claude API → generate tweet
  └── Call Claude API → generate Instagram caption
       ↓
poster/
  ├── twitter_poster.py   → Login → Compose → Post
  └── instagram_poster.py → Login → New post → Publish
       ↓
scheduler.py → Orchestrates timing, retries, logging
```

Stack: Python 3.10+ · Playwright async · Claude API / OpenAI · GitHub Actions · YAML config

---

## Quick Start

```bash
git clone https://github.com/nuoyadev/lumi.git
cd lumi
pip install -r requirements.txt
playwright install chromium
cp .env.example .env
python lumi.py --all --dry-run
```

Add your secrets to GitHub (`Settings → Secrets`) and the workflow runs daily automatically.

---

## Project Structure

```
lumi/
├── lumi.py                 # Entry point
├── content_generator.py    # LLM content generation
├── scheduler.py            # Orchestration & timing
├── poster/
│   ├── twitter_poster.py   # Twitter/X Playwright bot
│   └── instagram_poster.py # Instagram Playwright bot
├── config/
│   ├── platforms.yaml      # Per-platform settings
│   └── prompts.yaml        # LLM prompt templates
├── .github/workflows/
│   └── lumi.yml            # GitHub Actions workflow
├── CLAUDE.md               # AI instructions for Cursor
└── README.md
```

---

## Roadmap

- [x] Project setup and architecture
- [ ] - [x] CLAUDE.md — AI instructions for Cursor
- [ ] - [ ] content_generator.py — LLM integration
- [ ] - [ ] twitter_poster.py — Playwright automation
- [ ] - [ ] instagram_poster.py — Playwright automation
- [ ] - [ ] scheduler.py — orchestration logic
- [ ] - [ ] GitHub Actions workflow
- [ ] - [ ] Dry-run mode
- [ ] - [ ] Multi-account support

- [ ] ---

- [ ] ## License

- [ ] MIT © [nuoyadev](https://github.com/nuoyadev)

- [ ] ---

- [ ] <div align="center">
Lumi — Post while you build. Zero API cost.
</div>
