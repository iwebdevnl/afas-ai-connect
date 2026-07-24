# How the connection works

```mermaid
flowchart LR
  A[AI client<br/>Claude / ChatGPT / IDE] -->|MCP over HTTPS| B[AFAS AI Connect<br/>hosted MCP server · EU]
  B -->|AppConnector token| C[AFAS Profit API]
  B -.->|Analytics plan only| D[(Analysis copy<br/>EU)]
```

You sign in through your browser once. Your AFAS environment is connected with an AppConnector token that is configured once in AFAS; no tokens are pasted into your AI client config. Every write is prepared as a draft you approve before it is
posted. The authoritative terms are in iWeb's AV/DPA.
