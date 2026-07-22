<p align="center">
  <img src="https://raw.githubusercontent.com/hisunfei/broom/main/assets/broom-logo.png" width="100" alt="Broom - Free Mac Cleaner & Disk Cleanup Tool" />
</p>

<h1 align="center">Broom 🧹</h1>

<p align="center">
  <strong>Free AI Mac Cleaner — disk cleanup, cache cleaning, large file scanning, all in one sentence.</strong><br/>
  <strong>The open-source CleanMyMac alternative. No app. No subscription. Just say the word.</strong>
</p>

<p align="center">
  <a href="README.md">中文</a> · <strong>English</strong>
</p>

<p align="center">
  <a href="#installation"><img src="https://img.shields.io/badge/🚀_Install-say_%22broom%22-4A90D9?style=flat-square" alt="Install Mac Cleaner" /></a>
  <a href="#safety-rules"><img src="https://img.shields.io/badge/🔒_Safety-10_rules-green?style=flat-square" alt="Mac Cleaner Safety Rules" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/📄_License-MIT-lightgrey?style=flat-square" alt="MIT Open Source License" /></a>
  <a href="https://openclaw.ai"><img src="https://img.shields.io/badge/⚡_Powered_by-OpenClaw-orange?style=flat-square" alt="Powered by OpenClaw AI" /></a>
</p>

---

<!-- SEO: keyword-rich paragraph for search engine indexing -->
<p align="center">
<sub>Broom is an AI-powered macOS disk cleanup tool that intelligently scans caches, app data (WeChat, Slack, Edge, Docker), iOS backups, Downloads, and large files to free up disk space. A free, open-source alternative to CleanMyMac and DaisyDisk with full undo, trend tracking, and scheduled cleanup. Works on Apple Silicon and Intel Macs.</sub>
</p>

---

<br/>

## 💀 Your Mac's Disk Space Is Suffocating

Did you know?

> WeChat silently hoarded **20GB** — old phone backups, expired stickers, group chat images from 3 years ago.
>
> Docker stacked **15 image layers**. You've only used 2.
>
> `~/Downloads` has **47 `.zip` files**. The newest one is from last year.
>
> And your Mac has only **12GB** free. The fans are getting louder.

The old way: install a **Mac cleaner app**, pay $40/year, put your trust in a black box you don't understand.

**Broom is different — it's your AI Mac janitor.**

<br/>

## 🧹 See It Clean Your Mac (30 seconds)

```
You: broom

🧹 Scanning your Mac disk... (about 30 seconds)


🧹 Broom Mac Disk Diagnosis Complete

Disk: 34GB free (85% used). I found ~9GB that's safe to clean:

 🔑 Top 3:
  1. WeChat old backup     4.0GB  ← old phone migration, you probably don't need it
  2. Ollama model          3.2GB  ← an AI model you're not using
  3. Edge cache            503MB  ← pure cache, auto-rebuilds

 📊 Full cleanup plan saved to cleanup-plan.md
 Say "execute" — I'll preview everything before touching a single file.
```

**No install wizard. No scan progress popup. No "upgrade to Pro". One sentence to clean your Mac.**

<br/>

## ⚔️ Broom vs CleanMyMac — Free Open-Source Alternative

| | CleanMyMac / DaisyDisk | **Broom** 🧹 |
|:--|:--|:--|
| **Price** | $40/year | **Free**, forever (MIT open source) |
| **Setup** | Download → Install → Grant access → Wait | Say "broom" |
| **Logic** | Fixed rules, same for everyone | **AI learns** your habits over time |
| **Deleted wrong file?** | Good luck | Say "undo" — **full restore** from Trash |
| **Transparency** | Black box, you just have to trust it | Every step in a file you can **review** |
| **Configuration** | Settings panel | Plain English, **conversational config** |
| **Open source** | ❌ | ✅ MIT |

<br/>

## ✨ More Than a Mac Cache Cleaner — A Janitor That Knows You

<details>
<summary>🧠 <strong>Smart Mac Diagnosis</strong> — beyond cache scanning</summary>
<br/>

Scans WeChat, Slack, Lark, Edge, Docker, iOS backups, Downloads, large files, node_modules, Homebrew orphans... intelligently grouped and sorted by impact. No scrolling through 200-line lists.

Covers the most common macOS space hogs: app caches, chat attachments, browser caches, Docker images, Xcode derived data, npm/pip caches, and more.

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

Broom saves your preferences in `broom-preferences.yaml` and applies them automatically next time. No config file editing required.

</details>

<details>
<summary>↩️ <strong>Full Undo</strong> — changed your mind? One sentence to restore</summary>
<br/>

- App data → Trash (recoverable from macOS Trash)
- Every action logged in `cleanup-undo.log`
- Say "undo last cleanup" — everything comes back

**You don't need to trust Broom. You can verify every step.**

</details>

<details>
<summary>📈 <strong>Disk Space Trend Tracking</strong> — know where your space goes</summary>
<br/>

Weekly macOS disk comparisons. Tells you which app is the biggest hoarder:

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

macOS apps you're currently running are automatically detected. Broom only clears their caches (safe), never their main data.

</details>

<details>
<summary>🤖 <strong>Scheduled Mac Disk Cleanup (optional)</strong> — you don't need to remember</summary>
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

## 🚀 Install Broom — Free Mac Cleaner

### Prerequisites

- **macOS** (Apple Silicon M1/M2/M3/M4 or Intel)
- [OpenClaw](https://openclaw.ai) installed and running

### One Command to Install

```bash
git clone https://github.com/hisunfei/broom.git ~/.openclaw/workspace/skills/broom
```

No config to edit. No dependencies to install. No Mac restart needed.

### Start Cleaning Your Mac

Just say to your OpenClaw assistant:

> **"broom"** or **"clean my Mac"** or **"disk space running low"**

On first use, Broom introduces itself, guides you through the first Mac disk cleanup, and collects your preferences through conversation — **no config file editing required**.

<br/>

## 📋 Mac Cleanup Commands

| You say | Broom does |
|:--|:--|
| `broom` / `clean my Mac` / `disk cleanup` | 🔍 Full Mac disk diagnostic scan |
| `quick clean` | ⚡ Skip scan, clean safe items |
| `undo last cleanup` | ↩️ Restore files from Trash |
| `scan only Downloads` | 🎯 Partial scan of specific directory |
| `broom stats` | 🏆 Achievements & leaderboard |
| `share broom` | 📤 Generate project intro card |

<br/>

<a id="safety-rules"></a>

## 🔒 Mac Cleanup Safety Rules

**Broom follows 10 unbreakable safety rules to protect your Mac data:**

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
<td><strong>App data → macOS Trash</strong> — always recoverable</td>
</tr>
<tr>
<td align="center">5</td>
<td><strong>Pure caches → rm -rf</strong> — macOS auto-rebuilds, zero risk</td>
</tr>
<tr>
<td align="center">6</td>
<td><strong>Clear contents, not directories</strong> — avoids macOS permission issues</td>
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

## 🔄 Mac Cleanup Workflow

```
Phase 0  Onboarding (first time only)
  │       "Hi! I'm Broom, your AI Mac cleanup janitor."
  ▼
Phase 1  Mac Disk Diagnosis
  │       Parallel scan → Smart grouping → Cleanup plan
  ▼
Phase 2  Execute Cleanup
  │       Safety check → Dry Run preview → Confirm → Clean → Health check
  ▼
Phase 3  Achievements & Learning
  │       Leaderboard → Badges → Preference learning
  ▼
Phase 4  Scheduled Mac Cleanup (optional)
          Weekly/Monthly → Diagnose → Notify → Wait for you
```

<br/>

## ❓ Mac Cleaner FAQ

<details>
<summary><strong>Is Broom safe for cleaning my Mac data?</strong></summary>

Broom runs 100% locally on your Mac. No data leaves your machine. No analytics. No tracking. Your disk information never leaves your computer.
</details>

<details>
<summary><strong>Can I undo a Mac cleanup?</strong></summary>

Yes. App data goes to macOS Trash (recoverable). Pure caches auto-rebuild (no recovery needed). Just say "undo last cleanup".
</details>

<details>
<summary><strong>Will it break my Mac apps?</strong></summary>

No. Broom only clears caches and temp files. Running apps are detected and skipped. A health check after cleanup verifies app integrity.
</details>

<details>
<summary><strong>How is Broom different from CleanMyMac? Why is it a better Mac cleaner?</strong></summary>

Broom is free, open-source, runs inside your AI assistant, uses AI to learn your habits, and supports full undo. No $40/year. CleanMyMac is a standalone app; Broom is a capability of your AI assistant — smarter, more transparent.
</details>

<details>
<summary><strong>Does it work on Linux / Windows or only Mac cleanup?</strong></summary>

macOS only for now (Apple Silicon and Intel). The architecture supports extension to other platforms — contributions welcome!
</details>

<details>
<summary><strong>Which Mac apps can Broom clean?</strong></summary>

Currently supports: WeChat, Slack, Lark, Edge, Chrome, Safari, Docker Desktop, Xcode, iOS backups, Ollama, Homebrew, npm/pip caches, and more. Community-driven — you can contribute rules for your favorite apps.
</details>

<br/>

## 🤝 Contributing

### Add macOS App Cleanup Rules

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
├── LICENSE                             # MIT open source license
├── SKILL.md                            # Agent instructions
├── assets/
│   ├── cleanup-plan-template.md        # Chinese cleanup report template
│   ├── cleanup-plan-template-en.md     # English cleanup report template
│   └── broom-preferences-template.yaml # Default preferences
└── references/
    └── app-rules.yaml                  # macOS app cleanup rules (community)
```

<br/>

## 📄 License

[MIT](LICENSE) — Free for personal and commercial use.

<br/>

---

<p align="center">
  <strong>Free AI Mac Cleaner. No app. No subscription. Just say the word.</strong><br/><br/>
  Made with 🧹 by <a href="https://github.com/hisunfei">hisunfei</a> and the <a href="https://openclaw.ai">OpenClaw</a> community
</p>
