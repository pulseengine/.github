<div align="center">

# PulseEngine

### Infrastructure for AI and WebAssembly Integration

*Building secure, portable systems where AI agents interact safely with real-world applications*

<br>

![Rust](https://img.shields.io/badge/Rust-000000?style=flat&logo=rust&logoColor=white)
![WebAssembly](https://img.shields.io/badge/WebAssembly-654FF0?style=flat&logo=webassembly&logoColor=white)
![Bazel](https://img.shields.io/badge/Bazel-43A047?style=flat&logo=bazel&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)

</div>

<br>

## What We're Building

PulseEngine develops infrastructure at the intersection of AI and WebAssembly. Our work ranges from experimental proposals to production-tested implementations, focused on enabling AI systems to safely interact with real-world systems through WebAssembly's capability-based security model.

<br>

## Projects

<table>
<tr>
<td width="50%">

### [wrt](https://github.com/pulseengine/wrt)
**WebAssembly Runtime**

Safety-critical runtime supporting Core WebAssembly and Component Model. Designed for ASIL-B compliance with Control Flow Integrity, fuel-based execution limiting, and `no_std` support.

**Status:** 95% complete
**Target:** Embedded and safety-critical systems

</td>
<td width="50%">

### [mcp](https://github.com/pulseengine/mcp)
**Rust MCP Framework**

Framework for building Model Context Protocol servers. Extracted from a production home automation server with 30+ tools. Works with MCP Inspector, Claude Desktop, and HTTP clients.

**Status:** Production-tested
**Maturity:** Most stable project

</td>
</tr>
<tr>
<td width="50%">

### [glsp-mcp](https://github.com/pulseengine/glsp-mcp)
**AI-Native Graphical Modeling**

First AI-native implementation of Graphical Language Server Protocol using MCP. Enables AI agents to create and manipulate diagrams through natural language. Includes WebAssembly-based ADAS simulation.

**Status:** Functional MVP
**Innovation:** AI-native diagramming

</td>
<td width="50%">

### [rules_wasm_component](https://github.com/pulseengine/rules_wasm_component)
**Bazel Build Rules**

Modern Bazel rules for WebAssembly components with multi-profile support. Delivers 73% faster builds and 99% less disk usage through symlink optimization.

**Status:** Active development
**Supports:** Rust, C/C++, Component Model

</td>
</tr>
<tr>
<td colspan="2">

### [wasi-mcp](https://github.com/pulseengine/wasi-mcp)
**WASI API Proposal**

Proposed WebAssembly System Interface API for Model Context Protocol, targeting WASI Preview3. Aims to standardize how WebAssembly components act as MCP servers and clients.

**Status:** Early-stage proposal
**Goal:** Standardization for WASI ecosystem

</td>
</tr>
</table>

<br>

## Architecture

Our projects form an integrated stack:

```
┌─────────────────────────────────────────────────┐
│         Application Layer                       │
│  glsp-mcp: AI-native applications               │
└─────────────────────────────────────────────────┘
                      ↕
┌─────────────────────────────────────────────────┐
│         Bridge Layer                            │
│  mcp: AI-system integration                     │
│  wasi-mcp: Standardized interface               │
└─────────────────────────────────────────────────┘
                      ↕
┌─────────────────────────────────────────────────┐
│         Foundation Layer                        │
│  wrt: Safety-critical WASM runtime              │
└─────────────────────────────────────────────────┘
                      ↕
┌─────────────────────────────────────────────────┐
│         Developer Experience                    │
│  rules_wasm_component: Build tooling            │
└─────────────────────────────────────────────────┘
```

<br>

## Vision

We're exploring what becomes possible when AI systems can safely interact with real-world systems through WebAssembly's security sandbox.

**Our focus areas:**

| Area | Description |
|------|-------------|
| **Safety-Critical Systems** | Infrastructure for automotive (ASIL-B), medical, and industrial applications |
| **AI-Native Development** | Tools that treat AI agents as first-class participants |
| **Secure Integration** | Capability-based security for AI-to-system interaction |
| **Universal Portability** | Same code from embedded devices to cloud servers |

<br>

## Current Status

| Stage | Projects |
|-------|----------|
| ✅ **Production** | MCP framework (30+ tools in production) |
| 🔄 **Near Complete** | WRT runtime (95% done, addressing final issues) |
| 🚧 **Active Development** | Bazel rules, GLSP-MCP platform |
| 📝 **Proposal** | WASI-MCP standardization |

<br>

## The Opportunity

Traditional AI systems operate in isolation from real-world systems. WebAssembly's security model offers a path to safely bridge this gap. By treating AI agents as first-class citizens in our infrastructure, we're working toward systems where:

- AI safely controls physical systems in vehicles, factories, and homes
- Developers build AI-aware applications with security guarantees
- Code runs consistently from microcontrollers to cloud infrastructure

<br>

---

<div align="center">

*Work in progress. Contributions welcome.*

[Explore Our Repositories →](https://github.com/orgs/pulseengine/repositories)

</div>