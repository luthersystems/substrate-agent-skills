# Substrate Agent Skill

ELPS/substrate development toolkit for AI coding tools. Provides an MCP server and full CLI for code navigation, diagnostics, performance analysis, linting, debugging, testing, and documentation -- with full substrate builtin awareness.

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

## What is Substrate?

Substrate is [Luther Systems'](https://luthersystems.com) execution environment for business logic written in [ELPS](https://github.com/luthersystems/elps) (a Lisp dialect). Business logic modules are called **phyla** -- packages of `.lisp` files that define endpoints and business rules.

shirotester is the development toolkit that understands substrate's built-in packages (`cc:*`, `statedb:*`, `sidedb:*`, `crypto:*`, `router:*`) and provides accurate analysis that generic tools cannot.

---

## Security

shirotester runs **entirely locally**. No data leaves your machine. No API keys, tokens, or remote servers required. See [SECURITY.md](SECURITY.md) for details.

---

## Resources

- [ELPS Language](https://github.com/luthersystems/elps)
- [Substrate](https://github.com/luthersystems/substrate)
- [VS Code Extension](https://marketplace.visualstudio.com/items?itemName=LutherSystems.substrate)
- [npm: @luthersystems/shirotester](https://www.npmjs.com/package/@luthersystems/shirotester)
- [Agent Skills Standard](https://agentskills.io)
- [Luther Systems](https://luthersystems.com)

---

## License

[Apache License 2.0](LICENSE)
