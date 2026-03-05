# SDD playground

This project uses speckit and Spec driven development (SDD) to have an efficient
interface between the humans and AIs.

It also uses the Jira extension of speckit to mirror the specs contained in this
repository in Jira.

IMPORTANT: CLAUDE.md is just a symlink to AGENTS.md to improve interoperability.
It must stay that way and updates should only be made to AGENTS.md.

## Pre-Prompt Checks

At the start of every conversation (on the very first user message), check if
the `.specify` directory exists in the project root. If it does NOT exist,
immediately warn the user:

> WARNING: The .specify folder is missing. Run /project-bootstrap to set up the
spec-driven development.

Do this check before doing anything else.

## Hook Warnings

When hooks (e.g. `UserPromptSubmit`) produce warnings, always proactively relay
them to the user immediately before doing anything else.
