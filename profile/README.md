<div align="center">

# PulseEngine

<sup>A WebAssembly Component Model toolchain for safety-critical systems, with formally verified components</sup>

&nbsp;

![Rust](https://img.shields.io/badge/Rust-CE422B?style=flat-square&logo=rust&logoColor=white&labelColor=1a1b27)
![WebAssembly](https://img.shields.io/badge/WebAssembly-654FF0?style=flat-square&logo=webassembly&logoColor=white&labelColor=1a1b27)
![Bazel](https://img.shields.io/badge/Bazel-43A047?style=flat-square&logo=bazel&logoColor=white&labelColor=1a1b27)

[<kbd> &nbsp; Repositories &nbsp; </kbd>](https://github.com/orgs/pulseengine/repositories) &nbsp;&nbsp; [<kbd> &nbsp; Website &nbsp; </kbd>](https://pulseengine.eu) &nbsp;&nbsp; [<kbd> &nbsp; How it works &nbsp; </kbd>](https://pulseengine.eu/how-it-works/) &nbsp;&nbsp; [<kbd> &nbsp; Examples &nbsp; </kbd>](https://github.com/pulseengine/wasm-component-examples)

</div>

&nbsp;

## The pipeline

Components are composed at build time and lowered to native code — the interface boundaries exist while you build and are gone when you ship.

```
components ──▶ meld ──▶ loom ──▶ synth ──▶ native
                fuse    optimize  compile
                                            kiln — interpret, on host or device
```

Everything the pipeline produces is signed and attested by **sigil**; everything it claims is traced by **rivet**.

| | |
|---|---|
| [**meld**](https://github.com/pulseengine/meld) | Statically fuses WebAssembly components into one core module — import resolution, index-space merging, canonical-ABI adapter generation at build time, so nothing links at runtime. |
| [**loom**](https://github.com/pulseengine/loom) | WebAssembly optimizer. Each rewrite is checked by SMT translation validation *per run* — a validated pass, not a verified tool. |
| [**synth**](https://github.com/pulseengine/synth) | **Transcodes** WebAssembly to native ARM and RISC-V via program synthesis, targeting bare-metal Cortex-M/R. Declines an operation loudly rather than emitting code it cannot justify. |
| [**kiln**](https://github.com/pulseengine/kiln) | WebAssembly interpreter and runtime — full Component Model and WASI 0.2, with a `no_std` path for embedded. |
| [**sigil**](https://github.com/pulseengine/sigil) | Signing and attestation. Each stage records what changed, which tool version ran, and the hashes in and out; signatures embed in the module itself, and verification works offline for air-gapped devices. |

&nbsp;

## Verification

Different techniques, named separately — because they prove different things.

| | |
|---|---|
| [**rivet**](https://github.com/pulseengine/rivet) | Typed SDLC artifacts and traceability. Requirements, design, verification and their links as a checked graph; release readiness is a query over closed evidence rather than a date. |
| [**witness**](https://github.com/pulseengine/witness) | MC/DC structural coverage measured on the **lowered WebAssembly the runtime executes**, not on the source it came from. |
| [**scry**](https://github.com/pulseengine/scry) | Sound abstract interpretation — over-approximates, so it never misses a behaviour that can occur. Mechanized Rocq soundness proofs for specific domains. |
| [**ordeal**](https://github.com/pulseengine/ordeal) | Certificate-checked QF_BV SMT. The solver is untrusted; an independent, formally-verified LRAT checker re-derives every UNSAT. |
| [**spar**](https://github.com/pulseengine/spar) | Architecture models — AADL v2.3, SysML v2, CAN-DBC — with 30+ analyses including scheduling, fault trees and network-calculus timing bounds, and Lean proofs of the analyses themselves. |
| [**gale**](https://github.com/pulseengine/gale) | Formally verified Rust replacements for Zephyr RTOS kernel primitives (Verus + Rocq + Lean), composing toward `gust` — an OS built from verified components. |

> **What "verified" means here.** Verus (SMT, partial correctness, declared trusted base) · Kani (**bounded** model checking) · Rocq and Lean (specific theorems) · translation validation (per run, not the tool) · sound static analysis. Specific properties of specific components are proven. The toolchain as a whole is not, and we don't claim it is — see the [preprint](https://pulseengine.eu/publications/) for where the gates are still weak.

&nbsp;

## Applied

| | |
|---|---|
| [**relay**](https://github.com/pulseengine/relay) | Flight software as WebAssembly components, inspired by NASA's cFS. |
| [**wohl**](https://github.com/pulseengine/wohl) | OTA update and device lifecycle. |
| [**jess**](https://github.com/pulseengine/jess) | Hardware integration — getting verified components onto real boards and into flight. |

&nbsp;

<details>
<summary><b>Build &amp; toolchain</b></summary>

&nbsp;

- [**varve**](https://github.com/pulseengine/varve) — pinned, signed, dated toolchain bundles; projects freeze on a layer and stay there *(design)*
- [**rules_wasm_component**](https://github.com/pulseengine/rules_wasm_component) — Bazel rules for the Component Model across Rust, Go, C++, JavaScript
- [**rules_rocq_rust**](https://github.com/pulseengine/rules_rocq_rust) · [**rules_verus**](https://github.com/pulseengine/rules_verus) · [**rules_lean**](https://github.com/pulseengine/rules_lean) · [**rules_ordeal**](https://github.com/pulseengine/rules_ordeal) — hermetic Bazel rules for the proof and verification toolchains
- [**temper**](https://github.com/pulseengine/temper) — GitHub App that holds repositories to organizational standards

</details>

<details>
<summary><b>Agents &amp; MCP</b></summary>

&nbsp;

- [**mcp**](https://github.com/pulseengine/mcp) — Rust framework for Model Context Protocol servers and clients
- [**template-mcp-server**](https://github.com/pulseengine/template-mcp-server) — scaffolding for a new MCP server

</details>

<details>
<summary><b>Examples &amp; utilities</b></summary>

&nbsp;

- [**wasm-component-examples**](https://github.com/pulseengine/wasm-component-examples) — Component Model examples in C, C++, Go, Rust
- [**bazel-file-ops-component**](https://github.com/pulseengine/bazel-file-ops-component) — cross-platform file operations for Bazel, as a Wasm component

</details>

&nbsp;

---

<div align="center">

<sub>Rust · WebAssembly Component Model · WASI 0.2 · Bazel · Verus · Rocq · Lean · Kani · Sigstore</sub>

<sub>Everything is work in progress. Claims are scoped to what is checked.</sub>

</div>
