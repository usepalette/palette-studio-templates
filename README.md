# Palette Desktop Templates

A public catalog of templates for [Palette Desktop](https://palette.team) — folder structures, skills, and playbooks you can install in one click from the Templates browser.

## Templates

- [GTM-OS](./gtm-os/) — Your GTM as a file system
- [Project OS](./project-os/) — Run a single project or client engagement, with a live dashboard
- [Accounts](./accounts/) — Track accounts, log meetings, and prep for calls
- [Content](./content/) — Draft, voice-check, and distribute the writing you ship
- [Competitor Analysis](./competitor-analysis/) — Structured competitor tracking
- [Presentations](./presentations/) — Draft decks and generate self-contained HTML slides

## Structure

Each template lives in its own folder. Two reserved subfolders are the
only things Palette Desktop reads:

- `_install/` — files placed on disk at the chosen destination. A file
  at `<template>/_install/X` lands at `<destination>/X`.
- `_scaffold/` — install-time content the agent reads from the seed
  prompt instead of placing on disk. Use this for setup instructions
  (`integration.md`) and content templates with `{{PLACEHOLDER}}`
  markers the agent customizes before writing the final output to the
  user's chosen location.

Everything else at the template root (manifest, README, logo,
screenshots, CHANGELOG, …) is template metadata — Palette Desktop ignores it.
The required pieces are:

- `template.yaml` — manifest (name, slug, version, author, description, tags)
- `README.md` — detail-view content shown in the templates browser
- `_install/` and/or `_scaffold/` — at least one is required

## Contributing

Open a pull request with a new template folder. Templates are curated — please open an issue first to discuss the idea.
