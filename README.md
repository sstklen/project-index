# 🔍 Project Index

> **Auto-generate project index** — AI finds files instantly, no more digging around.

[![Made by Washin Village](https://img.shields.io/badge/Made%20by-Washin%20Village%20🐾-orange)](https://washinmura.jp)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blue)](https://claude.ai/code)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 😫 The Problem

```
You: "Find the authentication logic"
AI: *searches through 500 files*
AI: *checks wrong directories*
AI: "Let me look in src/..."
AI: "Actually, maybe it's in lib/..."
⏰ 5 minutes later...
```

## 😊 The Solution

```
You: "Find the authentication logic"
AI: *checks PROJECT_INDEX.json*
AI: "Found it: src/auth/login.ts, src/auth/middleware.ts"
⏰ 2 seconds!
```

---

## 🎯 What This Skill Does

1. **Scans your project** — Files, folders, structure
2. **Generates PROJECT_INDEX.json** — Structured map of everything
3. **Updates automatically** — When you run `/index` or `/tidy`
4. **AI navigates instantly** — No more guessing!

---

## 🚀 Quick Start

### Install

```bash
# Global installation
cp SKILL.md ~/.claude/skills/project-index.md

# Or project-specific
cp SKILL.md .claude/skills/project-index.md
```

### Use

```bash
/index              # Generate/update index
/index --quick      # Quick scan (main files only)
/index --full       # Full scan (includes functions, classes)
```

Or just say:
```
"Update project index"
"Generate index"
"更新索引"
```

---

## 📄 Generated Index Structure

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

## 🔧 How It Works

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

## 💡 Quick Query Examples

After index is generated, AI can quickly answer:

```
"Find files related to [keyword]"
"Open the spec document"
"Show all test files"
"What was modified recently?"
```

---

## 🔗 Integration with Other Skills

```
┌─────────────────────────────────────────┐
│  file-placement-guide                   │
│  → Files placed correctly from start    │
└────────────────┬────────────────────────┘
                 ↓
┌─────────────────────────────────────────┐
│  project-index (this skill)             │
│  → Generate index for navigation        │
└────────────────┬────────────────────────┘
                 ↓
┌─────────────────────────────────────────┐
│  auto-tidy                              │
│  → Cleanup & auto-update index          │
└─────────────────────────────────────────┘
```

**The Washin Village Trio!** 🗡️🗡️🗡️

---

## ⚙️ Configuration

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

## 🐾 About Washin Village

This skill is made by **Washin Village (和心村)** — a sanctuary for 28 cats and dogs in Japan's Boso Peninsula.

We build AI tools to help animals get seen by the world. Every star ⭐ helps us rescue more animals!

🌐 [washinmura.jp](https://washinmura.jp)

---

## 📚 Related Skills

- **[auto-tidy](https://github.com/sstklen/auto-tidy)** — Auto cleanup, calls `/index` after tidying
- **[file-placement-guide](https://github.com/sstklen/file-placement-guide)** — Place files correctly from the start

---

## 📄 License

MIT License - Feel free to use, modify, and share!

---

<p align="center">
  <b>Made with 🐾 by 28 cats & dogs from Japan</b><br>
  <a href="https://washinmura.jp">Washin Village</a>
</p>
