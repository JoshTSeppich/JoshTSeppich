# Joshua Seppich

I build AI agents and the layer underneath them that lets them operate real software: the part that clicks, types, reads the screen, and knows when to stop and ask a person.

## The idea I keep coming back to

The accessibility tree is the most honest description of a screen. The DOM is whatever a framework emitted this deploy. A screenshot is pixels. The accessibility tree is what a page has to expose to work at all, and it exists for desktop apps too. Three of the repos below are the same idea from different angles.

- **[bankbot](https://github.com/JoshTSeppich/bankbot)** — An LLM drives a legacy bank UI once. The run compiles into a typed, versioned capability that replays with no model in the loop, classifies "no such member" as an answer instead of a crash, and hands the live browser to a human when it is stuck. The model discovers; the artifact is the product.
- **[Lantern](https://github.com/JoshTSeppich/Lantern)** — Fingerprints a web page by tabbing through it and recording the role and state of every element it lands on. 259 tests. Across 40 sites the method found only five shape clusters, which means it under-discriminates on medium pages. I wrote that down instead of tuning until it looked better.
- **[cairn](https://github.com/JoshTSeppich/cairn)** — A Claude Code plugin that packages how I work with agents: no claim without a test, no design without a written decision, no scaffolding before the risky part is proven.

## Other solo work

- **[Conductor](https://github.com/JoshTSeppich/Conductor)** — Runs several Claude Code sessions from one place: a tmux CLI, a daemon, a web dashboard, an Electron workstation. I built it because I was copy-pasting between an architect chat and four terminal panes and the copy-paste was the bottleneck.
- **[Beacon](https://github.com/JoshTSeppich/Beacon)** — Maps a room with sound. One HTML file, no build step. I wanted to know if a laptop microphone was enough. It is, roughly.

## Built for Foxworks

I run [Foxworks](https://foxworks.dev), a one-person shop that builds internal tools for small businesses. These two are its own tooling.

- **[eventfold](https://github.com/JoshTSeppich/eventfold)** — Desktop app that runs B2B prospecting end to end: ICP generation, company search, lead tracking, email drafts.
- **[FindFold](https://github.com/JoshTSeppich/FindFold)** — Command-line pipeline that finds local service businesses that fit a customer profile, scores them cheaply, and only spends model calls on the ambiguous ones.

## How I work

I prove the risky part first, with a throwaway spike, before I scaffold anything. I write the decision down before the code, as an ADR, in one paragraph. I keep one linear main branch and every commit passes the same gate. I use AI tooling for most of the typing and I can explain every line it produced.

## Elsewhere

Northern Utah. I write poetry as J.S. I am usually building something that is not on this page yet.
