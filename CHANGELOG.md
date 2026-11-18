# Changelog

## [2.3.0] - 2026-11-18

### Added
- **Phase 5: 自我检查与持续改进**
  - 5.1 问题自动检测机制（扫描完整性/风险分类/保护名单/用户反馈）
  - 5.2 问题记录流程（自动写入 DIARY.md）
  - 5.3 经验教训库查询（基于标签匹配历史问题）
  - 5.4 持续改进触发条件（用户反馈/系统异常/新发现/定期回顾）
  - 5.5 自动改进流程（记录→分析→方案→修复→验证→文档→提交）
  - 5.6 自我优化指标（扫描覆盖率/误删率/满意度/修复时间/重复问题率）
  - 5.7 持续改进示例（飞书授权/扫描不完整/风险分类）

### Changed
- 工作流从 4 个 Phase 扩展到 5 个 Phase
- 版本号: 2.2.0 → 2.3.0

### Improvements
- 形成持续改进闭环
- 问题自动检测和记录
- 经验教训可查询和复用
- 避免重复犯错


All notable changes to Broom will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/),
and this project adheres to [Semantic Versioning](https://semver.org/).

## [2.2.0] - 2026-11-18

### Fixed
- **扫描范围不完整**: 第一次扫描遗漏大量空间占用，现在采用五层扫描策略
- **风险分类不清晰**: 没有区分安全和不安全的清理项目，现在采用三级风险分类
- **误删飞书授权**: 清理 ~/.local 时误删飞书 keyring 授权信息，现在添加保护名单机制

### Added
- **多层扫描策略**: 五层扫描（基础缓存→隐藏目录→容器虚拟机→应用数据→系统级）
- **三级风险分类**: 🟢绝对安全 / 🟡需要确认 / 🔴高风险
- **保护名单机制**: 全局保护 keyrings/tokens/credentials/auth
- **应用精细化规则**: 区分缓存和数据（微信/飞书/浏览器/开发工具）
- **清理前检查**: Dry-run 模式 + 敏感文件检测
- **飞书特别保护**: 标注授权信息在 ~/.local/share/keyrings

### Changed
- SKILL.md: 添加多层扫描、三级分类、保护名单章节
- app-rules.yaml: 精细化规则，每个应用区分 cache_dirs 和 data_dirs
- 版本号: 2.1.0 → 2.2.0

### Security
- 新增保护模式: **/keyrings/**, **/tokens/**, **/credentials/**, **/auth/**
- 清理前自动检查敏感文件（token/auth/key）
- 飞书/钉钉/企业微信授权信息永久保护

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
