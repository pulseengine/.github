<div align="center">

# PulseEngine

### Infrastructure for AI and WebAssembly

*Exploring the intersection where AI agents interact safely with real-world systems through WebAssembly's security model*

<br>

![Rust](https://img.shields.io/badge/Rust-000000?style=flat&logo=rust&logoColor=white)
![WebAssembly](https://img.shields.io/badge/WebAssembly-654FF0?style=flat&logo=webassembly&logoColor=white)
![Bazel](https://img.shields.io/badge/Bazel-43A047?style=flat&logo=bazel&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)

[View Repositories](https://github.com/orgs/pulseengine/repositories) • [Documentation](#project-details)

</div>

<br>

## What We're Building

PulseEngine develops infrastructure at the intersection of AI and WebAssembly, ranging from WASI proposals to production-tested implementations. Our work focuses on enabling AI systems to safely interact with real-world applications through WebAssembly's capability-based security model.

<br>

## Core Infrastructure

<table>
<tr>
<td width="50%" valign="top">

### WebAssembly Runtime
**[wrt](https://github.com/pulseengine/wrt)**

Safety-critical WebAssembly runtime with Component Model support. 22+ interconnected crates designed for automotive (ASIL-D), aerospace (DO-178C), and medical (IEC 62304) applications.

**Architecture**
Core execution engine, formal verification with 227 Kani harnesses, capability-based memory system, no_std compatibility

**Development Stage**
Advanced beta - foundational infrastructure production-grade, core execution engine under active development

</td>
<td width="50%" valign="top">

### MCP Framework
**[mcp](https://github.com/pulseengine/mcp)**

Rust framework for building Model Context Protocol servers. Extracted from production home automation deployment with 30+ tools. 12 modular crates covering protocol, security, auth, and monitoring.

**Features**
Complete MCP 2025-06-18 implementation, stdio/HTTP/WebSocket transports, 1,071 test functions, 80% code coverage

**Development Stage**
Production-ready beta (v0.13.0) - actively used in real systems, published to crates.io

</td>
</tr>
</table>

<br>

## Build & Development Tools

<table>
<tr>
<td width="50%" valign="top">

### Bazel Rules
**[rules_wasm_component](https://github.com/pulseengine/rules_wasm_component)**

Modern Bazel rules for WebAssembly Component Model development. Supports Rust, Go, C++, and JavaScript with multi-profile builds and 73% faster compilation.

**Highlights**
87 Starlark files, 415+ rule definitions, 30+ working examples, hermetic builds, OCI publishing, component signing

**Development Stage**
Beta → production-ready (v1.0.0) - comprehensive CI/CD, suitable for production with v2.0 planned

</td>
<td width="50%" valign="top">

### WebAssembly Signing
**[wsc](https://github.com/pulseengine/wsc)**

Enhanced WebAssembly signing toolkit with Rekor verification, based on wasmsign2. Bazel integration, keyless signing, WIT Component Model support.

**Security**
Checkpoint-based verification, key fingerprint validation, origin verification, cross-shard attack prevention

**Development Stage**
Active development - core signing/verification functional, Rekor validation operational

</td>
</tr>
<tr>
<td width="50%" valign="top">

### WebAssembly Optimizer
**[loom](https://github.com/pulseengine/loom)**

WebAssembly optimizer built with Cranelift's ISLE DSL. Declarative optimization rules with stateful dataflow analysis for constant propagation and memory optimization.

**Approach**
Novel contribution: extends ISLE's pure functional term rewriting with stateful tracking of locals and memory state

**Development Stage**
Proof of concept - 40+ operations, demonstrates feasibility of ISLE-based WASM optimization

</td>
<td width="50%" valign="top">

### File Operations
**[bazel-file-ops-component](https://github.com/pulseengine/bazel-file-ops-component)**

Universal file operations for Bazel via WebAssembly components. Dual implementation (TinyGo for security, Rust for performance) with WASM sandboxing.

**Cross-Platform**
Replaces platform-specific scripts with sandboxed components working identically on Linux, macOS, Windows

**Development Stage**
Active development - security model established, integration with rules_wasm_component ongoing

</td>
</tr>
</table>

<br>

## AI Integration

<table>
<tr>
<td width="50%" valign="top">

### AI-Native Graphical Modeling
**[glsp-mcp](https://github.com/pulseengine/glsp-mcp)**

First implementation of Graphical Language Server Protocol using MCP. Enables AI agents to create and manipulate diagrams through natural language with WebAssembly component execution.

**Stack**
Rust backend (23,722 lines), TypeScript frontend (39,571 lines), wasmtime 24.0 runtime, multi-database layer (PostgreSQL, InfluxDB, Redis)

**Demo**
15+ ADAS components showing automotive system simulation with YOLOv5n neural network integration

**Development Stage**
Advanced MVP/beta - core features functional, production path identified

</td>
<td width="50%" valign="top">

### WASI-MCP Proposal
**[wasi-mcp](https://github.com/pulseengine/wasi-mcp)**

Proposed WebAssembly System Interface API for Model Context Protocol, targeting WASI Preview3. Complete typed WIT interfaces mapping MCP protocol operations.

**Coverage**
Full MCP 2025-06-18 specification - resources, tools, prompts, streaming, pagination, notifications

**Approach**
Protocol-faithful design following successful WASI proposals (wasi-http, wasi-filesystem patterns)

**Development Stage**
Phase 0 pre-proposal - WIT interfaces complete, seeking stakeholder feedback for Phase 1

</td>
</tr>
</table>

<br>

## Production MCP Servers

<table>
<tr>
<td width="33%" valign="top">

### WindRiver Studio
**[studio-mcp](https://github.com/pulseengine/studio-mcp)**

MCP server for WindRiver Studio CLI with Pipeline Management integration, intelligent caching, multi-instance authentication.

**Status:** Production-ready
**Published:** npm (@pulseengine/studio-mcp-server)

</td>
<td width="33%" valign="top">

### Time & Date
**[timedate-mcp](https://github.com/pulseengine/timedate-mcp)**

Comprehensive time operations with timezone support, format detection, timezone conversion, built with chrono-tz.

**Status:** Production-ready
**Published:** npm (@pulseengine/timedate-mcp-server)

</td>
<td width="33%" valign="top">

### Template Server
**[template-mcp-server](https://github.com/pulseengine/template-mcp-server)**

Automated template for creating MCP servers with PulseEngine framework. Example tools, resources, CI/CD workflows.

**Purpose:** Developer onboarding
**Features:** Auto-setup script, validation, multi-platform binaries

</td>
</tr>
</table>

<br>

## Architecture Overview

Our projects form an integrated ecosystem for AI-WebAssembly development:

```
┌─────────────────────────────────────────────────────────┐
│  AI Integration Layer                                   │
│  • glsp-mcp: AI-native applications                     │
│  • studio-mcp, timedate-mcp: Production servers         │
└─────────────────────────────────────────────────────────┘
                           ↕
┌─────────────────────────────────────────────────────────┐
│  Protocol & Interface Layer                             │
│  • mcp: Rust framework for MCP servers                  │
│  • wasi-mcp: Standardization for WASI ecosystem         │
└─────────────────────────────────────────────────────────┘
                           ↕
┌─────────────────────────────────────────────────────────┐
│  WebAssembly Runtime Layer                              │
│  • wrt: Safety-critical WASM runtime                    │
│  • loom: Optimization engine                            │
│  • wsc: Component signing & verification                │
└─────────────────────────────────────────────────────────┘
                           ↕
┌─────────────────────────────────────────────────────────┐
│  Build & Developer Tools                                │
│  • rules_wasm_component: Bazel integration              │
│  • bazel-file-ops-component: Cross-platform operations  │
│  • template-mcp-server: Quick start templates           │
└─────────────────────────────────────────────────────────┘
```

<br>

## Vision & Focus Areas

We're exploring what becomes possible when AI systems can safely interact with real-world systems through WebAssembly's security sandbox.

| Focus Area | What We're Building |
|------------|---------------------|
| **Safety-Critical Systems** | Infrastructure for automotive (ASIL-D), medical (IEC 62304), and industrial applications with formal verification and certification frameworks |
| **AI-Native Development** | Tools treating AI agents as first-class participants - from diagram generation to build system integration |
| **Secure Integration** | Capability-based security allowing AI to control physical systems in vehicles, factories, and homes with verifiable safety properties |
| **Universal Portability** | Same code from microcontrollers to cloud infrastructure through WebAssembly's platform independence |

<br>

## Development Maturity

Our projects span different maturity stages, from proposals to production:

| Stage | Projects | Characteristics |
|-------|----------|-----------------|
| **🚀 Production** | mcp framework, studio-mcp, timedate-mcp | Published to registries, real-world deployments, comprehensive testing |
| **🔄 Advanced Beta** | wrt runtime, rules_wasm_component | Near-complete features, extensive infrastructure, production-quality tooling |
| **🚧 Active Development** | glsp-mcp, wsc, bazel-file-ops-component | Core features functional, integration ongoing, clear production path |
| **📝 Proposals & Research** | wasi-mcp, loom | Standards work, proof-of-concept implementations, seeking feedback |
| **🛠️ Developer Tools** | template-mcp-server | Onboarding and productivity tools |

<br>

## Project Metrics

Based on comprehensive codebase analysis:

| Repository | Language | Lines of Code | Commits | Test Coverage | Stage |
|------------|----------|---------------|---------|---------------|-------|
| wrt | Rust | 428,004 | 743 | 100+ test files, 227 Kani harnesses | Advanced Beta |
| mcp | Rust | 102,000 | 317 | 1,071 tests, 80% coverage enforced | Production Beta |
| glsp-mcp | Rust/TypeScript | 63,293 | 221 | Integration tests, UI demos | Advanced MVP |
| rules_wasm_component | Starlark/Rust | 252 files | 519 | 46 test builds, CI/CD | Beta → Production |
| wasi-mcp | WIT | - | - | Spec-complete | Phase 0 Proposal |
| studio-mcp | Rust | - | - | Production deployment | Production |
| wsc | Rust | - | - | Core functional | Active Dev |

<br>

## The Opportunity

Traditional AI systems operate in isolation from real-world systems. WebAssembly's security model offers a path to safely bridge this gap. By treating AI agents as first-class citizens in our infrastructure, we're working toward systems where:

- AI safely controls physical systems in vehicles, factories, and homes through verified WebAssembly components
- Developers build AI-aware applications with cryptographic security guarantees and formal verification
- Code runs consistently from embedded microcontrollers to cloud deployments with identical security properties
- Component composition enables complex AI workflows with modular, auditable security boundaries

<br>

## Technical Foundation

**Languages:** Rust (primary), C++, Go, JavaScript/TypeScript
**WebAssembly:** Component Model, WASI Preview2/3, wasmtime runtime
**Build Systems:** Bazel (bzlmod), Cargo workspaces
**Safety:** Formal verification (Kani), ASIL-D compliance frameworks, capability-based security
**AI Integration:** Model Context Protocol, Ollama LLM, WASI-NN
**Standards:** Active participation in WASI standardization

<br>

---

<div align="center">

*Work in progress. All projects under active development.*

**[Explore Repositories →](https://github.com/orgs/pulseengine/repositories)** | **[MCP Framework Docs](https://docs.rs/pulseengine-mcp-protocol)**

<sub>Built with a focus on safety, security, and enabling new possibilities at the intersection of AI and WebAssembly</sub>

</div>
