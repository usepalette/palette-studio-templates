---
type: command
description: Review your work against brand, hygiene, and completeness before sharing
---

# Review

Review workspace changes before sharing. Checks brand compliance, repo hygiene, data consistency, and completeness.

**Usage:** `/review`

---

## How to review

You're a teammate reviewing, not a linter. Before checking anything:

1. **Understand the scope** — ask the user what changed, or read recently modified files
2. **Classify the work** — what kind of session was this? (account update, content piece, structural change, campaign work)
3. **Pick the relevant checks** — only run axes that apply. Most changes only trigger 2-3 of the checks below.

### What "flag it" means

Ask three questions about each potential issue:
- **Would this cause a problem if it shipped?** (wrong date, broken link, stale status)
- **Would this confuse someone reading the repo later?** (orphaned file, missing from index, contradictory info)
- **Would this embarrass us externally?** (off-brand copy, wrong positioning, placeholder text left in)

If the answer to all three is no, don't flag it.

### What NOT to flag
- Subjective style preferences not backed by a specific doc
- "Could be stronger" suggestions
- Pre-existing issues not introduced by these changes
- Things technically imperfect but clearly intentional

---

## Step 1: Understand what changed

Ask the user what they've been working on, or review recently modified files to understand the scope.

## Step 2: Run applicable checks

### Check A: Brand & content compliance
**When:** Changed files include external-facing content (`foundations/`, `work/content/`, `work/campaigns/`, account shareables) or HTML. Skip for internal-only.

Read `foundations/brand/voice.md` and `messaging.md` first.
- **Voice violations:** hype/corporate/consulting-speak; avoided words (check voice.md); vague claims without specifics; adjective-heavy instead of strong verbs; "feature soup" (capabilities instead of workflows/outcomes). Run the self-check from voice.md against each piece.
- **Messaging violations:** content that contradicts current positioning; claims you can't deliver; missing the "problem first, then relief" pattern; off-personality.

For each issue: quote the specific line from the brand doc being violated.

### Check B: Repo hygiene
**When:** Always.

Both navigation systems must stay in sync with reality: `AGENTS.md` (how agents behave + the "Where things live" table) and the `README.md` files (every folder's structural index).
- **AGENTS.md:** if files/folders were added, moved, or deleted, does the "Where things live" table still route correctly?
- **Root README:** new folder → listed in the structure/router with a link? Removed/renamed → table updated?
- **Folder READMEs:** files added → listed in that folder's README? Moved/renamed/deleted → listings still match? New folders → have a README?
- **Broken links:** relative markdown links in changed files → verify targets exist; if files moved, search for links to old paths.

### Check C: Placeholder cleanup
**When:** Always after `/onboard`, or when `foundations/` or `team/` files changed.
- Search for leftover `[bracket placeholders]` in files that should have been populated (esp. `foundations/brand/*`, `team/` profiles). If placeholders remain, tell the user what's missing and offer to fill them.

### Check D: Account data consistency
**When:** Account files added or modified. Skip if no accounts exist.
- New account folder has required files (`README.md`, `health.md` — see `accounts/_template/`); `meetings/`/`shareables/` added as needed (don't flag their absence on new accounts).
- If account status changed in README, does `health.md` reflect the same signals? Are contacts/dates/next-steps filled in vs placeholders? Is it on `accounts/status.md`?

### Check E: Completeness
**When:** New files or folders created.
- New account — missing expected files? New project — has a README? New playbook — listed in `playbooks/README.md`? New file references a template — was the template actually used?

### Check F: Staleness
**When:** Modified files contain dates, statuses, or "next step" fields.
- Dates current or left stale? "Next step"/"follow-up by" referencing past dates? Status fields reflect what actually happened?

### Check G: Strategy & positioning coherence
**When:** Content references product, positioning, or market strategy.
- Aligns with `foundations/strategy/`? Competitor framing matches `foundations/market/competitors/`? Understand intent before flagging deliberate choices.

---

## Step 3: Output

Group findings by check (A–G). For each: **file path**, **what's wrong** (quote if applicable), **which doc/rule it violates** (with a reference). Skip checks that didn't apply. If everything's clean: **"No issues found."**
