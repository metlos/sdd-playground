---
name: project-constitution
description: keep the project guiding principles and development guidelines up-to-date
---

# Project Constitution

## When to use

* Whenever the user explicitly describes or updates the guiding principles or
development guidelines of the project.
* Whenever the user's request implicitly establishes or reveals project-level
decisions. This includes but is not limited to:
  * Technology choices (programming languages, frameworks, libraries)
  * Architectural patterns (e.g. CLI tool, microservice, monolith)
  * External integrations (APIs, services, databases)
  * Development workflow preferences (testing strategy, CI/CD, etc.)
  * Quality standards or constraints

Look for these signals even when the user is describing a feature or a bug fix,
not just when they are explicitly talking about project principles.

## Workflow

1. Read the current constitution at `.specify/memory/constitution.md`.
2. Identify what project-level decisions are implied or stated by the user's
input that are not yet captured in the constitution.
3. If there are new decisions to capture, run `speckit.constitution` with an
argument summarizing the new or updated principles derived from the user's
input.
4. If the constitution is already up-to-date, skip this step silently.
