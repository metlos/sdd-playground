---
name: initialize-jira
description: >
  Set up or reconfigure Jira integration for spec-driven development. Use when
  the user wants to connect to Jira, configure Jira tracking, or when a
  speckit.jira.* command fails because jira-config.yml is missing.
---

# Initialize Jira Integration

## Workflow

1. If `.specify/extensions/jira/jira-config.yml` already exists, tell the user
   Jira is configured and ask if they want to reconfigure. If not, stop.

2. Check available MCP tools for Jira operations (tools like `jira_create_issue`,
   `jira_search`). Common server names: `mcp-atlassian`, `atlassian`, `jira`.
   If none found, tell the user to add one (e.g. `mcp-atlassian` via `uvx`)
   and stop. Note the server name for step 3.

3. Copy `.specify/extensions/jira/jira-config.template.yml` to
   `.specify/extensions/jira/jira-config.yml`. Ask the user for their Jira
   project key and update `project.key` and `mcp_server` in the config.

4. Run `/speckit.jira.discover-fields`. Then verify the configured issue types
   (`epic_type`, `story_type`, `task_type`) exist and can form a hierarchy
   (epic > story > task). If not, suggest alternatives from the available types.

5. Present the config to the user for review. Confirm project key, issue types,
   relationships, and status mappings look correct.

6. Tell the user Jira is ready and they can use `/speckit.jira.specstoissues`,
   `/speckit.jira.sync-status`, or the `sync-jira` skill.
