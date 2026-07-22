<p align="center">
  <img src="https://raw.githubusercontent.com/hisunfei/broom/main/assets/broom-logo.png" width="100" alt="Broom" />
</p>

<h1 align="center">Broom 🧹</h1>

<p align="center">
  <strong>你的 Mac 越来越慢？</strong><br/>
  <strong>不需要装 App，不需要付费，说句话就行。</strong>
</p>

<p align="center">
  <a href="README_en.md">English</a> · <strong>中文</strong>
</p>

<p align="center">
  <a href="#安装"><img src="https://img.shields.io/badge/🚀_安装-说_%22broom%22-4A90D9?style=flat-square" alt="安装" /></a>
  <a href="#安全红线"><img src="https://img.shields.io/badge/🔒_安全-10_条红线-green?style=flat-square" alt="安全" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/📄_许可-MIT-lightgrey?style=flat-square" alt="许可" /></a>
  <a href="https://openclaw.ai"><img src="https://img.shields.io/badge/⚡_驱动-OpenClaw-orange?style=flat-square" alt="OpenClaw" /></a>
</p>

---

<br/>

## 💀 你的 Mac 正在窒息

你知道这些吗？

> 微信在你不知不觉中吞了 **20GB**——旧手机备份、过期表情包、三年前的群聊图片。
>
> Docker 镜像叠了 **15 层**，你只用过其中 2 个。
>
> `~/Downloads` 里有 **47 个 `.zip`**，最新的那个是去年下载的。
>
> 而你的 Mac 只剩 **12GB** 可用空间，风扇转得越来越勤。

传统做法：装个清理工具，每年交 ¥280，把信任交给一个你不了解的黑盒。

**Broom 不一样。**

<br/>

## 🧹 30 秒看它怎么工作

```
你：broom

🧹 正在扫描你的 Mac...（约 30 秒）


🧹 Broom 诊断完成

磁盘只剩 34GB（已用 85%）。我找到了 ~9GB 可以安全清理：

 🔑 最大的三块：
  1. 微信旧备份     4.0GB  ← 旧手机迁移来的，你大概不需要了
  2. Ollama 模型    3.2GB  ← 一个没在用的 AI 模型
  3. Edge 缓存      503MB  ← 纯缓存，删了自动重建

 📊 完整计划已保存到 cleanup-plan.md
 说「执行」— 我会先给你预览，确认后再动手。
```

**没有安装界面。没有扫描进度条弹窗。没有「升级到专业版」。就一句话的事。**

<br/>

## ⚔️ 和 CleanMyMac 们比一比

| | CleanMyMac 等 | **Broom** 🧹 |
|:--|:--|:--|
| **价格** | ¥280/年 | 免费，永远 |
| **安装** | 下载 → 安装 → 授权 → 等扫描 | 说句 "broom" |
| **清理逻辑** | 固定规则，所有人一样 | 越用越懂你的习惯 |
| **误删了？** | 自求多福 | 说「撤销」，从废纸篓恢复 |
| **透明度** | 黑盒扫描，你只能信它 | 每一步写在文件里，你可以审阅 |
| **配置** | 翻设置面板 | 直接说人话 |
| **开源** | ❌ | ✅ MIT |

<br/>

## ✨ 不只是清理，是一个懂你的管家

<details>
<summary>🧠 <strong>智能诊断</strong> — 不只是扫缓存</summary>
<br/>

扫描微信/飞书/Edge/Slack/Docker/iOS 备份/Downloads/大文件/node_modules/Homebrew 残留...智能分组，按影响大小排序，不让你翻 200 行列表。

</details>

<details>
<summary>🎯 <strong>说人话配置</strong> — 不用编辑任何文件</summary>
<br/>

```
你：3 个月以上的 Excel 自动清
你：每周日上午帮我检查一下
你：证件文件永远别动
你：以后遇到「调研报告」类的 PDF 默认跳过
```

Broom 把你的偏好记在 `broom-preferences.yaml` 里，下次自动应用。

</details>

<details>
<summary>↩️ <strong>完整撤销</strong> — 后悔了？一句话恢复</summary>
<br/>

- 应用数据 → 废纸篓（可从废纸篓恢复）
- 每个操作记录在 `cleanup-undo.log`
- 说「撤销上次清理」，全部恢复

**你不需要信任 Broom。你可以验证它的每一步。**

</details>

<details>
<summary>📈 <strong>趋势追踪</strong> — 知道空间去哪了</summary>
<br/>

每周对比磁盘变化，告诉你哪个应用最能「吃」空间：

```
📈 本周 vs 上周
  企业微信：+4GB（又是它）
  Downloads：+2GB
  Docker：不变
```

</details>

<details>
<summary>🏆 <strong>个人排行榜</strong> — 和自己的历史比赛</summary>
<br/>

```
🧹 你的 Broom 排行榜

🏆 个人最佳
  ⚡ 单次最多释放    34GB（7月21日）← 今天！
  🔥 最长连续周数    3 周（进行中）
  💎 累计释放        67GB
  📦 单次最多文件    53 个

🎯 下个里程碑
  再清理 33GB → 解锁 💎 100GB 徽章
```

**不收集任何外部数据，只和你自己的历史比。**

</details>

<details>
<summary>⚠️ <strong>运行检测</strong> — 不会打扰你正在用的应用</summary>
<br/>

正在运行的应用会被自动检测。Broom 只清它们的缓存（安全），不动主数据。

</details>

<details>
<summary>🤖 <strong>定时巡逻（可选）</strong> — 你不用记得它</summary>
<br/>

```
🧹 Broom 周报告

磁盘本周又涨了 6GB（目前 78%）
主要增长：企业微信 +4GB | Downloads +2GB

找到 ~8GB 可以清理。要看详情吗？

🎯 再清理 2 次就解锁 💎 100GB
```

你定频率，你定时间，安静时段不打扰（默认 22:00-08:00）。

</details>

<br/>

## 🚀 安装

### 前置条件

- **macOS**（Apple Silicon 或 Intel）
- [OpenClaw](https://openclaw.ai) 已安装并运行

### 一行搞定

```bash
git clone https://github.com/hisunfei/broom.git ~/.openclaw/workspace/skills/broom
```

不用改配置。不用装依赖。不用重启。

### 开始使用

对你的 OpenClaw 助手说：

> **"broom"** 或 **"帮我清理电脑"**

首次使用时 Broom 会自我介绍，引导你完成第一次清理，并通过对话收集你的偏好——**不用编辑任何配置文件**。

<br/>

## 📋 指令速查

| 你说 | Broom 做什么 |
|:--|:--|
| `broom` / `清理电脑` | 🔍 完整诊断扫描 |
| `快速清理` | ⚡ 跳过扫描，直接清理安全项 |
| `撤销上次清理` | ↩️ 从废纸篓恢复 |
| `只扫 Downloads` | 🎯 局部扫描特定区域 |
| `broom stats` | 🏆 成就和排行榜 |
| `分享 broom` | 📤 生成项目介绍卡片 |

<br/>

## 🔒 安全红线

**Broom 遵循 10 条不可违反的安全规则：**

<table>
<tr>
<td width="30" align="center">1</td>
<td><strong>永不删除个人证件</strong> — 毕业证、学位证、户口本、合同，即使被标记为 clean</td>
</tr>
<tr>
<td align="center">2</td>
<td><strong>永不删除应用数据库</strong> — Messages、mmkv、config、*.db、*.sqlite</td>
</tr>
<tr>
<td align="center">3</td>
<td><strong>运行中应用只清缓存</strong> — 自动检测，不动主数据</td>
</tr>
<tr>
<td align="center">4</td>
<td><strong>应用数据 → 废纸篓</strong> — 始终可恢复</td>
</tr>
<tr>
<td align="center">5</td>
<td><strong>纯缓存 → rm -rf</strong> — 自动重建，无风险</td>
</tr>
<tr>
<td align="center">6</td>
<td><strong>清内容不清目录</strong> — 避免权限问题</td>
</tr>
<tr>
<td align="center">7</td>
<td><strong>清理前快照</strong> — 记录原始大小用于对比</td>
</tr>
<tr>
<td align="center">8</td>
<td><strong>不确定 → 交给你决定</strong> — 标为 review，让你判断</td>
</tr>
<tr>
<td align="center">9</td>
<td><strong>每次必须 Dry Run</strong> — 执行前预览所有操作</td>
</tr>
<tr>
<td align="center">10</td>
<td><strong>完整撤销日志</strong> — 每个操作可回滚</td>
</tr>
</table>

<br/>

## 🔄 工作流程

```
Phase 0  新手引导（仅首次）
  │       "嗨！我是 Broom，你的 AI 电脑管家。"
  ▼
Phase 1  诊断
  │       并行扫描 → 智能分组 → 生成清理计划
  ▼
Phase 2  执行
  │       安全检查 → Dry Run 预览 → 确认 → 清理 → 健康检查
  ▼
Phase 3  成就与学习
  │       排行榜 → 徽章 → 偏好学习
  ▼
Phase 4  定期巡逻（可选）
          每周/每月 → 诊断 → 通知 → 等你确认
```

<br/>

## ❓ 常见问题

<details>
<summary><strong>我的数据安全吗？</strong></summary>

Broom 100% 本地运行。不上传任何数据，不做分析，不追踪。你的磁盘信息不会离开你的电脑。
</details>

<details>
<summary><strong>清理了能恢复吗？</strong></summary>

能。应用数据进废纸篓（可恢复），纯缓存自动重建（不需要恢复）。说「撤销上次清理」即可。
</details>

<details>
<summary><strong>会不会搞坏我的应用？</strong></summary>

不会。Broom 只清缓存和临时文件，正在运行的应用会被检测并跳过。清理后还有健康检查，验证应用关键文件完好。
</details>

<details>
<summary><strong>和 CleanMyMac 有什么区别？</strong></summary>

Broom 免费、开源、运行在你的 AI 助手里、学习你的习惯、支持完整撤销。不用每年交 ¥280。CleanMyMac 是一个独立 App；Broom 是你 AI 助手的一项能力。
</details>

<details>
<summary><strong>支持 Linux / Windows 吗？</strong></summary>

目前只支持 macOS。架构设计支持扩展到其他平台——欢迎贡献！
</details>

<br/>

## 🤝 贡献

### 添加应用规则

发现 Broom 不认识的应用？在 `references/app-rules.yaml` 中添加：

```yaml
- name: "你的应用"
  bundle_id: "com.example.app"
  process_name: "YourApp"
  category: "app"       # safe / app / skip
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

<br/>

## 📁 项目结构

```
broom/
├── README.md                           # 本文件（中文）
├── README_en.md                        # English version
├── LICENSE                             # MIT
├── SKILL.md                            # Agent 指令
├── assets/
│   ├── cleanup-plan-template.md        # 中文报告模板
│   ├── cleanup-plan-template-en.md     # 英文报告模板
│   └── broom-preferences-template.yaml # 默认偏好配置
└── references/
    └── app-rules.yaml                  # 应用清理规则（社区贡献）
```

<br/>

## 📄 许可证

[MIT](LICENSE) — 个人和商业使用均免费。

<br/>

---

<p align="center">
  <strong>不需要装 App，不需要付费，说句话就行。</strong><br/><br/>
  Made with 🧹 by <a href="https://github.com/hisunfei">hisunfei</a> and the <a href="https://openclaw.ai">OpenClaw</a> community
</p>
