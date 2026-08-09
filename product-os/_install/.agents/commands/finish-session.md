---
type: command
description: Wrap up meaningful product work with decisions, follow-ups, and durable learning
argument-hint: "[short recap slug]"
---

# Finish session

Use for meaningful product sessions. Skip quick fixes.

## 1. Survey the work

- Review the conversation and files created or changed.
- Read unfamiliar changed files so the recap reflects content, not filenames.
- Identify decisions, evidence surfaced, unresolved questions, and follow-ups.

## 2. Refresh affected systems

- If feedback changed, run `/feedback-sync`.
- If a decision changes a tracker item, prepare the proposed tracker update. Only make the external
  write when the user explicitly asks and the exact change is clear.
- Update local indexes or company profiles affected by the work.

## 3. Capture memory

Propose:

- A `lessons.md` line for a durable do-differently correction.
- A `log.md` line for what happened. Prefix genuine forks with `Decision:`.

After confirmation, add only the lines that clear the durability bar.

For a meaningful session, create `log/sessions/YYYY-MM-DD-short-slug.md`:

```markdown
---
type: meeting
owner: "[Responsible owner]"
status: active
date: YYYY-MM-DD
last_updated: YYYY-MM-DD
last_updated_by: "[Current human]"
edit_policy: team
---

# [Title]

## Goal
[What the session set out to do.]

## Decisions
[Real forks and reasoning.]

## Evidence surfaced
[User signal, analytics, market evidence, or team input.]

## What changed
[Created or materially updated files.]

## Open threads
[Unresolved work and next owner.]
```

## 4. Confirm

Tell the user:

- Memory lines added
- Recap path, or why it was skipped
- Dashboard, index, company profile, or tracker changes
- Remaining open threads

If a live context connector supports sharing a work update, offer it. Do not send without an
explicit request.
