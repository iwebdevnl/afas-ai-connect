# Cline

Cline (the open-source VS Code extension) connects to remote MCP servers through its MCP settings JSON. Cline itself is free to use.

Note the field name: Cline expects `streamableHttp`, in camelCase, not `http` or `streamable-http` like some other clients use.

## Steps

1. Open Cline's MCP settings JSON and add:

   ```json
   { "mcpServers": { "afas": { "type": "streamableHttp", "url": "https://mcp-afas.iwebdevelopment.com" } } }
   ```

2. Cline opens your browser to sign in on first use.

See the [compatibility matrix](https://github.com/iwebdevnl/afas-ai-connect#client-compatibility) (last verified 2026-07).
