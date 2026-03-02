---
name: update-feature
description: The workflow to follow when the user wants to update a feature spec.
---

# Update an existing feature

## When to use

* When the user wants to make changes to an already existing feature.

## Workflow

1. Check the name of the current branch. If there is directory called `specs/<branch-name>`,
then that's the spec that is being worked on. If there is no directory like
that, skip the rest of the steps and proceed answering user's request without
consulting this skill.

1. Use the `speckit.clarify` command. Formulate concisely what the user wants
to update and pass this formulation as the argument to the command.

1. If the above steps produced any changes and if the spec has an implementation
plan (`<spec-dir>/plan.md` file), figure out whether that plan needs updates,
too. If yes, run the `speckit.plan` command, describing what needs to be changed
(concisely) as the argument to it. If not, proceed to the next step.

1. If the above steps produced any changes and if the spec has tasks
(`<spec-dir>/tasks.md` file), run the `speckit.tasks` command. If not, proceed
to the next step.

1. If any of the above steps caused any changes to the spec, ask the user
whether they want to reflect those changes in Jira. If yes, run the `speckit.jira.specstoissues`
command. If not, proceed to the next step.

1. If there already is any implementation of the spec, make sure the implementation
corresponds to the changes made above by running `speckit.implement`. If there's no
implementation, proceed to the next step.

1. Finally, ask the user if they want the changes committed. If yes, commit to
the spec branch. If not, don't commit.
