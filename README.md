# Xata for Claude Code

The official [Xata](https://xata.io) plugin for Claude Code connects Claude to Xata's hosted [Model Context Protocol (MCP)](https://modelcontextprotocol.io) server.

Use it to work with Xata organizations, projects, Postgres branches, schemas, data, and platform resources without leaving Claude Code. The server is hosted by Xata, so there is no local MCP process or package to install.

## Installation

In Claude Code, add the Xata marketplace and install the plugin:

```text
/plugin marketplace add xataio/claude-plugin
/plugin install xata@xata
```

If Claude Code asks you to reload plugins, run `/reload-plugins`.

Open `/mcp`, select the `xata` server, and complete the browser-based OAuth flow. Claude Code stores and refreshes the resulting credentials; no API key is required.

## Usage

Once connected, ask Claude to perform Xata tasks in natural language. For example:

- "List my Xata organizations and projects."
- "Show me the Postgres branches in this project."
- "Describe the schema for this database."
- "Run a read-only query to find the ten most recently created users."
- "Create a development branch for this feature."

Claude discovers the available operations and Xata guidance from the MCP server. Write and destructive operations remain distinct from read operations, and destructive operations require explicit confirmation.

For more information about the MCP server and its capabilities, see the [Xata MCP documentation](https://xata.io/docs/platform/mcp).

## Local development

From a checkout of this repository, validate the plugin:

```bash
claude plugin validate . --strict
```

Then load the checkout from the project where you want to test it:

```bash
claude --plugin-dir /path/to/claude-plugin
```

Use `/mcp` to confirm that the `xata` server is connected and to complete or reset authentication.
