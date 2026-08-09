---
type: doc
owner: "[Owner]"
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: everyone
---

# Setup checklist

**Status: NOT STARTED**

<!-- AGENTS: while this file exists with unchecked boxes (or the status above isn't COMPLETE),
     this OS is not set up yet — proactively offer to run /onboard. Tick boxes as each step is
     done. When all boxes are checked, set Status to COMPLETE and tell the user they can delete
     this file. This is the deterministic first-run signal — check it at the start of a session. -->

This OS was created from the **Project OS** template. It ships pre-filled with a **sample project** (*Acme Co. — Customer Portal Rebuild*) so the dashboard works on first open — `/onboard` replaces that sample with your real project. Work through this once — an agent can do most of it with you (`/onboard`, or just say "set me up"). Delete this file when every box is checked.

## Steps

- [ ] **Project basics** — project name, client, dates, and one-liner filled into `context/project.md` and the root `README.md` / `AGENTS.md` headings (no more `[Project]` / `[Client]`).
- [ ] **Prefill source chosen** — connected a live connector, dropped docs in `_inbox/`, pasted context from another AI, or decided to go manual.
- [ ] **Stakeholders added** — `context/stakeholders.md` lists everyone on both sides (team / client / external).
- [ ] **Scope & goals** — `admin/scope.md`, `context/goals.md`, and `admin/timeline.md` reflect the real engagement.
- [ ] **Folders fit + team set up** — dropped any folders that don't apply; `team/ways-of-working.md` reflects how the team runs (or `team/` dropped if solo).
- [ ] **First real content** — one real decision (`/new-decision`) or meeting note (`/new-meeting`), so it's a living OS, not an empty shell.
- [ ] **Dashboard rendering** — `overview.html` shows the real project (`context/project.md` filled + snapshot regenerated).

## When you're done

Set **Status: COMPLETE** above, delete this file, and just start working — tell the agent what you're doing and it pulls the right context. Keep it healthy with the weekly habit in `AGENTS.md` → "Keeping the OS healthy".
