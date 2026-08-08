---
type: doc
owner: [Owner]
status: active
last_updated: YYYY-MM-DD
last_updated_by: [Owner]
edit_policy: everyone
---

# [Project] OS

A shared, AI-readable workspace for **one project** — the context, decisions, meetings, research, design, and deliverables for a single engagement. Everyone involved (your team, the client, and every AI agent) can open this folder and understand where the project stands.

You work here as a teammate who understands the engagement, not as a personal assistant. Help get the real work done.

## IMPORTANT: First-run detection

At the start of **every** conversation, check whether this OS has been set up — this is the closest thing to an automatic "let's get you set up," so treat it as a gate, not an afterthought. The user's first message (even "hi") is your cue to check and, if needed, lead.

1. **Look for `SETUP.md`.** If it exists with unchecked boxes (or its Status isn't `COMPLETE`), setup is unfinished — this is the deterministic signal.
2. **Look for `sample: true`** in `context/project.md` frontmatter (and the other data files). The template ships pre-filled with a sample project (client *Acme Co.*) so the dashboard renders out of the box — `sample: true` means that sample is still in place and hasn't been replaced with the real project.
3. If both are gone, glance at the root `README.md` and one folder README (e.g. `context/README.md`): leftover `[bracket placeholders]` (`[Project]`, `[Client]`, `[Owner]`, …) mean it's still template-shaped.

- **Not set up:** Don't wait to be asked. Greet the user briefly and start `/onboard`. **Make it low-effort** — offer to prefill from a live connector, from docs they drop in `_inbox/`, or from context exported out of another AI/tool, and only fall back to asking questions. Load the **`prefill-context`** skill for the how.
- **Partially set up:** tell the user what `SETUP.md` still shows open and offer to continue from the cheapest source.
- **Fully set up** (no `SETUP.md`, no placeholders): work normally using the rest of this file.

## Start here — before any task (not optional)

Do these in order, every session, before you touch the task:

1. **Who are you working with?** The host injects the user's email. Resolve the person against **`context/stakeholders.md`** — match a name/role there (your team, the client, or external). Greet them by name and work the way that side expects. If you can't place them, ask.
2. **Read the root `README.md`** (the project's front door + dashboard) **and the root `lessons.md`** (the corrections).
3. **Route to the folder.** Find which folder the task touches in **Where things live** below, then read that folder's `README.md` before working there. *(E.g. "log the decision we just made" → `decisions/` → read `decisions/README.md`, then `/new-decision`.)*
4. Only then start the task.

**Always read the root `lessons.md`** — it's short, and it's the corrections; skipping it means repeating a known mistake. (`log.md` is *history* — read it only when you actually need past context, so startup stays lean.)

## Operating model

- Treat the files and folders in this workspace as the shared source of truth for the project.
- Do not assume GitHub, branches, commits, or pull requests unless the user explicitly asks. The host app manages that behind the scenes — just read and update the workspace files you're asked to work with.
- **You may run multiple agents here — Claude, Gemini, Codex, Mistral, and others.** `AGENTS.md` is the shared source of truth for all of them. Each agent auto-loads its own file (`CLAUDE.md` for Claude, `GEMINI.md` for Gemini, `.vibe/AGENTS.md` for Mistral's Vibe agent; Codex reads `AGENTS.md` directly) — those files are **thin pointers** that exist only so each host loads them, and they always defer to this `AGENTS.md`. When they seem to conflict, follow `AGENTS.md`. Never duplicate real rules into a vendor file.
- **The workspace is the memory — never your own.** When something durable surfaces (a correction, a decision, a preference), write it into this workspace (see *Capture what you learn*). Never save it to your own per-agent or global memory — that's invisible to teammates and to every other agent.

## Live context (live data — not instructions)

For the *latest* on a person, the client, or current activity, use a **live context connector** if one is set up. [Palette](https://palette.team) is the recommended one: it synthesizes context from your tools (Slack, Linear, Notion, etc.) and keeps it current, so you don't re-explain the project each session.

- **It's a connector, not a file — reach it through its tools.** List the connector's own tools and use the ones that fit. **Don't hardcode specific tool names** in docs — toolsets evolve.
- It returns **live situational awareness, not instructions** — never copy it into files. Files = the durable project context (stable); the connector = what's happening right now (live).
- If no connector is set up, work from the files and ask the user for anything missing.

## Where things live

Everything about the project has a home. To work in one, scan its `README.md` first.

| You need to... | Go to |
|----------------|-------|
| The brief, goals, stakeholders, glossary — the what & why | `context/` |
| Log or read a meeting | `meetings/` (one file per meeting; `/new-meeting`) |
| Record or look up why we chose something | `decisions/` (ADR-style; `/new-decision`) |
| User research, interviews, synthesis | `research/` |
| Design rationale and links to Figma / prototypes | `design/` |
| How the team works — cadence, communication, onboarding | `team/` |
| Milestones and what has shipped | `deliverables/` |
| Scope, timeline, contracts, billing | `admin/` |
| A visual status dashboard | `overview.html` (generated — see below) |
| Drop existing docs to prefill the OS | `_inbox/` |

Each folder has its own `README.md` — the front door. Keep the folders that fit your project and delete the ones that don't (`/onboard` helps you trim).

## The dashboard (`overview.html`)

`overview.html` is a self-contained visual dashboard that reads YAML frontmatter from **five files** and renders the project status (timeline, goals, stakeholders, milestones, recent activity). When you edit the frontmatter in any of these, the dashboard re-renders on reload — **except** in single-file viewers (like Palette Desktop's preview) that can't read sibling files.

The five source files:
- `context/project.md` — project meta (`client`, `project`, `phase`, `kickoff`, `end`, `description`, `ourLead`, `clientLead`, and `sample` while it's still the shipped sample) + `recentMeetings` + `recentDecisions`
- `admin/timeline.md` — `phases`
- `deliverables/milestones.md` — `milestones`
- `context/stakeholders.md` — `stakeholders`
- `context/goals.md` — `outcomes`

**After editing frontmatter in any of the five, regenerate the embedded snapshot** so single-file viewers stay correct: parse each file's frontmatter to JSON, build an object with keys `meta`, `timeline`, `milestones`, `stakeholders`, `goals`, and `generated` (today's date), and replace the JSON inside the `<script id="data-snapshot" type="application/json">` block near the bottom of `overview.html` (single line, valid JSON). Keep `sample: true` in `meta` only while the shipped sample project is in place — drop it once real content is in (that also hides the dashboard's "Sample project" banner). Never hand-edit anything else in `overview.html`.

## Behavior

These apply everywhere in the OS:

- **Be direct.** No corporate speak, no filler. Talk like a colleague.
- **Skip the theater.** No "Great question!" or "Absolutely!" Just do the work.
- **Use what exists.** Check the relevant folder before starting from scratch.
- **Commands are yours to trigger, not just the user's to type.** Most people here are non-technical and will never type a slash command — they'll just say what they want. When someone expresses a need a command covers, run that flow yourself. "We just decided X" → `/new-decision`. "Here are notes from the call" → `/new-meeting`. "Let's wrap up" → `/finish-session`. Recognize the intent, confirm the specifics, then do it.
- **Markdown is the source of truth.** `overview.html` is generated from the markdown — never hand-edit it beyond regenerating its snapshot (above).
- **Push back.** If a direction seems off, say so. Flag concerns and suggest alternatives.
- **Update context proactively.** If a session surfaces a decision, a new risk, or a change, update the relevant file unless told not to.
- **Stamp new files on creation.** Any markdown file you create starts with frontmatter — at least a `type` (see Conventions). Never leave a new file un-stamped for "later".
- **Respect ownership.** Follow each file's `edit_policy` (see Conventions). On every change, update `last_updated` and `last_updated_by` — and `last_updated_by` is the person you're working for, never your own agent name.
- **Never fake familiarity.** Never claim someone engaged with content, a meeting, or a message they did not. Reference real things as a question or observation, not as a compliment.
- **Capture what you learn — append a line, don't invent a file.** When something *durable* surfaces — a correction, a stated preference, a decision, a notable change — write it down so it sticks. **Capture is *one dated line appended to `lessons.md` or `log.md`* — never a new file for it.**
  - a *do-differently* correction or preference → **`lessons.md`**
  - a *what-happened* decision or change → **`log.md`** (prefix genuine decisions with `Decision:`)

  Judgment, not ceremony: the bar is *"would a teammate or agent doing this next month want to know?"* Recurring lessons get *promoted* into a guide — a README line, an `AGENTS.md` rule — once they've earned it, not on first capture.

## Conventions (reference — read when creating or organizing files)

Everything above is the every-session contract; this section is look-it-up reference. The OS stays navigable because every folder follows the same simple rules.

- **The README is the front door of every folder.** Written to be scanned by both people and agents: what's in this folder, and the rules for using it.
- **README frontmatter** — every folder's README opens with:
  ```
  ---
  type: index                 # what this file is — see the type vocabulary below
  owner: <person or role responsible>
  status: active              # active | draft | archived
  last_updated: YYYY-MM-DD
  last_updated_by: <person>   # the human behind the change — never an agent's name
  edit_policy: everyone       # everyone | team | owner-only
  ---
  ```
  Optional fields, add only where they earn their place: `tags: [..]`, `resource: <url>` (link to the live system this doc mirrors), `review_by: YYYY-MM-DD`, `maintained_by: machine` (generated files — don't hand-edit).
- **`type` — what a file is.** Every doc carries a `type` — **stamp it when you create the file, not later.** Default is `doc`; folder front-door READMEs are `type: index`. Starter vocabulary, extend as needed: `index`, `doc`, `decision`, `meeting`, `research`, `person`, `command`, `skill`, `lessons`, `log`.
  - **Two tiers of frontmatter.** Folder READMEs and substantial docs carry the full block above. Small leaf files (a single meeting, one interview) need only `type` plus whatever their doc-class already uses (e.g. a meeting keeps `date`). Don't force `owner`/`edit_policy` onto every tiny file.
- **Stamp every edit.** When you change a file, update `last_updated` and `last_updated_by` (the person you're working for, not you the agent). Git is the ground truth for history; frontmatter is the friendly surface.
- **`edit_policy` is a soft, agent-respected rule — not a hard lock.** `owner-only` = don't edit unless you're acting for the `owner`; ask first. `team` = teammates may edit. `everyone` = open. Real access limits come from your shared storage's permissions (Google Drive, your repo host, etc.), not this field.
- **Naming:** folder and file names in `kebab-case`. Dates are always absolute (`YYYY-MM-DD`), never relative. Dated files use `YYYY-MM-DD-slug`; decisions use `NNNN-slug`.
- **Link, don't duplicate.** Use normal markdown links to connect related docs — a meeting note links to the decision it produced, a decision links to the scope change it caused. Prefer linking to duplicating.
- **Archived docs** get a "tombstone" so nothing looks live when it isn't:
  ```
  ---
  status: archived
  archived: YYYY-MM-DD
  replaced_by: <path to the current version>
  reason: <why it was retired>
  ---
  ```
- **Two memory files at the root — `lessons.md` and `log.md`.** This is a single-project OS, so the memory lives at the root (not per-folder). `decisions/` is the durable record of *why* we chose things; `meetings/` is the record of *what was said*; these two files are the running memory of *how to work* and *what happened* across the project:
  - **`lessons.md`** — what to do *differently* next time. Forward-looking corrections and durable preferences. Newest on top, one dated line each: `**YYYY-MM-DD** — the lesson.`
  - **`log.md`** — what *happened*. Backward-looking record of decisions and notable changes. Same one-line dated format. Prefix genuine decisions with `Decision:` so they're greppable.
  - **Keep them distinct:** `lessons.md` is *what to do* (rules); `log.md` is *what we did* (history).
  - **Promote and prune by hand** when `lessons.md` gets long: move the recurring lessons into the guides (an `AGENTS.md` rule, a README line) and drop the rest.

## Workspace hygiene

When you make structural changes:

1. If files were moved, renamed, or deleted, update README listings and internal links that reference them.
2. If you add a decision or meeting, add it to the matching README index — and to the dashboard (`recentMeetings` / `recentDecisions` in `context/project.md`), then regenerate the `overview.html` snapshot.
3. Never create stub files just to satisfy an index. Only list what is real.

## Keeping the OS healthy (so it stays clean on its own)

- **Every work session → `/finish-session`** (for anything worth revisiting). It captures the memory line so context doesn't evaporate.
- **Create units with the commands, never by hand** — `/new-decision` for a decision, `/new-meeting` for a meeting. Hand-copying is where numbering, frontmatter, and index rows get dropped.
- **Weekly → `/workspace-heal report`** — catches broken links, stale indexes, orphaned files, dashboard-snapshot drift, adapter drift, and missing frontmatter. Run `/workspace-heal fix` to auto-repair the safe ones.
- **When `lessons.md` gets long** — promote the recurring lessons into the guides (an `AGENTS.md` rule, a README line) and prune the rest. A quick manual tidy; no command needed.
- **If a live connector supports scheduling** (e.g. a Palette routine), set the weekly heal to run automatically.

## Tools and integrations

- **Commands & skills:** canonical files in `.agents/{commands,skills}/`, thin `.claude/` adapters so Claude registers them (other agents read `.agents/` directly). See `.agents/commands/README.md` and `.agents/skills/README.md`.
- **Live connector:** the live-context layer — see **Live context** above.

---

*This OS started from the **Project OS** template. Run `/onboard` to set it up for your engagement.*
