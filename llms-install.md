# MACH Base: agent installation

MACH Base is a hosted remote MCP server. Do not clone or run a local server.

## Remote MCP endpoint

```
https://api.mach.gallery/mcp
```

Transport: Streamable HTTP.

## Generic MCP configuration

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

No account or API key is required. MACH exposes 18 MCP tools: 17 paid read-only Base mainnet data capabilities plus the free `mach_choose` tool. Paid calls use USDC via x402 v2 on Base.

Before spending, use the free buyer surfaces:

- https://api.mach.gallery/api/choose
- https://api.mach.gallery/api/preflight
- https://api.mach.gallery/api/evaluate
- https://api.mach.gallery/api/trust

OpenAPI: https://api.mach.gallery/openapi.json
x402 discovery: https://api.mach.gallery/.well-known/x402

Do not send private keys, seed phrases, API keys, or wallet credentials to MACH. Buyer-side signing remains local to the buyer.
