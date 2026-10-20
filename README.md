# Newton Agent Tools: a Claude Code plugin marketplace

Security and negotiation tools for AI agents, by Erik Newton. Open source, Apache-2.0.

Add the marketplace in Claude Code, then install a plugin:

```bash
/plugin marketplace add eriknewton/claude-plugins
/plugin install sanctuary-framework@newton-agent-tools
/plugin install concordia-protocol@newton-agent-tools
```

## Sanctuary (v1.8.4)

Security for AI agents. Sanctuary puts a wall under the agent that the operating system enforces, under a policy the operator signs; keeps keys and agent state encrypted on hardware the operator controls; and writes what the agent did to a hash-chained record.

What this plugin adds: the Sanctuary MCP server (`@sanctuary-framework/mcp-server@1.8.4`, pinned) with encrypted state, a self-held Ed25519 identity, approval gates for irreversible operations, selective disclosure, portable reputation and a posture audit. The operating-system wall is a separate arming step:

- macOS: proven. A signed operator policy with a clean per-account allow/deny demonstration that survives reboots. Not an audited per-rule, per-flow trail.
- Linux: proven on Ubuntu 24.04 (x86-64) only, for the separate [Castle Wall Linux 0.1.0-1 package](https://github.com/eriknewton/sanctuary-framework/releases/tag/castle-wall-linux-0.1.0-1) (a GitHub pre-release). The npm package does not include it.
- Windows: roadmapped. Nothing enforces on Windows today.

Every claim traces to a row of the [Assurance Matrix](https://github.com/eriknewton/sanctuary-framework/blob/main/ASSURANCE_MATRIX.md).

To route an existing harness through Sanctuary instead of running it beside your other MCP servers, run `protect` once (the CLI also calls this `wrap`):

```bash
npx -y @sanctuary-framework/mcp-server@1.8.4 protect --claude-code --no-open --no-dashboard
npx -y @sanctuary-framework/mcp-server@1.8.4 doctor --json
```

Opt-in preview: `1.8.6-rc.5` on npm's `next` channel. Details: [README](https://github.com/eriknewton/sanctuary-framework#readme), [sanctuaryprotocol.ai](https://sanctuaryprotocol.ai).

## Concordia Protocol (v0.10.0)

An open standard for structured negotiation between autonomous agents: signed offers and counter-offers across several terms at once, binding commitments, session receipts, portable reputation and discovery. It degrades gracefully when the other agent does not speak Concordia.

Requires Python 3.10 or later and the server extra:

```bash
pip install "concordia-protocol[server]"
concordia-mcp-server --version
```

Details: [README](https://github.com/eriknewton/concordia-protocol#readme), [specification](https://github.com/eriknewton/concordia-protocol/blob/main/SPEC.md), [concordiaprotocol.dev](https://concordiaprotocol.dev).

## How they fit together

Each works alone; neither requires the other. Sanctuary protects the agent and holds its keys. Concordia structures the deal. When both run, Sanctuary can commit to a Concordia outcome and verify it cryptographically instead of trusting it. [Verascore](https://verascore.ai) scores agent reputation from those signed records.

## Links

- Sanctuary: [GitHub](https://github.com/eriknewton/sanctuary-framework), npm [`@sanctuary-framework/mcp-server`](https://www.npmjs.com/package/@sanctuary-framework/mcp-server)
- Concordia: [GitHub](https://github.com/eriknewton/concordia-protocol), PyPI [`concordia-protocol`](https://pypi.org/project/concordia-protocol/)
- Erik Newton: [GitHub](https://github.com/eriknewton), [X @newtonlaw](https://x.com/newtonlaw), [LinkedIn](https://www.linkedin.com/in/erikwnewton/)

## License

Apache-2.0
