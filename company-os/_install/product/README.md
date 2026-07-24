---
type: index
owner: [Owner]
status: draft
last_updated: YYYY-MM-DD
last_updated_by: [Owner]
edit_policy: team
---

# product

Product knowledge as a file system.

A version-controlled, AI-readable workspace where user feedback, product strategy, discovery, and competitive intel live as markdown — one source of truth instead of scattered docs, threads, and tribal knowledge.

## Where does it go?

| You have… | Put it in… |
|---|---|
| A raw feedback snippet from a user | `user-feedback/feedback/` |
| An explicit feature ask | `user-feedback/feature-requests/` |
| Notes from a user interview | `user-feedback/user-interviews/` |
| A recurring pain pattern across multiple users | `user-feedback/painpoints/` |
| A product strategy thesis | `strategy/` |
| An open question you're still exploring | `discovery/` |
| A competitor profile | `competitors/` — template in `competitors/README.md` |
| A spec to draft | `specs/` — copy `specs/_template.md` (paste-ready for Linear/Notion) |

## Folder map

```
product/
├── user-feedback/   # feedback, feature-requests, user-interviews, painpoints
├── strategy/         # product strategy theses
├── discovery/        # open questions / areas to explore
├── competitors/      # what they're building — competitor intel (template in its README)
└── specs/            # product spec drafts, paste-ready (template in its README)
```

`competitors/` and `specs/` ship with a fill-in template in their README. The `user-feedback/` subfolders appear as real feedback arrives — don't pre-create empty ones.

## How this space thinks

This space has its own mindset — see [`AGENTS.md`](AGENTS.md) for the thinking-partner posture and local rules that layer on top of the company-wide [`../AGENTS.md`](../AGENTS.md).
