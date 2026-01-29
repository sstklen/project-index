# Index Structure Reference

## Full PROJECT_INDEX.json Structure

```json
{
  "project": "project-name",
  "generated": "2026-01-30T12:00:00Z",
  "version": "1.0",

  "structure": {
    "research": ["00-research/**/*.md"],
    "knowledge": ["01-knowledge/**/*.md"],
    "ideation": ["02-ideation/**/*.md"],
    "specs": ["03-specs/**/*.md"],
    "source": ["src/**/*.ts", "src/**/*.tsx"],
    "tests": ["tests/**/*.test.ts"],
    "docs": ["docs/**/*.md"]
  },

  "key_files": {
    "entry_point": "src/index.ts",
    "config": [
      "package.json",
      "tsconfig.json",
      ".env.example"
    ],
    "docs": [
      "README.md",
      "CLAUDE.md",
      "CHANGELOG.md"
    ]
  },

  "recent_files": [
    {
      "path": "src/components/Button.tsx",
      "modified": "2026-01-30T11:30:00Z"
    }
  ],

  "stats": {
    "total_files": 150,
    "total_dirs": 25,
    "by_type": {
      ".ts": 45,
      ".tsx": 30,
      ".md": 25,
      ".json": 10,
      ".css": 5
    },
    "by_category": {
      "source": 75,
      "tests": 30,
      "docs": 25,
      "config": 10
    },
    "last_modified": "2026-01-30T11:30:00Z"
  }
}
```

## Field Descriptions

### project
Project name from `package.json` or directory name.

### structure
File paths grouped by category. Uses glob patterns.

### key_files
Important files that AI should know about:
- `entry_point`: Main application entry
- `config`: Configuration files
- `docs`: Key documentation

### recent_files
Last 10 modified files for quick access.

### stats
Project statistics for overview:
- `total_files`: Count of all indexed files
- `by_type`: Breakdown by file extension
- `by_category`: Breakdown by category
- `last_modified`: Most recent file change

## Quick Index vs Full Index

### Quick Index
- Only populates `structure` and `key_files`
- Faster generation (< 5 seconds)
- Good for daily use

### Full Index
- Includes function/class listings
- Adds `exports` field with public APIs
- Slower (30+ seconds for large projects)
- Good for onboarding new contributors
