---
description: Audit workspace structure for broken references, stale indexes, and misplaced files
argument-hint: "[fix|report]"
---

# Workspace Heal

Structural health check for the company OS workspace. Finds broken internal links, stale README listings, orphaned files, index drift, missing frontmatter/`type`, and file-role drift — across the root and every space folder (`accounts/`, `gtm/`, `product/`, `engineering/`, `ops/`, `people/`, and any spaces added later). Run with `fix` to auto-repair, or `report` to just list issues.

Default: `report` (no changes made).

## Trigger

User runs `/workspace-heal` (report only) or `/workspace-heal fix` (report + fix).

## Checks

Run every check below. Collect all issues, then present a summary grouped by severity.

### 1. Broken internal links

Scan all `.md` files for markdown links (`[text](path)`) where the target is a relative path. Verify each target exists on disk.

**Exclude:** URLs (http/https), anchor links (#), and template placeholders like `[name]` or `$VAR`.

**Report:** Each broken link with source file, line, and the dead target path.

**Fix:** Flag for manual review — broken links need human judgment on whether to update or remove.

### 2. README file listings vs reality

For each README.md that contains a file/folder listing (code blocks showing directory trees, or bullet lists with `**filename**` patterns), verify that every listed file actually exists in that directory.

Also check the reverse: files that exist in a directory but aren't mentioned in its README (when the README appears to be an exhaustive listing).

**Exclude (standard furniture):** `README.md`, `CLAUDE.md` / `GEMINI.md`, `lessons.md`, and `log.md` are assumed in every folder — never flag them as "exists but unlisted." (`.vibe/AGENTS.md` is the root-only Mistral pointer — also never flag it.)

**Key READMEs to check:**
- `README.md` (root — structure tree, owners table)
- `AGENTS.md` (root — navigation table paths)
- Each space's front-door README: `accounts/README.md`, `gtm/README.md`, `product/README.md`, `engineering/README.md`, `ops/README.md`, `people/README.md`
- Each space's `AGENTS.md` where present (e.g. `gtm/AGENTS.md`, `product/AGENTS.md`) — navigation tables and skill/command references
- Command & skill indexes at every level: `.agents/commands/README.md` and `.agents/skills/README.md` at the root and inside any space that keeps them (e.g. `gtm/.agents/`)
- Any subfolder README that carries an explicit listing (e.g. `gtm/foundations/*/README.md`, `product/*/README.md`)

**Report:** Each mismatch — "listed but missing" or "exists but unlisted."

**Fix:** Update the README listing to match reality. Remove references to non-existent files. Add references to unlisted files. Never create stub files.

### 3. Orphaned files

Check for files that are clearly in the wrong location:
- Session log files (`YYYY-MM-DD-*.md`) sitting loose in a folder that keeps a dedicated session-log location (e.g. `gtm/log/sessions/`). The OS-wide memory convention is a `lessons.md` + `log.md` in every folder; some spaces additionally keep a richer `log/` folder for dated recaps. Flag obvious strays (a dated recap loose in a folder), not the standard `lessons.md` / `log.md` furniture.
- Files in root that should be in a subdirectory

**Report:** Each orphaned file with suggested correct location.

**Fix:** Move files to their correct location.

### 4. Project index freshness

Only where a folder maintains a project index (e.g. `gtm/work/projects/README.md`). For each project in the index table:
- Verify the project folder still exists
- Check if "Last active" date looks stale compared with the visible file and session context
- Check for any project folders not in the index

**Report:** Stale dates, missing projects, deleted projects still listed.

**Fix:** Update the index table with correct dates and add missing projects.

### 5. Status board consistency

Only where a folder keeps a status board (e.g. `accounts/status.md`). For each account row:
- Verify the account folder exists in `accounts/`
- Check if the "Updated" date is stale (>30 days old)
- Flag accounts with stale status rows that still look active

**Report:** Stale rows, missing folders, inconsistent statuses.

**Fix:** Flag for manual review — account status changes need human judgment.

### 6. AGENTS.md navigation paths

For each row in the AGENTS.md navigation table, verify the referenced path exists.

**Report:** Any dead paths.

**Fix:** Update paths or flag for review.

### 7. Agent adapter parity

Check every level that uses the canonical + adapter split — the root (`/.agents/` ↔ `/.claude/`) and any space that keeps its own (e.g. `gtm/.agents/` ↔ `gtm/.claude/`). Within each level:

- Every `.agents/commands/*.md` file has a matching `.claude/commands/*.md` adapter.
- Every `.agents/skills/*.md` file has a matching `.claude/skills/*.md` adapter.
- Each `.claude/` adapter points to the matching canonical file with `../../.agents/{commands|skills}/{filename}`.
- If the canonical file has YAML frontmatter, the adapter has the same frontmatter so native discovery metadata stays in sync.

Do not flag a space adapter as "extra" just because its canonical file was promoted to the root `/.agents/` — a space may legitimately reference a root-level command or skill.

**Report:** Missing adapters, extra adapters without a canonical file, adapters pointing to the wrong canonical file, or stale adapter frontmatter.

**Fix:** Create or update the adapter. Preserve YAML frontmatter from the canonical file when present, then point to the canonical file.

### 8. Frontmatter & `type` coverage

Every content `.md` should carry frontmatter with a `type` (the "stamp on creation" rule — root `AGENTS.md` → Conventions).

- Flag content `.md` files with **no frontmatter** or **no `type:`** field.
- Flag frontmatter keys that aren't `snake_case` — the one allowed exception is `argument-hint` (a Claude Code harness key).

**Exclude:** agent/behaviour files (`AGENTS.md`, `CLAUDE.md` / `GEMINI.md` / `.vibe/AGENTS.md`), example OS templates, and generated viewers.

**Report:** files missing frontmatter or `type`; non-snake_case keys.

**Fix:** add `type` (infer from folder — see the `type` vocabulary); rename keys to snake_case. Never touch `argument-hint`.

### 9. File-role compliance (which file for what)

Check the OS follows the four-file model (root `AGENTS.md` → Conventions → "The four files in a space"):

- Every space folder has a `README.md` (its front door), plus the `lessons.md` + `log.md` furniture. (A space may satisfy the log side with a richer `log/` folder instead of `log.md` — don't flag that.)
- Every top-level space is **registered**: it appears in the root `README.md` `## Owners` table + `## Structure` tree and in the root `AGENTS.md` "The spaces" routing table. Flag a space folder that exists on disk but is missing from either (a space scaffolded by `/create-space` should already be registered).
- An `AGENTS.md` exists **only where the space has a distinct mindset**. Flag an `AGENTS.md` that is empty, a stub, or that just restates its README — it should be behavioural rules, not navigation.
- Each space's front door carries a **"what to do when" table** where the space has real workflows (`accounts/`, `gtm/`, `product/`, `ops/`). Flag a workflow-heavy space whose README/AGENTS has no task→do routing.

**Report:** missing README or furniture; thin/duplicative `AGENTS.md`; missing routing table.

**Fix:** flag for review — these need human judgment. **Never auto-create an `AGENTS.md`, a routing table, or a stub file.** (Tidying `lessons.md` and promoting recurring lessons into guides is `/reflect`'s job, not this command's.)

### 10. Leftover template placeholders (is setup finished?)

This OS started from a template. Real content should have replaced the placeholders. Scan for un-filled `[bracket placeholders]` (e.g. `[Company]`, `[Owner]`), literal `YYYY-MM-DD` in a `last_updated`/`last_updated_by` field, and `# [Company] OS` in the root `AGENTS.md`.

**Exclude:** `_template/` folders (their placeholders are intentional — that's what they're for) and prose that *names* a placeholder as an instruction (e.g. "run `/onboard` to replace `[Company]`").

**Report:** each file still carrying template placeholders — this usually means `/onboard` hasn't finished, or a folder was hand-copied instead of scaffolded with `/new-account` / `/new-person`.

**Fix:** flag for review, and suggest running `/onboard` (if broad) or filling the specific fields. Never invent the values.

## Output

### Summary format

```
## Workspace Health Report — {date}

**{N} issues found** ({X} auto-fixable, {Y} need review)

### Broken links ({count})
- `{source}:{line}` → `{dead_target}` — {suggestion}

### README drift ({count})
- `{readme}` — {file} listed but missing
- `{readme}` — {file} exists but unlisted

### Orphaned files ({count})
- `{file}` → should be in `{correct_location}`

### Project index ({count})
- `{project}` — last active shows {listed}, actual is {actual}

### Status board ({count})
- `{account}` — {issue}

### Navigation paths ({count})
- `AGENTS.md` row "{task}" → `{path}` — {issue}

### Adapter drift ({count})
- `{adapter}` — {issue}

### Frontmatter & type ({count})
- `{file}` — missing frontmatter / missing `type` / non-snake_case key `{key}`

### File-role drift ({count})
- `{space}` — missing README or furniture / thin AGENTS.md / no "what to do when" table
```

If running in `fix` mode, show what was changed after each section.

## When to run

- Before any presentation or demo
- After large restructuring sessions
- When onboarding a new team member (first impressions matter)
