# PulseEngine: AI + WebAssembly Infrastructure (Work in Progress)

**Building the intersection of AI and WebAssembly - from safety-critical runtimes to AI-native applications**

## About PulseEngine

PulseEngine is developing infrastructure at the intersection of AI and WebAssembly. Our projects range from experimental proposals to battle-tested implementations, all focused on enabling AI systems to safely interact with real-world systems through WebAssembly's security model.

## Our Projects

### 🔧 [wrt](https://github.com/pulseengine/wrt) - WebAssembly Runtime (95% complete)
A safety-critical WebAssembly runtime supporting both Core WebAssembly and Component Model. Designed for ASIL-B compliance with features like Control Flow Integrity, fuel-based execution limiting, and support for no_std environments. Nearly production-ready for embedded and safety-critical applications.

### 🤖 [mcp](https://github.com/pulseengine/mcp) - Rust MCP Framework (Production-tested)
A comprehensive framework for building Model Context Protocol servers in Rust. Extracted from a real-world home automation server with 30+ tools that successfully integrates with MCP Inspector, Claude Desktop, and HTTP clients. The most mature of our projects.

### 🎨 [glsp-mcp](https://github.com/pulseengine/glsp-mcp) - AI-Native Graphical Modeling (MVP)
World's first AI-native implementation of the Graphical Language Server Protocol using MCP. Enables AI agents to create and manipulate diagrams through natural language. Includes a WebAssembly-based ADAS demo showing how WASM components can simulate automotive systems. Functional MVP demonstrating the concept.

### 🏗️ [rules_wasm_component](https://github.com/pulseengine/rules_wasm_component) - Bazel Build Rules (Active Development)
Modern Bazel rules for building WebAssembly components with multi-profile support. Features 73% faster builds and 99% less disk usage through symlink optimization. Supports Rust, C/C++, and provides seamless integration with the Component Model toolchain.

### 📐 [wasi-mcp](https://github.com/pulseengine/wasi-mcp) - WASI API Proposal (Early Stage)
A proposed WebAssembly System Interface API for the Model Context Protocol, targeting WASI Preview3. This early-stage proposal aims to standardize how WebAssembly components can act as MCP servers and clients, leveraging WASI's security model for safe AI integration.

## Our Vision

We're exploring what happens when AI systems can safely interact with real-world systems through WebAssembly's security sandbox. Our work spans:

- **Safety-Critical Systems**: Building infrastructure suitable for automotive, medical, and industrial applications
- **AI-Native Development**: Creating tools that assume AI agents are first-class participants in the development process
- **Secure Integration**: Using WebAssembly's capability-based security for safe AI-to-system interaction
- **Universal Portability**: Write once, run anywhere - from embedded devices to cloud servers

## The Rhythm of Our Work

Looking across our repositories, there's a clear pattern:

1. **Foundation Layer**: WRT provides the bulletproof WebAssembly runtime that everything builds on
2. **Bridge Layer**: MCP and WASI-MCP enable AI systems to interact with WebAssembly components
3. **Application Layer**: GLSP-MCP demonstrates AI-native applications built on this infrastructure
4. **Developer Experience**: Bazel rules make it practical to build and deploy these systems

Each project reinforces the others, creating a cohesive ecosystem for AI-WebAssembly integration.

## Project Status

- ✅ **Production-Ready**: MCP Rust framework (extracted from working system)
- 🔄 **Nearly Complete**: WRT WebAssembly runtime (95% done, fixing final issues)
- 🚧 **Active Development**: Bazel build rules, GLSP-MCP platform
- 📝 **Early Proposal**: WASI-MCP standardization effort

## Why This Matters

Traditional AI systems are limited by their isolation from real-world systems. WebAssembly's security model offers a unique opportunity to safely bridge this gap. By building infrastructure that assumes AI agents are first-class citizens, we're working toward a future where:

- AI can safely control physical systems in cars, factories, and homes
- Developers can build AI-aware applications with confidence in their security
- The same code runs everywhere from tiny embedded devices to massive cloud deployments

## Get Involved

This is all work in progress, and we're excited about where it's heading. Whether you're into AI, WebAssembly, safety-critical systems, or just think this intersection is as cool as we do - there's plenty to explore and contribute to.

Check out our individual repositories for detailed documentation, examples, and contribution guidelines.

---

*Building the infrastructure for a future where AI and WebAssembly work together seamlessly and safely.*