<div align="center">

# PulseEngine

### Formally Verified WebAssembly Toolchain

*From component composition to native execution — every transformation proven correct*

<br>

![Rust](https://img.shields.io/badge/Rust-000000?style=flat&logo=rust&logoColor=white)
![WebAssembly](https://img.shields.io/badge/WebAssembly-654FF0?style=flat&logo=webassembly&logoColor=white)
![Bazel](https://img.shields.io/badge/Bazel-43A047?style=flat&logo=bazel&logoColor=white)

<br>

[<kbd> &nbsp; Repositories &nbsp; </kbd>](https://github.com/orgs/pulseengine/repositories) &nbsp;&nbsp; [<kbd> &nbsp; Documentation &nbsp; </kbd>](https://docs.rs/pulseengine-mcp-protocol)

</div>

<br>

## The Toolchain

We build infrastructure for running WebAssembly where correctness is non-negotiable — automotive, medical, industrial, aerospace. Four projects form a pipeline, each stage carrying formal proof of correctness.

```
  Components ───► Meld ───► Loom ───► Kiln     execute
                  fuse      optimize   runtime
                                  └──► Synth    native ARM
                                       compile
```

<br>

<table>
<tr>
<td width="50%" valign="top">

### [Kiln](https://github.com/pulseengine/kiln)

WebAssembly runtime for safety-critical systems. Full Component Model and WASI Preview 2 support with a modular `no_std` architecture built for embedded, automotive, medical, and aerospace environments. Memory safety guaranteed through Kani bounded model checking.

</td>
<td width="50%" valign="top">

### [Meld](https://github.com/pulseengine/meld)

Statically fuses multiple WebAssembly components into a single core module. Eliminates runtime linking entirely — import resolution, index-space merging, and canonical ABI adapter generation happen at build time. Transformation correctness verified through Rocq formal proofs.

</td>
</tr>
<tr>
<td width="50%" valign="top">

### [Loom](https://github.com/pulseengine/loom)

Twelve-pass WebAssembly optimization pipeline built on Cranelift's ISLE pattern-matching engine. Constant folding, strength reduction, CSE, inlining, dead code elimination — each pass proven correct through Z3 SMT verification and Rocq mechanized proofs. Includes a fused mode purpose-built for Meld output.

</td>
<td width="50%" valign="top">

### [Synth](https://github.com/pulseengine/synth)

Compiles WebAssembly to native ARM for embedded Cortex-M targets. Not just translation — program synthesis: exploring equivalent implementations to find provably optimal native code. Z3 translation validation ensures compiled output faithfully preserves WebAssembly semantics.

</td>
</tr>
</table>

<br>

> [!TIP]
> **Correctness at every layer** — Kani bounded model checking in the runtime, Rocq mechanized proofs for fusion and optimization, Z3 SMT verification for compilation. No transformation ships without a proof.

<br>

## Ecosystem

#### Build & Verification

- [**rules_wasm_component**](https://github.com/pulseengine/rules_wasm_component) — Bazel rules for WebAssembly Component Model across Rust, Go, C++, and JavaScript
- [**rules_rocq_rust**](https://github.com/pulseengine/rules_rocq_rust) — Bazel rules for Rocq theorem proving and Rust formal verification
- [**rules_moonbit**](https://github.com/pulseengine/rules_moonbit) — Bazel rules for MoonBit with hermetic toolchain support
- [**wsc**](https://github.com/pulseengine/wsc) — WebAssembly signing and verification with Sigstore/Rekor integration

#### AI & MCP

- [**mcp**](https://github.com/pulseengine/mcp) — Rust framework for building Model Context Protocol servers and clients
- [**glsp-mcp**](https://github.com/pulseengine/glsp-mcp) — AI-native graphical modeling with MCP integration and WebAssembly component execution
- [**wasi-mcp**](https://github.com/pulseengine/wasi-mcp) — Proposed WASI API for Model Context Protocol, targeting Preview 3

#### Developer Tools

- [**thrum**](https://github.com/pulseengine/thrum) — Gate-based pipeline orchestrator for autonomous AI-driven development
- [**temper**](https://github.com/pulseengine/temper) — GitHub App that hardens repositories to organizational standards
- [**wasm-component-examples**](https://github.com/pulseengine/wasm-component-examples) — Working examples for Component Model development in C, C++, Go, and Rust

<br>

---

<div align="center">

<sub>Rust · WebAssembly Component Model · WASI Preview 2/3 · Bazel · Rocq · Z3 · Kani</sub>

</div>
