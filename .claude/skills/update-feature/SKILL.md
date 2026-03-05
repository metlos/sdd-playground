---
name: update-feature
description: >
  Update an existing feature spec. Use when the user wants to change, revise,
  or refine a feature that already has a spec — e.g. "change the auth approach",
  "add a field to the spec", "revise the design", "update the requirements".
  Also triggers for corrections or scope changes to in-progress features.
---

# Update an existing feature

1. Check the current branch name. If `specs/<branch-name>` exists, that's the
   active spec. If not, stop consulting this skill and handle the request
   directly.

2. Run `/speckit.clarify`, passing a concise summary of what the user wants
   to update.

3. If changes were made and `<spec-dir>/plan.md` exists, check whether the
   plan needs updating. If yes, run `/speckit.plan` with a summary of the
   needed changes.

4. If changes were made and `<spec-dir>/tasks.md` exists, run `/speckit.tasks`.

5. If any spec artifacts changed, ask the user whether to sync to Jira. If
   yes, run `/speckit.jira.specstoissues`.

6. If implementation already exists, run `/speckit.implement` to align the
   code with the updated spec.

7. Ask the user if they want to commit the changes.
