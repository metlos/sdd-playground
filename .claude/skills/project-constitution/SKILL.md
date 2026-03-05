---
name: project-constitution
description: >
  Capture project-level decisions into the constitution. Trigger whenever the
  user states or implies technology choices, architectural patterns, framework
  selections, integrations, workflow preferences, or quality standards — even
  inside feature requests or bug reports. E.g. "we're using TypeScript",
  "this is a REST API", "let's use Postgres", "we do TDD".
---

# Project Constitution

## Workflow

1. Read the current constitution at `.specify/memory/constitution.md`.
2. Identify project-level decisions in the user's input not yet captured.
3. If there are new decisions, run `/speckit.constitution` summarizing the new
   or updated principles.
4. If the constitution is already up-to-date, skip silently.
