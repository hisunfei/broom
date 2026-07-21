---
auto_rules:
  downloads_excel_age: 180
  downloads_ppt_age: 180
  downloads_zip_age: 90
  downloads_image_age: 90
  cache_auto_clean: true
  duplicate_auto_clean: true
---

# 🖥️ Mac Cleanup Plan

> Generated: {{timestamp}} | Expires: {{expires_at}}
> Disk: {{disk_total}} total | {{disk_used}} used ({{usage_percent}}%) | {{disk_avail}} available
> Memory: {{mem_total}} | Pressure: {{mem_pressure}} | Strategy: {{disk_pressure}}
> Schema: {{schema_version}}

## How to use

1. Review each item's `action`: `clean` = cleanup | `skip` = skip | `review` = needs confirmation
2. Save and tell Agent "execute" — it will show a Dry Run preview first
3. Shortcuts: "quick clean" skips diagnosis | "undo last cleanup" restores files | "scan only XX" for partial scan

## Auto Cleanup Rules

| Rule | Value | Description |
|------|-------|-------------|
| `downloads_excel_age` | 180 days | Excel/CSV older than N days → clean |
| `downloads_ppt_age` | 180 days | PPT older than N days → clean |
| `downloads_zip_age` | 90 days | Installers older than N days → clean |
| `downloads_image_age` | 90 days | Screenshots older than N days → clean |
| `cache_auto_clean` | true | 🟢 always auto-clean |
| `duplicate_auto_clean` | true | Duplicate files auto-clean |

---

## 📈 Trend

| Date | Before | After | Freed |
|------|--------|-------|-------|
| {{prev_date}} | {{prev_before}} | {{prev_after}} | {{prev_freed}} |
| This run | {{disk_avail}} | - | - |

Growth sources: {{growth_sources}}

---

## 💡 Memory Recommendations

{{memory_recommendations}}

---

## ⚠️ Running Apps

> These apps are running. Their cache items have been downgraded to review:

{{running_apps}}

---

## 🟢 Safe Cleanup (rm -rf, caches auto-rebuild)

| # | Item | Path | Size | action | Notes |
|---|------|------|------|--------|-------|
| ... | ... | ... | ... | `clean` | ... |

---

## 🟡 App Data (trash ♻️, recoverable)

| # | Item | Path | Size | action | Notes |
|---|------|------|------|--------|-------|
| ... | ... | ... | ... | `review` | ... |

---

## 🗑️ Uninstalled App Remnants

| # | App | Remnant Path | Size | action | Notes |
|---|-----|-------------|------|--------|-------|
| ... | ... | ... | ... | `review` | Uninstalled? |

---

## 🔵 Downloads (grouped, trash ♻️)

| # | Group | Files | Total Size | action | Notes |
|---|-------|-------|------------|--------|-------|
| ... | ... | ... | ... | ... | ... |

> Say "expand group X" to see individual files

---

## 🔍 Large Files (>500MB)

| # | File | Path | Size | action | Notes |
|---|------|------|------|--------|-------|
| ... | ... | ... | ... | `skip` | Decide if still needed |

---

## ⏭️ Skipped by Default

| # | Item | Path | Size | action | Notes |
|---|------|------|------|--------|-------|
| ... | ... | ... | ... | `skip` | ... |

---

## 📊 Summary

| Category | Items | Total Size | Default | Method |
|----------|-------|------------|---------|--------|
| 🟢 Safe | {{n}} | {{size}} | clean | rm -rf |
| 🟡 App Data | {{n}} | {{size}} | review | trash ♻️ |
| 🗑️ Remnants | {{n}} | {{size}} | review | trash ♻️ |
| 🔵 Downloads | {{n}} | {{size}} | by rules | trash ♻️ |
| 🔍 Large Files | {{n}} | {{size}} | skip | - |
| ⏭️ Skipped | {{n}} | {{size}} | skip | - |
| **Est. Free** | | **{{estimated_free}}** | | |

---

*After editing, tell Agent "execute". A Dry Run preview will be shown first.*
*After cleanup, say "undo last cleanup" to restore files from trash.*
