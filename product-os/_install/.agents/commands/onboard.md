---
type: command
description: Set up Product OS from connected context, existing documents, or one short conversation
---

# Onboard

Turn the blank Product OS template into the user's living product workspace.

## 1. Check current setup

- Read `SETUP.md`, the root README, `AGENTS.md`, `lessons.md`, and
  `documentation/product-overview.md`.
- Check unresolved placeholders only in living content that setup is expected to fill.
- Do not overwrite real content from a partial setup.

Treat these as protected reusable material, not incomplete setup:

- Any path inside a `_template/` folder
- Files named `_template.md` or ending `-template.md`
- Fenced code examples and instructional HTML comments
- Inline code and lines that document a filename or date format, such as `YYYY-MM-DD-slug.md`
- `.agents/`, `.claude/`, `.vibe/`, and `_scaffold/`
- The feedback dashboard's HTML, CSS, JavaScript, and seed-data shape

Never replace placeholders inside protected material.

## 2. Load existing context first

Load the `prefill-context` skill and work in this order:

1. Live context connector
2. Documents in `_inbox/` or paths the user named
3. Exported context from another AI or product tool
4. One short conversational round

Use only sources that are available and authorized. Skip unavailable source types without treating
them as setup failures.

Gather only what exists or is useful:

- Workspace scope: one product, a product area, a platform, or a coherent portfolio
- Scope name, one-line description, current capabilities, users, and core workflows
- Current human performing setup
- Default workspace steward: a person, team, or role; this may differ by folder
- Teammates, if profiles would be useful
- Current product direction, without copying task status
- Issue tracker and analytics links, if those systems are used
- Feedback and research sources
- Existing feedback, discovery, strategy, specs, and competitors worth importing

Ask which Product OS modules fit the team's work. Keep the default structure unless the user asks
to customize it; empty modules are harmless and can be used later. Record unavailable facts as
`unknown`, optional systems as `not used`, and manual capture as a valid feedback source. Never
fabricate.

## 3. Propose the setup

Before writing, show:

- Workspace scope, description, and users you will use
- Current human whose name will be used for attribution
- Default steward and any folder-specific ownership
- Team profiles you will create
- Files you will fill or import
- Live systems you will link
- Optional systems or modules that will be recorded as `not used` or left available for later
- Remaining unknowns that will be written plainly as `unknown`

Ask for one confirmation.

## 4. Write the workspace

After confirmation:

1. Replace the root README landing page with its "After setup" living-index block **only when it is
   still the untouched starter**. On a partial setup the README may already carry real workspace
   context — in that case update just the starter/setup block and leave everything else intact.
   Never overwrite content a human has written.
2. Fill `documentation/product-overview.md`.
3. Fill ownership, dates, and attribution only in living workspace files: `lessons.md`, `log.md`,
   folder READMEs, the root README, and `documentation/product-overview.md`.
   - Fill `owner` with the confirmed steward for that scope: a person, team, or role.
   - Fill `last_updated_by` with the current human performing setup.
   - Do not assume the owner and current human are the same.
   - Preserve every placeholder in the protected reusable material listed in step 1.
4. Add each teammate through `/new-person`.
5. File imported material into the narrowest matching folder. Preserve source links.
6. When an issue tracker exists, keep initiatives, projects, tasks, status, and dates there. Link
   them from the relevant Product OS file instead of copying the roadmap. When there is no tracker,
   record `not used`.
7. If real feedback is available, capture it through `/feedback`.
8. Run `/feedback-sync` if feedback was added.

## 5. Close setup

- Tick completed items in `SETUP.md`.
- Run `/workspace-heal report`.
- Resolve setup-related broken links, adapter drift, or placeholders in living content. Do not
  "fix" intentional placeholders in protected templates or examples.
- When every item is complete, set `Status: COMPLETE` and offer to delete `SETUP.md`.

Tell the user what was filled, what remains unknown, and the next useful command:
`/feedback`, `/synthesize-feedback`, `/spec`, or `/review`.
