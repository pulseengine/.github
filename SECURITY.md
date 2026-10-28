# Security policy

This policy applies to every repository in the PulseEngine organisation that does not have its own `SECURITY.md`.

PulseEngine is a WebAssembly Component Model engine for safety-critical systems. It is work in progress, and no part of it is certified for production use. We still want to hear about security problems early.

## Reporting a vulnerability

Report it privately through GitHub:

1. Open the affected repository on GitHub.
2. Go to the **Security** tab and choose **Report a vulnerability**.
3. Describe the problem, the affected version or commit, and how to reproduce it if you can.

Please do **not** open a public issue, pull request or discussion for a vulnerability. If you are not sure which repository is affected, report it in the one that seems closest. We will move it if needed.

## What to expect

- We confirm receipt within a few working days. The project is run by a small team, so please allow for that.
- We assess the report and keep you informed in the private advisory thread.
- We fix the problem and publish a GitHub Security Advisory, with credit if you want it.

## Scope

In scope:

- the engine and its tools (for example meld, loom, synth, kiln, sigil, rivet, spar, witness);
- their release artifacts and CI workflows;
- the `pulseengine-claude` plugin published from `pulseengine/pulseengine.eu`.

Out of scope:

- forks of third-party projects in this organisation. Report those upstream.
