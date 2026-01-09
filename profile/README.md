# LSP Client Ecosystem 🚀

> Please visit our [website](https://lsp-client.github.io)!

Welcome to the **LSP Client** ecosystem — a professional-grade toolkit and agent-native ecosystem designed to transform the [Language Server Protocol (LSP)](https://microsoft.github.io/language-server-protocol/) into **actionable repository intelligence** for AI Agents and developers.

---

## 🏛 The Architecture: From Protocol to Intelligence

Our ecosystem is built as a layered stack, progressively evolving raw language server capabilities into specialized reasoning "skills" for coding agents.

### 1. [LSP Client](https://github.com/lsp-client/lsp-client/) (The Base)

The industrial-strength foundation. A modern, async-first Python SDK for fine-grained LSP control.

- **Protocol Native**: Full support for LSP specifications with automatic capability negotiation.
- **Robustness**: Type-safe, async-first (AnyIO), and production-ready.
- **[Container Registry](https://github.com/lsp-client/containers)**: Pre-built, isolated environments for 20+ language servers, enabling instant, zero-config deployment.

### 2. [LSAP](https://github.com/lsp-client/LSAP) (The Abstraction)

**Language Server Agent Protocol**. A semantic abstraction layer that transforms granular LSP operations into agent-friendly snapshots.

- **Agent-Centric**: Converts raw JSON-RPC data into structured Markdown/JSON optimized for LLM consumption.
- **Semantic Context**: Provides high-signal context (e.g., "Summarize this class" instead of just "Get symbols").

### 3. [LSP CLI](https://github.com/lsp-client/lsp-cli) (The Tool)

A universal command-line interface that brings LSP and LSAP capabilities to any terminal or script.

- **Human & Machine Friendly**: Use it for manual exploration or as a backend for automation scripts.
- **Universal Interface**: One CLI to rule all language servers.

### 4. [LSP Skill](https://github.com/lsp-client/lsp-skill) (The Intelligence)

High-level repository analysis capabilities designed specifically for **Coding Agents** (like Opencode).

- **Deep Understanding**: Provides cross-file reference analysis, project-wide symbol mapping, and architectural insights.
- **Plugin for Agents**: Acts as a skill that agents can invoke to perform complex repository-wide tasks via LSP.

---

## 🛠 Supported Languages & Servers

We provide optimized, pre-built [container images](https://github.com/lsp-client/containers) for instant, zero-config deployment:

| Language          | Server        | Container Image                    |
| :---------------- | :------------ | :--------------------------------- |
| **Python**        | Pyright, Ruff | `ghcr.io/lsp-client/pyright`       |
| **Rust**          | Rust Analyzer | `ghcr.io/lsp-client/rust-analyzer` |
| **Go**            | Gopls         | `ghcr.io/lsp-client/gopls`         |
| **TypeScript/JS** | TS Server     | `ghcr.io/lsp-client/typescript`    |
| **C/C++**         | Clangd        | `ghcr.io/lsp-client/clangd`        |
| **Java**          | JDTLS         | `ghcr.io/lsp-client/jdtls`         |
| **Swift**         | SourceKit-LSP | `ghcr.io/lsp-client/sourcekit-lsp` |
| **Vue**           | Volar         | `ghcr.io/lsp-client/vue`           |

---

## 🚀 Quick Start (SDK)

Integrate language intelligence into your Python projects:

```python
import anyio
from lsp_client.clients.pyright import PyrightClient, PyrightContainerServer
from lsp_client.common import Position

async def main():
    # Run Pyright in an isolated container
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

We are building the future of AI-native software engineering.

- **Contribute**: Add new servers to our [Container Registry](https://github.com/lsp-client/containers).
- **Extend**: Help us evolve **LSAP** for better agent reasoning.
- **Integrate**: Use **LSP Skills** to empower your own AI coding assistants.

Built with ❤️ by the **LSP Client** team.
