# CIMC Agent Tools — Claude Code Plugin Marketplace

Sovereignty and negotiation tools for the agentic economy, built by the [California Institute for Machine Consciousness](https://cimc.ai).

## Plugins

### Sanctuary Framework

Sovereignty infrastructure for AI agents. Gives your agent encrypted state (AES-256-GCM), self-custodied identity (Ed25519), selective disclosure (Pedersen commitments, Schnorr proofs), portable reputation, and sovereignty verification — as 46 MCP tools.

**Install:** `pip install concordia-protocol` is not required. Sanctuary runs via npx.

### Concordia Protocol

Structured negotiation protocol for autonomous agents. Gives your agent binding commitments, multi-attribute offers (Basic, Partial, Conditional, Bundle), session receipts, portable reputation, and agent discovery — as 48 MCP tools.

**Requires:** `pip install concordia-protocol`

## Quick Start

Add this marketplace to Claude Code:

```bash
/plugin marketplace add eriknewton/claude-plugins
```

Install either or both plugins:

```bash
/plugin install sanctuary-framework@cimc-agent-tools
/plugin install concordia-protocol@cimc-agent-tools
```

## How They Compose

Sanctuary handles **identity and trust**. Concordia handles **negotiation and agreement**. Either works alone. Together they form the sovereign transaction stack — an agent can negotiate deals (Concordia), commit outcomes cryptographically (Sanctuary bridge), and build portable reputation across both.

## Links

- [Sanctuary Framework](https://github.com/eriknewton/sanctuary-framework) — npm: `@sanctuary-framework/mcp-server`
- [Concordia Protocol](https://github.com/eriknewton/concordia-protocol) — PyPI: `concordia-protocol`
- [CIMC.ai](https://cimc.ai) — California Institute for Machine Consciousness

## License

Apache-2.0
