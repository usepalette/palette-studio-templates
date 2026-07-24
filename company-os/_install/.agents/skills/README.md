---
type: index
---

# Company-wide skills

Canonical, cross-space tool skills for the whole OS. These are the real skill files; the root `/.claude/skills/` holds thin adapters that point here so Claude registers them (Codex/Gemini/Mistral read these directly).

A skill here should be a neutral tool guide any space could load. Space-flavored guidance (built around one space's folders and workflows) stays in that space's own `.agents/skills/`.

## Current skills

- **`prefill-context.md`** — How to prefill the OS from existing sources (a live connector, docs in `_inbox/`, or context exported from another AI/tool) instead of typing it. Loaded by `/onboard`.

## Adding a skill

1. Add the canonical `.md` file here.
2. Add a matching thin adapter in `/.claude/skills/<name>.md` (same frontmatter, pointing to `../../.agents/skills/<name>.md`).
3. If the skill leans on one space's folders/workflows, keep it in that space's `.agents/skills/` and decouple it before promoting.
