# 🧹 Broom

**Your AI Mac janitor. No app. No subscription. Just say the word.**

---

<p align="center">
  <img src="assets/broom-hero.png" width="400" alt="Broom" />
</p>

<p align="center">
  <a href="#installation"><img src="https://img.shields.io/badge/Install-say%20%22broom%22-blue" /></a>
  <a href="#features"><img src="https://img.shields.io/badge/Platform-macOS-lightgrey" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-green" /></a>
</p>

## Why Broom?

| Traditional cleaners | Broom 🧹 |
|---------------------|----------|
| Install a $40 app | Just say "broom" |
| Fixed rules | Learns your habits |
| Can't undo | Full undo from trash |
| Scans silently | Every step transparent |
| One-size-fits-all | Conversational config |

Broom is an [OpenClaw](https://openclaw.ai) skill that turns your AI assistant into a Mac janitor. No GUI, no subscription, no data leaving your machine.

## Features

- 🧠 **Smart Diagnosis** — Scans caches, app data, Docker, iOS backups, Downloads, and large files with intelligent grouping
- 🎯 **Conversational Config** — Never edit a file. Just say what you want
- ↩️ **Full Undo** — App data goes to trash. Every action logged and reversible
- 📈 **Trend Tracking** — See what's eating your space and where it came from
- 🏆 **Personal Leaderboard** — Beat your own records. Track streaks and milestones
- 🔒 **10 Safety Rules** — Personal docs never deleted. Databases never touched. Dry Run before every action

## Quick Start

```bash
# Copy skill to your OpenClaw workspace
cp -r broom/ ~/.openclaw/workspace/skills/broom/
```

Then just say: **"broom"** or **"help me clean my Mac"**

## Commands

| Command | What it does |
|---------|-------------|
| `broom` / `clean my Mac` | Full diagnostic scan |
| `quick clean` | Skip scan, clean safe items |
| `undo last cleanup` | Restore files from trash |
| `scan only Downloads` | Partial scan |
| `broom stats` | Achievements & personal leaderboard |
| `share broom` | Project intro card |

## Safety

10 strict rules: never delete personal docs, never touch databases, detect running apps, always Dry Run, complete undo log, macOS only.

## Contributing

Add app rules to `references/app-rules.yaml`. See README for schema.

## License

MIT
