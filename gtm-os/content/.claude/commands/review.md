# Review

Review workspace changes before sharing. Checks brand compliance, repo hygiene, data consistency, and completeness.

**Usage:** `/review`

---

## How to review

You're a teammate reviewing, not a linter. Before checking anything:

1. **Understand the scope** — ask the user what changed, or read recently modified files
2. **Classify the work** — what kind of session was this? (account update, content piece, structural change, campaign work)
3. **Pick the relevant checks** — only run axes that apply to this type of work. Most changes only trigger 2-3 of the checks below.

### What "flag it" means

Ask yourself three questions about each potential issue:
- **Would this cause a problem if it shipped?** (wrong date, broken link, stale status)
- **Would this confuse someone reading the repo later?** (orphaned file, missing from index, contradictory info)
- **Would this embarrass us externally?** (off-brand copy, wrong positioning, placeholder text left in)

If the answer to all three is no, don't flag it.

### What NOT to flag

- Subjective style preferences not backed by a specific doc
- "Could be stronger" suggestions
- Pre-existing issues not introduced by these changes
- Things that are technically imperfect but clearly intentional

---

## Step 1: Understand what changed

Ask the user what they've been working on, or review recently modified files to understand the scope.

---

## Step 2: Run applicable checks

### Check A: Brand & content compliance

**When to run:** Changed files include external-facing content (foundations/, work/content/, work/campaigns/, account shareables) or HTML files. Skip for internal-only changes.

Read the brand docs first:
- `foundations/brand/voice.md`
- `foundations/brand/messaging.md`

**Voice violations:**
- Hype language, corporate speak, consulting-speak
- Avoided words/phrases (check the list in voice.md)
- Vague claims without specifics
- Adjective-heavy writing instead of strong verbs
- "Feature soup" — listing capabilities instead of workflows/outcomes
- Run the self-check from voice.md against each piece of changed content

**Messaging violations:**
- Content that contradicts current positioning
- Claims that promise outcomes you can't deliver
- Missing the "problem first, then relief" pattern
- Messaging that doesn't match brand personality

For each issue: quote the specific line from the brand doc being violated.

### Check B: Repo hygiene

**When to run:** Always.

This repo uses two navigation systems. `CLAUDE.md` tells Claude how to navigate and behave. `README.md` files are the structural index — every folder has one explaining what's there and how to use it. Both must stay in sync with reality.

**CLAUDE.md navigation:**
- If files or folders were added, moved, or deleted — does the "How to navigate" table still route correctly?
- Does the "Where things go" table reflect the current folder structure?
- If a new playbook was added, is it referenced where relevant?

**Root README folder table:**
- If a new folder was created, is it listed in the root `README.md` folder table with a link to its README?
- If a folder was removed or renamed, is the table updated?

**Folder README listings:**
- Files added to a directory — is the new file listed in that folder's README?
- Files moved, renamed, or deleted — do folder README listings still match reality?
- New folders — do they have a README?

**Broken internal links:**
- Search changed files for markdown links with relative paths — verify targets exist
- If files were moved/renamed, search for links pointing to old paths

### Check C: Placeholder cleanup

**When to run:** Always after `/onboard`, or when files in `foundations/` or `team/` were modified.

- Search for leftover `[bracket placeholders]` (like `[Company Name]`, `[Your tagline here]`) in files that should have been populated
- Check `foundations/brand/voice.md`, `foundations/brand/messaging.md`, `foundations/brand/positioning.md` — these are the most visible
- Check `team/` profile and voice files for unfilled templates
- If placeholders remain, tell the user what's still missing and offer to fill them in

### Check D: Account data consistency

**When to run:** Account files were added or modified. Skip if no accounts exist yet.

**Structure compliance:**
- New account folder has the required files: `README.md` and `health.md` (see `accounts/_template/`)
- `meetings/` and `shareables/` folders are added as needed — don't flag their absence on new accounts
- Modified account files follow the expected format

**Cross-file consistency:**
- If account status changed in README, does `health.md` reflect the same signals?
- Are contacts, dates, and next steps actually filled in vs left as placeholders?

### Check E: Completeness

**When to run:** New files or folders were created.

- New account folder — missing any expected files?
- New project folder — has a README?
- New playbook — listed in `playbooks/README.md`?
- New file references a template — was the template actually used?

### Check F: Staleness

**When to run:** Modified files contain dates, statuses, or "next step" fields.

- Dates in modified files — are they current or left stale from a previous edit?
- "Next step" or "follow-up by" fields — do they reference dates in the past?
- Status fields — do they reflect what actually happened?

### Check G: Strategy & positioning coherence

**When to run:** Content references product, positioning, or market strategy.

- Does new content align with current direction in `foundations/strategy/`?
- If mentioning competitors, does the framing match `foundations/market/competitors/`?
- Understand intent before flagging — if someone clearly chose a phrasing deliberately, note it but don't hard-flag.

---

## Step 3: Output

Group findings by check (A through G). For each issue:
- **File path**
- **What's wrong** (quote the problematic text if applicable)
- **Which doc/rule it violates** (with a reference)

If a check was skipped (not applicable), don't mention it.

If everything is clean: **"No issues found."**
