# recued

Connects Claude Code to your own [Recued](https://recued.com) server over MCP, and brings the
`recued` skill for working with Recued's approvals. Reads run at once; a change waits for your
approval in the Recued app.

It asks for two settings: the Recued MCP address from your contract's Connect tab (on the computer
Recued runs on, `http://127.0.0.1:7717/mcp`), and the contract's key, which Claude Code keeps in
secure storage. Install it from this marketplace: `claude plugin marketplace add recued/claude-plugins`,
then `claude plugin install recued@recued`. See the [repository README](../../README.md) for the
details.
