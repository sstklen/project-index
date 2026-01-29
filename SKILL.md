---
name: project-index
description: Auto-generate project index for instant file navigation. AI finds files in 2 seconds instead of 5 minutes of searching. Generates PROJECT_INDEX.json with structure, key files, and stats.
argument-hint: [--quick|--full|update]
---

# Project Index 🔍

> Auto-generate project index — AI finds files instantly, no more digging around.

## Quick Reference

### Commands

| Command | What It Does |
|---------|--------------|
| `/index` | Generate/update index |
| `/index --quick` | Quick scan (main files only) |
| `/index --full` | Full scan (includes functions, classes) |
| "Update project index" | Natural language trigger |

### Generated Output

Creates `PROJECT_INDEX.json` at project root:

```json
{
  "project": "my-project",
  "generated": "2026-01-30T12:00:00Z",
  "structure": {
    "source": ["src/**/*.ts"],
    "tests": ["tests/**/*.test.ts"],
    "docs": ["docs/**/*.md"]
  },
  "key_files": {
    "entry_point": "src/index.ts",
    "config": ["package.json", "tsconfig.json"]
  },
  "stats": {
    "total_files": 150,
    "by_type": { ".ts": 45, ".tsx": 30 }
  }
}
```

## How It Works

1. **Scan** — Find all files (exclude .git, node_modules)
2. **Categorize** — Group by location and extension
3. **Identify** — Detect entry points, configs, key files
4. **Generate** — Write PROJECT_INDEX.json

## After Index Generated

AI can instantly answer:
- "Find files related to [keyword]"
- "Show all test files"
- "What was modified recently?"
- "Open the spec document"

## Additional Resources

- For index structure details, see [references/index-structure.md](references/index-structure.md)
- For categorization rules, see [references/categorization.md](references/categorization.md)

## Related Skills

- **ai-dojo** — Foundation (environment tools + file placement)
- **auto-tidy** — Calls `/index` after cleanup

---

*Part of 🥋 AI Dojo Series by [Washin Village](https://washinmura.jp) 🐾*
