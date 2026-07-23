---
description: Wrap up the current session — recap, follow-ups, memory line
argument-hint: "[short slug for the recap filename]"
---

# Finish session

End-of-session wrap-up for this project OS. Recap the work, sweep follow-ups, and capture a memory line so the context survives past this conversation.

**Skip for quick fixes or single-file edits.** The point is to capture sessions that future-you (or a teammate) would want to revisit.

---

## Step 1: Survey the work

Understand what's been done across the workspace, not just this conversation.

- Review the current session context.
- Check recently created or modified files across the project folders.
- Read unfamiliar files so the recap reflects real work, not just file names.

## Step 2: Follow-ups

Quick sweep before writing the recap. Do the ones that apply:

- **Follow-up tracker** — Did the session surface follow-ups, blockers, or things to revisit? Log them wherever the project tracks them — if you use an issue tracker (e.g. Linear), file it there; otherwise a line in the root `log.md` is enough.
- **Indexes & dashboard** — If the work added a decision or a meeting, make sure it's listed in `decisions/README.md` / `meetings/README.md` and, if `context/project.md` tracks it (`recentMeetings` / `recentDecisions`), there too. If any of the five frontmatter files changed (`context/project.md`, `admin/timeline.md`, `deliverables/milestones.md`, `context/stakeholders.md`, `context/goals.md`), regenerate the `overview.html` `data-snapshot`.

## Step 3: Session recap

Capture what the session produced in the project's two memory files (root `AGENTS.md` → Conventions): a *do-differently* line in the root **`lessons.md`** and a *what-happened* line in the root **`log.md`**. Propose → confirm → write.

For a meaningful session, also write a fuller recap as `YYYY-MM-DD-<slug>.md` in a sensible spot (a `log/` folder if the project keeps one, otherwise alongside the work). If a slug argument was provided (Claude passes it as `$ARGUMENTS`), use it; otherwise pick a short kebab-case slug. Otherwise the `log.md` line is enough — don't force a recap file.

```markdown
# <Title> — YYYY-MM-DD

## Summary
2-3 sentences. What was the goal, what got done.

## Decisions
Choices that were made and why. Skip obvious ones — only capture forks
someone revisiting would care about.

## What changed
Files created, moved, or significantly edited. Group logically.

## Context surfaced
Client signals, scope shifts, risks, or insight worth keeping.
Skip if nothing notable.

## Open threads
Unfinished work, known issues, things to pick up next. Skip if clean.
```

## Step 4: Confirm

Tell the user:
- Which root `lessons.md` / `log.md` entries were added
- The session recap file path (or that you skipped it, and why)
- Which follow-up tracker, index, or dashboard was updated, if any

## Optional: Live-context signal

If a live-context connector (e.g. Palette) is set up, capture a work signal to it so the context survives past this chat. Cover:

- What was done and the motivation behind it
- Key decisions made and the reasoning (what was considered, what was chosen, why)
- New context surfaced — client signals, scope shifts, risks, strategic insight
- How this connects to the project's goals and timeline
- Follow-ups, open threads, or things that need attention next
- Who or which stakeholders this is relevant to

Skip purely mechanical details (file moves, workspace hygiene). Include anything carrying project or client context. If no connector is set up, skip this step.
