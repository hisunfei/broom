# 应用使用分析 - 第一版

## 扫描时间
2026-11-05 10:26:11

## 数据源
- Spotlight 使用次数 (kMDItemUseCount)
- Spotlight 最后使用时间 (kMDItemLastUsedDate)
- Application Support 活动时间
- 进程运行状态
- Bundle ID 推断存储目录

## 扫描结果

### 👻 未发现使用痕迹

| # | 应用 | 大小 | 热度 | 状态 |
|---|------|------|------|------|
| 1 | wechatwebdevtools | 1.1G | 0次 | 未发现使用痕迹 |
| 2 | Microsoft OneNote | 714M | 0次 | 未发现使用痕迹 |
| 3 | QQ | 561M | 0次 | 未发现使用痕迹 |
| 4 | SiYuan | 404M | 0次 | 未发现使用痕迹 |
| 5 | UPDF | 132M | 0次 | 未发现使用痕迹 |
| 6 | mpv | 95M | 0次 | 未发现使用痕迹（偶尔使用） |

**小计：3.0GB**

### 🌫️ 已落灰，建议检查

| # | 应用 | 大小 | 热度 | 状态 |
|---|------|------|------|------|
| 1 | Trae CN | 922M | 0次 | 104天未活动，已落灰 |
| 2 | Thunder | 294M | 0次 | 93天未活动，已落灰 |
| 3 | Microsoft Word | 2.4G | 10次 | 77天未活动，已落灰 |
| 4 | 元宝 | 495M | 6次 | 66天未活动，已落灰 |

**小计：4.1GB**

### 🔥 活跃使用中

| # | 应用 | 大小 | 热度 | 状态 |
|---|------|------|------|------|
| 1 | Microsoft Edge | 1.6G | 9,670次 | 🔥 今天活跃 |
| 2 | 企业微信 | 1.5G | 5,940次 | 🔥 今天活跃 |
| 3 | WeChat | 662M | 1,650次 | 🔥 今天活跃 |
| 4 | TIEXIN | 797M | 1,198次 | 🔥 今天活跃 |
| 5 | Obsidian | 439M | 754次 | 🔥 今天活跃 |
| 6 | Xmind | 593M | 331次 | 2天前活跃 |
| 7 | Microsoft Excel | 2.2G | 303次 | 23天前活跃 |
| 8 | Sketch | 168M | 243次 | 🔥 今天活跃 |
| 9 | Microsoft PowerPoint | 1.8G | 186次 | 5天前活跃 |
| 10 | Visual Studio Code | 669M | 9次 | 43天前活跃 |
| 11 | Xnip | 16M | 13次 | 2天前活跃 |
| 12 | VideoFusion-macOS | 2.8G | 6次 | 1天前活跃 |
| 13 | Ollama | 664M | 2次 | 8天前活跃 |
| 14 | ChatGPT | 1.6G | 0次 | 🔥 6天前活跃（Bundle ID 修复） |
| 15 | Doubao | 1.2G | 0次 | 🔥 今天活跃，正在运行 |

## 技术实现

### 1. 通过 Bundle ID 查找存储目录

```javascript
const APP_DIR_MAP = {
  'ChatGPT': ['OpenAI', 'com.openai.codex'],
  'Doubao': ['Doubao'],
  '企业微信': ['com.tencent.WeWorkMac'],
  'Microsoft OneNote': ['com.microsoft.onenote.mac'],
  'QQ': ['com.tencent.qq'],
  'UPDF': ['com.superace.updf.mac']
};
```

### 2. 文案拟人化

| 原版 | 优化版 |
|------|--------|
| 使用次数: 0 | 热度: 0次 |
| 从未使用 | 未发现使用痕迹 |
| 90天未使用 | 已落灰，建议检查 |
| 建议卸载 | 如果不再使用，可考虑卸载 |

### 3. 保护名单

```yaml
protected_apps:
  - net.downloadhelper    # Chrome 下载助手
  - 豆包浏览器            # 豆包组件（替身）
  - Safari                # 系统浏览器
  - Keynote/Numbers/Pages # 系统应用
```

## 发现的问题

1. **Spotlight 数据盲区**：某些应用（如 Doubao、ChatGPT）Spotlight 不记录使用数据
2. **应用名称 ≠ 存储目录**：需要通过 Bundle ID 推断
3. **"替身"类型**：不是独立应用，需要过滤
4. **命令行调用**：如 mpv，Spotlight 不记录

## 解决方案

1. **多数据源交叉验证**：Spotlight + Application Support + 进程状态
2. **Bundle ID 映射**：查找实际存储目录
3. **自动过滤替身**：检测 kMDItemKind = "替身"
4. **标记"数据不足"**：让用户确认
