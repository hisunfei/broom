# Broom App Rules Reference

This directory contains the application-specific cleanup rules for Broom.

## Files

| File | Description |
|------|-------------|
| `app-rules.yaml` | Application cleanup rules (v2.2, 30+ apps) |
| `README.md` | This file |

## app-rules.yaml Schema

```yaml
schema_version: "2.2"

apps:
  - name: "应用名称"
    bundle_id: "com.example.app"        # macOS bundle ID (optional)
    container_path: "~/Library/Containers/com.example.app"  # Container path (optional)
    process_name: "AppName"              # Process name for running detection
    detect_command: "command 2>/dev/null" # Command to detect if app is installed
    category: "app"                      # safe | app | skip
    rules:
      - name: "规则名称"
        path: "~/Library/Caches/AppName"
        size_threshold: "1GB"            # Only clean if larger than this (optional)
        size_threshold_age: 180          # Only clean files older than N days (optional)
        default_action: "review"         # clean | review | skip
        safe_command: "rm -rf <resolved_path>/*"  # For 🟢 safe items
        trash_command: "trash <resolved_path>/*"   # For 🟡 app items
        command: "custom_command"        # Custom cleanup command
    protected:                           # Files/dirs to never delete
      - "config"
      - "*.db"
```

## Categories

| Category | Description | Cleanup Method |
|----------|-------------|----------------|
| `safe` | Pure caches, safe to delete | `rm -rf` |
| `app` | App data, may need restart | `trash` (recoverable) |
| `skip` | Never clean (user preference) | Skip |

## Default Actions

| Action | Description |
|--------|-------------|
| `clean` | Auto-clean without asking |
| `review` | Show to user for confirmation |
| `skip` | Never clean |

## Placeholders

| Placeholder | Description |
|-------------|-------------|
| `<resolved_path>` | Full resolved path after expanding ~ and wildcards |
| `<path>` | Same as <resolved_path> |

## Global Protected Patterns

These patterns are never deleted, regardless of app rules:

```yaml
global_protected:
  - "Messages"
  - "mmkv"
  - "config"
  - "*.db"
  - "*.sqlite"
  - "*.plist"
  - "*.keychain"
```

## Personal Document Keywords

Files matching these keywords are protected by Safety Rule #1:

```yaml
personal_doc_keywords:
  - "毕业证"
  - "学位证"
  - "户口本"
  - "结婚证"
  - "身份证"
  - "录用通知书"
  - "离职证明"
  - "租房合同"
  - "电子准迁证"
  - "学历证书"
  - "工资单"
  - "承诺书"
  - "passport"
  - "visa"
  - "license"
  - "contract"
  - "insurance"
  - "invoice"
  - "发票"
```

## Contributing

To add a new app rule:

1. Find the app's container path:
   ```bash
   # For sandboxed apps
   ls ~/Library/Containers/ | grep -i appname
   
   # For non-sandboxed apps
   ls ~/Library/Application\ Support/ | grep -i appname
   ls ~/Library/Caches/ | grep -i appname
   ```

2. Check what's taking space:
   ```bash
   du -sh ~/Library/Containers/com.example.app/*
   du -sh ~/Library/Caches/com.example.app/*
   ```

3. Identify safe-to-clean directories (caches, logs, temp files)

4. Add the rule to `app-rules.yaml` following the schema above

5. Test with `broom` and verify the cleanup plan looks correct

6. Submit a PR with the app data directory screenshot
