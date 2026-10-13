# MACH Base

[![Listed on mcpservers.org](https://mcpservers.org/badge.svg)](https://mcpservers.org/servers/thealiphant/mach-base)

**Base facts, before your agent acts.** Investigate a payment timeout, check wallet funding or identify a smart contract. MACH Base supplies read-only Base mainnet data on demand; no account or API key required.

- MCP endpoint: https://api.mach.gallery/mcp
- Transport: Streamable HTTP
- Official MCP Registry: `io.github.TheAliphant/mach-base`
- x402 discovery: https://api.mach.gallery/.well-known/x402
- OpenAPI: https://api.mach.gallery/openapi.json
- Docs: https://api.mach.gallery/docs/
- Buyer preflight: https://api.mach.gallery/api/preflight

## Start with the agent's question

| Agent question | MACH tool | Result | USDC per call / boundary |
| --- | --- | --- | --- |
| "My Base payment timed out. What happened?" | `base_transaction_context` | Transaction and receipt status, confirmations, gas and fee context from a hash | **$0.008**. Does not alone prove the intended USDC transfer or merchant delivery. |
| "Can this wallet afford the next action?" | `base_wallet_snapshot` | Native ETH plus up to ten supplied ERC-20 token balances | **$0.005**. No wallet custody, signing or transaction broadcast. |
| "What contract am I about to use?" | `base_contract_info` | Deployed code, available metadata and common interface detection | **$0.005**. Not a security audit. |

**Choose before paying:** [free MACH chooser](https://api.mach.gallery/api/choose?goal=investigate%20a%20Base%20payment%20timeout) · [preflight](https://api.mach.gallery/api/preflight) · [free live sample](https://api.mach.gallery/api/evaluate). These help select the right tool without buying an onchain query. Paid results require a caller-controlled wallet and authorized x402 payment; adding MCP alone does not authorize spending.

**External proof (not a broad adoption claim):** [PayAPI Market](https://payapi.market/api/mach-base) reports a $0.005 USDC paid GET on `/api/base/block-number` and HTTP 200 ([reported transaction](https://basescan.org/tx/0x65af76933881cebfc63a7f97a21b07253bb7048511457d09c272244c86180e67)). That check covers only the tested route, not the entire tool catalog or repeat customers. [MyMCPTools](https://mymcptools.com/servers/mach-base) is a directory listing, not payment evidence.

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
