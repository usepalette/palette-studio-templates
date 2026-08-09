---
type: index
owner: "[Owner]"
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: team
---

# Accounts

Working memory for companies you're actively engaged with. This is the **synthesis layer** on top of your CRM (accounts list, pipeline), product analytics (usage), and wherever conversations happen (Slack, email, call notes).

What goes here is the stuff that doesn't fit in a CRM field: what you actually think about an account, your strategy, meeting takeaways, what they care about, internal dynamics.

## You need to… / Where does it go

| You need to… | Go to |
|---|---|
| Set up a new account | Run `/new-account <name>` — scaffolds `<account-name>/` from `_template/` and adds it to the board |
| Log a meeting | `<account>/meetings/YYYY-MM-DD-topic.md` |
| Track a feature request | `<account>/requests.md` |
| Add a shareable | `<account>/shareables/` |
| See where every account stands | [`status.md`](status.md) — the live board |
| Understand one account fast | that account's `README.md` — the brief |

## When to create a folder

Create a folder when there's real engagement — meetings have happened, a channel exists, or they've signed up. A name in your CRM doesn't need a folder. If you don't have enough context to write anything meaningful, you don't need one yet.

## The per-account file model

Each account folder is scaffolded by `/new-account` (which copies `_template/` and stamps it):

| File | Purpose | Update cadence | Who writes it |
|---|---|---|---|
| `README.md` | The account brief — identity, people, what they care about, strategy, open threads | After meetings, strategy shifts | Human |
| `health.md` | Health signals — product usage, communication activity | Regular check-ins | Human, or a machine sync if one exists |
| `meetings/` | One file per meeting — summary, notes, follow-ups | After each meeting | Human |
| `requests.md` | Features requested, with context and status | As requests come in / get shipped | Human |
| `shareables/` | Customer-facing materials (decks, docs, exports) | As created | Human |

## README.md structure

Keep the account brief scannable — detail belongs in meeting files. See [`_template/README.md`](_template/README.md) for the full shape: identity table, key people, about them, what they care about, history, strategy (objective / current bet / risks), open threads, links, timeline.

**Key principles:**
- **Stay under ~120 lines.** If it's growing, move detail to meeting files.
- **"What they care about" is a summary, not a transcript.** One line per theme.
- **"About them" gets replaced, not appended.** It's a snapshot of how they work now, not a history.
- **Open threads is a working list.** Remove items when done.

## Status board

See [`status.md`](status.md) for the live status of all accounts — stage, health, and next step, at a glance.

**Stages:** Lead · Outreach · Engaged · Onboarding · Active · Paused · Churned
**Health:** 🟢 Active · 🟡 Cooling · 🔴 Cold · ⚪ Unknown
