<p align="center">
  <img src="https://raw.githubusercontent.com/hisunfei/broom/main/assets/broom-logo.png" width="120" alt="Broom" />
</p>

<h1 align="center">🧹 Broom</h1>

<p align="center">
  <strong>你的 AI 电脑管家。不装软件、不付费、说句话就行。</strong>
</p>

<p align="center">
  <a href="README_en.md">English</a> · <strong>中文</strong>
</p>

<p align="center">
  <a href="#安装"><img src="https://img.shields.io/badge/安装-说%20%22broom%22-4A90D9?style=flat-square" alt="安装" /></a>
  <a href="#功能"><img src="https://img.shields.io/badge/平台-macOS-lightgrey?style=flat-square" alt="平台" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/许可-MIT-green?style=flat-square" alt="许可" /></a>
  <a href="https://openclaw.ai"><img src="https://img.shields.io/badge/驱动-OpenClaw-orange?style=flat-square" alt="OpenClaw" /></a>
</p>

---

## 为什么选 Broom？

| 传统清理工具（CleanMyMac 等） | Broom 🧹 |
|:---|:---|
| 装一个 $40/年的 App | 说句话就行 |
| 固定清理规则 | 越用越懂你的习惯 |
| 删了不能恢复 | 从废纸篓完整恢复 |
| 后台静默扫描 | 每一步透明可审阅 |
| 一刀切 | 对话式配置，不用改文件 |
| 闭源 | 开源，社区共建 |

## 它能做什么

```
你: "broom"
🧹 正在扫描你的电脑...（约 30 秒）

🧹 Broom 诊断完成

你的磁盘只剩 34GB 了（85% 已用），我找到 ~9GB 可以清理：

  🔑 最大的三块：
  1. 微信旧备份 — 4.0GB（旧手机迁移来的，可能不需要了）
  2. Ollama 本地模型 — 3.2GB（未使用的 AI 模型）
  3. Edge 浏览器缓存 — 503MB（纯缓存，自动重建）

  📊 详细计划已保存到 cleanup-plan.md
  说「执行」，我会先让你预览再动手。
```

## 功能

- 🧠 **智能诊断** — 扫描缓存、应用数据（微信/飞书/Edge/Slack...）、Docker、iOS 备份、Downloads、大文件，智能分组展示
- 🎯 **对话式配置** — 不用改任何文件，直接说：
  - *"3 个月以上的 Excel 自动清"*
  - *"每周日帮我检查一下"*
  - *"证件文件永远别动"*
- ↩️ **完整撤销** — 应用数据进废纸篓（可恢复），每次操作记录在 `cleanup-undo.log`，说 *"撤销上次清理"* 即可恢复
- 📈 **趋势追踪** — 看磁盘空间每周怎么涨的，哪来的
- 🏆 **个人排行榜** — 和自己的历史比，追踪连续清理、徽章、里程碑
- ⚠️ **运行中应用检测** — 正在用的应用缓存自动跳过
- 🔒 **10 条安全红线** — 个人证件永不删除，数据库永不触碰，每次执行前必须预览确认。[查看全部 →](#安全红线)

<a id="安装"></a>

## 快速上手

### 前置条件

- macOS（Apple Silicon 或 Intel）
- [OpenClaw](https://openclaw.ai) 已安装并运行

### 安装

```bash
# 方式 1：直接 clone
git clone https://github.com/hisunfei/broom.git ~/.openclaw/workspace/skills/broom

# 方式 2：复制文件
mkdir -p ~/.openclaw/workspace/skills/broom
cp -r broom/* ~/.openclaw/workspace/skills/broom/
```

就这么多。不用改配置，不用装依赖。

### 首次使用

对你的 OpenClaw 助手说：

> **"broom"** 或 **"帮我清理电脑"**

Broom 会自我介绍，扫描系统，引导你完成第一次清理。

## 指令

| 指令 | 功能 |
|:---|:---|
| `broom` / `清理电脑` | 完整诊断扫描 |
| `快速清理` | 跳过扫描，清理上次的 🟢 安全项 |
| `撤销上次清理` | 从废纸篓恢复文件 |
| `只扫 Downloads` | 局部扫描特定区域 |
| `broom stats` | 查看成就和个人排行榜 |
| `分享 broom` | 生成项目介绍卡片 |

## 工作流程

```
┌──────────────────────────────────────────────┐
│  Phase 0: 新手引导（仅首次）                    │
│  "嗨！我是 Broom，你的 AI 电脑管家。"            │
├──────────────────────────────────────────────┤
│  Phase 1: 诊断                                │
│  并行扫描 → 智能分组 → 生成清理计划              │
├──────────────────────────────────────────────┤
│  Phase 2: 执行                                │
│  安全检查 → Dry Run 预览 → 确认 → 清理 → 健康检查│
├──────────────────────────────────────────────┤
│  Phase 3: 成就与学习                           │
│  排行榜 → 徽章 → 偏好学习                       │
├──────────────────────────────────────────────┤
│  Phase 4: 定期运行（可选）                      │
│  每周/每月 → 诊断 → 通知 → 等待确认              │
└──────────────────────────────────────────────┘
```

<a id="安全红线"></a>

## 安全红线

Broom 遵循 10 条严格的安全规则：

1. **永不删除个人证件** — 毕业证、学位证、户口本、合同等，即使标记 clean
2. **永不删除应用数据库** — Messages、mmkv、config、*.db、*.sqlite
3. **检测运行中的应用** — 只清缓存，不动主数据
4. **应用数据 → 废纸篓** — 始终可从废纸篓恢复
5. **安全缓存 → rm -rf** — 自动重建，无风险
6. **清内容不清目录** — 避免权限问题
7. **清理前快照** — 记录原始大小用于对比
8. **不确定 → review** — 让用户决定
9. **每次必须 Dry Run** — 执行前预览所有操作
10. **完整撤销日志** — 每个操作可回滚

## 贡献

### 添加应用规则

发现 Broom 不认识的应用？在 `references/app-rules.yaml` 中添加：

```yaml
- name: "你的应用"
  bundle_id: "com.example.app"
  process_name: "YourApp"
  category: "app"
  rules:
    - name: "缓存"
      path: "~/Library/Caches/YourApp"
      default_action: "review"
      trash_command: "trash <resolved_path>/*"
  protected:
    - "*.db"
    - "config"
```

提交 PR 时附上应用数据目录的截图。

### 改进翻译

- 中文模板: `assets/cleanup-plan-template.md`
- 英文模板: `assets/cleanup-plan-template-en.md`

## 常见问题

**Q: 我的数据安全吗？**
A: Broom 100% 本地运行。不上传任何数据，不做分析，不追踪。

**Q: 清理了能恢复吗？**
A: 能！说「撤销上次清理」即可从废纸篓恢复。

**Q: 会不会搞坏我的应用？**
A: 不会。Broom 只清缓存和临时文件。正在运行的应用会被检测并跳过。清理后还有健康检查。

**Q: 和 CleanMyMac 有什么区别？**
A: Broom 免费、开源、在你的 AI 助手里运行、学习你的习惯、支持完整撤销。不用每年交 $40。

**Q: 支持 Linux/Windows 吗？**
A: 目前只支持 macOS。架构支持扩展到其他平台——欢迎贡献！

## 项目结构

```
broom/
├── README.md                           # 本文件（中文）
├── README_en.md                        # English version
├── LICENSE                             # MIT
├── SKILL.md                            # Agent 指令
├── assets/
│   ├── cleanup-plan-template.md        # 中文报告模板
│   ├── cleanup-plan-template-en.md     # 英文报告模板
│   └── broom-preferences-template.yaml # 默认偏好
└── references/
    └── app-rules.yaml                  # 应用清理规则（社区贡献）
```

## 许可证

[MIT](LICENSE) — 个人和商业使用均免费。

---

<p align="center">
  Made with 🧹 by <a href="https://github.com/hisunfei">hisunfei</a> and the <a href="https://openclaw.ai">OpenClaw</a> community
</p>
