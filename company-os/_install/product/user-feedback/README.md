---
type: index
owner: "[Owner]"
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: team
---

# User feedback

What users say — structured so it can be searched, filtered, and synthesized across companies and time.

## The feedback model

```
user-feedback/
├── feedback/            # raw snippets — chat, email, support, calls
├── feature-requests/    # explicit asks, tied back to a feedback or interview source
├── user-interviews/     # interview notes (longer, structured)
└── painpoints/          # synthesized patterns across multiple sources
```

This is the intended shape — these subfolders appear as real feedback arrives. Don't pre-create empty ones; the first snippet creates `feedback/`.

## Lifecycle

Raw feedback lands in `feedback/`. A repeated theme across sources gets synthesized into `painpoints/`. An explicit ask gets logged as a `feature-requests/` entry, linked back to its source. Don't synthesize too early — a single piece of feedback (N=1) is rarely a painpoint.

## Feedback-file frontmatter convention

Every file in `feedback/` (and similar leaf files elsewhere in this folder) opens with:

```
---
type: feedback
date: YYYY-MM-DD
source: "[chat | interview | email | support | call]"
person: "[Name]"
company: "[Company]"
tags: [tag1, tag2]
sentiment: "[positive | neutral | negative | mixed]"
---
```

## Conventions

- Filenames: `YYYY-MM-DD_company_person_topic.md` — underscores separate the *fields*, each field is
  lowercase kebab-case (`2026-03-04_acme-corp_alex-rivera_slow-search.md`)
- Dates always absolute, never relative
- Everywhere else, file and folder names are plain kebab-case — the underscore field separator is
  specific to these dated leaf files
