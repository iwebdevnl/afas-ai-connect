# Zed

Recent Zed builds support remote MCP servers natively. Older builds need a small stdio bridge instead.

## Recent builds

1. Go to **Settings → AI → MCP Servers** and add the URL: `https://mcp-afas.iwebdevelopment.com`
2. Sign in through your browser when prompted.

## Older builds

Bridge the remote server as a stdio context server with `mcp-remote`:

```
npx mcp-remote https://mcp-afas.iwebdevelopment.com
```

See the [compatibility matrix](https://github.com/iwebdevnl/afas-ai-connect#client-compatibility) (last verified 2026-07).
