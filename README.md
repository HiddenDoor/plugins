# Hidden Door MCP and skills

Create and develop Hidden Door worlds from your AI harness.

Includes the Hidden Door MCP connection, and related skills.

See the [plugin guide](plugins/hiddendoor/README.md) for workflows, example prompts,
and account requirements.

**For agents:** to install and connect Hidden Door in any app (Claude, Claude Code,
Codex, ChatGPT, Cursor, VS Code and others), follow the
[setup instructions for agents](https://www.hiddendoor.co/mcp/setup.md).
To set it up without the plugin, see [hiddendoor.co/mcp](https://www.hiddendoor.co/mcp#set-it-up).

## Install in Claude Code

Run:

```sh
claude plugin marketplace add HiddenDoor/plugins
claude plugin install hiddendoor
```

Start a new session, or run `/reload-plugins` in an existing session.

### Keep it updated

In Claude Code, open `/plugin`, select **Marketplaces → hiddendoor**,
and enable **auto-update**.

To update manually:

```sh
claude plugin marketplace update hiddendoor
claude plugin update hiddendoor
```

Start a new session or run `/reload-plugins` to load the update.

## Install in Codex

Run:

```sh
codex plugin marketplace add hiddendoor/plugins
codex plugin add hiddendoor@hiddendoor
```
