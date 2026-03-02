---
name: implement-feature
description: how to proceed when the user is ready to implement a feature to the spec
---

# Implement feature

## When to use

* When the user expresses the intention to implement the feature described by the spec.

## Workflow

1. Check the name of the current branch. If there is directory called `specs/<branch-name>`,
then that's the spec that is being worked on. If there is no directory like
that, skip the rest of the steps and proceed answering user's request without
consulting this skill.

2. Invoke the `/specify.implement` command.

3. Sync the state of the tasks, stories and spec using the `sync-jira` skill.

4. Ask the user whether they want to commit the changes and commit the changes
if they do. Don't commit if they don't want to.
