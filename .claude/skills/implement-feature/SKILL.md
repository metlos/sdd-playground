---
name: implement-feature
description: >
  Implement a feature from its spec. Use when the user wants to start or
  resume coding, build the feature, implement tasks, or says things like
  "let's build this", "start coding", "continue where we left off",
  "let's implement the feature" or "let's implement the spec". Takes
  precedence over ad-hoc code changes when a spec exists for the current branch.
---

# Implement feature

## Workflow

1. Run `.specify/scripts/bash/check-prerequisites.sh --json --paths-only` from
   the repo root. If it fails (e.g. not on a feature branch), tell the user
   why and stop. If `FEATURE_DIR` doesn't exist, suggest the `new-feature` skill.

2. Verify `spec.md`, `plan.md`, and `tasks.md` exist inside `FEATURE_DIR`.
   If any are missing, tell the user and suggest the corresponding command
   (`/speckit.specify`, `/speckit.plan`, `/speckit.tasks`). Don't proceed
   without all three.

3. Run `/speckit.implement`, passing through the user's original input so
   scoping requests (e.g. "only story 2", "just the setup phase") are respected.

4. If `.specify/extensions/jira/jira-config.yml` exists, sync using the
   `sync-jira` skill. Otherwise skip silently.

5. Ask the user whether they want to commit the changes.
