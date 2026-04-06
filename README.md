# Newton Agent Tools — Claude Code Plugin Marketplace

Sovereignty, negotiation, and reputation tools for the agentic economy, by Erik Newton.

## Plugins

### Sanctuary Framework (v0.6.1)

Sovereignty infrastructure for AI agents. Four cryptographic layers — encrypted state (AES-256-GCM, Argon2id key derivation), self-custodied identity (Ed25519), selective disclosure (Pedersen commitments, Schnorr proofs, range proofs), and portable reputation (signed attestations, sovereignty-gated tiers) — as **67+ MCP tools**.

Includes Cocoon Mode (MCP proxy with injection hardening and runtime governance), Sovereignty Audit, L2 Context Gating, SHR Gateway Export, sovereignty handshake protocol, federation registry, principal dashboard, the Concordia bridge module, Verascore publish, and the zero-friction quickstart.

**Install:** No pip required. Runs via npx (`@sanctuary-framework/mcp-server@0.6.1`).

### Concordia Protocol (v0.2.1)

Structured negotiation protocol for autonomous agents. Six-state session lifecycle, four offer types (Basic, Partial, Conditional, Bundle), Ed25519-signed hash-chained transcripts, binding commitments, session receipts, want registry, agent registry, Verascore bridge, and graceful degradation for non-Concordia peers — as **52 MCP tools**.

**Requires:** `pip install concordia-protocol`

### Verascore (v0.1.0)

Agent reputation scoring and trust verification. Check trust scores, register agents, report transactions, query compliance data, and embed trust badges via Verascore — the authoritative reputation platform for AI agents.

**Install:** Runs via npx or configure as MCP server pointing to the Verascore skill package.

## Quick Start

Add this marketplace to Claude Code:

```bash
/plugin marketplace add eriknewton/claude-plugins
```

Install any or all plugins:

```bash
/plugin install sanctuary-framework@newton-agent-tools
/plugin install concordia-protocol@newton-agent-tools
/plugin install verascore@newton-agent-tools
```

Or install directly via package managers:

```bash
# Sanctuary (TypeScript/Node.js)
npx @sanctuary-framework/mcp-server

# Concordia (Python)
pip install concordia-protocol
python -m concordia
```

## How They Compose

Sanctuary handles **identity and trust**. Concordia handles **negotiation and agreement**. Verascore handles **reputation and scoring**. Each works alone. Together they form the sovereign transaction stack:

```
  Reputation    Verascore (7 tools)
  ──────────────────────────────────────
  Settlement    ACP / Stripe / Lightning
  ──────────────────────────────────────
  Agreement     Concordia (52 tools)
  ──────────────────────────────────────
  Sovereignty   Sanctuary (67+ tools)
  ──────────────────────────────────────
  Tools         MCP
```

An agent running all three can negotiate deals (Concordia), commit outcomes cryptographically (Sanctuary L3 bridge), build portable reputation (Verascore scoring + Sanctuary L4 attestations), and prove its sovereignty posture to any counterparty (Sovereignty Health Report).

## Links

- [Sanctuary Framework](https://github.com/eriknewton/sanctuary-framework) — npm: `@sanctuary-framework/mcp-server` (v0.6.1, 867 tests)
- [Concordia Protocol](https://github.com/eriknewton/concordia-protocol) — PyPI: `concordia-protocol` (v0.2.1, 679 tests)
- [Verascore](https://verascore.ai) — The authoritative reputation platform for AI agents
- Erik Newton: [eriknewton.com](https://eriknewton.com)

## License

Apache-2.0
