# Joshua Seppich

I build AI agents and the layer underneath them that lets them operate real software: the part that clicks, types, reads the screen, and knows when to stop and ask a person.

## The idea I keep coming back to

The accessibility tree is the most stable description of a screen I've found so far. The DOM is whatever a framework emitted this deploy. A screenshot is pixels. The accessibility tree is what a page has to expose to work at all, and it exists for desktop apps too. Three of the repos below are the same idea from different angles. Lantern's results say where that premise runs out.

- **[bankbot](https://github.com/JoshTSeppich/bankbot)** — An LLM drives a legacy bank UI once, with the run recorded as a typed, versioned artifact that names each control the way a person sees it, so it can be reviewed and rerun. The artifact then replays with no model in the loop, classifies "no such member" as an answer instead of a crash, and hands the live browser to a human when it is stuck. The bank app is mine, a FastAPI app built to be hard to automate: table layouts, an iframe, no ids, and fault-injection endpoints so every failure can be triggered on demand without real member data. The model discovers; the artifact is the product.
- **[Lantern](https://github.com/JoshTSeppich/Lantern)** — Fingerprints a web page by tabbing through it in headless Chromium and recording the role and state of every element it lands on, so two sites with the same interaction shape match even when their markup differs. Built as the upstream classifier for Sherpa, a private browser-agent project, behind one frozen call. 259 tests, run in CI on every push. Across 40 sites the method found only five shape clusters, which means it under-discriminates on medium pages. I wrote that down in the ADRs and paused instead of tuning until it looked better.
- **[cairn](https://github.com/JoshTSeppich/cairn)** — A Claude Code plugin that packages how I work with agents: no claim without a test, no design without a written decision, no scaffolding before the risky part is proven. It ships ten disciplines (anti-fabrication, a confidence label on every claim, a five-verb commit grammar, a nine-question self-check, literal halts) and five agents that enforce them at specific points in a ticket, such as verifying a claim about the codebase with a file and line citation before the session asserts it. I wrote it after watching an assistant fabricate file contents and drift out of scope on a large monorepo.

## Other work

- **[Conductor](https://github.com/JoshTSeppich/Conductor)** — Runs several Claude Code sessions from one place. It grew in layers: `fd`, a CLI that names each tmux session once and then sends prompts and pulls replies without ever calling an LLM itself; a local daemon that watches hand-off files, git refs and status and coordinates sessions over HTTP and WebSocket; a web dashboard on the daemon; and an Electron workstation with an orchestrator chat panel. I built it because I was copy-pasting between an architect chat and four terminal panes and the copy-paste was the bottleneck. The CLI still works with nothing else running.
- **[Beacon](https://github.com/JoshTSeppich/Beacon)** — Maps a room with sound from a phone: it plays an exponential sine sweep, records the reflections, deconvolves an impulse response, and turns the echo peaks into wall distances and a floor plan. One HTML file, DSP written by hand, because the fastest loop for an acoustics experiment on a phone is editing one file. The finding was physical: one phone can't separate its own speaker from its mic, and iOS echo cancellation eats the sweep, so the design moved to two devices paired through a small relay.

## Not on GitHub yet — ask me

Private or unfinished, so no links. Each one is a real build I can walk through.

- **Registry** — The design the three repos above are pieces of: turn an application's accessibility tree into a queryable API, so an agent asks "what can I do on this screen" instead of parsing markup. Lantern is its classifier, cairn is the discipline it was built under, bankbot is what it looks like pointed at a bank.
- **RECOGNITION** — A recursive multi-agent orchestrator. Each agent runs with an injected identity, the topology fractures a problem across them and converges the results, and the loop stops on a semantic fixed point instead of a step count.
- **OBAC** — Opacity-Based Agent Chaining. A validation architecture for chains of agents where each link can only see what the previous one chose to expose. Written up with a formal argument, not just a diagram.
- **Counsel AI** — Eviction-defense analysis for Utah tenants: scrapes the case documents, runs them through Claude, produces the arguments a person without a lawyer would otherwise not find. I built it because the people who need it most can't pay for it.
- **A canvassing tool for a school-board race** — FastAPI, Leaflet, SQLite. Built for a campaign; never deployed.

## Built for Foxworks

I run [Foxworks](https://foxworks.dev) with William Travis Stanley; we build internal tools for small businesses. These two are its own tooling.

- **[eventfold](https://github.com/JoshTSeppich/eventfold)** — Desktop app that runs B2B prospecting end to end: it generates an ideal customer profile from a NAICS code with Claude, pulls matching companies and contacts from Apollo, tracks outreach in a leads table, drafts cold emails, and turns feature ideas into GitHub issues. Tauri v2 around React 18, with Rust for the network calls, an SQLite cache, and the OS keychain for API keys. It replaced five standalone tools that passed data to each other through the clipboard and each kept their own copy of the keys.
- **[FindFold](https://github.com/JoshTSeppich/FindFold)** — Command-line pipeline that scrapes Google Maps or Bing for local service businesses, fetches each homepage, scores it against a customer profile with keyword rules, and sends only the ambiguous band (0.40 to 0.72) to Claude Haiku, ten leads per request. Clear passes and clear fails never cost a model call, and paid Apollo enrichment comes last, only for what survived. It remembers the domains it has already processed so a business is never enriched twice.

## How I work

On bankbot I prove the risky part first with a throwaway spike, write each design decision as a one-paragraph ADR before the code, and every commit passes format, lint, strict types and tests in pre-commit and in CI. Lantern runs its full test suite in CI. cairn is a plugin — markdown and agent definitions — so its check is the manual test plan in the repo, not a CI gate. eventfold and FindFold are working tools I use; each has a small test suite (FindFold around the scoring band, eventfold around the credential fix) and their READMEs say so. I use AI tooling for most of the typing and I can explain every line it produced.

## Elsewhere

Northern Utah. I write poetry as J.S. I am usually building something that is not on this page yet.
