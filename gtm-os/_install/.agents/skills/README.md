---
type: index
owner: "[Owner]"
status: active
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: everyone
---

# GTM OS skills

Canonical tool skills for this GTM OS. These are the real skill files; the sibling `.claude/skills/` holds thin adapters that point here so Claude registers them (Codex/Gemini/Mistral read these directly).

## Current skills

- **`prefill-context.md`** — How to prefill the OS from existing sources (a live connector, dropped docs, or context exported from another AI/tool) instead of typing it. Loaded by `/onboard`.

## Adding a skill

1. Add the canonical `.md` file here.
2. Add a matching thin adapter in `../../.claude/skills/<name>.md` (same frontmatter, pointing to `../../.agents/skills/<name>.md`).
