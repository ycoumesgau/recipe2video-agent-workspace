# AGENTS.md

## Cursor Cloud specific instructions

This is a **creative planning workspace**, not an application codebase. There is no source code, no package manager, no build system, no database, and no services to run.

### What this workspace does

The Cursor AI agent reads rules (`.cursor/rules/`), skills (`.cursor/skills/`), and agent definitions (`.cursor/agents/`) to produce recipe-to-video planning artifacts in `agent-recipes/{videoId}/`. The Recipe2Video production app (separate repo) consumes these artifacts.

### Key facts

- **No dependencies to install.** There is no `package.json`, `requirements.txt`, or equivalent.
- **No lint, test, or build commands.** Validation is structural: JSON must be strict (no comments, no Markdown fences) and conform to `contracts/artifact-schemas.md`.
- **67 static PNG assets** live in `assets/` (character, kitchen, utensils). The `asset-reference-system` skill maps canonical `@Names` to file paths.
- **`agent-recipes/`** is gitignored. Daily recipe artifacts are never committed; Recipe2Video retrieves and syncs them via the Cursor SDK.
- **`examples/paris-brest/`** is the canonical worked example showing the full artifact set.

### Validating artifacts

To check JSON validity and contract conformance, use Python's `json` module:

```bash
python3 -c "import json; json.load(open('agent-recipes/{videoId}/recipe-analysis.json'))"
```

Cross-reference asset names in `seedance-segments.json` references against actual files in `assets/` using the mapping in `.cursor/skills/asset-reference-system/SKILL.md`.

### Gotchas

- The `assets/` directory contains **binary PNGs tracked by Git** (not LFS). Clones may be slow on constrained networks.
- The `ustensils/` directory is intentionally spelled that way (French spelling).
- Artifact JSON must have no trailing commas, no comments, and no Markdown code fences — strict JSON only.
