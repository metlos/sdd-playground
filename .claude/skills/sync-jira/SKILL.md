---
name: sync-jira 
description: how to sync specs, user stories and tasks to jira issues 
---

# How to sync specs, user stories and tasks to jira issues

## When to use

Whenever the state of the spec, user stories and/or tasks should be sync to jira..

IMPORTANT: This skill takes precedence over just invoking `/speckit.jira.sync-status`

## Workflow

1. If there are any semantical changes to the spec, stories or tasks (other than
their completion status), use `/spec.jira.specstoissues` command to make sure
Jira is up-to-date. Be as specific as possible when requesting the issue contents
from Jira to prevent large responses.

1. Use the `/speckit.jira.sync-status` command to sync the status of the tasks.

1. check the following conditions in the exact order:
   * if some, but not all, tasks of a user story are completed,
     mark the user story as "in progress" in Jira.
   * if all tasks of a user story are completed, mark the user
     story as done also in Jira.
   * if some, but not all, user stories of an epic are completed
     or in progress, mark the epic as "in progress" in Jira.
   * if all user stories of an epic are completed, mark the epic
   as done also in Jira.
