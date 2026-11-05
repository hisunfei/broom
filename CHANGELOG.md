# Changelog

All notable changes to Broom will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/),
and this project adheres to [Semantic Versioning](https://semver.org/).

## [2.1.0] - 2026-11-05

### Added
- **Phase 1.5: 应用使用分析** — 识别不再需要的应用，建议卸载
- **多数据源交叉验证** — Spotlight + Application Support + 进程状态
- **Bundle ID 映射** — 通过 Bundle ID 查找应用实际存储目录，解决应用名称 ≠ 目录名问题
- **热度评分** — 直接使用 Spotlight 使用次数，直观展示应用活跃度
- **保护名单** — 系统应用、配套应用、工具类应用不提示卸载
- **拟人化文案** — "未发现使用痕迹"、"已落灰，建议检查"

### Changed
- 触发指令新增：`检查不常用应用`、`哪些应用没用`
- 安全原则：只提示，不自动卸载；卸载使用 `trash`（可恢复）
- 自动过滤"替身"类型应用（非独立应用）

### Fixed
- Spotlight 数据盲区：某些应用（如 ChatGPT、Doubao）Spotlight 不记录使用数据，通过 Application Support 活动时间补充
- 应用名称 ≠ 存储目录名称：通过 Bundle ID 推断实际存储目录
- 命令行调用的应用（如 mpv）标记为"数据不足"，让用户确认

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
