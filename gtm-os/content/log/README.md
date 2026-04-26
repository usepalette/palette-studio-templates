# Log

Institutional memory. What happened, what was decided, what was learned.

## Structure

```
log/
├── overview.md    # running record — the file you read to catch up
└── sessions/      # per-session recaps — reference material
```

## overview.md

Reverse-chronological. Three sections:

- **Decisions** — Forks in the road where you chose A over B, and why
- **Learnings** — Things discovered that should inform future work
- **Log** — What happened (most entries land here)

Format: `**YYYY-MM-DD** — Description.`

## Session recaps

One file per work session in `sessions/`. Format:

```markdown
# {Title} — YYYY-MM-DD

## Summary
2-3 sentences. What was the goal, what got done.

## Decisions
Choices that were made and why. Skip obvious ones.

## What changed
Files created, moved, or significantly edited.

## Context surfaced
Market intel, competitor info, user feedback, strategic insight.
Skip if nothing notable.

## Open threads
Unfinished work, known issues, things to pick up next.
Skip if clean.
```

## When to log

- After any session that makes decisions or surfaces insights
- Skip for quick fixes or single-file edits
- When in doubt, log it — future you will thank present you
