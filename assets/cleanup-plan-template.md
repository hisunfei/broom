---
auto_rules:
  downloads_excel_age: 180
  downloads_ppt_age: 180
  downloads_zip_age: 90
  downloads_image_age: 90
  cache_auto_clean: true
  duplicate_auto_clean: true
---

# 🧹 Broom 诊断报告

> 生成时间：{{timestamp}} | 过期时间：{{expires_at}}
> 磁盘：{{disk_total}} | 已用 {{disk_used}} ({{usage_percent}}%) | 可用 {{disk_avail}}
> 内存：{{mem_total}} | 压力：{{mem_pressure}} | 策略：{{disk_pressure}}
> Schema：{{schema_version}}

## 如何使用

1. 审阅下方 `action` 字段：`clean`=清理 | `skip`=跳过 | `review`=需确认
2. 保存后说「执行」，Broom 会先展示 Dry Run 预览
3. 快捷指令：「快速清理」| 「撤销上次清理」| 「只扫 XX」

## 自动清理规则

> 通过自然语言修改，例如「以后 3 个月以上的 Excel 自动清」

| 规则 | 值 | 说明 |
|------|-----|------|
| `downloads_excel_age` | 180 天 | Excel/CSV 超期标记 clean |
| `downloads_ppt_age` | 180 天 | PPT 超期标记 clean |
| `downloads_zip_age` | 90 天 | 安装包超期标记 clean |
| `downloads_image_age` | 90 天 | 截图超期标记 clean |
| `cache_auto_clean` | true | 🟢始终自动 clean |
| `duplicate_auto_clean` | true | 重复文件自动 clean |

---

## 📈 趋势

| 日期 | 清理前可用 | 清理后可用 | 释放 |
|------|-----------|-----------|------|
| {{prev_date}} | {{prev_before}} | {{prev_after}} | {{prev_freed}} |
| 本次 | {{disk_avail}} | - | - |

增长来源：{{growth_sources}}

---

## 💡 内存优化建议

{{memory_recommendations}}

---

## ⚠️ 运行中应用

{{running_apps}}

---

## 🟢 安全清理（rm -rf，纯缓存自动重建）

| # | 清理项 | 路径 | 大小 | action | 说明 |
|---|--------|------|------|--------|------|
| ... | ... | ... | ... | `clean` | ... |

---

## 🟡 应用数据（trash ♻️，可恢复）

| # | 清理项 | 路径 | 大小 | action | 说明 |
|---|--------|------|------|--------|------|
| ... | ... | ... | ... | `review` | ... |

---

## 🗑️ 已卸载应用残留

| # | 应用 | 残留路径 | 大小 | action | 说明 |
|---|------|---------|------|--------|------|
| ... | ... | ... | ... | `review` | 已卸载？ |

---

## 🔵 Downloads（按分组，trash ♻️）

| # | 分组 | 文件数 | 总大小 | action | 说明 |
|---|------|--------|--------|--------|------|
| ... | ... | ... | ... | ... | ... |

> 说「展开第X组」查看具体文件

---

## 🔍 全局大文件（>500MB）

| # | 文件 | 路径 | 大小 | action | 说明 |
|---|------|------|------|--------|------|
| ... | ... | ... | ... | `skip` | 请判断 |

---

## ⏭️ 默认跳过

| # | 项目 | 路径 | 大小 | action | 说明 |
|---|------|------|------|--------|------|
| ... | ... | ... | ... | `skip` | ... |

---

## 📊 汇总

| 类别 | 条目数 | 总大小 | 默认动作 | 执行方式 |
|------|--------|--------|----------|----------|
| 🟢 安全清理 | {{n}} | {{size}} | clean | rm -rf |
| 🟡 应用数据 | {{n}} | {{size}} | review | trash ♻️ |
| 🗑️ 残留 | {{n}} | {{size}} | review | trash ♻️ |
| 🔵 Downloads | {{n}} | {{size}} | 按规则 | trash ♻️ |
| 🔍 大文件 | {{n}} | {{size}} | skip | - |
| ⏭️ 跳过 | {{n}} | {{size}} | skip | - |
| **预计可释放** | | **{{estimated_free}}** | | |

---

*说「执行」开始清理。Broom 会先 Dry Run 预览，确认后才真正执行。*
*清理后可说「撤销上次清理」恢复 trash 中的文件。*
