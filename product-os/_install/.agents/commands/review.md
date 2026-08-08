---
type: command
description: Review product work for evidence, traceability, hygiene, and completeness
---

# Review

Review the relevant workspace changes as a product teammate, not a generic linter.

## 1. Understand the scope

Read the changed files or ask what should be reviewed. Classify the work as capture, synthesis,
discovery, strategy, specification, competitor research, or structural change.

Run only the relevant checks.

## 2. Checks

### A. Source fidelity

For feedback and interviews:

- Quotes are verbatim or labelled as paraphrases.
- Person, company, date, and source are not guessed.
- Context does not masquerade as the user's words.

### B. Synthesis discipline

For painpoints and requests:

- Derived items carry valid `source_files`.
- A recurring painpoint has at least two independent sources, unless a one-source blocking
  interview is explicitly labelled.
- Duplicate jobs are updated rather than split into near-identical files.
- Scores match the evidence and do not pretend to be roadmap priority.

### C. Product reasoning

- Discovery files frame open questions rather than hiding a preferred solution.
- Strategy files include evidence and credible counter-arguments.
- Specs trace to upstream evidence, set a clear audience, define measurable success, and state
  meaningful non-goals.
- Competitor claims cite primary sources and separate fact from inference.

### D. Roadmap boundary

- Initiatives, projects, tasks, status, owners, and delivery dates remain in the issue tracker.
- Product OS links to tracker work instead of recreating it.

### E. Workspace hygiene

- Relative links resolve.
- New files are listed where the folder README maintains a roster.
- Full documents carry the complete frontmatter contract — `type`, `owner`, `status`,
  `last_updated`, `last_updated_by`, and `edit_policy` — matching what `/workspace-heal` enforces.
  A `type` alone is not enough; a document `/review` passes must not be one `/workspace-heal` flags.
- Dates are absolute and attribution names the human.
- No unintended `[bracket placeholders]` remain outside templates or incomplete setup.
- Canonical `.agents/` files and `.claude/` adapters remain aligned.

### F. Dashboard freshness

When feedback changed, verify `/feedback-sync` was run and the dashboard includes the source.

### G. Data boundaries

- Customer names, quotes, and source links are appropriate for the workspace audience.
- Secrets, restricted raw exports, and unnecessary private details remain in their controlled
  source.
- Anonymized or summarized material is labelled accurately.

## 3. Output

Lead with blocking issues, then important improvements. For each finding include:

- File path
- Specific problem
- Evidence or rule
- Smallest useful fix

Skip checks that do not apply. If nothing material is wrong, say `No issues found.`
