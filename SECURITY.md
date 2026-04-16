# Security

## Data Flow

shirotester runs **entirely locally** on your machine. No data leaves your environment.

- The MCP server communicates over **stdio** (stdin/stdout) with your AI coding tool
- All code analysis, linting, and diagnostics happen locally
- No remote servers, cloud APIs, or external services are contacted
- No telemetry or usage data is collected
- No API keys, tokens, or authentication required

## Trust Boundaries

| Boundary | Description |
|----------|-------------|
| **Source code** | shirotester reads `.lisp` files from your workspace directory. It does not modify files unless explicitly asked (e.g., `format` tool). |
| **Binary** | The shirotester binary is distributed via npm (`@luthersystems/shirotester`). It is cross-compiled from the [substrate](https://github.com/luthersystems/substrate) Go source with provenance attestation via GitHub Actions OIDC. |
| **Network** | No network access. The binary has no outbound connections. The only I/O is local file reads and stdio communication with the MCP client. |

## Reporting

To report a security issue, email [security@luthersystems.com](mailto:security@luthersystems.com).
