---
type: index
owner: "[Owner]"
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: team
---

# Engineering

The connective tissue of how you build — architecture, technical decisions, standards, and the knowledge you need when something breaks.

**This folder is docs and decisions, not code.** Code, PRs, and CI live in your code host; task tracking lives in your issue tracker; detailed reference docs may live in a wiki. This folder holds the durable *why* and the cross-repo *how we operate* — the things that don't belong next to code and would go stale in a wiki. When a doc is really just reference, keep it in the wiki and **link** to it from here rather than copying.

## Structure

```
engineering/
├── decisions/       # Architecture Decision Records — why we chose X over Y (dated, one per file)
├── runbooks/        # "It's on fire, do this" — deploy, rollback, common ops
├── postmortems/     # Blameless incident write-ups
├── security/        # Security posture, policies, compliance notes
├── architecture.md  # Cross-repo system map — the big pieces and how they fit
├── stack.md         # What you run and why — languages, frameworks, vendors, infra
├── standards.md     # How you work — PR process, review norms, testing bar, conventions
├── onboarding.md    # Day 1 for a new engineer
├── glossary.md      # Internal terms, acronyms, and vendors
├── AGENTS.md        # How to think/behave in this space (+ thin CLAUDE/GEMINI pointers)
├── lessons.md · log.md · README.md
```

Each subfolder has its own `README.md` — start there.

## Where does it go?

| You have... | Put it in... |
|---|---|
| A significant architectural choice + its reasoning | `decisions/YYYY-MM-DD-<slug>.md` (see `decisions/README.md`) |
| Steps to handle an incident, deploy, or rollback | `runbooks/<name>.md` (see `runbooks/README.md`) |
| An update to how services fit together | `architecture.md` |
| A change to PR / review / testing expectations | `standards.md` |
| A new tool, language, or vendor you've adopted | `stack.md` |
| A write-up of a production incident | `postmortems/YYYY-MM-DD-<slug>.md` |
| A security policy or compliance note | `security/` |
| Onboarding a new engineer | `onboarding.md` |
| An unfamiliar internal term or vendor | `glossary.md` |

## What lives elsewhere (don't duplicate)

Each system stays canonical for what it owns. This folder holds the durable *why* and **links** to the rest rather than copying it. Fill in the systems you actually use:

| System | Canonical for | How `engineering/` relates |
|---|---|---|
| [Your code host, e.g. GitHub] | Code, code-level docs, CI | Synthesize + link — overview here, links down to the repo |
| [Your issue tracker, e.g. Linear/Jira] | Tasks, projects, decision *tracking* | Link, never copy — ADRs point at the issue trail |
| [Your wiki, e.g. Notion/Confluence] | Detailed reference docs | Link (or copy-in deliberately), don't mirror |
| [Your live-context connector] | Live people / team / org context | Read live, never copy into files |

**One rule:** if a system above owns it, don't paste a second copy here — link.

## Surface ownership

Who owns which part of the system — fill this in so agents can route questions and set doc owners.

| Person | Role | Owns |
|---|---|---|
| [Name] | [role] | [surface / area] |

## Quick start

1. Read the root [`../AGENTS.md`](../AGENTS.md), then this README and [`AGENTS.md`](AGENTS.md).
2. New to the system? Read `architecture.md` → `stack.md` → skim `decisions/`.
3. On call or shipping? Go straight to `runbooks/`.
