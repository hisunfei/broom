# Broom 🧹 Cleanup Plan

> Generated: {{generated_at}}
> Expires: {{expires_at}}
> Disk Usage: {{disk_usage_percent}}% ({{pressure_level}})

---

## 🟢 Safe Cleanup (~{{safe_total}})

Pure caches. Automatically rebuilt after deletion. No impact on usage.

| # | Item | Size | Command |
|---|------|------|---------|
{{#each safe_items}}
| {{index}} | {{name}} | {{size}} | `{{command}}` |
{{/each}}

---

## 🟡 App Data (~{{review_total}})

Requires confirmation. May need app restart after cleanup.

| # | Item | Size | Status | Command |
|---|------|------|--------|---------|
{{#each app_items}}
| {{index}} | {{name}} | {{size}} | {{#if app_running}}⚠️ Running{{else}}✅ Not running{{/if}} | `{{command}}` |
{{/each}}

---

## 📦 Downloads (~{{downloads_total}})

| # | File | Size | Age | Action |
|---|------|------|-----|--------|
{{#each download_items}}
| {{index}} | {{name}} | {{size}} | {{age}} | {{action}} |
{{/each}}

### 🔵 Protected Files

{{#each protected_files}}
- {{this}}
{{/each}}

---

## 📊 Estimated Free Space

**~{{grand_total}}** ≈ {{photos_equiv}} photos ≈ {{movies_equiv}} HD movies

---

## ⚠️ Notes

{{#if running_apps}}
The following apps are running and may need restart after cleanup:
{{#each running_apps}}
- {{this}}
{{/each}}
{{/if}}

Reply:
- "Execute all" — Run all cleanup
- "Safe only" — Only clean 🟢 items
- "Skip XX" — Skip specific items
