# AFAS AI Connect

<img src="assets/logo.png" alt="iWebDevelopment" width="180">

AFAS AI Connect, by iWebDevelopment, is a hosted MCP server that connects your AFAS Profit administration to your AI assistant. Ask questions, pull reports, and prepare bookings for approval, right from the chat you already use.

Hosted at `https://mcp-afas.iwebdevelopment.com`. Sign in through your browser on first use; no tokens to paste into your AI client config.

**Get started in about 2 minutes.** See the [installation guide](https://www.iwebdevelopment.com/kennisbank/hoe-werkt-de-afas-ai-mcp-koppeling) to connect your administration.

[![Add to Cursor](https://img.shields.io/badge/Add_to-Cursor-000?logo=cursor)](https://cursor.com/install-mcp?name=afas&config=eyJ1cmwiOiJodHRwczovL21jcC1hZmFzLml3ZWJkZXZlbG9wbWVudC5jb20ifQ%3D%3D) [![Install in VS Code](https://img.shields.io/badge/Install_in-VS_Code-007ACC?logo=visualstudiocode)](https://insiders.vscode.dev/redirect/mcp/install?name=afas&config=%7B%22name%22%3A%22afas%22%2C%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp-afas.iwebdevelopment.com%22%7D)

Works with Claude on all plans (including the free plan); also with ChatGPT (Developer Mode, paid plans), Perplexity (Pro/Max/Enterprise), GitHub Copilot in VS Code, Cursor and other developer tools. Availability and setup differ per client. See the [client compatibility matrix](#client-compatibility) below.

![AFAS AI Connect in action](assets/demo.gif)


## What you can do

- **Ask**: plain-language questions about your administration ("Wat heb ik klant X vorig kwartaal gefactureerd?").
- **Report**: outstanding items, aging, profit & loss, balance sheet.
- **Create & book with approval**: every write is a draft you review and approve first. Nothing posts to AFAS Profit without your confirmation.
- **Analyse**: large-dataset analysis and trend overviews, on the Analytics plan.

## Example prompts

- "Toon mijn tien recentste verkoopfacturen met het openstaande bedrag."
- "Welke debiteuren staan nog open en hoe lang?"
- "Wat heb ik klant X vorig kwartaal gefactureerd?"
- "Omzet per klant per maand dit jaar."
- "Kolommenbalans voor deze periode."
- "Maak een verkoopfactuur voor klant X (ter goedkeuring)."

## Install

### First: connect your AFAS environment (one-time)

AFAS authenticates with an AppConnector token, not a per-user login, so an administrator connects the environment once. In AFAS, go to **Algemeen › Beheer › App connector** and add a new one (**Nieuw**):

- Give it a description (e.g. "AI Connect") and set **Authenticatietype** to **Classic token** (confirm the two security prompts).
- Enable **Automatisch token genereren** and choose **Maak nieuwe gebruikersgroep op basis van App connector-naam**.
- Link the required connectors via **Nieuw › select › Voltooien**.

Then register the generated token with AFAS AI Connect. The [installation guide](https://www.iwebdevelopment.com/kennisbank/hoe-werkt-de-afas-ai-mcp-koppeling) walks through every step. After that, everyone you invite just signs in through their browser.

### Add to Claude (web + Desktop)

1. Go to **Settings → Connectors → Add custom connector**.
2. Paste the base URL: `https://mcp-afas.iwebdevelopment.com`
3. Sign in through your browser when prompted.

On the free plan you can add one custom connector. On Team/Enterprise, an owner adds it org-wide.

For a legacy `mcp-remote` fallback, see `examples/claude-desktop-config.json` (optional, not required).

### Claude Code (plugin)

```
/plugin marketplace add iwebdevnl/afas-ai-connect
/plugin install afas-ai-connect@iwebdevnl-afas
/reload-plugins
/mcp
```

The last command signs you in.

Prefer to add it manually? `claude mcp add --transport http afas https://mcp-afas.iwebdevelopment.com`

### Other clients

AFAS AI Connect is a standard remote MCP server, so most MCP-capable clients (ChatGPT, Perplexity, GitHub Copilot, Cursor, Cline, Windsurf, Zed, and others) can add it by URL. Setup steps and plan requirements vary per client, see the matrix below.

See the [full documentation](https://www.iwebdevelopment.com/kennisbank/hoe-werkt-de-afas-ai-mcp-koppeling) for per-client setup.

## Client compatibility

**Last verified: 2026-07**

| Client | Remote MCP? | Plan / mode | How to add |
|---|---|---|---|
| Claude (web / Desktop) | Yes, full read + write | All plans incl. **Free** (Free = 1 custom connector); Team/Ent = owner adds | Settings → Connectors → Add custom connector → base URL |
| Claude Code | Yes | Claude Code itself needs Pro/Max or API billing | `claude mcp add --transport http afas https://…`; OAuth in the browser |
| GitHub Copilot (VS Code) | Yes | All Copilot plans; Business/Enterprise need an admin "MCP servers" policy (off by default) | `.vscode/mcp.json` with `"type":"http"` + the server URL |
| Cursor | Yes | No documented plan gate | Settings → Tools & MCP → New MCP Server (`url`), or the Add-to-Cursor badge |
| Cline | Yes | Free (open-source) | mcp.json `"type":"streamableHttp"` (camelCase) |
| Windsurf | Yes | Enterprise may gate | Settings → Tools → Add Server (`serverUrl`) |
| Zed | Yes on recent builds (native HTTP since 2026-03); older builds via `mcp-remote` bridge | No documented gate | Settings → AI → MCP Servers (URL + Authorization header) |
| ChatGPT | Yes, **Developer Mode only** | **Paid** (Plus/Pro/Business/Enterprise/Edu), not Free | Settings → Connectors → Advanced → Developer mode → add the URL |
| Perplexity | Yes (since 2026-03) | **Paid** (Pro/Max/Enterprise), not Free, not in Comet | Add a custom remote connector by URL |
| Microsoft 365 Copilot | **No end-user "paste a URL"** | Agent path only (Copilot Studio) | Build/publish an agent (a heavier path) |

## Verify the connection

Once connected, try:

- "Toon mijn tien recentste verkoopfacturen met het openstaande bedrag."
- "Welke debiteuren staan deze week nog open?"

## Trust

- **ISO 27001** certified.
- Every write is a draft you approve, nothing books to AFAS Profit without your confirmation.
- Runs within the scope of the AFAS AppConnector configured in your environment.
- Data hosted in the EU.

See [TRUST.md](TRUST.md), [PRIVACY.md](PRIVACY.md), and [SECURITY.md](SECURITY.md) for details.

## Plans & limitations

- **Essentials**: day-to-day questions and processing, with approval on every write.
- **Analytics**: adds large-dataset analysis and trend overviews.
- **Free trial**: 30 days on the Analytics plan. After the trial, the integration stops unless a subscription is activated.

Not available through the AFAS API: deleting posted financial entries or certain master records, which AFAS keeps immutable. You correct these with a counter-entry.

## Support

Product page: https://www.iwebdevelopment.com/afas/ai-mcp-koppeling
