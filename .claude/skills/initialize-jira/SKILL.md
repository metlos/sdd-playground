---
name: initialize-jira
description: setup Jira integration in Speckit
---

# Initialize Jira Integration

## When to use

* User wants to invoke some Jira related command in speckit (the command name starts with `speckit.jira`)
but there is no `.specify/extensions/jira/jira-config.yml` file.

## Workflow

1. Make sure you have available an MCP server for integration with Jira (there
are more supported, `mcp-atlassian` ran using `uvx` works for example). If there
is no such MCP server, ask the user to install one following the guide in
<https://github.com/sooperset/mcp-atlassian> and re-run the command once it is
configured.

2. Copy the `.specify/extensions/jira/jira-config.template.yml` to `.specify/extensions/jira/jira-config.yml`

3. Ask the user for the Jira project name that should be used and update
the `project.key` property of the `jira-config.yml` file with it. Update
the `mcp_server` field with the name of the actual MCP server used.

4. Run the `speckit.jira.discover-fields` command.

5. Additionally, make sure that the detected Jira issue types for epics, stories and tasks can
form the hierarchy in Jira. If not try to find equivalent issue types that can.

6. Ask the user to review the `.specify/extension/jira/jira-config.yml` file and
make sure it correctly maps the all the fields and statuses to the Jira project.

7. Inform the user that the Jira integration setup is complete and that they can
start using it.
