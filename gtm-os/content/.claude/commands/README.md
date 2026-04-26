# Commands

Executable workflows that Claude runs as slash commands.

## Available commands

| Command | What it does |
|---------|-------------|
| `/onboard` | Set up this repo for your company — asks questions, populates template files |
| `/review` | Review workspace changes for brand compliance, hygiene, and consistency |

## How commands work

A command is a markdown file in `.claude/commands/` that tells Claude what to do when you run the slash command. It's like a runbook that Claude follows.

## The progression

The gtm-os follows a natural progression:

1. **Manual work** — you do things by hand, figure out what works
2. **Playbook** — you capture how you think about it (`playbooks/`)
3. **Command** — you automate the repeatable parts (`.claude/commands/`)

Write playbooks first. Commands come later, when the workflow is stable enough to automate.

## Writing your own commands

Create a new `.md` file in this folder. Include:
- A clear description of what the command does
- When to run it
- Step-by-step instructions for Claude to follow
- What files it reads and writes

Name the file after the command: `meeting-end.md` → `/meeting-end`
