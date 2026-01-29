---
name: project-index
description: Auto-generate PROJECT_INDEX.json so AI can navigate your project instantly. No more searching through 500 files!
triggers:
  - "/index"
  - "update index"
  - "generate index"
  - "更新索引"
  - "生成索引"
---

# Project Index Generator

> **Let AI find files in 2 seconds instead of 5 minutes**

Auto-generate a structured index of your project so Claude (and you) can navigate instantly.

---

## Commands

```
/index              # Generate/update project index
/index --quick      # Quick scan (main files only)
/index --full       # Full scan (includes functions, classes)
```

Or just say:
- "Update project index"
- "Generate index"
- "更新索引"

---

## Generated Index Structure

Creates `PROJECT_INDEX.json` in your project root:

```json
{
  "project": "my-awesome-project",
  "generated": "2026-01-29T12:00:00Z",

  "structure": {
    "research": ["00-research/summary.md", "00-research/notes.md"],
    "specs": ["03-specs/spec.md", "03-specs/plan.md"],
    "source": ["src/**/*.ts", "src/**/*.tsx"],
    "tests": ["tests/**/*.test.ts"],
    "docs": ["docs/**/*.md"]
  },

  "key_files": {
    "entry_point": "src/index.ts",
    "config": ["package.json", "tsconfig.json", ".env.example"],
    "docs": ["README.md", "CLAUDE.md", "CHANGELOG.md"]
  },

  "stats": {
    "total_files": 150,
    "by_type": {
      ".ts": 45,
      ".tsx": 30,
      ".md": 25,
      ".json": 10
    },
    "last_modified": "2026-01-29T11:30:00Z"
  }
}
```

---

## How It Works

### Step 1: Scan Project Structure

```bash
find . -type f \
  -not -path './.git/*' \
  -not -path './node_modules/*' \
  -not -path './_archive/*' \
  -not -path './_temp/*' \
  -not -name '.DS_Store' \
  | sort
```

### Step 2: Categorize Files

Based on path and extension:
- Research: `00-research/`
- Knowledge: `01-knowledge/`
- Ideas: `02-ideation/`
- Specs: `03-specs/`
- Source: `04-src/` or `src/`
- Tests: `05-tests/` or `tests/`
- Docs: `docs/`

### Step 3: Identify Key Files

Auto-detect:
- Entry points: `index.ts`, `main.ts`, `app.ts`
- Config: `package.json`, `tsconfig.json`, `.env.example`
- Docs: `README.md`, `CLAUDE.md`, `CHANGELOG.md`

### Step 4: Generate Index

Write `PROJECT_INDEX.json` to project root.

### Step 5: Update CODEMAPS (Optional)

If `docs/CODEMAPS/` exists, update module codemaps.

---

## Quick Query Examples

After index is generated, AI can quickly answer:

```
"Find files related to [keyword]"
"Open the spec document"
"Show all test files"
"What was modified recently?"
```

---

## Integration with Other Skills

Works great with:
- **file-placement-guide** — Files placed correctly from start
- **auto-tidy** — Cleanup & auto-update index

The Washin Village Trio! 🗡️🗡️🗡️

---

## Configuration

### .gitignore (Recommended)

```gitignore
# Project index (auto-generated)
PROJECT_INDEX.json
```

### Notes

- Index regenerates quickly (usually < 5 seconds)
- Large projects may take a few seconds on first scan
- Sensitive paths are marked but content not indexed

---

## About

Made by **Washin Village (和心村)** — a sanctuary for 28 cats and dogs in Japan's Boso Peninsula. We build AI tools to help animals get seen by the world!

🌐 [washinmura.jp](https://washinmura.jp)
