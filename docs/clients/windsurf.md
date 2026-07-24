# Windsurf

Windsurf connects to remote MCP servers through its Tools settings, or by editing the raw config directly. Note the field name: Windsurf uses `serverUrl`, not `url`.

## Steps

1. Go to **Settings → Tools → Add Server**, or edit the raw config:

   ```json
   { "mcpServers": { "afas": { "serverUrl": "https://mcp-afas.iwebdevelopment.com" } } }
   ```

2. Sign in through your browser when Windsurf opens it.

Some Enterprise Windsurf plans may gate remote MCP servers by admin policy.

See the [compatibility matrix](https://github.com/iwebdevnl/afas-ai-connect#client-compatibility) (last verified 2026-07).
