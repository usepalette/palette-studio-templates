---
type: index
---

# GTM OS commands

Canonical slash-commands for this GTM OS. These are the real command files; the sibling `.claude/commands/` holds thin adapters that point here so Claude registers them (Codex/Gemini/Mistral read these directly).

## Current commands

| Command | What it does |
|---------|-------------|
| `/onboard` | Set up this OS for your company — fills the template with real content. Run this first. |
| `/new-account` | Scaffold `accounts/<name>/` from the template and add it to the status board. |
| `/new-person` | Scaffold a teammate's `team/<name>/` folder (profile + voice), stamped and ready. |
| `/review` | Review your work against brand, hygiene, and completeness before sharing. |
| `/finish-session` | Wrap up the session — recap, follow-ups, memory line. |
| `/workspace-heal` | Audit the workspace for broken links, stale indexes, orphaned files, and missing frontmatter. `report` (default) or `fix`. |

## Adding a command

1. Add the canonical `.md` file here.
2. Add a matching thin adapter in `../../.claude/commands/<name>.md` that carries the same frontmatter and points to `../../.agents/commands/<name>.md`.
