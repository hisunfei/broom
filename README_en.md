<p align="center">
  <img src="https://raw.githubusercontent.com/hisunfei/broom/main/assets/broom-logo.png" width="100" alt="Broom" />
</p>

<h1 align="center">Broom 🧹</h1>

<p align="center">
  <strong>Your Mac is suffocating.</strong><br/>
  <strong>No app to install. No subscription. Just say the word.</strong>
</p>

<p align="center">
  <a href="README.md">中文</a> · <strong>English</strong>
</p>

<p align="center">
  <a href="#installation"><img src="https://img.shields.io/badge/🚀_Install-say_%22broom%22-4A90D9?style=flat-square" alt="Install" /></a>
  <a href="#safety-rules"><img src="https://img.shields.io/badge/🔒_Safety-10_rules-green?style=flat-square" alt="Safety" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/📄_License-MIT-lightgrey?style=flat-square" alt="License" /></a>
  <a href="https://openclaw.ai"><img src="https://img.shields.io/badge/⚡_Powered_by-OpenClaw-orange?style=flat-square" alt="OpenClaw" /></a>
</p>

---

<br/>

## 💀 Your Mac is suffocating

Did you know?

> WeChat silently hoarded **20GB** — old phone backups, expired stickers, group chat images from 3 years ago.
>
> Docker stacked **15 image layers**. You've only used 2.
>
> `~/Downloads` has **47 `.zip` files**. The newest one is from last year.
>
> And your Mac has only **12GB** free. The fans are getting louder.

The old way: install a cleaner app, pay $40/year, put your trust in a black box you don't understand.

**Broom is different.**

<br/>

## 🧹 See it in action (30 seconds)

```
You: broom

🧹 Scanning your Mac... (about 30 seconds)


🧹 Broom Diagnosis Complete

Disk: 34GB free (85% used). I found ~9GB that's safe to clean:

 🔑 Top 3:
  1. WeChat old backup     4.0GB  ← old phone migration, you probably don't need it
  2. Ollama model          3.2GB  ← an AI model you're not using
  3. Edge cache            503MB  ← pure cache, auto-rebuilds

 📊 Full plan saved to cleanup-plan.md
 Say "execute" — I'll preview everything before touching a single file.
```

**No install wizard. No scan progress popup. No "upgrade to Pro". Just one sentence.**

<br/>

## ⚔️ Broom vs. CleanMyMac

| | CleanMyMac & friends | **Broom** 🧹 |
|:--|:--|:--|
| **Price** | $40/year | Free, forever |
| **Setup** | Download → Install → Grant access → Wait | Say "broom" |
| **Logic** | Fixed rules, same for everyone | Learns your habits over time |
| **Oops, deleted the wrong thing?** | Good luck | Say "undo" — restores from Trash |
| **Transparency** | Black box, you just have to trust it | Every step in a file you can review |
| **Configuration** | Settings panel | Plain English |
| **Open source** | ❌ | ✅ MIT |

<br/>

## ✨ More than a cleaner — a janitor that knows you

<details>
<summary>🧠 <strong>Smart Diagnosis</strong> — beyond cache scanning</summary>
<br/>

Scans WeChat, Slack, Lark, Edge, Docker, iOS backups, Downloads, large files, node_modules, Homebrew orphans... intelligently grouped and sorted by impact. No scrolling through 200-line lists.

</details>

<details>
<summary>🎯 <strong>Plain English Config</strong> — never edit a file</summary>
<br/>

```
You: Auto-clean Excel files older than 3 months
You: Check my Mac every Sunday morning
You: Never touch my personal documents
You: Skip research report PDFs from now on
```

Broom saves your preferences in `broom-preferences.yaml` and applies them automatically next time.

</details>

<details>
<summary>↩️ <strong>Full Undo</strong> — changed your mind? One sentence to restore</summary>
<br/>

- App data → Trash (recoverable)
- Every action logged in `cleanup-undo.log`
- Say "undo last cleanup" — everything comes back

**You don't need to trust Broom. You can verify every step.**

</details>

<details>
<summary>📈 <strong>Trend Tracking</strong> — know where your space goes</summary>
<br/>

Weekly disk comparisons. Tells you which app is the biggest hoarder:

```
📈 This week vs last week
  Slack: +4GB (again)
  Downloads: +2GB
  Docker: unchanged
```

</details>

<details>
<summary>🏆 <strong>Personal Leaderboard</strong> — compete with yourself</summary>
<br/>

```
🧹 Your Broom Leaderboard

🏆 Personal Bests
  ⚡ Most freed in one run    34GB (Jul 21) ← today!
  🔥 Longest streak           3 weeks (ongoing)
  💎 Total freed              67GB
  📦 Most files in one run    53

🎯 Next milestone
  33GB more → unlock 💎 100GB badge
```

**No external data collection. You only compete with your own history.**

</details>

<details>
<summary>⚠️ <strong>Running App Detection</strong> — won't touch what you're using</summary>
<br/>

Apps you're currently running are automatically detected. Broom only clears their caches (safe), never their main data.

</details>

<details>
<summary>🤖 <strong>Scheduled Patrol (optional)</strong> — you don't need to remember</summary>
<br/>

```
🧹 Broom Weekly Report

Disk grew 6GB this week (now 78%)
Main growth: Slack +4GB | Downloads +2GB

Found ~8GB to clean. Want details?

🎯 2 more cleanups to unlock 💎 100GB
```

You set the frequency, you set the time. Quiet hours respected (default 22:00–08:00).

</details>

<br/>

<a id="installation"></a>

## 🚀 Installation

### Prerequisites

- **macOS** (Apple Silicon or Intel)
- [OpenClaw](https://openclaw.ai) installed and running

### One command

```bash
git clone https://github.com/hisunfei/broom.git ~/.openclaw/workspace/skills/broom
```

No config to edit. No dependencies to install. No restart needed.

### First run

Just say to your OpenClaw assistant:

> **"broom"** or **"help me clean my Mac"**

On first use, Broom introduces itself, guides you through the first cleanup, and collects your preferences through conversation — **no config file editing required**.

<br/>

## 📋 Command Reference

| You say | Broom does |
|:--|:--|
| `broom` / `clean my Mac` | 🔍 Full diagnostic scan |
| `quick clean` | ⚡ Skip scan, clean safe items |
| `undo last cleanup` | ↩️ Restore from Trash |
| `scan only Downloads` | 🎯 Partial scan of specific area |
| `broom stats` | 🏆 Achievements & leaderboard |
| `share broom` | 📤 Generate project intro card |

<br/>

<a id="safety-rules"></a>

## 🔒 Safety Rules

**Broom follows 10 unbreakable safety rules:**

<table>
<tr>
<td width="30" align="center">1</td>
<td><strong>Never delete personal documents</strong> — IDs, diplomas, contracts, even if marked clean</td>
</tr>
<tr>
<td align="center">2</td>
<td><strong>Never delete app databases</strong> — Messages, mmkv, config, *.db, *.sqlite</td>
</tr>
<tr>
<td align="center">3</td>
<td><strong>Running apps: caches only</strong> — auto-detected, main data untouched</td>
</tr>
<tr>
<td align="center">4</td>
<td><strong>App data → Trash</strong> — always recoverable</td>
</tr>
<tr>
<td align="center">5</td>
<td><strong>Pure caches → rm -rf</strong> — auto-rebuild, zero risk</td>
</tr>
<tr>
<td align="center">6</td>
<td><strong>Clear contents, not directories</strong> — avoids permission issues</td>
</tr>
<tr>
<td align="center">7</td>
<td><strong>Snapshot before cleanup</strong> — records sizes for comparison</td>
</tr>
<tr>
<td align="center">8</td>
<td><strong>When unsure → let you decide</strong> — marked as review</td>
</tr>
<tr>
<td align="center">9</td>
<td><strong>Always Dry Run</strong> — preview every operation before execution</td>
</tr>
<tr>
<td align="center">10</td>
<td><strong>Complete undo log</strong> — every action is rollbackable</td>
</tr>
</table>

<br/>

## 🔄 How It Works

```
Phase 0  Onboarding (first time only)
  │       "Hi! I'm Broom, your AI Mac janitor."
  ▼
Phase 1  Diagnosis
  │       Parallel scan → Smart grouping → Cleanup plan
  ▼
Phase 2  Execution
  │       Safety check → Dry Run preview → Confirm → Clean → Health check
  ▼
Phase 3  Achievements & Learning
  │       Leaderboard → Badges → Preference learning
  ▼
Phase 4  Scheduled Patrol (optional)
          Weekly/Monthly → Diagnose → Notify → Wait for you
```

<br/>

## ❓ FAQ

<details>
<summary><strong>Is my data safe?</strong></summary>

Broom runs 100% locally. No data leaves your machine. No analytics. No tracking. Your disk information never leaves your computer.
</details>

<details>
<summary><strong>Can I undo a cleanup?</strong></summary>

Yes. App data goes to Trash (recoverable). Pure caches auto-rebuild (no recovery needed). Just say "undo last cleanup".
</details>

<details>
<summary><strong>Will it break my apps?</strong></summary>

No. Broom only clears caches and temp files. Running apps are detected and skipped. A health check after cleanup verifies app integrity.
</details>

<details>
<summary><strong>How is this different from CleanMyMac?</strong></summary>

Broom is free, open-source, runs inside your AI assistant, learns your habits, and supports full undo. No $40/year. CleanMyMac is a standalone app; Broom is a capability of your AI assistant.
</details>

<details>
<summary><strong>Does it work on Linux / Windows?</strong></summary>

macOS only for now. The architecture supports extension to other platforms — contributions welcome!
</details>

<br/>

## 🤝 Contributing

### Add App Rules

Found an app Broom doesn't recognize? Add it to `references/app-rules.yaml`:

```yaml
- name: "Your App"
  bundle_id: "com.example.app"
  process_name: "YourApp"
  category: "app"       # safe / app / skip
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

- Chinese template: `assets/cleanup-plan-template.md`
- English template: `assets/cleanup-plan-template-en.md`

<br/>

## 📁 Project Structure

```
broom/
├── README.md                           # Default (中文)
├── README_en.md                        # This file (English)
├── LICENSE                             # MIT
├── SKILL.md                            # Agent instructions
├── assets/
│   ├── cleanup-plan-template.md        # Chinese report template
│   ├── cleanup-plan-template-en.md     # English report template
│   └── broom-preferences-template.yaml # Default preferences
└── references/
    └── app-rules.yaml                  # App cleanup rules (community)
```

<br/>

## 📄 License

[MIT](LICENSE) — Free for personal and commercial use.

<br/>

---

<p align="center">
  <strong>No app to install. No subscription. Just say the word.</strong><br/><br/>
  Made with 🧹 by <a href="https://github.com/hisunfei">hisunfei</a> and the <a href="https://openclaw.ai">OpenClaw</a> community
</p>
