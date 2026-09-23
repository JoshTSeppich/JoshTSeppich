# Joshua Seppich

**AI engineer building agents and the infrastructure that lets them operate real software.**

I work on the layer between an AI model and the systems it needs to use: agent orchestration, browser and desktop automation, accessibility-tree interfaces, deterministic execution, and human-in-the-loop workflows.

I’m especially interested in making computer-use systems more reliable. Models can discover possibilities, but production systems need stronger interfaces, explicit state, evidence, and clear boundaries around when a person must take over.

## Selected work

### [Conductor](https://github.com/JoshTSeppich/Conductor)

A local system for coordinating multiple Claude Code sessions from one place.

It started as a tmux CLI and grew into a daemon, HTTP and WebSocket APIs, a web dashboard, lifecycle state management, and an Electron workstation. It exists to eliminate the mechanical work of moving prompts, handoffs, and status information between parallel coding-agent sessions.

`TypeScript · Node.js · Fastify · WebSocket · React · tmux · Electron`

### [BotWatch](https://github.com/JoshTSeppich/botwatch)

A macOS desktop utility that shows what every Claude Code session is doing.

It reads local Claude Code state, displays active sessions in an always-on-top overlay, tracks waiting and stopped states, estimates token usage, and brings the relevant terminal window to the front.

The project also documents the limits of its security model rather than implying that a same-user local agent can be perfectly contained.

`JavaScript · Electron · macOS APIs`

### [Lantern](https://github.com/JoshTSeppich/Lantern)

An experiment in describing web pages by their **interaction shape** rather than their markup.

Lantern probes pages in headless Chromium, reads the accessibility tree, records the roles and states encountered during interaction, and produces a page fingerprint. The work includes validation spikes, real browser experiments, and documented contract mismatches that stopped downstream implementation until they could be resolved.

The broader thesis is that accessibility trees may be a more stable interface for agents than raw DOM structure or screenshots.

`Python · Playwright · Chromium · accessibility trees`

## Other work

- **[cairn](https://github.com/JoshTSeppich/cairn)** — a Claude Code plugin for evidence-driven agent-assisted development: claim verification, confidence labels, written decisions, impact analysis, test triage, and explicit halt conditions.
- **[bankbot](https://github.com/JoshTSeppich/bankbot)** — an experiment in compiling one model-guided browser run into a typed, versioned capability that can replay without a model in the production loop.
- **[FindFold](https://github.com/JoshTSeppich/FindFold)** — a prospecting pipeline that uses deterministic filtering first and reserves model calls for ambiguous candidates.
- **[Beacon](https://github.com/JoshTSeppich/Beacon)** — a browser-based acoustics experiment for estimating room geometry from recorded impulse responses.

## Foxworks

I run [Foxworks](https://foxworks.dev) with William Travis Stanley. We build internal tools and automation for small businesses.

- **eventfold** — a desktop B2B prospecting application built with Tauri, React, Rust, and SQLite.
- **FindFold** — a command-line pipeline for discovering and qualifying local service businesses.

## How I work

I try to prove the riskiest assumption before building the surrounding system.

That usually means:

- writing important design decisions down before implementation
- keeping commits small and explainable
- separating model-guided discovery from deterministic execution
- running formatting, linting, type checks, tests, and security checks automatically
- documenting failed experiments and known limitations
- treating confidence and evidence as part of the engineering output

I use AI tooling heavily, but generated code is not evidence that something works.

## Elsewhere

Northern Utah · I write poetry as **J.S.**

I am usually building something that is not on this page yet.
