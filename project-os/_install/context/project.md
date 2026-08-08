---
type: doc
sample: true
last_updated: 2026-06-11
last_updated_by: Sam Rivera
# --- Project metadata: overview.html reads this file for the dashboard hero, timeline dates, and recent activity. ---
# /onboard fills this in. Remove the `sample: true` line above once real content is in (that hides the dashboard's sample banner).
# phase  = project phase: discovery | design | build | launch
# kickoff = project start date (day 0 on the dashboard); the kickoff meeting itself can be a day or two later
client: "Acme Co."
project: "Customer Portal Rebuild"
phase: build
kickoff: "2026-06-02"
end: "2026-09-30"
ourLead: "Sam Rivera"
clientLead: "Jordan Lee"
description: "Rebuilding Acme's customer portal — faster, self-serve, and mobile-first."
# Add filenames (newest first) as the team logs meetings and decisions:
recentMeetings:
  - 2026-06-04-kickoff.md
recentDecisions:
  - 0001-rebuild-not-refit.md
---

# Project at a glance

The project's headline facts. **This file powers the [`overview.html`](../overview.html) dashboard** — its hero, phase pill, timeline dates, and recent-activity lists all read the frontmatter above, so keep that current (and regenerate the dashboard snapshot after edits — see `AGENTS.md` → "The dashboard").

> **Sample data** — replace with your real project (`/onboard` does this).

- **Client:** Acme Co.
- **Project:** Customer Portal Rebuild
- **Phase:** Build · **Timeline:** 2026-06-02 → 2026-09-30
- **Leads:** Sam Rivera (our side) · Jordan Lee (client)

For the full brief see [`brief.md`](./brief.md); the roster in [`stakeholders.md`](./stakeholders.md); goals in [`goals.md`](./goals.md).

---
_Last updated: 2026-06-11_
