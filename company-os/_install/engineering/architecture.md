---
type: doc
owner: "[Owner]"
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: team
read_when: [You're onboarding, or making a change that crosses service or repo boundaries]
---

# Architecture

The cross-repo system map — the big pieces and how they fit. Keep it high-level; the code is the source of truth for detail (link down to it).

## Overview

[One paragraph: what the system is, at a glance. The 30-second version a new engineer needs.]

## Components

| Component | Responsibility | Repo / where it lives |
|---|---|---|
| [e.g. web app] | [what it does] | [repo link] |
| [e.g. API] | [what it does] | [repo link] |
| [e.g. worker/jobs] | [what it does] | [repo link] |

## How data flows

[The main path(s) a request or a piece of data takes through the system. A short description or a simple diagram. Where the boundaries are.]

## Key design choices

[The 2–4 architectural decisions that shape everything else, and *why* — link the ADR in `decisions/` for each.]

- **[Choice]** — [why] → `decisions/<slug>.md`

## Boundaries & invariants

[The things that must always hold — tenant isolation, auth boundaries, data ownership. What breaks if they're violated.]
