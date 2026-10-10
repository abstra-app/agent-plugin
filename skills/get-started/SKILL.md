---
name: get-started
description: Set up Abstra after installing the plugin. Confirms the connected account, picks the organization and project to work on, and loads the team's instructions. Use right after install, or when the user asks which Abstra organization or project is in use.
---

# Get started with Abstra

Abstra builds and runs business process automations written in Python. A
project is a workflow of stages (Pages, Forms, Hooks, Tasklets and Jobs)
connected by transitions, and it lives inside an organization.

1. Call `whoami` to confirm which Abstra account is connected. Tell the user
   the email. If the call fails with an authentication error, ask them to
   reconnect the Abstra plugin.
2. Call `list_organizations`. With one organization, use it. With several,
   list them by name and ask which one to use.
3. Call `get_organization_instructions` for that organization. These are the
   team's own rules; follow them for the rest of the conversation.
4. Call `list_projects` and ask which project to work on, or offer to create
   a new one if the user has none. Do not create one without their go-ahead.
5. Call `get_project_instructions` for the chosen project.
6. Summarize in two or three lines: the account, the organization, the
   project, and what the user can ask next (for example: explain the
   workflow, investigate failed executions, add a stage, query a table).

Before building or changing a project, call `get_platform_guide` once per
conversation.

Changes made through the editor tools stay in development until `deploy`.
`deploy`, `update_env_vars`, `run_production_snippet` and connector writes
take effect in production immediately: run them only when the user asked for
that change.
