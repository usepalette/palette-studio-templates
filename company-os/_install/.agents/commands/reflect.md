---
type: command
description: Tidy the OS's lessons.md and log.md files and propose promotions — suggest-only
argument-hint: "[scope path, e.g. gtm/ or people/<name>/ — omit for whole OS]"
---

# Reflect

Periodic clean-up and self-reflection over the OS's memory files — `lessons.md` and `log.md` at every scope. This is the "distill up, prune down" pass that makes *teach once* actually compound: recurring lessons get promoted into the guides agents read every time, and the inbox stays short.

**Suggest-only.** Propose changes as diffs a human approves. Never auto-rewrite an `AGENTS.md` rule, never delete history from a `log.md`, never touch a folder you're not allowed to edit (respect `edit_policy`).

Scope: the path in `$ARGUMENTS` (e.g. `gtm/`, `people/<name>/`), or the whole OS if omitted.

## Two tiers

Run Tier 1 always. Run Tier 2 and present its proposals; apply only what the human confirms.

### Tier 1 — Hygiene (low-risk; still confirm before writing)

For each `lessons.md` and `log.md` in scope:

- **Dedupe / merge** near-duplicate lines into one.
- **Absolute dates** — convert relative dates ("yesterday", "last week") to `YYYY-MM-DD` **only when a reliable timestamp exists** (the line's own date, a dated neighbour, the file's history). If you can't anchor it, leave the text as-is and flag the line for the human to date — never guess a `YYYY-MM-DD`.
- **Right file?** — flag a *do-differently* rule sitting in `log.md`, or *what-happened* history sitting in `lessons.md`, and propose moving it.
- **Right scope?** — flag a person-specific line in a space/root file (or vice-versa) and propose relocating it to the narrowest scope that benefits.
- **Contradictions** — surface two lessons that conflict; don't pick a winner, ask.
- **Broken links** — don't re-implement link checking; run `/workspace-heal report` and fold its findings in.

### Tier 2 — Reflection (needs human OK before any change)

- **Promote:** find lessons that have recurred, stabilized, or clearly belong in the always-loaded layer. Propose moving each into the right guide — a rule in `AGENTS.md`, a line in a `README.md` / person profile, or a playbook — and pruning it from `lessons.md`.
- **Retire:** propose dropping lessons that have already graduated into a guide, or that are stale and never recurred. Say why.

## Output

One review, grouped, as proposed diffs the human approves item by item:

```
## Reflect — {scope} — {date}

### Tier 1 · Hygiene ({count})
- {file}: {dedupe | date | wrong-file | wrong-scope | contradiction} → {proposed change}

### Tier 2 · Promote ({count})
- "{lesson}" → promote into {guide}, prune from {lessons.md} — {why}

### Tier 2 · Retire ({count})
- "{lesson}" in {file} → drop — {graduated | stale}
```

Apply only confirmed items. Stamp `last_updated` / `last_updated_by` on any file you change (`last_updated_by` = the person, never the agent).

## When to run

- On a schedule (e.g. a weekly live-connector routine) so the memory files don't drift.
- At the end of a heavy session, after `/finish-session`.
- Whenever a `lessons.md` is getting long — that length *is* the signal to promote and prune.
