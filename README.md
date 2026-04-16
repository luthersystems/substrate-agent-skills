# Substrate Agent Skill

<p align="center">
  <img src="assets/substrate-icon.png" alt="Luther Systems" width="120" />
</p>

<p align="center">
  <strong>Developer toolkit for <a href="https://enterprise.luthersystems.com/">Luther Enterprise</a></strong>
</p>

---

[Luther Enterprise](https://enterprise.luthersystems.com/) is Luther Systems' platform for building and operating regulated, auditable business processes. **Substrate** is the core runtime of Luther Enterprise -- an execution environment for business logic written in [ELPS](https://github.com/luthersystems/elps) (a Lisp dialect). Business logic modules are called **phyla** -- packages of `.lisp` files that define endpoints and business rules.

**shirotester** is the development toolkit for substrate. It provides an MCP server, language server, semantic linter, performance analyzer, debugger, REPL, test runner, and documentation browser -- all with full awareness of substrate's built-in packages.

This agent skill brings shirotester's capabilities to any AI coding tool.

| Tool | Install |
|------|---------|
| **Any tool** | `npx skills add luthersystems/substrate-agent-skills` |
| **Claude Code** | `npx skills add luthersystems/substrate-agent-skills --agent claude-code` |
| **Codex** | `npx skills add luthersystems/substrate-agent-skills --agent codex` |
| **Cursor** | `npx skills add luthersystems/substrate-agent-skills --agent cursor` |

Works with **Claude Code**, **Codex**, **Cursor**, **Kiro**, **Windsurf**, and [30+ other tools](https://agentskills.io).

---

## What You Get

### MCP Server (via npx -- no install required)

The shirotester MCP server runs locally and provides:

- **Hover docs** -- documentation for any symbol, including substrate builtins
- **Go-to-definition** -- jump to symbol definitions across files
- **Find references** -- find all usages of a symbol
- **Diagnostics** -- semantic errors and warnings with cross-file resolution
- **Performance analysis** -- call graphs, hotspots, anti-pattern detection
- **Eval & test** -- evaluate expressions and run tests in a shiro environment
- **Documentation** -- browse all packages and symbols at runtime

### Full CLI

Beyond MCP, the complete shirotester CLI is available via `npx @luthersystems/shirotester`:

```bash
npx @luthersystems/shirotester lint ./phylum          # Semantic linting
npx @luthersystems/shirotester analyze ./phylum       # Performance analysis
npx @luthersystems/shirotester debug ./phylum         # DAP debugger
npx @luthersystems/shirotester repl                   # Interactive REPL
npx @luthersystems/shirotester unit-tests ./phylum    # Run unit tests
npx @luthersystems/shirotester doc statedb            # Browse docs
```

### VS Code Extension

A companion [VS Code extension](https://marketplace.visualstudio.com/items?itemName=LutherSystems.substrate) provides syntax highlighting, LSP, and debugging. Install: search "Substrate" in the VS Code marketplace.

---

## Installation

### Recommended: Skills CLI

```bash
npx skills add luthersystems/substrate-agent-skills
```

This installs the skill for all detected AI coding tools.

### Claude Code

```bash
npx skills add luthersystems/substrate-agent-skills --agent claude-code
```

Then add the MCP server:

```bash
claude mcp add shirotester -- npx -y @luthersystems/shirotester mcp --workspace-root .
```

### Codex

```bash
npx skills add luthersystems/substrate-agent-skills --agent codex
codex mcp add shirotester -- npx -y @luthersystems/shirotester mcp --workspace-root .
```

### Cursor

```bash
npx skills add luthersystems/substrate-agent-skills --agent cursor
```

Then add the MCP server in Cursor Settings > MCP:

```json
{
  "mcpServers": {
    "shirotester": {
      "command": "npx",
      "args": ["-y", "@luthersystems/shirotester", "mcp", "--workspace-root", "."]
    }
  }
}
```

### Windsurf

```bash
npx skills add luthersystems/substrate-agent-skills --agent windsurf
```

Add MCP via Windsurf MCP settings with the same config as Cursor.

### Manual Installation

```bash
git clone https://github.com/luthersystems/substrate-agent-skills.git
cp -r substrate-agent-skills ~/.agents/skills/substrate
```

The `~/.agents/skills/` directory is the standard cross-tool location.

---

## Security

shirotester runs **entirely locally**. No data leaves your machine. No API keys, tokens, or remote servers required. See [SECURITY.md](SECURITY.md) for details.

---

## Resources

- [Luther Enterprise](https://enterprise.luthersystems.com/) -- the platform substrate powers
- [Documentation](https://docs.luthersystems.com)
- [ELPS Language](https://github.com/luthersystems/elps)
- [Substrate](https://github.com/luthersystems/substrate)
- [VS Code Extension](https://marketplace.visualstudio.com/items?itemName=LutherSystems.substrate)
- [npm: @luthersystems/shirotester](https://www.npmjs.com/package/@luthersystems/shirotester)
- [Agent Skills Standard](https://agentskills.io)

---

## Get Help

- [Discord](https://insideout.luthersystems.com/discord) -- chat with the devs
- [Subreddit](https://www.reddit.com/r/luthersystems/) -- community discussion
- [Documentation](https://docs.luthersystems.com)
- Email: [contact@luthersystems.com](mailto:contact@luthersystems.com)

---

## About Luther Systems

Luther Systems is an enterprise infrastructure and automation company founded in 2015, headquartered in London, UK. Our mission is to accelerate the advent of the automated enterprise.

- [Luther Systems](https://luthersystems.com)
- [Luther Enterprise](https://enterprise.luthersystems.com/)
- [Documentation](https://docs.luthersystems.com)

---

## License

[Apache License 2.0](LICENSE)
