# Categorization Rules Reference

## Directory-Based Categorization

| Directory Pattern | Category |
|-------------------|----------|
| `00-research/` | research |
| `01-knowledge/` | knowledge |
| `02-ideation/` | ideation |
| `03-specs/` | specs |
| `04-src/`, `src/` | source |
| `05-tests/`, `tests/` | tests |
| `docs/` | docs |
| `scripts/` | scripts |
| `config/` | config |
| `_archive/` | archive |
| `_temp/` | temp |

## Extension-Based Categorization

### Source Code
- `.ts`, `.tsx`, `.js`, `.jsx` → source
- `.py` → source
- `.go`, `.rs`, `.java` → source

### Tests
- `*.test.ts`, `*.spec.ts` → tests
- `*.test.js`, `*.spec.js` → tests
- `*_test.py`, `test_*.py` → tests

### Documentation
- `.md`, `.mdx` → docs
- `.txt` → docs
- `.rst` → docs

### Configuration
- `.json`, `.yaml`, `.yml` → config
- `.toml`, `.ini` → config
- `.*rc`, `*.config.js` → config

### Assets
- `.png`, `.jpg`, `.svg` → assets
- `.ico`, `.gif`, `.webp` → assets

### Styles
- `.css`, `.scss`, `.less` → styles
- `.module.css` → styles

## Excluded Paths

Never index these:
- `.git/`
- `node_modules/`
- `dist/`, `build/`, `out/`
- `coverage/`
- `_archive/`
- `_temp/`
- `.next/`, `.nuxt/`
- `*.lock` (lockfiles)
- `.env` (sensitive)

## Key File Detection

### Entry Points
Priority order:
1. `src/index.ts` or `src/main.ts`
2. `src/app.ts` or `src/App.tsx`
3. `index.ts` or `main.ts` in root

### Config Files
Auto-detect:
- `package.json`
- `tsconfig.json`
- `vite.config.ts`
- `next.config.js`
- `.env.example`

### Documentation
Auto-detect:
- `README.md`
- `CLAUDE.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`
- `LICENSE`
