---
type: command
description: Wrap up the current session — recap, follow-ups, memory line
argument-hint: "[short slug for the recap filename]"
---

# Finish session

Company-wide end-of-session wrap-up. Recap the work, sweep follow-ups, and capture a memory line so the context survives past this conversation. Works in any space — the steps below adapt to whatever the folder you worked in actually keeps.

**Skip for quick fixes or single-file edits.** The point is to capture sessions that future-you (or a teammate) would want to revisit.

---

## Step 1: Survey the work

Understand what's been done across the workspace, not just this conversation.

- Review the current session context.
- Check recently created or modified files in the relevant workspace areas.
- Read unfamiliar files so the recap reflects real work, not just file names.

## Step 2: Follow-ups

Quick sweep before writing the recap. Do the ones that apply to where you worked:

- **Follow-up tracker** — Did the session surface follow-ups, blockers, or things to revisit? Log them wherever that space tracks them — if you use an issue tracker (e.g. Linear), file it there; otherwise a line in the space's `log.md` is enough.
- **Status board** — If a space keeps a status board that this work affects (e.g. `accounts/status.md` when account files changed), refresh the relevant rows: today's date in Updated; check Next step, Follow-up by, and Blocker fields.

## Step 3: Session recap

Capture what the session produced in the space's two memory files (root `AGENTS.md` → Conventions): a *do-differently* line in **`lessons.md`** and a *what-happened* line in **`log.md`**, at the narrowest scope that benefits (person → space → company). Propose → confirm → write.

For a meaningful session, also write a fuller recap as `YYYY-MM-DD-<slug>.md` in a sensible spot in the space you worked in (a `log/sessions/` folder if the space keeps one, otherwise alongside the work). If `$ARGUMENTS` is set, use it as the slug; otherwise pick a short kebab-case slug. Otherwise the `log.md` line is enough — don't force a recap file.

```markdown
---
type: meeting
owner: "[Owner]"
status: active
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: team
---

# <Title> — YYYY-MM-DD

## Summary
2-3 sentences. What was the goal, what got done.

## Decisions
Choices that were made and why. Skip obvious ones — only capture forks
someone revisiting would care about.

## What changed
Files created, moved, or significantly edited. Group logically.

## Context surfaced
Market intel, competitor info, user feedback, or strategic insight.
Skip if nothing notable.

## Open threads
Unfinished work, known issues, things to pick up next. Skip if clean.
```

## Step 4: Confirm

Tell the user:
- Which `lessons.md` / `log.md` entries were added, and at what scope (person / space / company)
- The session recap file path (or that you skipped it, and why)
- Which follow-up tracker / status board was updated, if any

## Optional: Live-context signal

If a live-context connector (e.g. Palette) is set up, capture a work signal to it so the context survives past this chat. Cover:

- What was done and the motivation behind it
- Key decisions made and the reasoning (what was considered, what was chosen, why)
- New context surfaced — market intel, customer signals, strategic insights, positioning shifts
- How this connects to broader initiatives or goals
- Follow-ups, open threads, or things that need attention next
- Who or what teams this is relevant to

Skip purely mechanical details (file moves, workspace hygiene). Include anything carrying business or strategic context. If no connector is set up, skip this step.
