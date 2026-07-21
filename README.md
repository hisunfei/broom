<p align="center">
  <img src="https://raw.githubusercontent.com/hisunfei/broom/main/assets/broom-logo.png" width="120" alt="Broom" />
</p>

<h1 align="center">🧹 Broom</h1>

<p align="center">
  <strong>Your AI Mac janitor. No app. No subscription. Just say the word.</strong>
</p>

<p align="center">
  <a href="README_zh.md">中文</a> · <strong>English</strong>
</p>

<p align="center">
  <a href="#installation"><img src="https://img.shields.io/badge/Install-say%20%22broom%22-4A90D9?style=flat-square" alt="Install" /></a>
  <a href="#features"><img src="https://img.shields.io/badge/Platform-macOS-lightgrey?style=flat-square" alt="Platform" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License" /></a>
  <a href="https://openclaw.ai"><img src="https://img.shields.io/badge/Powered%20by-OpenClaw-orange?style=flat-square" alt="OpenClaw" /></a>
</p>

---

## Why Broom?

| Traditional cleaners (CleanMyMac, etc.) | Broom 🧹 |
|:---|:---|
| Install a $40/year app | Just say "broom" |
| Fixed cleaning rules | Learns your habits over time |
| Can't undo deletions | Full undo from trash |
| Scans silently in background | Every step transparent & reviewable |
| One-size-fits-all | Conversational config, no YAML editing |
| Closed source | Open source, community-driven |

## What it does

```
You: "broom"
🧹 Scanning your Mac... (30 seconds)

🧹 Broom Diagnosis

Your disk has 34GB free (85% used). I found ~9GB to clean:

  🔑 Top 3:
  1. WeChat old backup — 4.0GB (old phone migration, probably don't need)
  2. Ollama local model — 3.2GB (unused AI model)
  3. Edge browser cache — 503MB (pure cache, auto-rebuilds)

  📊 Full plan saved to cleanup-plan.md
  Say "execute" — I'll show you a preview before touching anything.
```

## Features

- 🧠 **Smart Diagnosis** — Scans caches, app data (WeChat, Lark, Edge, Slack...), Docker, iOS backups, Downloads, and large files with intelligent grouping
- 🎯 **Conversational Config** — Never edit a file. Just say what you want:
  - *"Clean Excel files older than 3 months automatically"*
  - *"Check my Mac every Sunday morning"*
  - *"Never touch my personal documents"*
- ↩️ **Full Undo** — App data goes to trash (recoverable). Every action logged in `cleanup-undo.log`. Say *"undo last cleanup"* to restore
- 📈 **Trend Tracking** — See what's eating your space and where it came from week over week
- 🏆 **Personal Leaderboard** — Beat your own records. Track streaks, badges, and milestones
- ⚠️ **Running App Detection** — Skips caches of apps you're currently using
- 🔒 **10 Safety Rules** — Personal docs never deleted. Databases never touched. Dry Run before every action. [Read all 10 →](#safety-rules)

<a id="installation"></a>

## Quick Start

### Prerequisites

- macOS (Apple Silicon or Intel)
- [OpenClaw](https://openclaw.ai) installed and running

### Installation

```bash
# Option 1: Clone directly
git clone https://github.com/hisunfei/broom.git ~/.openclaw/workspace/skills/broom

# Option 2: Copy files
mkdir -p ~/.openclaw/workspace/skills/broom
cp -r broom/* ~/.openclaw/workspace/skills/broom/
```

That's it. No config files to edit. No dependencies to install.

### First Run

Just say to your OpenClaw assistant:

> **"broom"** or **"help me clean my Mac"**

Broom will introduce itself, scan your system, and guide you through the first cleanup.

## Commands

| Command | What it does |
|:---|:---|
| `broom` / `clean my Mac` | Full diagnostic scan |
| `quick clean` | Skip scan, clean safe items from last plan |
| `undo last cleanup` | Restore files from trash |
| `scan only Downloads` | Partial scan of specific area |
| `broom stats` | Show achievements & personal leaderboard |
| `share broom` | Generate project intro card |

## How It Works

```
┌──────────────────────────────────────────────┐
│  Phase 0: Onboarding (first time only)       │
│  "Hi! I'm Broom, your AI Mac janitor."       │
├──────────────────────────────────────────────┤
│  Phase 1: Diagnosis                          │
│  Parallel scan → Smart grouping → Plan       │
├──────────────────────────────────────────────┤
│  Phase 2: Execution                          │
│  Safety check → Dry Run → Confirm → Clean    │
│  → Health check                              │
├──────────────────────────────────────────────┤
│  Phase 3: Achievements & Learning            │
│  Leaderboard → Badges → Preference learning  │
├──────────────────────────────────────────────┤
│  Phase 4: Scheduled Runs (optional)          │
│  Weekly/Monthly → Diagnose → Notify → Wait   │
└──────────────────────────────────────────────┘
```

<a id="safety-rules"></a>

## Safety Rules

Broom follows 10 strict safety rules:

1. **Never delete personal documents** — ID, diploma, contracts, etc. Even if marked `clean`
2. **Never delete app databases** — Messages, mmkv, config, *.db, *.sqlite
3. **Running apps detected** — Only clear caches, never main data of running apps
4. **App data → `trash`** — Always recoverable from Trash
5. **Safe caches → `rm -rf`** — These auto-rebuild, no risk
6. **Clear contents, not directories** — Avoids permission issues
7. **Snapshot before cleanup** — Records sizes for comparison
8. **When unsure → `review`** — Let the user decide
9. **Always Dry Run** — Preview every operation before execution
10. **Complete undo log** — Every action recorded for rollback

## Contributing

### Add App Rules

Found an app Broom doesn't recognize? Add it to `references/app-rules.yaml`:

```yaml
- name: "Your App"
  bundle_id: "com.example.app"
  process_name: "YourApp"
  category: "app"  # safe / app / skip
  rules:
    - name: "Cache"
      path: "~/Library/Caches/YourApp"
      default_action: "review"
      trash_command: "trash <resolved_path>/*"
  protected:
    - "*.db"
    - "config"
```

Submit a PR with a screenshot of the app's data directories.

### Improve Translations

- Chinese: `assets/cleanup-plan-template.md`
- English: `assets/cleanup-plan-template-en.md`

## FAQ

**Q: Is my data safe?**
A: Broom runs 100% locally. No data leaves your machine. No analytics. No tracking.

**Q: Can I undo a cleanup?**
A: Yes! Say "undo last cleanup" to restore files from trash.

**Q: Will it break my apps?**
A: No. Broom only clears caches and temp files. Running apps are detected and skipped. A health check runs after cleanup.

**Q: How is this different from CleanMyMac?**
A: Broom is free, open-source, runs inside your AI assistant, learns your habits, and supports full undo. No $40/year subscription.

**Q: Does it work on Linux/Windows?**
A: Not yet. macOS only. The architecture supports extension to other platforms — contributions welcome!

## Architecture

```
broom/
├── README.md                           # This file (English)
├── README_zh.md                        # 中文版
├── LICENSE                             # MIT
├── SKILL.md                            # Agent instructions
├── assets/
│   ├── cleanup-plan-template.md        # Chinese report template
│   ├── cleanup-plan-template-en.md     # English report template
│   └── broom-preferences-template.yaml # Default preferences
└── references/
    └── app-rules.yaml                  # App cleanup rules (community)
```

## License

[MIT](LICENSE) — Free for personal and commercial use.

---

<p align="center">
  Made with 🧹 by <a href="https://github.com/hisunfei">hisunfei</a> and the <a href="https://openclaw.ai">OpenClaw</a> community
</p>
