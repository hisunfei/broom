---
name: broom
display_name: Broom 🧹 Mac 智能清理助手
display_name_en: Broom 🧹 Smart Mac Cleaner
description: "AI Mac 磁盘清理工具。说 'broom' 或 '清理电脑' 即可智能扫描缓存、应用数据、Downloads，安全释放空间。支持撤销、趋势追踪、定时清理。"
description_zh: "你的 AI Mac 电脑管家。不装软件、不付费、说句话就行。智能扫描磁盘，清理缓存、应用数据、Downloads，支持完整撤销和趋势追踪。"
description_en: "Your AI Mac janitor. No app. No subscription. Just say 'broom'. Smart disk cleanup with undo, scheduling, and trend tracking."
examples_zh:
  - "broom"
  - "清理电脑"
  - "撤销上次清理"
examples_en:
  - "broom"
  - "clean my Mac"
  - "undo last cleanup"
version: 2.1.0
author: "hisunfei"
---

# Broom 🧹

**Your AI Mac janitor. No app. No subscription. Just say the word.**

你的 AI 电脑管家。不装软件、不付费、说句话就行。

仅支持 macOS。

## 触发指令

| 指令 | 行为 |
|------|------|
| 「电脑诊断」「清理磁盘」「broom」 | Phase 1 完整诊断 |
| 「快速清理」 | 跳过诊断，按上次 plan 的 🟢 safe 项执行 |
| 「撤销上次清理」 | 从 cleanup-undo.log 恢复文件 |
| 「只扫 Downloads」 | 局部扫描 |
| 「清理统计」「broom stats」 | 展示成就、排行榜、历史趋势 |
| 「检查不常用应用」「哪些应用没用」 | 应用使用分析，识别不常用应用 |
| 定期任务（cron） | Phase 1 → 通知 → 等待确认 |

## 工作流

```
Phase 0: Onboarding（仅首次）
Phase 1: 诊断 → cleanup-plan.md + cleanup-plan.yaml
Phase 1.5: 应用使用分析（可选）→ 识别不常用应用
Phase 2: 安全检查 → Dry Run → 确认 → 执行 → 健康检查
Phase 3: 成就 + 个人排行榜 + 偏好学习
Phase 4: (可选) 定期运行
```

## Phase 1: 诊断

### 1.1 并行扫描

三批并行：基础信息 → 缓存与临时文件 → 专项扫描（大文件、iOS 备份、Docker、Time Machine、系统日志、字体缓存、Mail 附件、node_modules、已卸载应用残留、Homebrew 未使用包、历史对比）。

### 1.2 智能分类

从 `references/app-rules.yaml` 读取规则：🟢 safe / 🟡 app / 🔵 skip

### 1.3 生成计划

`cleanup-plan.md`（人类可读）+ `cleanup-plan.yaml`（机器可读）

### 1.4 人格化诊断报告

用一段话总结，不直接甩表格。



## Phase 1.5: 应用使用分析（可选）

### 1.5.1 数据源

多数据源交叉验证：

| 数据源 | 说明 | 可靠性 |
|--------|------|--------|
| Spotlight kMDItemUseCount | 应用使用次数 | ⭐⭐⭐⭐ |
| Spotlight kMDItemLastUsedDate | 最后使用时间 | ⭐⭐⭐⭐ |
| ~/Library/Application Support/ | 应用数据目录活动时间 | ⭐⭐⭐⭐⭐ |
| 进程运行状态 | 当前是否运行 | ⭐⭐⭐⭐⭐ |

### 1.5.2 Bundle ID 映射

应用名称 ≠ 存储目录名称，需要通过 Bundle ID 推断：

```javascript
const APP_DIR_MAP = {
  'ChatGPT': ['OpenAI', 'com.openai.codex'],
  'Doubao': ['Doubao'],
  '企业微信': ['com.tencent.WeWorkMac'],
  'WeChat': ['com.tencent.xinWeChat'],
  'Microsoft OneNote': ['com.microsoft.onenote.mac'],
  'QQ': ['com.tencent.qq'],
  'UPDF': ['com.superace.updf.mac']
};
```

### 1.5.3 分类规则

| 分类 | 条件 | 文案 |
|------|------|------|
| 👻 未发现使用痕迹 | 热度 0次 + 无 Application Support 数据 | 未发现使用痕迹 |
| 🌫️ 已落灰 | 热度 ≤10次 + >90天未活动 | 已落灰，建议检查 |
| 🔥 活跃使用中 | 7天内有活动 | 今天活跃 / N天前活跃 |

### 1.5.4 保护名单

以下应用不提示卸载：

```yaml
protected_apps:
  # 系统应用
  - Safari
  - Keynote
  - Numbers
  - Pages
  
  # 配套应用
  - net.downloadhelper    # Chrome 下载助手
  - 豆包浏览器            # 豆包组件（替身）
  
  # 工具类
  - Tailscale             # VPN
  - The Unarchiver        # 解压工具
  
  # AI 助手
  - DeepSeek Harness
  - WorkBuddy
```

### 1.5.5 自动过滤

- **替身类型**：kMDItemKind = "替身"，不是独立应用
- **系统应用**：/System/Applications 下的应用

### 1.5.6 报告格式

```markdown
### 👻 未发现使用痕迹

| # | 应用 | 大小 | 热度 | 状态 |
|---|------|------|------|------|
| 1 | wechatwebdevtools | 1.1G | 0次 | 未发现使用痕迹 |

### 🌫️ 已落灰，建议检查

| # | 应用 | 大小 | 热度 | 状态 |
|---|------|------|------|------|
| 1 | Trae CN | 922M | 0次 | 104天未活动，已落灰 |

### 🔥 活跃使用中

| # | 应用 | 大小 | 热度 | 状态 |
|---|------|------|------|------|
| 1 | Microsoft Edge | 1.6G | 9,670次 | 🔥 今天活跃 |
```

### 1.5.7 文案规范

| 场景 | 文案 |
|------|------|
| 热度显示 | 热度: 9,670次 |
| 从未使用 | 未发现使用痕迹 |
| 很久没用 | 已落灰，建议检查 |
| 卸载建议 | 如果不再使用，可考虑卸载 |
| 不确定 | 数据不足，需要你确认 |

### 1.5.8 安全原则

- **只提示，不自动卸载**
- 卸载使用 `trash`（可恢复）
- 用户确认后才会执行

## Phase 2: 执行

### 2.1 安全检查

运行中应用检测 → 计划过期 → 证件二次确认 → 数据库保护

### 2.2 Dry Run

展示将要执行的操作，醒目标注运行中的应用。

### 2.3 执行

- 🟢 `rm -rf`（纯缓存）
- 🟡 `trash`（可恢复），降级为 `mv ~/.Trash/`
- 每项独立 try/catch
- 写 `cleanup-undo.log`

### 2.4 健康检查

验证应用关键目录和 plist 完好。

## 安全红线（10 条）

1. **永远不删个人证件文件**
2. **永远不删应用数据库**
3. **应用运行时只清缓存**
4. **🟡用 `trash`，🟢用 `rm -rf`**
5. **清目录内容不删目录本身**
6. **清理前快照到 `cleanup-snapshot.json`**
7. **不确定时标 `review`**
8. **每次执行前必须 Dry Run**
9. **仅支持 macOS**
10. **Undo 日志必须完整记录**

## 应用规则

`references/app-rules.yaml` 存储 30+ 应用的清理规则，支持社区贡献。

## 偏好文件

`~/.broom/broom-preferences.yaml`，由 Agent 自动维护。

## 成就系统

11 个徽章 + 个人排行榜，和自己的历史比赛。

## 版本

当前版本：v2.1.0
