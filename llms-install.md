# MACH Base: agent installation

MACH Base is a hosted remote MCP server for read-only Base mainnet facts. Investigate payment timeouts, check wallet funding and inspect smart contracts before your agent acts. Do not clone or run a local server.

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

Use the tool that matches your actual job:
- Investigate a failed transaction or payment timeout: `base_transaction_context` — $0.008 USDC. Includes receipt and gas/fee context, but does not prove exact USDC payee/amount or delivered work.
- Check ETH and up to ten specified tokens before spending: `base_wallet_snapshot` — $0.005 USDC; read-only, no signing.
- Inspect a contract's deployed code and metadata: `base_contract_info` — $0.005 USDC; not a security audit.
- Start with the free `mach_choose` tool or choose/preflight endpoints. Generic MCP clients do not sign x402 payments on their own.

Before spending, use the free buyer surfaces:

- https://api.mach.gallery/api/choose
- https://api.mach.gallery/api/preflight
- https://api.mach.gallery/api/evaluate
- https://api.mach.gallery/api/trust

OpenAPI: https://api.mach.gallery/openapi.json
x402 discovery: https://api.mach.gallery/.well-known/x402

Do not send private keys, seed phrases, API keys, or wallet credentials to MACH. Buyer-side signing remains local to the buyer.
