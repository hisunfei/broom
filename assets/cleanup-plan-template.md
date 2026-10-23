# Broom 🧹 清理计划

> 生成时间: {{generated_at}}
> 过期时间: {{expires_at}}
> 磁盘使用率: {{disk_usage_percent}}% ({{pressure_level}})

---

## 🟢 安全清理（~{{safe_total}}）

纯缓存，删除后自动重建，不影响使用。

| # | 项目 | 大小 | 命令 |
|---|------|------|------|
{{#each safe_items}}
| {{index}} | {{name}} | {{size}} | `{{command}}` |
{{/each}}

---

## 🟡 应用数据（~{{review_total}}）

需要确认，删除后可能需要重启应用。

| # | 项目 | 大小 | 状态 | 命令 |
|---|------|------|------|------|
{{#each app_items}}
| {{index}} | {{name}} | {{size}} | {{#if app_running}}⚠️ 运行中{{else}}✅ 未运行{{/if}} | `{{command}}` |
{{/each}}

---

## 📦 Downloads（~{{downloads_total}}）

| # | 文件 | 大小 | 时间 | 操作 |
|---|------|------|------|------|
{{#each download_items}}
| {{index}} | {{name}} | {{size}} | {{age}} | {{action}} |
{{/each}}

### 🔵 已保护文件

{{#each protected_files}}
- {{this}}
{{/each}}

---

## 📊 预计释放

**~{{grand_total}}** ≈ {{photos_equiv}} 张照片 ≈ {{movies_equiv}} 部高清电影

---

## ⚠️ 注意事项

{{#if running_apps}}
以下应用正在运行，清理后可能需要重启：
{{#each running_apps}}
- {{this}}
{{/each}}
{{/if}}

回复：
- 「全部执行」— 执行所有清理
- 「只清安全的」— 只清 🟢 项
- 「跳过 XX」— 跳过指定项目
