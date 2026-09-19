# Joshua Seppich

I build AI agents and the layer underneath them that lets them operate real software: the part that clicks, types, reads the screen, and knows when to stop and ask a person.

## The idea I keep coming back to

The accessibility tree is the most stable description of a screen I've found so far. The DOM is whatever a framework emitted this deploy. A screenshot is pixels. The accessibility tree is what a page has to expose to work at all, and it exists for desktop apps too. Three of the repos below are the same idea from different angles. Lantern's results say where that premise runs out.

- **[bankbot](https://github.com/JoshTSeppich/bankbot)** — An LLM drives a legacy bank UI once. The run compiles into a typed, versioned capability that replays with no model in the loop, classifies "no such member" as an answer instead of a crash, and hands the live browser to a human when it is stuck. The model discovers; the artifact is the product.
- **[Lantern](https://github.com/JoshTSeppich/Lantern)** — Fingerprints a web page by tabbing through it and recording the role and state of every element it lands on. 259 tests. Across 40 sites the method found only five shape clusters, which means it under-discriminates on medium pages. I wrote that down instead of tuning until it looked better.
- **[cairn](https://github.com/JoshTSeppich/cairn)** — A Claude Code plugin that packages how I work with agents: no claim without a test, no design without a written decision, no scaffolding before the risky part is proven.

## Other solo work

- **[Conductor](https://github.com/JoshTSeppich/Conductor)** — Runs several Claude Code sessions from one place: a tmux CLI, a daemon, a web dashboard, an Electron workstation. I built it because I was copy-pasting between an architect chat and four terminal panes and the copy-paste was the bottleneck.
- **[Beacon](https://github.com/JoshTSeppich/Beacon)** — Maps a room with sound from a phone. One HTML file, DSP written by hand. The finding was physical: one phone can't separate its own speaker from its mic, and iOS echo cancellation eats the sweep, so the design moved to two devices.

## Not on GitHub yet — ask me

Private or unfinished, so no links. Each one is a real build I can walk through.

- **Registry** — The design the three repos above are pieces of: turn an application's accessibility tree into a queryable API, so an agent asks "what can I do on this screen" instead of parsing markup. Lantern is its classifier, cairn is the discipline it was built under, bankbot is what it looks like pointed at a bank.
- **RECOGNITION** — A recursive multi-agent orchestrator. Each agent runs with an injected identity, the topology fractures a problem across them and converges the results, and the loop stops on a semantic fixed point instead of a step count.
- **OBAC** — Opacity-Based Agent Chaining. A validation architecture for chains of agents where each link can only see what the previous one chose to expose. Written up with a formal argument, not just a diagram.
- **Counsel AI** — Eviction-defense analysis for Utah tenants: scrapes the case documents, runs them through Claude, produces the arguments a person without a lawyer would otherwise not find. I built it because the people who need it most can't pay for it.
- **A canvassing tool for a school-board race** — FastAPI, Leaflet, SQLite. Built for a campaign; never deployed.

## Built for Foxworks

I run [Foxworks](https://foxworks.dev) with William Travis Stanley; we build internal tools for small businesses. These two are its own tooling.

- **[eventfold](https://github.com/JoshTSeppich/eventfold)** — Desktop app that runs B2B prospecting end to end: ICP generation, company search, lead tracking, email drafts.
- **[FindFold](https://github.com/JoshTSeppich/FindFold)** — Command-line pipeline that finds local service businesses that fit a customer profile, scores them cheaply, and only spends model calls on the ambiguous ones.

## How I work

On bankbot, Lantern and cairn I prove the risky part first with a throwaway spike, write each design decision as a one-paragraph ADR before the code, and every commit passes the same gate (format, lint, strict types, tests — see [bankbot's CI workflow](https://github.com/JoshTSeppich/bankbot/blob/main/.github/workflows/ci.yml)). eventfold and FindFold are working tools I use; each has a small test suite (FindFold around the scoring band, eventfold around the credential fix) and their READMEs say so. I use AI tooling for most of the typing and I can explain every line it produced.

## Elsewhere

Northern Utah. I write poetry as J.S. I am usually building something that is not on this page yet.
