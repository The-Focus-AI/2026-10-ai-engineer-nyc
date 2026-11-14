# AI Engineer New York 2026 — Public Archive

**Live Archive:** **[https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/)**

Field guide, cross-talk synthesis, scrollytelling talk stories, stage slides, and verbatim evidence from **AI Engineer New York 2026** (October 12–14, 2026 · New York Marriott Marquis), compiled and published by **[TheFocus.AI](https://thefocus.ai)**.

## Explore the Archive

- **[Themes Explorer (Front Page)](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/)** — Interactive synthesis of all 8 architectural shifts, 5 contested fault lines, and 176 verbatim claim atoms.
- **[Guided Summit Presentation](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/atlases/conference-themes/page.html)** — Scrollytelling walkthrough of the conference's overarching thesis with stage slides and speaker quotes.
- **[Talks Directory](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/site/talks/index.html)** — 31 scrollytelling talk stories paired with official video stills, verified dossiers, and full Qwen3-ASR transcripts (plus 1 photo-captured workshop).
- **[Full Conference Schedule](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/site/schedule.html)** & **[Interactive Field Guide](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/site/index.html)** — All 167 sessions across 4 days and 161 speakers.
- **[Speaker Roster](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/site/people.html)** — Every speaker, session link, and social handle.

## Corpus Snapshot

| Metric | Count | Source of Truth |
| --- | --- | --- |
| Schedule sessions | **167** (Oct 11–14, 2026 · 161 speakers) | `state/world-model/conference-schedule/published/` |
| Recorded & transcribed talks | **31** (**95,224** Qwen3-ASR words) | `talks/*/transcript.md` |
| Scrollytelling talk stories | **31** (with extracted stage slides) | `talks/*/story.md`, `talks/*/experience/page.html` |
| Verbatim claim atoms | **176** (anchored to transcript timestamps) | `state/world-model/talk-insights/published/claims.json` |
| Synthesized themes & atlases | **8** theme deep dives + **1** master atlas | `analysis/themes.md`, `atlases/*/page.html` |
| Contested fault lines | **5** multi-speaker architectural debates | `state/world-model/conference-themes/published/contested.json` |

## The 8 Architectural Shifts

1. **[Bootstrapping Domain Evals Without Public Benchmarks](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/atlases/bootstrapping-domain-evals-without-public-benchmarks/page.html)** *(11 talks)* — Public benchmarks never measure a team's real task, so builders engineer bespoke evaluation loops: synthesizing inputs from known answers, replaying historical outages, backtesting dated web snapshots, and grading trajectories with behavior rubrics.
2. **[Token Economics, Right-Sizing, and Open Foundations](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/atlases/token-economics-right-sizing-and-open-foundations/page.html)** *(10 talks)* — As frontier intelligence commoditizes while aggregate token bills surge, durable economics come from attributing spend per workload, routing subtasks to fast specialist or open-weight models, tuning KV caches, and owning a model-swappable stack.
3. **[Sandboxed Computers, Context Architecture, and the Shrinking Harness](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/atlases/sandboxed-computers-context-architecture-and-the-shrinking-harness/page.html)** *(9 talks)* — As frontier models absorb prompt-level coding tricks, the durable agent harness converges on isolated create-run-delete VM sandboxes and outer-loop context engines that supply institutional intent and living codebase maps.
4. **[Bounded Autonomy, Runtime Governance, and the Enterprise Diffusion Gap](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/atlases/bounded-autonomy-runtime-governance-and-the-enterprise-diffusion-gap/page.html)** *(8 talks)* — Outside software engineering, non-deterministic workers require institutional trust infrastructure—automatic registries, build-time policy DAGs, risk-tiered entitlements, and opinionated workflows—between reckless autonomy and paralyzing lockdown.
5. **[Deterministic Verification Loops Over Line-by-Line Review](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/atlases/deterministic-verification-loops-over-line-by-line-review/page.html)** *(8 talks)* — Because coding agents generate pull requests far faster than humans can read them, shipping confidence moves into independent, multi-layered verification harnesses and runnable behavioral proofs rather than manual diff inspection.
6. **[Self-Improving Fleets and the Agent Manager](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/atlases/self-improving-fleets-and-the-agent-manager/page.html)** *(8 talks)* — Software engineering shifts from writing code locally to managing asynchronous cloud agent fleets and closing the trace-to-skill loop—centralizing transcripts, grading runs post-merge, and distilling recurring failures into versioned skills.
7. **[Governed Ontologies, Provenance, and Financial Workbenches](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/atlases/governed-ontologies-provenance-and-financial-workbenches/page.html)** *(5 talks)* — In institutional investing and private markets, agents earn front-office trust only atop governed firm ontologies, validated golden sources, unified MCP connectors, and hybrid code-ML-LLM-human pipelines.
8. **[Spatiotemporal World Models and Real-Time Simulation](https://the-focus-ai.github.io/ai-engineer-nyc-2026-oct/atlases/spatiotemporal-world-models-and-real-time-simulation/page.html)** *(2 talks)* — Scaling laws extend beyond turn-based text to continuous video and action streams, turning pixels-to-actions policies and next-frame predictors into real-time world simulators.

---

## Reproducibility & Architecture

This archive is an [OpenProse](https://prose.md) build derived from [`The-Focus-AI/conference-reporter`](https://github.com/The-Focus-AI/conference-reporter). Every claim atom, dossier link, and theme synthesis keeps its verbatim transcript citation and world-model receipt under `state/world-model/`.

```mermaid
flowchart TB
  subgraph sources["Sources"]
    page["Conference schedule"]
    memos["Room recordings (Qwen3-ASR)"]
    videos["Official video stills"]
    notes["Operator notes & photo manifest"]
  end
  subgraph truth["state/world-model (durable truth)"]
    sched["conference-schedule"]
    intake["recording-intake"]
    media["talk-links & talk-photos"]
    atoms["talk-insights (176 claims)"]
    synth["conference-themes (8 themes)"]
  end
  subgraph views["Published Archive"]
    hub["index.html & site/"]
    stories["talks/*/story.md & experience/"]
    atlases["atlases/*/page.html"]
  end

  page --> sched --> hub
  memos --> intake --> media --> hub
  intake --> atoms --> synth --> hub
  intake --> stories
  videos --> stories
  synth --> atlases
  notes --> media
```

### Repository Layout

| Path | Description |
| --- | --- |
| `index.html` | Archive front page: interactive themes explorer, fault lines, and talk matrix. |
| `atlases/<slug>/` | Master summit presentation (`conference-themes`) and 8 theme deep-dive presentations. |
| `talks/<date>-<slug>/` | Per-talk `transcript.md` (verbatim Qwen3-ASR evidence), `links.md` (verified dossier), `story.md`, and `experience/page.html` + stage slide `.jpg` stills. |
| `analysis/themes.md` | Cross-talk synthesis with verbatim quotes, timestamps, contested debates, and singletons. |
| `brief/` | Readable `schedule.md` and append-only `changes.md`. |
| `site/` | Rendered schedule grid (`schedule.html`), interactive planner (`index.html`), speaker directory (`people.html`), talk evidence hubs (`site/talks/*.html`), and shared cross-reference bundle (`xref.js`). |
| `state/world-model/<node>/` | Versioned JSON truth and cryptographic receipt ledgers (`receipts.jsonl`) for all 9 pipeline nodes. |
| `src/` | OpenProse `.prose.md` contracts governing schedule extraction, intake, dossiers, claims, and themes. |

Raw audio (`recordings/**/*.m4a`) and full-resolution camera originals (`photos/PXL_*`, `talks/*/photos/`) are excluded via `.gitignore`; their SHA-256 hashes, durations, timestamps, and transcripts are preserved in `recordings/inbox/` and `photos/manifest.json`.

### Run the pipeline

Toolchain dependencies (`bun` and `yt-dlp`) are pinned in `mise.toml`:

```bash
mise install
bun install
```

Re-render all HTML views locally from the committed world-model and markdown sources:

```bash
mise run views                 # runs render-site.ts + render-pages.ts
```

Verify contracts, world-model validators, canonicalizer fingerprints, and TypeScript types:

```bash
mise run contracts             # lint every OpenProse contract under src/
mise run validate              # validate compiled manifest and trigger plan (when dist/ is compiled)
mise run fingerprints          # check canonicalizer sensitivity (when dist/ is compiled)
mise run typecheck             # tsc --noEmit
```

> **`prose compile` and `prose run <contract>`** execute inside an OpenProse-capable coding agent session (see [`AGENTS.md`](AGENTS.md) and [`docs/USAGE.md`](docs/USAGE.md)).

### Toolchain

Bun and TypeScript, pinned via `mise`. Static views are pre-rendered locally with zero runtime framework dependencies and deployed directly to GitHub Pages via [`.github/workflows/pages.yml`](.github/workflows/pages.yml).

### Further Documentation

| Document | Purpose |
| --- | --- |
| [`MAP.md`](MAP.md) | Path index, join keys (`session_id`, `slug`, `claim_id`), and world-model layout. |
| [`TALKS.md`](TALKS.md) | Verbatim subsequence invariants for talk transcripts, stories, and scrollytelling pages. |
| [`FRAMEWORK.md`](FRAMEWORK.md) | Editorial pipeline from raw capture to claim atoms, themes, and atlases. |
| [`docs/USAGE.md`](docs/USAGE.md) | Operator guide for live conference capture, Qwen3-ASR transcription, and publishing. |
