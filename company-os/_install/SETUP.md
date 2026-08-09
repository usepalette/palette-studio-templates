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

This OS was created from the **Company OS** template. Work through this once — an agent can do most of it with you (`/onboard`, or just say "set me up"). Delete this file when every box is checked.

## Steps

- [ ] **Company basics** — name + one-liner filled into the root `README.md` and `AGENTS.md` (no more `[Company]`).
- [ ] **Prefill source chosen** — connected a live connector, dropped docs in `_inbox/`, pasted context from another AI, or decided to go manual.
- [ ] **Spaces chosen** — kept the six that fit, dropped the ones that don't, added any others with `/create-space`.
- [ ] **Owners assigned** — every kept space has an owner in the root `README.md` Owners table.
- [ ] **Team added** — a `people/<name>/` folder for each teammate (use `/new-person`).
- [ ] **Brand voice captured** — `gtm/foundations/brand/voice.md` reflects how you actually sound (if you kept `gtm/`).
- [ ] **First real content** — one real account (`/new-account`) or one real doc in a space, so it's a living OS, not an empty shell.

## When you're done

Set **Status: COMPLETE** above, delete this file, and just start working — tell the agent what you're doing and it pulls the right context. Keep it healthy with the weekly habit in `AGENTS.md` → "Keeping the OS healthy".
