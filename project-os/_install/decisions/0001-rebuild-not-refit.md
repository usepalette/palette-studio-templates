---
type: decision
sample: true
date: 2026-06-10
status: accepted
last_updated: 2026-06-10
last_updated_by: Sam Rivera
---

# 0001 — Rebuild the portal, don't refit the legacy one

- **Date:** 2026-06-10
- **Status:** accepted
- **Decided by:** Sam Rivera, Jordan Lee, Alex Chen

> **Sample decision** — this ships as an example so the workspace isn't empty. Delete it (and clear the `sample: true` flags) when you set up your real project.

## Context

Acme's customer portal runs on a legacy stack that's slow on mobile and hard to change. We had to choose between patching the existing portal or rebuilding it. Kickoff surfaced that most of the pain (page speed, checkout drop-off) is baked into the old architecture.

## Options considered

1. **Refit the legacy portal** — incremental fixes on the current codebase.
2. **Rebuild** — a new portal on a modern stack, migrating data and URLs.
3. **Buy an off-the-shelf portal** — configure a SaaS product instead.

## Decision

Rebuild on a modern stack, migrating the existing data and 301-redirecting old URLs.

## Why

Refitting can't fix the architectural causes of the slowness, and the checkout flow needs to change end-to-end. Off-the-shelf wouldn't cover Acme's custom pricing rules. A rebuild is more up-front work but is the only option that hits the speed and conversion targets in `context/goals.md`.

## Consequences

- A data-migration workstream and a redirect plan are now in scope (see `admin/scope.md`).
- Short-term: two portals run in parallel until cutover.
- We accept a bigger up-front build for a faster, maintainable end state.
