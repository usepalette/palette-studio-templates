---
type: doc
sample: true
last_updated: 2026-06-11
last_updated_by: Sam Rivera
---

# Scope

What's in, what's out, and the assumptions the plan rests on. When scope changes, log a decision in [`../decisions/`](../decisions/) and add a row to the change log below.

> **Sample scope** — replace with your real project's scope (`/onboard` does this).

## In scope

- Rebuilt customer portal (browse, account, checkout) — mobile-first.
- New checkout flow integrated with the existing payment provider.
- Self-serve help centre for common support questions.
- Migration of existing customer data and 301 redirects from old URLs.
- Security review before go-live.

## Out of scope / deferred

- The internal admin tools (a separate system — untouched).
- Replacing the payment provider (we integrate with the current one).
- A native mobile app — the rebuilt portal is a responsive web app; app is a possible later phase.

## Assumptions

- The current payment provider stays and exposes the API we need.
- Acme provides analytics access and a test copy of customer data.
- Priya (support lead) is available through discovery and build for domain questions.

## Change log

When scope changes, add a row here and link to the decision.

| Date | Change | Reason | Decision |
| ---- | ------ | ------ | -------- |
| 2026-06-10 | Added data-migration workstream | Rebuild requires migrating legacy data | [0001](../decisions/0001-rebuild-not-refit.md) |

---
_Last updated: 2026-06-11_
