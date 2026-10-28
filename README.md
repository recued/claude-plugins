# Recued for Claude Code

A [Claude Code](https://code.claude.com) plugin marketplace with one plugin, `recued`, that
connects Claude Code to your own [Recued](https://recued.com) server.

Recued is a server you run on a computer you control. It keeps your notes, tasks, mail, calendar
and the things you own, and it stands between your data and any AI: it checks every request
against what you granted, asks you before a change, and keeps a record of what was done.

The plugin adds Recued as an MCP server and brings the `recued` skill, which tells Claude how to
work with Recued's approvals. It runs no code of its own.

## What you need

- Claude Code.
- A Recued server: [install it](https://recued.com/docs/setup/install-server/) on a computer you
  control.
- A contract for Claude Code. In the Recued web app, open Contracts, make a contract, choose the
  tools Claude Code may use, and copy the key Recued shows.

## Install

```sh
claude plugin marketplace add recued/claude-plugins
claude plugin install recued@recued
```

Or, inside a session: `/plugin marketplace add recued/claude-plugins`, then
`/plugin install recued@recued`.

Claude Code asks for two settings:

- **Recued MCP address**: the address the contract's Connect tab shows. On the computer Recued
  runs on, it is `http://127.0.0.1:7717/mcp`, the default.
- **Recued contract key**: the contract's key. Claude Code keeps it in secure storage, not in its
  settings file.

To change them later, run `/plugin configure recued@recued`, then restart Claude Code.

## How it works

- The tools you see are the ones the contract grants. To give Claude Code another tool, change the
  contract in the Recued web app. Claude Code picks up the change within about ten seconds,
  without a restart.
- Reading runs at once: Recued marks its read-only tools.
- A change waits for you. Recued holds it for your approval in the Recued app, from the bell at the
  top of the page. When you have answered, tell Claude, and it can ask Recued for the result.

## Privacy

Your data stays on your Recued server. The model sees only what a tool returns, and Recued returns
only what the contract grants. The key stays in Claude Code's secure storage; it is not written
into the plugin.

## Remove

```sh
claude plugin uninstall recued@recued
claude plugin marketplace remove recued
```

## License

MIT
