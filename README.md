# Abstra

[Abstra](https://www.abstra.io) is a platform for business process automation in Python.
This plugin connects your AI agent to your Abstra account, so you can build and operate
your workflows from the conversation.

## What you can do

- Explore the organizations and projects your account can access, and explain how a
  workflow's stages (Pages, Forms, Hooks, Tasklets and Jobs) connect.
- Create and edit stages, transitions and code in a project's editor, and run them there.
- Query and change Abstra Tables.
- Configure connectors to the external systems your organization uses.
- Investigate production executions, logs and tasks, and deploy changes to production.

Example prompts:

- "List my Abstra projects and what each workflow does."
- "Why did the last production execution of my project fail?"
- "Add a job to my project that runs every morning."

## How it works

The plugin bundles two things:

- **The Abstra MCP server** at `https://mcp.abstra.io/`, a remote server run by Abstra.
  You sign in with your Abstra account through OAuth the first time you use it. The agent
  only sees the organizations and projects your account can access, and every action
  respects your role in each organization.
- **A `get-started` skill** that confirms the connected account, helps you pick the
  organization and project to work on, and loads your team's instructions.

Changes made in a project's editor stay in development until you deploy. Deploys,
production environment variables, connector writes and production snippets take effect
immediately, so the agent should only run them when you ask for that change.

## Data

The plugin sends to Abstra the requests the agent makes on your behalf: tool names and
their arguments, such as project identifiers, code, table queries and connector
parameters. Abstra processes them under its
[privacy policy](https://www.abstra.io/privacy-policy) and
[terms of service](https://www.abstra.io/terms-of-service). The plugin itself stores
nothing on your machine and sends nothing to any other destination.

## Requirements

An Abstra account. Sign up at [abstra.io](https://www.abstra.io).

## Compatibility

The package follows the [Agent Plugins](https://agent-plugins.org/) format (`plugin.json`,
`mcp.json`, `skills/`), read by ChatGPT, Codex and
[other compatible clients](https://agent-plugins.org/compatible-clients).
`.claude-plugin/plugin.json` makes the same package load in Claude.

## Support

[help.abstra.io](https://help.abstra.io) or help@abstra.app.
