---
type: index
owner: "[Owner]"
status: active
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: everyone
---

# Agent guidance

Shared instructions live in `../AGENTS.md`. This folder holds the canonical commands (`commands/`) and skills (`skills/`); the sibling `.claude/` folder holds thin adapters so Claude registers them. Other agents (Codex/Gemini/Mistral) read `.agents/` directly.

Keep canonical content here; keep vendor folders (`.claude/`) as thin adapters that point back. Never symlink — some file-sync layers (e.g. Google Drive) break them.
