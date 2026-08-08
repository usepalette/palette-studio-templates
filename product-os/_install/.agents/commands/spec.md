---
type: command
description: Draft and save a tight product spec linked to its evidence
argument-hint: "<problem or feature brief>"
---

# Spec

Create a paste-ready product brief in `specs/`.

## 1. Understand the brief

Use the request text. If the problem or audience is unclear, ask one concise question.

Search:

- `user-feedback/painpoints/`
- `user-feedback/feature-requests/`
- `discovery/`
- `strategy/`
- `competitors/`
- `team-input/`

Use live context only for current state, and confirm facts that will become durable.

## 2. Check the evidence

Before drafting, state:

- Sources that support the problem
- Missing evidence or unresolved discovery
- Existing specs or tracker items that may overlap

Do not manufacture certainty. A useful spec can explicitly say evidence is thin.

## 3. Draft and save

Create `specs/<what-ships>.md` from `specs/_template.md`. Derive `<what-ships>` as a lowercase,
kebab-case **single path segment** — reject or rewrite anything containing `/`, `..`, or characters
outside `a-z0-9-` so the spec cannot land outside `specs/`.

Keep it concise:

- Problem
- Audience
- Measurable success criteria
- In scope and out of scope
- Optional solution sketch
- Open questions
- Rollout and GTM notes
- Sources

Replace every runtime placeholder in the created spec. Stamp today's date and the current human
author. Use the real tracker link when one exists, `not-created` when the team uses a tracker but
no item exists yet, or `not used` when the team has no tracker.

## 4. Confirm

Show the saved file and summarize the main scope boundary and open question.

Do not create or update an external tracker item unless the user explicitly asks. If they do, show
the exact proposed title, body, team, and project before the external write.
