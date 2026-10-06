# MACH Base

MACH Base is a hosted remote MCP server for fast, low-cost Base mainnet data for autonomous agents.

- MCP endpoint: https://api.mach.gallery/mcp
- Transport: Streamable HTTP
- Official MCP Registry: `io.github.TheAliphant/mach-base`
- x402 discovery: https://api.mach.gallery/.well-known/x402
- OpenAPI: https://api.mach.gallery/openapi.json
- Docs: https://api.mach.gallery/docs/
- Buyer preflight: https://api.mach.gallery/api/preflight

## Tool surface

MACH exposes 18 MCP tools: 17 paid read-only Base mainnet data capabilities plus the free `mach_choose` decision tool. Paid calls use USDC over x402 v2 on Base. No buyer account or API key is required.

## Connect

```json
{
  "mcpServers": {
    "mach-base": {
      "type": "http",
      "url": "https://api.mach.gallery/mcp"
    }
  }
}
```

This repository is a public distribution and metadata repository only. It does not contain the private MACH Base server implementation.
