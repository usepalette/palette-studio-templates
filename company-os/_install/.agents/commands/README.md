---
type: index
owner: "[Owner]"
status: active
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: everyone
---

# Company-wide commands

Canonical, cross-space slash-commands for the whole OS. These are the real command files; the root `/.claude/commands/` holds thin adapters that point here so Claude registers them (Codex/Gemini/Mistral read these directly).

Keep this list to commands that genuinely apply across spaces. Space-specific commands live in that space's own `.agents/commands/`.

## Current commands

| Command | What it does |
|---------|-------------|
| `/onboard` | Set up this OS for your company — fills the template with real content. Run this first. |
| `/create-space` | Scaffold a new top-level space (README + `lessons.md` + `log.md`, optional `AGENTS.md` + vendor pointers) to the OS conventions, then register it in the root Owners table + spaces routing table. |
| `/new-account` | Scaffold `accounts/<name>/` from the template and add it to the status board. |
| `/new-person` | Scaffold a teammate's `people/<name>/` folder from the template, stamped and ready. |
| `/finish-session` | Wrap up the session — recap, follow-ups, memory line. Adapts to whichever space you worked in. |
| `/workspace-heal` | Audit the whole workspace for broken links, stale README listings, orphaned files, and adapter drift. `report` (default) or `fix`. |
| `/reflect` | Tidy the OS's `lessons.md` + `log.md` files and propose promotions into the guides — suggest-only. Optional scope path (e.g. `gtm/`). |

## Adding a command

1. Add the canonical `.md` file here.
2. Add a matching thin adapter in `/.claude/commands/<name>.md` that carries the same frontmatter and points to `../../.agents/commands/<name>.md`.
3. Keep it space-neutral — if it only makes sense for one space, it belongs in that space's `.agents/commands/` instead.
