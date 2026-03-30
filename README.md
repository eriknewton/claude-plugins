# Sanctuary & Concordia — Claude Code Plugin Marketplace

Sovereignty and negotiation tools for the agentic economy, by Erik Newton.

## Plugins

### Sanctuary Framework (v0.3.1)

Sovereignty infrastructure for AI agents. Four cryptographic layers — encrypted state (AES-256-GCM, Argon2id key derivation), self-custodied identity (Ed25519), selective disclosure (Pedersen commitments, Schnorr proofs, range proofs), and portable reputation (signed attestations, sovereignty-gated tiers) — as **46 MCP tools**.

Includes the **Sovereignty Audit** tool for environment fingerprinting and four-layer gap analysis with OpenClaw-specific detection. Also includes Sovereignty Health Report generation/verification, sovereignty handshake protocol, federation registry, principal dashboard, and the Concordia bridge module.

**Install:** No pip required. Runs via npx (`@sanctuary-framework/mcp-server@0.3.1`).

### Concordia Protocol (v0.1.0)

Structured negotiation protocol for autonomous agents. Six-state session lifecycle, four offer types (Basic, Partial, Conditional, Bundle), Ed25519-signed hash-chained transcripts, binding commitments, session receipts, want registry, agent registry, and graceful degradation for non-Concordia peers — as **48 MCP tools**.

**Requires:** `pip install concordia-protocol`

## Quick Start

Add this marketplace to Claude Code:

```bash
/plugin marketplace add eriknewton/claude-plugins
```

Install either or both plugins:

```bash
/plugin install sanctuary-framework@sanctuary-concordia
/plugin install concordia-protocol@sanctuary-concordia
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

Sanctuary handles **identity and trust**. Concordia handles **negotiation and agreement**. Either works alone. Together they form the sovereign transaction stack:

```
  Settlement    ACP / Stripe / Lightning
  ──────────────────────────────────────
  Agreement     Concordia (48 tools)
  ──────────────────────────────────────
  Sovereignty   Sanctuary (46 tools)
  ──────────────────────────────────────
  Tools         MCP
```

An agent running both can negotiate deals (Concordia), commit outcomes cryptographically (Sanctuary L3 bridge), build portable reputation across both (Sanctuary L4 + Concordia attestations), and prove its sovereignty posture to any counterparty (Sovereignty Health Report).

## Links

- [Sanctuary Framework](https://github.com/eriknewton/sanctuary-framework) — npm: `@sanctuary-framework/mcp-server` (v0.3.1, 315 tests)
- [Concordia Protocol](https://github.com/eriknewton/concordia-protocol) — PyPI: `concordia-protocol` (v0.1.0, 587 tests)
- Erik Newton: [eriknewton.com](https://eriknewton.com)

## License

Apache-2.0
