---
type: command
description: Audit Product OS for broken links, stale indexes, adapter drift, and unfinished setup
argument-hint: "[report|fix]"
---

# Workspace heal

Default to `report`. In `fix` mode, apply only safe structural repairs after showing the proposed
changes. Never invent product content.

## Checks

### 1. Links

Verify every relative markdown link, including directory links. Report source file, line, and dead
target.

### 2. README listings

Check explicit folder maps, rosters, and tracked lists against real files. Ignore standard
furniture unless the README explicitly lists it.

### 3. Frontmatter

Flag content markdown without frontmatter or without `type`. Folder READMEs and substantial
standalone documents should carry `type`, `owner`, `status`, `last_updated`, `last_updated_by`,
and `edit_policy`. Small leaf files need `type` plus the fields defined by their document class.
Exclude `AGENTS.md`, vendor pointers, `.agents/`, `.claude/`, `.vibe/`, `_scaffold/`, and
intentionally simple adapter files. While setup is incomplete, allow the starter root README and
`SETUP.md` to use their minimal setup frontmatter.

Check that `owner` identifies the responsible person, team, or role and `last_updated_by`
identifies the current human who made the change. Do not infer that they must match and do not
auto-fix attribution.

### 4. Product evidence

- Every feature request and painpoint has valid `source_files`.
- Every company-profile link resolves.
- One-source recurring painpoints are explicitly justified or flagged for review.
- Specs with sources link to real files.

Do not auto-fix evidence or scores.

### 5. Dashboard

- The data markers in `user-feedback/index.html` exist exactly once.
- Every source markdown file appears in the generated data.
- No generated item points to a missing file.
- The embedded data parses as JSON after HTML-safe escaping.
- The serialized data contains no literal `<`, `>`, or `&`; these must be encoded as Unicode
  escapes so user-provided text cannot close the data script.
- Local source links stay inside the four feedback-data folders, and external source links use
  HTTP(S).
- Search and filter controls have accessible names.

### 6. Navigation

Verify each path in the root README and AGENTS "Where things live" table.

### 7. Agent parity

- Root `CLAUDE.md`, `GEMINI.md`, and `.vibe/AGENTS.md` point to the root `AGENTS.md`.
- Every `.agents/commands/*.md` has a matching `.claude/commands/*.md`.
- Every `.agents/skills/*.md` has a matching `.claude/skills/*.md`.
- Adapters point to `../../.agents/...` and carry matching registration frontmatter.

### 8. Setup and placeholders

Search for `[bracket placeholders]` and literal `YYYY-MM-DD` only in living files that setup is
expected to fill. Cross-check with `SETUP.md`.

Ignore intentional placeholders in:

- Any `_template/` directory
- Files named `_template.md` or ending `-template.md`
- Fenced code examples and instructional HTML comments
- Inline code and lines that document a filename or date format
- `.agents/`, `.claude/`, `.vibe/`, and `_scaffold/`
- The root README onboarding skeleton and dashboard code

An optional integration recorded as `not used` is complete, not a setup failure.

### 9. Roadmap duplication

Flag markdown files that appear to recreate a task board, project backlog, or delivery status
table instead of linking to the issue tracker.

### 10. Data boundaries

Flag likely secrets, credentials, unnecessary private personal details, restricted raw exports,
or customer material copied without a usable source or access rationale. Do not print suspected
secret values in the report. Recommend linking to the access-controlled source or anonymizing the
local record.

## Output

Group findings by:

- Blocking
- Important
- Tidy

For each finding include the file, problem, and recommended action. In fix mode, list every file
changed and every issue left for human judgment.
