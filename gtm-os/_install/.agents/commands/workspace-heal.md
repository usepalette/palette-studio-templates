---
type: command
description: Audit workspace structure for broken references, stale indexes, and misplaced files
argument-hint: "[fix|report]"
---

# Workspace Heal

Structural health check for this GTM OS workspace. Finds broken internal links, stale README listings, orphaned files, index/board drift, adapter drift, and missing frontmatter — across the root and every folder (`foundations/`, `work/`, `accounts/`, `playbooks/`, `templates/`, `team/`, `log/`). Run with `fix` to auto-repair, or `report` to just list issues.

Default: `report` (no changes made).

## Trigger

User runs `/workspace-heal` (report only) or `/workspace-heal fix` (report + fix).

## Checks

Run every check below. Collect all issues, then present a summary grouped by severity.

### 1. Broken internal links

Scan all `.md` files for markdown links (`[text](path)`) where the target is a relative path. Verify each target exists on disk.

**Exclude:** URLs (http/https), anchor links (#), and template placeholders like `[name]` or `$VAR`.

**Report:** Each broken link with source file, line, and the dead target path. **Fix:** Flag for manual review.

### 2. README file listings vs reality

For each README.md that contains a file/folder listing, verify every listed file exists in that directory. Also check the reverse: files that exist but aren't mentioned (when the README looks like an exhaustive listing).

**Exclude (standard furniture):** `README.md`, `CLAUDE.md` / `GEMINI.md`, `lessons.md`, `log.md` — never flag them as "exists but unlisted." (`.vibe/AGENTS.md` is the root-only Mistral pointer — also never flag it.)

**Key READMEs to check:** the root `README.md` structure tree; the root `AGENTS.md` "Where things live" table; each folder's front-door README (`foundations/README.md`, `work/README.md`, `accounts/README.md`, `playbooks/README.md`, `templates/README.md`, `team/README.md`); the command & skill indexes `.agents/commands/README.md` and `.agents/skills/README.md`; and any subfolder README with an explicit listing (e.g. `foundations/*/README.md`, `templates/launch/README.md`).

**Report:** each mismatch — "listed but missing" or "exists but unlisted." **Fix:** update the listing to match reality. Never create stub files.

### 3. Orphaned files

Check for files clearly in the wrong location:
- A dated recap (`YYYY-MM-DD-*.md`) sitting loose outside `log/sessions/`.
- Files in root that should be in a subfolder.

**Report:** each orphaned file with a suggested location. **Fix:** list the exact `from → to` for every move and get confirmation before touching anything. "Orphaned" is a heuristic — a file that looks misplaced may be deliberate.

### 4. Work index freshness

Where a folder maintains an index (e.g. `work/projects/README.md`, `work/campaigns/README.md`): verify each listed item's folder still exists, flag stale "last active" dates, and flag folders not in the index.

**Report:** stale dates, missing items, deleted items still listed. **Fix:** update the index.

### 5. Account status board consistency

For each row in `accounts/status.md`: verify the account folder exists in `accounts/`; flag rows whose "Updated" date is stale (>30 days) but still look active.

**Report:** stale rows, missing folders, inconsistent statuses. **Fix:** flag for manual review — account status needs human judgment.

### 6. AGENTS.md navigation paths

For each row in the root `AGENTS.md` "Where things live" table, verify the referenced folder exists.

**Report:** any dead paths. **Fix:** update paths or flag for review.

### 7. Agent adapter parity

Check the canonical + adapter split (`/.agents/` ↔ `/.claude/`):
- Every `.agents/commands/*.md` has a matching `.claude/commands/*.md` adapter; every `.agents/skills/*.md` has a matching `.claude/skills/*.md` adapter.
- Each `.claude/` adapter points to its canonical file with `../../.agents/{commands|skills}/{filename}`.
- If the canonical file has YAML frontmatter, the adapter carries the same frontmatter.

**Report:** missing/extra/mismatched adapters or stale adapter frontmatter. **Fix:** creating or rewriting an adapter is a content write — show the exact file and the frontmatter/body you'd write, and confirm before applying. Only the deterministic, reversible part (copying the canonical frontmatter verbatim and pointing the body at the canonical file) is eligible for automatic repair; anything ambiguous stays a report-only suggestion.

### 8. Frontmatter & `type` coverage

Every content `.md` should carry frontmatter with a `type` (root `AGENTS.md` → Conventions).
- Flag content `.md` files with **no frontmatter** or **no `type:`**.
- Flag frontmatter keys that aren't `snake_case` — the one allowed exception is `argument-hint` (a Claude Code harness key).

**Exclude:** agent/behaviour files (`AGENTS.md`, `CLAUDE.md` / `GEMINI.md` / `.vibe/AGENTS.md`), `_template/` files, and generated viewers.

**Report:** files missing frontmatter or `type`; non-snake_case keys. **Fix:** add `type` (infer from folder); rename keys to snake_case. Never touch `argument-hint`.

### 9. Leftover template placeholders (is setup finished?)

This OS started from a template. Scan for un-filled `[bracket placeholders]` (e.g. `[Company]`, `[Company Name]`, `[Owner]`), literal `YYYY-MM-DD` in a `last_updated`/`last_updated_by` field, and `# [Company] GTM OS` in the root README.

**Exclude:** `_template/` folders (their placeholders are intentional) and prose that *names* a placeholder as an instruction (e.g. "run `/onboard` to replace `[Company]`").

**Report:** each file still carrying template placeholders — usually means `/onboard` hasn't finished, or a folder was hand-copied instead of scaffolded with `/new-account` / `/new-person`. **Fix:** flag for review, suggest `/onboard` (if broad) or filling the specific fields. Never invent values.

## Output

```
## Workspace Health Report — {date}

**{N} issues found** ({X} auto-fixable, {Y} need review)

### Broken links ({count})
- `{source}:{line}` → `{dead_target}` — {suggestion}

### README drift ({count})
- `{readme}` — {file} listed but missing / exists but unlisted

### Orphaned files ({count})
- `{file}` → should be in `{correct_location}`

### Work index ({count})
- `{item}` — {issue}

### Account status board ({count})
- `{account}` — {issue}

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

- Before any presentation or delivery
- After large restructuring sessions
- Weekly, as the routine structural tidy
