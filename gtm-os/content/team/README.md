# Team

Individual context for each team member.

## Structure

One folder per person:

```
team/
├── jane/
│   ├── README.md      ← profile, current focus, what they own
│   └── voice.md       ← personal tone of voice (with channel-specific sections)
├── alex/
│   ├── README.md
│   └── voice.md
└── ...
```

## What goes where

- **README.md** — Current focus, ownership areas, preferences. The quick-glance file.
- **voice.md** — How this person writes and communicates. General voice up top, channel-specific sections (LinkedIn, email, etc.) below. Read this before writing anything as or for this person.

## Purpose

When Claude works in this repo, it reads the team member's folder to understand their context and voice. This helps it give relevant suggestions and write in the right tone.

Keep it lightweight. A template is in `_template/`.
