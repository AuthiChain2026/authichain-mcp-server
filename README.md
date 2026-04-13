# AuthiChain MCP Server

**The Stripe of Product Authentication — now accessible to every AI agent on Earth.**

The AuthiChain MCP server exposes the full AuthiChain authentication protocol to AI models via the Model Context Protocol. Every tool call is a billable API event, turning AI agents into distribution channels for AuthiChain.

## Tools (8 total, 7 revenue-generating)

| Tool | Description | Revenue |
|------|-------------|---------|
| `authichain_verify_product` | 5-agent AI consensus verification | $0.01–0.05/call |
| `authichain_register_product` | Register product + mint NFT cert | $0.10–1.00/reg |
| `authichain_search_products` | Search authenticated product registry | $0.01/call |
| `authichain_check_eu_dpp` | EU Digital Product Passport compliance | $0.50–5.00/check |
| `authichain_truth_network` | Query 5-agent AI consensus directly | $0.05–0.10/query |
| `authichain_mint_certificate` | Mint NFT auth cert on Polygon | $0.10–1.00/mint |
| `authichain_verify_cannabis` | StrainChain cannabis verification | $0.50–2.00/verify |
| `authichain_get_pricing` | View API pricing tiers | Free (discovery) |

## Quick Start

```bash
# Install
npm install

# Run locally (stdio)
npm run dev

# Run as HTTP server
TRANSPORT_MODE=http PORT=3847 npm run dev

# Build for production
npm run build
npm start
```

## Environment Variables

```bash
AUTHICHAIN_API_URL=https://authichain-api.authichain2026.workers.dev
AUTHICHAIN_API_KEY=your_api_key
SUPABASE_URL=https://nhdnkzhtadfkkluiulhs.supabase.co
SUPABASE_ANON_KEY=your_supabase_key
TRANSPORT_MODE=stdio|http
PORT=3847
```

## Deploy to Cloudflare Workers

```bash
# Deploy as CF Worker for global edge distribution
wrangler deploy --name authichain-mcp-server
```

## Connect to Claude Desktop

Add to `~/.config/claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "authichain": {
      "command": "node",
      "args": ["/path/to/authichain-mcp-server/dist/index.js"],
      "env": {
        "AUTHICHAIN_API_KEY": "your_key"
      }
    }
  }
}
```

## Connect as Remote MCP (Claude.ai)

Once deployed to CF Workers, the MCP server URL can be added directly in Claude.ai settings:

```
https://authichain-mcp.authichain2026.workers.dev/mcp
```

## Revenue Model

Every AI agent that connects to this MCP server becomes a revenue channel:
- Claude users verifying products → $0.05/verification
- Enterprise AI systems doing bulk DPP checks → $2.00/check
- Cannabis dispensary AI tools → $0.50/cannabis verification
- Developer AI assistants registering products → $1.00/registration

**At 10,000 MCP tool calls/month = $500–$20,000/month in API revenue.**

## Architecture

```
AI Agent (Claude, GPT, etc.)
    ↓ MCP Protocol
AuthiChain MCP Server (this)
    ↓ REST API
AuthiChain CF Workers (34+ workers)
    ↓ Blockchain
Polygon (NFT certs, $QRON token)
    ↓ Data
Supabase (product registry, scan logs)
```

## Part of the Authentic Economy

- **AuthiChain.com** — The Protocol (enterprise backend)
- **QRON.space** — The Interface (consumer scanner)
- **StrainChain.io** — The Vertical (cannabis authentication)
- **This MCP Server** — The AI Distribution Layer

---

Built by AuthiChain | Polygon Contract: `0x4da4D2675e52374639C9c954f4f653887A9972BE` | $QRON: `0xAebfA6b08fb25b59748c93273aB8880e20FfE437`
