# AFAS AI Connect (Claude Code plugin)

Connects Claude Code to your AFAS Profit environment through the hosted MCP server at
`https://mcp-afas.iwebdevelopment.com`. You connect the environment once with an AppConnector
token, after which you sign in through your browser.

```
/plugin marketplace add iwebdevnl/afas-ai-connect
/plugin install afas-ai-connect@iwebdevnl-afas
/reload-plugins
/mcp
```

The last command signs you in. Full documentation, including how to create the AppConnector token,
is in the [repository README](https://github.com/iwebdevnl/afas-ai-connect).

## What is in this plugin

| Component | Contents |
|---|---|
| MCP server | One hosted HTTP server (`.mcp.json`) |
| Commands | 4 slash commands, prefixed `afas-` |
| Skills | None. The server ships its own routing guidance for AFAS |

The plugin ships `defaultEnabled: false`, so it stays off until you enable it. That is deliberate:
the MCP server is a paid subscription and the tools reach your live environment.

## Commands

Command names carry an `afas-` prefix so they do not collide with the Exact Online and Twinfield
plugins, which offer the same four reports.

| Command | Does |
|---|---|
| `/afas-balans [periode]` | Balance sheet and general ledger totals |
| `/afas-omzet [jaar]` | Revenue per customer per month |
| `/afas-openstaande-debiteuren [administratie]` | Outstanding receivables |
| `/afas-ouderdomsanalyse [peildatum]` | Aging analysis of open items |

AFAS has no fixed API specification: data comes from GetConnectors and UpdateConnectors that are
built per environment, so which endpoints exist differs from customer to customer. The commands
therefore locate the right connector with `search_endpoints` rather than hardcoding names.

One more thing worth knowing: a single AFAS environment can hold several administrations. General
ledger, debtors and creditors live at environment level and apply to all of them, while entries are
per administration. Group or filter on the administration (the `Unit` field, or the `unit` column in
the analysis tables) before reading figures for one administration, and never add balances across
administrations blindly.

## Support

Questions about the product go to <support@iwebdevelopment.com>. Bugs in this plugin go to the
[issue tracker](https://github.com/iwebdevnl/afas-ai-connect/issues). Security reports:
see [SECURITY.md](https://github.com/iwebdevnl/afas-ai-connect/blob/main/SECURITY.md).

MIT licensed. AFAS and AFAS Profit are trademarks of AFAS Software B.V. This plugin is built by
iWebDevelopment and is not affiliated with or endorsed by AFAS.
