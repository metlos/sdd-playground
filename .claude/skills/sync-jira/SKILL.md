---
name: sync-jira
description: >
  Sync local specs, stories, and tasks to Jira. Use whenever the user wants to
  push changes to Jira, update Jira from local specs, or sync task status --
  even if they just say "update jira" or "push to jira". Takes precedence over
  invoking `/speckit.jira.sync-status` directly.
---

# Sync specs, stories and tasks to Jira

## Workflow

1. **Sync content changes** (if any). If the spec, stories, or tasks have
   semantic changes (updated descriptions, added/removed tasks, renamed phases
   -- not just completion status), run `/speckit.jira.specstoissues`. Detect
   changes by comparing against `jira-mapping.json` timestamps or git history.
   If unsure, ask the user. Be specific when requesting issue contents from
   Jira to keep responses small.

2. **Sync task completion status.** Run `/speckit.jira.sync-status` to push
   `[x]`/`[ ]` markers from tasks.md to Jira.

3. **Roll up status to stories and epic.** The sync-status command only handles
   individual tasks. Load the hierarchy from `specs/<spec-name>/jira-mapping.json`
   and the MCP server name from `.specify/extensions/jira/jira-config.yml`
   (`mcp_server` field, default `mcp-atlassian`), then:

   - For each story: some tasks done → "In Progress"; all done → "Done";
     none done → leave as-is.
   - For the epic: some stories progressed → "In Progress"; all done → "Done";
     none progressed → leave as-is.

   To transition: call `jira_get_transitions` for the issue, find the matching
   transition ID, then `jira_transition_issue`. If no matching transition exists
   (already in target state), skip it.