---
name: new-feature
description: >
  Start a spec-driven feature or bug fix. Use whenever the user wants to add
  functionality, fix a bug, or build something new — e.g. "add login", "build
  an API", "fix the parser", "I need a new endpoint". Always use this skill
  for non-trivial changes, even if the user doesn't mention specs explicitly.
---

# Add a new feature

Ask the user whether they want to start a new spec for the change they're
describing. If they decline, stop consulting this skill and handle the request
directly.

If they agree, follow these steps:

1. If the user's input implies project-level decisions (technology choices,
   architectural patterns, integrations, etc.), trigger the
   `project-constitution` skill first.

2. Run `/speckit.specify` with a short description of the feature derived from
   the user's input. Focus on what and why — omit concrete technical details.

3. Offer follow-up commands:
    * `/speckit.clarify` — refine underspecified areas
    * `/speckit.plan` — create an implementation plan
    * `/speckit.tasks` — generate tasks from the plan
    * `/speckit.jira.specstoissues` — create epics/stories in Jira
