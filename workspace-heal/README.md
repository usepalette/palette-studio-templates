# Workspace Heal

Find the small structural problems that make a workspace harder for people and
agents to trust.

Workspace Heal checks the workspace against its own instructions, reports what
has drifted, and can repair safe issues when you ask. It does not impose a
particular folder structure, and it also works when no instructions exist yet.

## What it checks

- Broken relative links in Markdown files
- README and index entries that no longer match the files on disk
- Files that appear misplaced or disconnected from the workspace map
- References to missing instructions, workflows, or folders
- Incomplete setup placeholders
- Generated files that may need to be rebuilt
- Agent instructions and adapter files that have drifted apart
- Frontmatter and naming conventions, when the workspace defines them

Checks that depend on a local convention only run when the workspace actually
declares that convention.

## No setup required

If the workspace has a README, agent instructions, or another clear guide,
Workspace Heal uses those as the standard. If it has none, the workflow says so
and falls back to neutral checks such as broken references, stale paths, active
setup markers, and conflicting instructions.

A missing README is not automatically a problem. For a larger or harder-to-use
workspace, the report may include a separate **Foundations to consider**
section with lightweight recommendations:

- A root README that explains what the workspace is and where to start
- A folder README for a substantial area that is hard to navigate
- One source of truth for recurring agent instructions
- A note identifying the source and rebuild command for generated files
- Clear ownership of plans or status when several files appear to overlap

These are suggestions, not health failures. The workflow does not recommend
extra documentation for a small, self-explanatory workspace.

## Report first, fix when asked

Ask Workspace Heal to check the folder for a read-only health report. Findings
are grouped by impact, with exact file paths and a clear split between safe
fixes and items that need review. The report also states whether workspace
guidance was found, partial, or absent, plus what was scanned, what was
excluded, and whether the review was complete.

Ask it to fix safe structural issues when you want conservative repairs. The
workflow rechecks its work afterward and asks before any move, rename,
deletion, or content decision. Foundation recommendations are never created
automatically.

## How it works

The workflow starts by reading whatever guidance the workspace already uses,
including README files, agent instructions, documentation indexes, or
equivalent project guidance. Those rules determine which checks apply and what
a healthy workspace looks like.

It ignores dependency folders, build output, version-control internals, and
other generated noise unless the workspace says they matter. External links
are not checked by default.

## After setup

Ask naturally:

- "Check this workspace's health."
- "Find broken links and stale indexes."
- "Fix the safe structural issues."
- "Why is this folder hard for agents to navigate?"

The workflow starts in read-only mode. It does not change workspace content
unless you explicitly ask it to fix safe issues.
