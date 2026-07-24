---
name: workspace-heal
description: Audit a workspace for structural drift and optionally repair safe issues. Use when the user invokes /workspace-heal, asks to check workspace health, find broken links, clean up folder structure, verify indexes or agent instructions, finish setup, or diagnose why a workspace is hard to navigate. Default to a read-only report; use fix mode only when the user explicitly asks to fix or repair.
---

# Workspace Heal

Audit the current workspace against its own rules. Report first by default.
Repair conservative, structural issues only in fix mode.

## Choose the mode

- `/workspace-heal` or a request to check, audit, inspect, or diagnose:
  **report mode**. Do not edit files.
- `/workspace-heal fix` or an explicit request to fix, repair, clean up, or
  apply the findings: **fix mode**.
- If the request is ambiguous, use report mode.

## 1. Learn what healthy means here

Before running checks:

1. Find and read the workspace guidance that exists, starting with the root
   `AGENTS.md`, README, and any equivalent instruction files.
2. Before inspecting a nested folder, check for local instructions that apply
   there.
3. Note the workspace's declared conventions for navigation, naming,
   frontmatter, ownership, generated files, commands, skills, and external
   task trackers.
4. Inspect existing examples before deciding that something is missing or
   malformed.
5. Classify the guidance basis:
   - **Found**: clear workspace guidance covers the area being audited.
   - **Partial**: some useful guidance exists, but it does not cover the
     relevant area or applicable instructions conflict.
   - **None**: no usable guidance exists for the area being audited.

Missing a specifically named file does not make guidance partial or absent.
A workspace may use `CONTRIBUTING.md`, a docs index, tool configuration, or
another clear source instead of README or `AGENTS.md`.

The workspace's rules are the standard. Do not introduce a fixed folder model,
a four-file model, frontmatter, pointer files, or any other convention unless
this workspace already requires it.

If instructions conflict, follow the most specific applicable instruction and
surface the conflict in the report.

When guidance is partial or absent, use the neutral baseline below. A small,
single-purpose workspace may be healthy without any additional documentation.

## 2. Set the audit scope

Audit the current workspace unless the user names a narrower folder.

Skip `.git`, dependency folders, caches, build output, and generated artifacts
that the workspace does not treat as source. Treat archives according to local
rules. Do not follow links outside the workspace unless the user included those
locations in scope.

Use ignore files and project configuration as scope evidence when they exist.
Do not mistake ignored or generated content for workspace source.

Record the intended scope and material exclusions before reporting. If the
workspace is too large to inspect completely, access is limited, or a check
could not run, do not imply full coverage. Mark the review partial and name the
unscanned areas or skipped checks.

## 3. Apply the neutral baseline

These checks do not depend on a particular workspace model and may run even
when no guidance exists:

- Broken local links and missing targets explicitly referenced by workspace
  documents or instructions.
- Stale paths left behind by confirmed moves or renames.
- Unfinished setup markers that are clearly active, not examples, fixtures, or
  runtime template syntax.
- Conflicting instructions that would make the same task behave differently.
- Generated or dependency noise that is being mistaken for source.

Only report what can be supported by evidence in the workspace. Without local
rules, do not call a file misplaced, a name wrong, an index stale, or metadata
missing.

## 4. Run the convention-based checks

Run applicable checks from this list:

### Links and navigation

- Find broken relative Markdown links to files, folders, and local anchors.
- Ignore web URLs, email links, intentional examples, unresolved runtime
  templates, and links inside code examples.
- Decode URL-encoded local paths before deciding that a target is missing.
- Verify that paths named in README and agent-instruction files exist.
- Flag important documents that are hard to reach from the workspace's normal
  navigation, but only when the workspace expects an index or folder map.

### Index and folder drift

- Compare README or index listings with the files on disk.
- Only require every file to be listed when the index presents itself as
  exhaustive.
- Find renamed or moved files that left stale references behind.
- Flag files that appear misplaced according to explicit local rules. Do not
  invent a better folder structure based on preference alone.
- Never create empty files merely to satisfy an index.

### Setup and templates

- Find setup checklists or placeholders that appear unfinished.
- Distinguish real unresolved placeholders from examples and runtime template
  syntax.
- Check that template instructions point to files that actually ship.
- Do not fill in company facts, owners, dates, status, or other meaningful
  content by guessing.

### Instructions and agent adapters

- Check instruction files for references to missing paths or obsolete names.
- If the workspace uses canonical agent resources plus thin host adapters,
  compare the two sides and flag missing or stale adapters.
- If the workspace declares required pointer files for multiple agents, verify
  that those pointers exist and defer to the declared source of truth.
- Do not require a particular agent vendor or duplicate full instructions into
  pointer files.

### Metadata and naming

- Check frontmatter, required fields, type values, file names, dates, and
  attribution only when local guidance defines those conventions.
- Respect edit policies and ownership rules.
- Do not change business status, ownership, authorship, or historical dates as
  a structural fix.

### Generated and tracked state

- Identify generated files that are stale relative to their sources when the
  workspace documents how they are generated.
- In report mode, identify the documented sync command without running it. In
  fix mode, inspect the command definition and expected outputs before running
  it. Use the command instead of hand-editing generated output only when its
  effects are understood and limited to the approved scope.
- Treat a generator or sync command as a review item when it may install
  dependencies, contact an external system, deploy or publish, alter data
  outside the workspace, or rewrite a broad area. Show the exact command and
  likely effects, then get the user's approval before running it.
- Check status boards, registries, or task references only against declared
  sources of truth.
- If an external tracker is authoritative, flag duplicate local roadmaps or
  task lists for review rather than deleting them.

Do not validate external URLs by default. Offer that as a separate check when
it would be useful.

## 5. Suggest foundations when they would help

When guidance is partial or absent, look for concrete navigation or maintenance
problems that a lightweight foundation could solve. Put these in a separate
**Foundations to consider** section. They are recommendations, not health
failures.

Use these recommendation rules:

- **Root README**: recommend one when the workspace has several meaningful
  areas, setup steps, or recurring workflows but no clear starting point. A
  useful README should briefly explain what the workspace is, where to start,
  what the main areas contain, and any essential setup or source-of-truth
  links.
- **Folder README or index**: recommend one only for a substantial, shared, or
  non-obvious folder whose contents are hard to navigate. Do not recommend a
  README for every folder.
- **Agent guidance**: recommend a canonical instruction file when the workspace
  is used with agents and important recurring rules are missing or scattered.
  Do not require the file to be named `AGENTS.md`, and do not require
  vendor-specific pointer files.
- **Source-of-truth note**: recommend documenting which file or external system
  wins when several places appear to track the same plan, status, or record.
- **Generated-file guidance**: recommend naming the source and rebuild command
  when generated output exists but people or agents cannot tell how to update
  it safely.
- **Ignore rules**: recommend an appropriate ignore file when dependency,
  cache, or build output repeatedly obscures the source workspace.
- **Naming or metadata guidance**: recommend documenting a convention only when
  inconsistent existing patterns are already causing ambiguity. Do not
  standardize for its own sake.

Do not recommend frontmatter, logs, lessons files, agent pointers, or a folder
taxonomy by default. Do not recommend documentation for an intentionally tiny
or self-explanatory workspace.

Recommendations are never auto-fixable. Offer a short outline or draft, but do
not create the file until the user approves the file and its intended scope.
For each recommendation, cite the observed navigation or maintenance problem,
explain the benefit, and give a short proposed outline so the user can make a
real choice.

## 6. Report the findings

Start with a one-line health summary. Then state:

- `Scope: [workspace or folder inspected]`
- `Excluded: [material exclusions, or none]`
- `Coverage: complete` or `Coverage: partial; [what was not checked and why]`

State the guidance basis:

- `Workspace guidance: found`
- `Workspace guidance: partial`
- `Workspace guidance: none; neutral baseline used`

Then group confirmed health findings as:

1. **Blocking**: navigation or instructions are broken enough to stop normal
   work.
2. **Important**: the workspace is usable, but drift could mislead people or
   agents.
3. **Tidy**: low-risk cleanup and consistency improvements.

For every finding, include:

- the exact path and line when available;
- what is wrong;
- which local rule, observed convention, or objective broken reference makes
  it a problem;
- whether it is safely auto-fixable or needs review;
- the smallest sensible fix.

After the findings, include **Foundations to consider** only when a
recommendation passes the rules above. Keep recommendations separate from
Blocking, Important, and Tidy.

End with separate counts for findings, safe fixes, review items, and optional
recommendations. If the workspace is healthy, say what was checked instead of
inventing improvements.

## 7. Fix safely

In fix mode:

1. Briefly state the repairs you will make.
2. Apply small, reversible, mechanical fixes such as correcting a confirmed
   relative path, updating an exhaustive listing, repairing a thin adapter, or
   running a confirmed local-only generator.
3. Ask before moving, renaming, deleting, overwriting, or materially rewriting
   files, unless the user already approved that exact action.
4. Preserve user work and unrelated changes.
5. Follow local requirements for edit dates and attribution.
6. Re-run the affected checks and report what remains.
7. Keep foundation recommendations out of the automatic fix set. If the user
   wants one, propose its contents and get approval before creating it.

Never delete content, fabricate missing facts, create stubs, or broaden the
workspace's rules just to produce a clean report.

Never treat a command with unknown, external, or broad side effects as a safe
automatic fix.
