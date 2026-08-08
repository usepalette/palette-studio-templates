---
type: index
owner: Shared
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: everyone
---

# People

Personal folders for each team member. Agents read your folder automatically at the start of every conversation to adapt to how you work.

> The folder itself is open (`edit_policy: everyone`), but each `people/<name>/` subfolder is **owner-only** — only edit your own.

## How it works

1. **Identify you.** The host injects your email into every session (e.g. `you@[company].com`). The agent matches it to a folder — first by an `email:` in your `README.md` frontmatter, else by the email's name part (`name@…` → `name/`), else by name. If nothing resolves, it asks.
2. **Read your folder.** The agent reads `README.md` (your profile — who you are + how to work with you) and `lessons.md` (things learned about you).
3. **Adapt.** Tone, style, and behavior follow your preferences.

> **New here with no folder?** An agent will offer to create one with `/new-person` (it scaffolds from `people/_template/` and stamps it). **Profile too thin?** It'll offer to fill it in — asking you or pulling from a live connector, never fabricating.

> **Add `email:` to your `README.md` frontmatter** so the match is always exact — especially if your address doesn't follow the default pattern. Your `README.md` carries `type: person`, `owner:`, `email:`, `role:`, optional `slack`/`github`/`linkedin`, and `edit_policy: owner-only`.

## What to put here

Three files:

- **`README.md`** — your profile: identity frontmatter (`email`, `slack`, `github`, `linkedin`) + who you are + a **How to work with me** section (tone, what to avoid, how to push back).
- **`lessons.md`** — what to do *differently* with you: dated, person-specific corrections agents have learned. Read at the start of every session.
- **`log.md`** — what *happened*: durable milestones and decisions about how you work here. Read on demand, not every session.

**These aren't frozen.** Agents *offer to add* to your profile and lessons as they learn how you work — you confirm. Run `/new-person` to start (it copies `people/_template/` and stamps it). Profiles are **public** — teammates can read them and crib for inspiration.

## Static vs. live context

Files in your folder are **static** — they only change when you edit them. This is for stable preferences: tone, working style, how an agent should behave.

For **live context** (current focus, active projects, blockers), use a live context connector if one is set up — it's the live layer that reflects your work signals. Don't duplicate it here; just point to it:

```markdown
## Live context
For my current focus and priorities, get the latest from the live connector.
```

**Your files = how to work with you. The connector = what you're working on.**

## Folders

_None yet — add a folder per teammate, starting from `_template/`._

## Rules

- **Only edit your own folder** — don't modify other people's files
- **Start with `/new-person`** — it scaffolds from `_template/`: `README.md` (profile) + `lessons.md` (what to do differently) + `log.md` (what happened). Add other files if useful.
- **Keep it useful** — these files shape how agents work with you, so keep them honest and up to date
