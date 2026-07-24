---
description: Scaffold a new top-level space folder to the OS conventions and register it
argument-hint: "<space-name>"
---

# Create Space

Scaffold a new **space** — a top-level area of the OS (like `accounts/`, `gtm/`, `product/`) — to the exact conventions in the root `AGENTS.md`, then register it so nothing dangles. Use this when a team needs its own area and hand-copying the furniture would drift from the conventions.

This is the make-a-space companion to the structure family: **`/create-space`** (make) → **`/workspace-heal`** (audit links, listings, adapter parity, frontmatter) → **`/reflect`** (tidy the memory files, promote lessons).

## Trigger

User runs `/create-space marketing`, `/create-space design`, or bare `/create-space` (then you ask for the name).

## Inputs

Gather these — parse from the argument where you can, ask conversationally for the rest. Don't dump a form; ask a round at a time.

1. **Name / slug** (required) — the space name. Slug it: lowercase, spaces → hyphens, kebab-case (e.g. "Customer Success" → `customer-success`).
2. **Purpose** (required) — one line: what lives in this space and who works there.
3. **Owner** (required) — the person or role responsible (goes in frontmatter + the root Owners table).
4. **`edit_policy`** — default `team`. Use `owner-only` for sensitive/personal spaces (like `ops/`), `everyone` for open ones.
5. **Needs its own `AGENTS.md`?** — apply the test below. Default **no**.

### The `AGENTS.md` test (from root `AGENTS.md` → Conventions)

Only create a space `AGENTS.md` if the space has a **distinct mindset** — a way to think or act that differs from the root rules (e.g. `gtm/`'s brand voice + session modes, `ops/`'s discretion + approval flow). If the guidance is just "what's here + where things go + what to do when," that's a **README**, not an `AGENTS.md`. When unsure, skip it — it can be added later once a real local posture emerges.

## Process

### 1. Check it doesn't already exist

Look for a folder at `<slug>/` and a row in the root `README.md` Owners table. If it exists, stop and tell the user — offer to open its README instead of overwriting.

### 2. Show the plan, wait for confirmation

List the exact paths you're about to create and the two root files you'll edit. **Wait for the user to confirm before writing anything.** Respect `edit_policy` on the root files.

### 3. Create the space folder

Create `<slug>/` with this furniture. Use today's date (from session context) for `last_updated`, and the **person you're working for** for `last_updated_by` — never an agent name.

#### `<slug>/README.md` — the front door

```markdown
---
type: index
owner: {owner}
status: active
last_updated: {today}
last_updated_by: {person}
edit_policy: {edit_policy}
---

# {Space name}

{One-line purpose — what lives here and who works in it.}

## You need to...

| You need to... | Go to |
|----------------|-------|
| {common task in this space} | {subfolder or file} |

## Structure

```
{slug}/
├── README.md     # this front door
├── lessons.md    # what to do differently here (furniture)
└── log.md        # what happened here (furniture)
```

Add subfolders as real work arrives — each new folder gets its own `README.md`. Don't create empty stubs just to fill the tree.
```

Keep the routing table honest: seed it with one or two real rows if the user named concrete tasks, otherwise leave a single placeholder row and a note to fill it in.

#### `<slug>/lessons.md` and `<slug>/log.md` — standard furniture

Copy the shape from the root `lessons.md` / `log.md` (header + convention note), stamped `type: lessons` / `type: log`, `owner: {owner}`, `edit_policy` matching the space (memory files are usually `everyone`, but follow the space's policy for a sensitive space). Newest-on-top, one dated line each — start empty below the header.

### 4. Only if the space needs its own `AGENTS.md`

If step 5 of Inputs said yes, create `<slug>/AGENTS.md` — **no frontmatter**, opening `# {slug}`, a line linking the root `../AGENTS.md` ("company-wide rules live there; this layers on top; root always applies"), then the local behavioral rules and a nav table. Keep it lean and behavioral — routine placement belongs in the README.

Then create the three thin vendor pointers so every host loads the local rules. Use this exact adapter text (swap the header per agent):

```markdown
# Claude adapter

Read and follow `AGENTS.md` in this folder.

`AGENTS.md` is the source of truth for this workspace. If this file conflicts with `AGENTS.md`, `AGENTS.md` wins.

Do not duplicate shared instructions here.
```

Create `<slug>/CLAUDE.md` and `<slug>/GEMINI.md` (Codex reads `AGENTS.md` directly; Mistral's Vibe agent loads the root `.vibe/AGENTS.md`, so spaces don't get their own pointer). Never symlink; some file-sync layers break them.

### 5. Register the space

Two edits so the space is reachable and nothing dangles:

- **Root `README.md`** — add the space to the structure tree (the `## Structure` block) and a row to the **`## Owners`** table (`| \`{slug}/\` | {owner} |`).
- **Root `AGENTS.md`** — add a row to **The spaces** routing table (`| {when you need this space} | \`{slug}/\` |`).

Stamp `last_updated` / `last_updated_by` on both root files.

### 6. Confirm

Print a short summary:

```
Created space: {slug}/
  Files: README.md, lessons.md, log.md{, AGENTS.md + CLAUDE/GEMINI pointers}
  Registered in: README.md (Owners + tree), AGENTS.md (spaces table)
  Next: run /workspace-heal report to confirm it's wired correctly.
```

## Notes

- The furniture and frontmatter follow the root `AGENTS.md` → Conventions. If those conventions change, this command should track them.
- **Never create empty stub subfolders** just to look complete — only the README + `lessons.md` + `log.md` furniture up front; subfolders arrive with real work.
- Adding an `AGENTS.md` later is fine — start with a README and run `/create-space` guidance again, or add it by hand and create the three pointers.
- After creating, `/workspace-heal report` should pass: the new space has README + furniture, is listed in the root tables, and (if it has an `AGENTS.md`) the vendor pointers exist.
