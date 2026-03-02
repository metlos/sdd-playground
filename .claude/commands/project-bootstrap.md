---
description: Bootstraps the project to use speckit and its Jira integration.
---

## Goal

This prepares the project to use the standard tooling for spec-driven development.

## Execution Steps

1. Make sure the project is on the default branch (`main`, `master` or similar).
If not, do not proceed to the next steps.

2. Run the following commands:
    - `uv tool install specify-cli --from git+https://github.com/github/spec-kit.git`
    - `yes | specify init . --ai <YOURSELF>`
where `YOURSELF` is `claude` if you're Claude Code, or `cursor-agent` if you're
Cursor. If you don't know what kind of AI agent you are, ask the user.

3. Figure out the latest release (or tag) of the Jira integration for Speckit at
<https://github.com/mbachorik/spec-kit-jira> and take note of the URL to download
its zip. Install it using:
`specify extension add jira --from <RELEASE-OR-TAG-ZIP-FILE-URL>`

4. Inform the user that the bootstrap is complete. It is still necessary to
setup Jira integration but the project as such is now usable for spec-driven
development.
