---
type: index
owner: "[Owner]"
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: team
---

# Postmortems

Blameless write-ups of production incidents — what happened, why, and what changes so it doesn't recur. **Blameless means: about the system and contributing factors, never individuals.** The goal is learning, not blame.

## When to write one

After any incident that affected users, risked data, or woke someone up. Small or large — if it taught you something about the system, capture it.

## How

1. Copy `_template.md` to `YYYY-MM-DD-<short-title>.md`.
2. Write it soon after, while it's fresh. Facts first, then analysis.
3. Turn each action item into a real task, and link the ADR/runbook if this changes how you build or operate.

## Index

| Date | Incident | Impact |
|---|---|---|
| _[YYYY-MM-DD]_ | _[what happened]_ | _[who/what was affected]_ |
