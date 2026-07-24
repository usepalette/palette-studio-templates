---
type: index
owner: [Workspace steward]
status: active
last_updated: YYYY-MM-DD
last_updated_by: [Setup author]
edit_policy: team
---

# User feedback

Product signal kept close to its source, structured so the team can search, compare, and synthesize
it without losing attribution.

## Structure

```text
user-feedback/
├── feedback/            # Short raw snippets
├── user-interviews/     # Longer conversations and research sessions
├── feature-requests/    # Explicit asks linked to a source
├── painpoints/          # Synthesized problems linked to one or more sources
├── _companies/          # Per-company context and signal index
├── recaps/              # Sourced summaries prepared for sharing
├── _template.md         # Raw feedback template
└── index.html           # Generated dashboard
```

## Lifecycle

```text
raw feedback ──┬──> explicit ask ──> feature request
               │
               └──> repeated or blocking problem ──> painpoint
user interview ┘
```

Raw input remains raw. Derived files always link back with `source_files`.

## Data boundaries

- Keep only product-relevant context the workspace audience is allowed to see.
- Leave secrets, private personal details, restricted transcripts, and bulk raw exports in their
  controlled source. Link, anonymize, or summarize instead.
- Never treat access to a source as permission to redistribute it.

## After editing

Run `/feedback-sync`. The command rebuilds only the data block inside `index.html`. Markdown is the
source of truth.

## Naming

- Feedback and interviews: `YYYY-MM-DD_company_person_topic.md`
- Feature requests and painpoints: `YYYY-MM-DD_company_topic.md`
- Company profiles: `_companies/company-name.md`
- Recaps: `recaps/YYYY-MM-DD-company-or-topic.md`
- Lowercase, hyphenated slugs. Underscores separate the filename fields.
