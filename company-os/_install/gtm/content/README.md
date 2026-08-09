---
type: index
owner: "[Owner]"
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: team
---

# Content

Where finished and in-progress content lives — the actual pieces. This is the *output* end of GTM's modular chain:

**`foundations/` (what you know) → `playbooks/` (how you think) → `templates/` (the format) → `content/` (the piece).**

## Structure

```
content/
├── blog/        # posts — drafts and published
├── email/       # newsletters, sequences, announcements
├── social/      # LinkedIn / X posts and threads
└── changelog/   # release notes — one folder per release (YYYY-MM-DD-<slug>/)
```

Starting shape — subfolders appear as real work arrives (the first post creates `blog/`). Don't pre-create empty ones.

## What goes where

| You have… | Put it in… |
|---|---|
| A blog post (draft or published) | `blog/<slug>.md` |
| A newsletter or email | `email/<slug>.md` |
| A social post or thread | `social/YYYY-MM-DD-<slug>.md` |
| Release notes for a launch | `changelog/YYYY-MM-DD-<slug>/` (see `../playbooks/launch.md`) |

## How it connects

- **Load `../foundations/brand/voice.md` before writing anything here** — every piece is on-voice.
- Use the **fill-in templates** in `../templates/` for the format (e.g. `../templates/launch/blog-post.md`).
- The **content playbook** (`../playbooks/content.md`) is the *how we think* — formats, cadence, distribution.
- Ideas come from real signal — customer calls, `../../product/user-feedback/`, sales questions. Keep a running list rather than starting cold.
