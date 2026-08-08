---
type: index
owner: "[Owner]"
status: active
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: everyone
---

# log/

Fuller **session recaps** — the richer memory superset. The one-line record lives at the root: `lessons.md` (what to do differently) and `log.md` (what happened + decisions). This folder holds the longer write-ups worth keeping from a meaningful session.

`/finish-session` appends the one-liners to the root files and, for a meaningful session, drops a full recap here.

## Session recaps (`sessions/`)

One file per work session, named `YYYY-MM-DD-slug.md`:

```markdown
# {Title} — YYYY-MM-DD

## Summary
2-3 sentences. What was the goal, what got done.

## Decisions
Choices made and why. Skip obvious ones.

## What changed
Files created, moved, or significantly edited.

## Context surfaced
Market intel, competitor info, user feedback, strategic insight. Skip if nothing notable.

## Open threads
Unfinished work, known issues, things to pick up next. Skip if clean.
```

## When to log

- After any session that makes decisions or surfaces insights (via `/finish-session`)
- Skip for quick fixes or single-file edits
