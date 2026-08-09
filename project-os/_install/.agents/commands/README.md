---
type: index
owner: "[Owner]"
status: active
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: everyone
---

# Project commands

Canonical slash-commands for this project OS. These are the real command files; the sibling `.claude/commands/` holds thin adapters that point here so Claude registers them (Codex/Gemini/Mistral read these directly).

## Current commands

| Command | What it does |
|---------|-------------|
| `/onboard` | Set up this OS for your project — fills the template with real content. Run this first. |
| `/new-decision` | Scaffold a `decisions/NNNN-slug.md` from the template, auto-numbered, add it to the decisions index, and update the dashboard (`recentDecisions` + snapshot). |
| `/new-meeting` | Scaffold a `meetings/YYYY-MM-DD-slug.md` from the template, stamped with today's date, add it to the meetings index, and update the dashboard (`recentMeetings` + snapshot). |
| `/finish-session` | Wrap up the session — recap, follow-ups, memory line in the root `lessons.md` / `log.md`. |
| `/workspace-heal` | Audit the workspace for broken links, stale indexes, orphaned files, snapshot drift, and adapter drift. `report` (default) or `fix`. |

## Adding a command

1. Add the canonical `.md` file here.
2. Add a matching thin adapter in `../../.claude/commands/<name>.md` that carries the same frontmatter and points to `../../.agents/commands/<name>.md`.
3. Keep it project-neutral — every command here should apply to running this engagement.
