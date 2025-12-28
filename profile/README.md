# LSP Client Ecosystem 🚀

Welcome to the **LSP Client** ecosystem — a professional-grade toolkit and Agent-native ecosystem built around the [Language Server Protocol (LSP)](https://microsoft.github.io/language-server-protocol/). 

We provide a complete stack to transform raw language intelligence into high-fidelity context for humans and AI Agents alike.

---

## 🌟 Core Components

### 🐍 [Python SDK](https://github.com/lsp-client/lsp-client/tree/main/python-sdk)
The industrial-strength foundation. A modern, async-first library for fine-grained LSP control.
- **Mixin Architecture**: Zero-overhead system for automatic capability negotiation and method safety.
- **Async-First**: Built with `anyio` for high-concurrency tool development.
- **Production Ready**: Full type safety, explicit environment control, and robust error handling.

### 🐳 [Container Registry](https://github.com/lsp-client/lsp-client/tree/main/containers)
The isolation layer. Optimized, pre-built Docker images for instant, secure server deployment.
- **Zero-Config Isolation**: Protect your host environment and ensure reproducible analysis.
- **Auto-Updated**: Weekly builds to keep you at the bleeding edge of language support.
- **Lean & Fast**: Multi-stage builds for minimal footprint and rapid startup.

### 🤖 Agent & MCP Integration
The intelligence layer. Designed for the next generation of AI tools and coding assistants.
- **[LSAP (Language Server Agent Protocol)](https://github.com/lsp-client/lsp-client/tree/main/LSAP)**: A semantic abstraction that transforms granular LSP operations into agent-friendly Markdown snapshots.
- **Model Context Protocol (MCP)**: Standardized integration to expose LSP and LSAP capabilities directly to LLM-powered agents.
- **Progressive Disclosure**: Engineered to provide high-signal context with minimal noise for autonomous reasoning.

---

## 🛠 Supported Languages & Servers

Our ecosystem supports a growing list of language servers, available locally or via our container registry:

| Language | Server | Container Image |
| :--- | :--- | :--- |
| **Python** | Pyright, Pyrefly, Ruff, Ty | `ghcr.io/lsp-client/pyright` |
| **Rust** | Rust Analyzer | `ghcr.io/lsp-client/rust-analyzer` |
| **Go** | Gopls | `ghcr.io/lsp-client/gopls` |
| **TypeScript/JS** | Deno, TS Server, ESLint | `ghcr.io/lsp-client/typescript` |
| **C/C++** | Clangd | `ghcr.io/lsp-client/clangd` |
| **Java** | JDTLS | `ghcr.io/lsp-client/jdtls` |
| **Swift** | SourceKit-LSP | `ghcr.io/lsp-client/sourcekit-lsp` |
| **Vue** | Volar | `ghcr.io/lsp-client/vue` |

---

## 🚀 Quick Start

Integrate language intelligence into your project using the Python SDK:

```python
import anyio
from lsp_client.clients.pyright import PyrightClient, PyrightContainerServer
from lsp_client.common import Position

async def main():
    # Use Pyright in a container for instant isolation and zero configuration
    async with PyrightClient(server=PyrightContainerServer()) as client:
        definitions = await client.request_definition_locations(
            file_path="app.py",
            position=Position(line=10, character=5)
        )
        for loc in definitions:
            print(f"Found definition: {loc.uri} at {loc.range}")

anyio.run(main)
```

---

## 🤝 Join the Ecosystem

We are building a robust, open ecosystem for the future of software engineering. 

- **Contribute a Server**: Add a new `ContainerFile` to our registry.
- **Extend the Protocol**: Help us evolve LSAP and the Python SDK.
- **Build Agents**: Use our tools to create the next generation of AI coding assistants.

Check out our [Contribution Guidelines](https://github.com/lsp-client/lsp-client/blob/main/python-sdk/docs/contribution/) to get started.

---

Built with ❤️ by the **LSP Client** team.
