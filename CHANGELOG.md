# Changelog

All notable changes to Broom will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/),
and this project adheres to [Semantic Versioning](https://semver.org/).

## [2.0.0] - 2026-10-23

### Added
- **Version tracking**: SKILL.md now includes version field
- **Platform neutrality**: Removed all OpenClaw-specific references; works with any AI assistant
- **Error handling**: Added guidance for permission denied, resource busy, and other error scenarios
- **Timing & speed tracking**: Added start/end time recording for cleanup speed calculation
- **cleanup-snapshot.json**: Pre-cleanup snapshot implementation (Safety Rule #6)
- **cleanup-plan.yaml schema**: Full schema definition (v2.1) for machine-readable plans
- **Uninstalled app detection**: Logic to compare /Applications with ~/Library/Application Support
- **Large file scanning strategy**: Adaptive thresholds based on disk pressure levels
- **Homebrew unused packages**: brew_autoremove command for unused dependency detection
- **trash fallback**: Explicit mv ~/.Trash/ fallback when trash CLI is not installed
- **Scheduled scans**: Implementation guide using schedule_create or equivalent
- **CHANGELOG.md**: This file
- **20+ new app rules**: Chrome, Safari, Arc, Slack, Telegram, DingTalk, Notion, Obsidian, Cursor, VS Code, JetBrains, Xcode, Ollama, Claude, ChatGPT, and more

### Changed
- **show_widget → HTML visualization**: Replaced non-existent show_widget tool with portable HTML file generation
- **app-rules.yaml v2.2**: Expanded from 14 to 30+ app rules, reorganized by category
- **Personal doc keywords**: Added invoice/发票 to protected keywords list
- **Global protected patterns**: Added *.keychain to protected patterns

### Fixed
- Duplicate frontmatter in SKILL.md (had both "mac-cleaner" and "broom" entries)
- fastest_cleanup record calculation (was returning 0 due to missing timing)
- ⚡ badge threshold documentation (correctly states > 30GB)

## [1.0.0] - 2026-07-21

### Added
- Initial release
- Phase 1-4 workflow
- 10 safety rules
- Badge system (11 badges)
- Personal leaderboard
- Conversational configuration
- Undo support
- Trend tracking
- 14 app rules (WeChat, WeWork, Lark, Doubao, Edge, Trae CN, Xmind, Docker, iOS Backup, Time Machine, Steam, Quark, Apple Mail, Homebrew)
- Bilingual support (Chinese/English)
