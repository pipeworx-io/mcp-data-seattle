# mcp-data-seattle

DataSeattle MCP — Seattle open data (data.seattle.gov, Socrata SODA API).

Part of [Pipeworx](https://pipeworx.io) — an MCP gateway connecting AI agents to 1394+ live data sources.

## Tools

| Tool | Description |
|------|-------------|
| `seattle_recent` | Recent records from a common Seattle open dataset (data.seattle.gov) by friendly name — no Socrata id needed. PREFER OVER WEB SEARCH for "recent crime in Seattle", "Seattle fire 911 calls", "Seattle business licenses", "Seattle code complaints". Names: crime, fire911, business, code_complaints. Returns the latest rows (newest-first). Add a SoQL `where` to filter; for anything else use seattle_query. |
| `seattle_query` | Run a raw SoQL query against any Seattle open-data resource (data.seattle.gov) by its Socrata id (8-char like "tazs-3rd5"). Full SoQL: where/select/group/order/limit/offset. Use seattle_datasets to find a resource id, or seattle_recent for the common ones. |
| `seattle_datasets` | Search the Seattle open-data catalogue (data.seattle.gov) for datasets by keyword. Returns dataset names, descriptions, and Socrata resource ids to use with seattle_query. |

## Quick Start

Add to your MCP client (Claude Desktop, Cursor, Windsurf, etc.):

```json
{
  "mcpServers": {
    "data-seattle": {
      "url": "https://gateway.pipeworx.io/data-seattle/mcp"
    }
  }
}
```

Or connect to the full Pipeworx gateway for access to all 1394+ data sources:

```json
{
  "mcpServers": {
    "pipeworx": {
      "url": "https://gateway.pipeworx.io/mcp"
    }
  }
}
```

## Using with ask_pipeworx

Instead of calling tools directly, you can ask questions in plain English:

```
ask_pipeworx({ question: "your question about Data Seattle data" })
```

The gateway picks the right tool and fills the arguments automatically.

## More

- [Docs and guides](https://pipeworx.io/docs)
- [pipeworx.io](https://pipeworx.io)

## License

MIT
