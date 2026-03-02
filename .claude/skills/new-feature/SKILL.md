---
name: new-feature
description: The procedure to add new features and fix bugs in this project
---

# Add a new feature

## When to use

* When the user wants to change the code (either because of a bug or a new
feature), it should be backed by a spec that fully defines
what should be implemented.

## Workflow

First and foremost, ask the user whether they want to start a new spec for
the problem they're describing.

If not, proceed fulfilling user's request without consulting this skill.

If yes, follow this execution flow:

1. Check whether the user's input implies project-level decisions (technology
choices, architectural patterns, integrations, etc.) that should be captured
in the project constitution. If so, trigger the `project-constitution` skill
first, before proceeding with the spec.

2. Use the `/speckit.specify` command with a short description of the feature.
Use the user's input to formulate the feature description. Focus on what and
why, there's no need to specify concrete technical details and choices.

3. Offer the user the choice of the follow-up commands:
    * `speckit.jira.specstoissues` - at this stage this can only create epics
      and stories
    * `speckit.clarify`
    * `speckit.plan`
    * `speckit.tasks`
