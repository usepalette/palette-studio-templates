---
name: prefill-context
description: How to prefill the project OS from existing sources — a live connector, docs dropped in _inbox/, or context exported from another AI (Claude, ChatGPT, Gemini) or tool (Notion, Slack, Granola, a CRM). Use during /onboard or whenever setting up / backfilling the OS.
---

# Prefill context

The fastest way to fill this OS is not to type it — it's to pull from where the project's context already lives. Work the sources in this order (most leverage first); stop when you have enough, and always **propose → confirm → write**. Never fabricate; leave a placeholder where you genuinely don't know.

The target is a **project brief**: client, scope, stakeholders, timeline, decisions, and goals.

## 1. Live connector (best)

If a live-context connector is available (e.g. Palette, or any MCP that exposes project/people/work context), use it first:

- Ask the connector for the broadest project overview, then the client, then the people involved, then the current status.
- Map what it returns into the template: project + client → root `README.md` / `context/brief.md`; people → `context/stakeholders.md`; scope & timeline → `admin/scope.md` + `admin/timeline.md`; goals → `context/goals.md`.
- Confirm the important bits with the user rather than writing silently — the connector is a starting point, not gospel.

## 2. Dropped documents (`_inbox/`)

If the user has dropped files in `_inbox/` (or points you at any folder/files):

- Read everything. Common inputs: the brief, SOW / contract, proposal, kickoff deck or notes, project plan, org chart or contact list, meeting notes, transcripts.
- Extract: project one-liner, client name, scope (in / out), key deliverables, stakeholders + roles on both sides, timeline / milestones, goals, and any decisions already made.
- File each fact into the right folder (`context/`, `admin/`, `decisions/`, `meetings/`), using the scaffolding commands (`/new-decision`, `/new-meeting`) where they apply, not by hand.
- When done, tell the user what you filed and **clear `_inbox/`** (move originals into the folder they informed, or delete if fully absorbed).

## 3. Export from another AI (copy-paste prompts)

If they already use another assistant that knows this project, have them paste its answer to one of these. Give them the exact prompt to run *over there*, then parse what they paste back.

**Claude (Projects / past chats) / ChatGPT / Gemini — general project dump:**
> "Summarize everything you know about my project for a new teammate joining it: what the project is (one line), the client, what's in and out of scope, the key deliverables, the timeline and milestones, who's involved on both sides with their roles, our goals, and any decisions already made. Be specific; use bullet points; say 'unknown' where you're not sure."

**Existing brief / SOW / kickoff notes:**
> "Paste your project brief, SOW, or kickoff notes here." — map these straight into `context/brief.md`, `admin/scope.md`, `admin/timeline.md`, and `context/stakeholders.md`.

**Stakeholders specifically:**
> "List everyone involved in this project — on our side, the client side, and any external partners: name, role, and what they own or approve." → `context/stakeholders.md`.

**Scope & goals:**
> "What's in scope and explicitly out of scope for this project, what are the key deliverables, and what does success look like for the client?" → `admin/scope.md` + `context/goals.md`.

## 4. Tool exports (when a connector isn't wired but the tool is used)

- **Notion / Confluence / Google Docs** — ask for an export or a pasted project space / brief; extract into the matching folder.
- **Slack** — a pasted project-channel description, pinned kickoff doc, or member list gives stakeholders + working norms.
- **Granola / meeting tools** — pasted kickoff or recent meeting summaries seed `meetings/` and surface decisions for `decisions/`.
- **PM tool (Asana, Jira, Linear, a spreadsheet)** — a task/milestone export seeds `admin/timeline.md` and `admin/scope.md`.

## 5. Conversational fallback

No connector, no docs, nothing to paste? Ask the `/onboard` questions directly and build from the answers. Keep it light — a thin-but-real OS beats a perfect-but-empty one.

---

**After any source:** update `SETUP.md` (tick the boxes you completed), tell the user what got filled vs. what's still `[placeholder]`, and point them at the next cheapest source for the gaps.
