---
description: Audit workspace structure for broken references, stale indexes, and misplaced files
argument-hint: "[fix|report]"
---

# Workspace Heal

Structural health check for this project OS workspace. Finds broken internal links, stale README listings, orphaned files, index drift, dashboard-snapshot drift, missing frontmatter/`type`, and adapter drift — across the root and every project folder (`context/`, `admin/`, `decisions/`, `meetings/`, `research/`, `design/`, `deliverables/`, `team/`, and any others you keep). Run with `fix` to auto-repair, or `report` to just list issues.

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

For each README.md that contains a file/folder listing (code blocks showing directory trees, or bullet lists with `**filename**` patterns), verify that every listed file actually exists in that directory. Also check the reverse: files that exist but aren't mentioned (when the README appears to be an exhaustive listing).

**Exclude (standard furniture):** `README.md`, `CLAUDE.md` / `GEMINI.md` / `.vibe/AGENTS.md`, `lessons.md`, and `log.md`.

**Key READMEs to check:**
- Root `README.md` — the structure tree
- Root `AGENTS.md` — the "Where things live" table paths
- Each folder's README where it carries a listing (`decisions/README.md`, `meetings/README.md`, `deliverables/README.md`)
- Command & skill indexes: `.agents/commands/README.md` and `.agents/skills/README.md`

**Report:** Each mismatch — "listed but missing" or "exists but unlisted."

**Fix:** Update the README listing to match reality. Never create stub files.

### 3. Orphaned files

Check for files clearly in the wrong location:
- A dated recap (`YYYY-MM-DD-*.md`) sitting loose in a folder that keeps a dedicated `log/` location.
- A decision file loose outside `decisions/`, or a meeting note loose outside `meetings/`.
- Files in root that should be in a subfolder.

**Report:** Each orphaned file with suggested correct location.

**Fix:** Move files to their correct location.

### 4. Dashboard snapshot freshness

The `overview.html` dashboard renders from a `data-snapshot` JSON block that mirrors the five frontmatter files: `context/project.md`, `admin/timeline.md`, `deliverables/milestones.md`, `context/stakeholders.md`, and `context/goals.md`. Verify the snapshot is in sync with those files — every field present, values matching the current frontmatter.

**Report:** Each field where the snapshot and a frontmatter file disagree, or a frontmatter file the snapshot omits.

**Fix:** Regenerate the `data-snapshot` from the five frontmatter files (see `AGENTS.md` → "The dashboard").

### 5. Decisions & meetings index consistency

Verify the index lists match the files on disk:
- Every row in `decisions/README.md` points to a `decisions/NNNN-*.md` that exists, and every `decisions/NNNN-*.md` on disk appears in the index. Flag numbering gaps or duplicate NNNN.
- Every row in `meetings/README.md` points to a `meetings/YYYY-MM-DD-*.md` that exists, and every meeting note on disk appears in the index.
- Cross-check the root README `recentMeetings` / `recentDecisions` against the newest files.

**Report:** Listed-but-missing, exists-but-unlisted, numbering gaps or duplicates.

**Fix:** Update the index (and the dashboard lists) to match reality. Never create stub files.

### 6. AGENTS.md navigation paths

For each row in the root `AGENTS.md` "Where things live" table, verify the referenced folder exists.

**Report:** Any dead paths.

**Fix:** Update paths or flag for review.

### 7. Agent adapter parity

Check the canonical + adapter split (`/.agents/` ↔ `/.claude/`):

- Every `.agents/commands/*.md` has a matching `.claude/commands/*.md` adapter.
- Every `.agents/skills/*.md` has a matching `.claude/skills/*.md` adapter.
- Each `.claude/` adapter points to its canonical file with `../../.agents/{commands|skills}/{filename}`.
- If the canonical file has YAML frontmatter, the adapter carries the same frontmatter so native discovery metadata stays in sync.

**Report:** Missing adapters, extra adapters without a canonical file, adapters pointing to the wrong canonical file, or stale adapter frontmatter.

**Fix:** Create or update the adapter, preserving the canonical frontmatter, then point to the canonical file.

### 8. Frontmatter & `type` coverage

Every content `.md` should carry frontmatter with a `type` (the "stamp on creation" rule — root `AGENTS.md` → Conventions).

- Flag content `.md` files with **no frontmatter** or **no `type:`** field.
- Flag frontmatter keys that aren't `snake_case`. Allowed exceptions (do NOT flag): `argument-hint` (a Claude Code harness key), and the dashboard-contract keys in `context/project.md` — `recentMeetings`, `recentDecisions`, `ourLead`, `clientLead` — which `overview.html` reads by exact name. Renaming those would break the dashboard.

**Exclude:** agent/behaviour files (`AGENTS.md`, `CLAUDE.md` / `GEMINI.md` / `.vibe/AGENTS.md`), `TEMPLATE.md` files (their placeholders are intentional), and generated viewers.

**Report:** files missing frontmatter or `type`; non-snake_case keys (excluding the allowed exceptions above).

**Fix:** add `type` (infer from folder); rename stray keys to snake_case. Never touch `argument-hint` or the dashboard-contract keys.

### 9. Leftover template placeholders (is setup finished?)

This OS started from a template. Real content should have replaced the placeholders and the shipped sample project. Scan for: `sample: true` in any frontmatter (the shipped *Acme Co.* sample — should be gone once real content is in), un-filled `[bracket placeholders]` (e.g. `[Project]`, `[Client]`, `[Owner]`), literal `YYYY-MM-DD` in a `last_updated`/`last_updated_by` field, and `# [Project] OS` in the root `AGENTS.md`.

**Exclude:** `TEMPLATE.md` files (their placeholders are intentional) and prose that *names* a placeholder as an instruction (e.g. "run `/onboard` to replace `[Project]`").

**Report:** each file still carrying template placeholders or `sample: true` — this usually means `/onboard` hasn't finished, or a file was hand-copied instead of scaffolded with `/new-decision` / `/new-meeting`.

**Fix:** flag for review, and suggest running `/onboard` (if broad) or filling the specific fields. Never invent the values.

## Output

### Summary format

```
## Workspace Health Report — {date}

**{N} issues found** ({X} auto-fixable, {Y} need review)

### Broken links ({count})
- `{source}:{line}` → `{dead_target}` — {suggestion}

### README drift ({count})
- `{readme}` — {file} listed but missing / exists but unlisted

### Orphaned files ({count})
- `{file}` → should be in `{correct_location}`

### Dashboard snapshot ({count})
- `overview.html` — {field} out of sync with `{frontmatter file}`

### Decisions & meetings index ({count})
- `{index}` — {file} listed but missing / exists but unlisted / numbering gap

### Navigation paths ({count})
- `AGENTS.md` row "{task}" → `{path}` — {issue}

### Adapter drift ({count})
- `{adapter}` — {issue}

### Frontmatter & type ({count})
- `{file}` — missing frontmatter / missing `type` / non-snake_case key `{key}`

### Template placeholders ({count})
- `{file}` — still carries `[placeholder]`
```

If running in `fix` mode, show what was changed after each section.

## When to run

- Before any client presentation or delivery
- After large restructuring sessions
- Weekly, as the routine structural tidy
