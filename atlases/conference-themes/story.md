---
title: "Eight Shifts from AI Engineer New York 2026"
kind: conference-atlas-story
phase: archive
talks: 31
claims: 176
---

# Eight shifts from AI Engineer New York 2026

Across 31 recorded talks, 95,224 spoken words, and 176 transcript-verified claims, New York’s engineering rooms converged on one reckoning: generating code and prose is now cheap, so the real engineering work has moved into synthetic domain evals, sandboxed computers, deterministic verification gates, runtime risk governance, and self-improving agent fleets.

## Opening synthesis: Generation got cheap, so confidence became the bottleneck

Across 31 recorded sessions and 176 transcript-verified claims, New York's engineering rooms reported the same inversion: generating code and prose is cheap, so engineering effort has shifted to synthetic domain evals, right-sized serving, sandboxed computers, runtime governance, deterministic verification, governed ontologies, and self-improving agent fleets.

> “And yes, it did do something to the UI, but we didn't check the other half. And so it was never persisted, and we lost that email.” — Nick Nisi, Zack Proser (Beyond “Done”: Building Verification Loops for AI Agents, 00:02:47)

## Theme 01: Bootstrapping Domain Evals Without Public Benchmarks (11 talks, 21 claims)

**Public benchmarks never measure a team's real task, so builders must engineer bespoke evaluation loops—synthesizing inputs from known answers, replaying historical outages, backtesting dated web snapshots, and grading trajectories with behavior rubrics—or redesign the agent until it is evaluable.**

Across enterprise RAG, legal review, creative writing, code review, accounting, and quantitative investing, speakers converged on the same wall: off-the-shelf benchmarks tell you nothing about whether your agent works, and domain experts cannot hand-grade thousands of runs. Air Canada inverted dataset creation by generating questions from known source pages and populating legal templates with clauses engineered to breach or pass rules, even re-architecting an agent purely to make it deterministically evaluable. Greptile benchmarks prompt changes against historical outage-causing PRs; Bridgewater hand-labeled 200 investment queries in a week to lift precision@10 from 60% to 95%; Exa Snapshot backtests predictive agents against 400 billion dated web pages without lookahead leakage; Towards AI runs five drafts per prompt under a two-stage cross-family rubric; and Basis grades ground-truth-free production runs with behavior specs and trajectory forking. The sharp counter-position centers on the grader itself: Sonar and Air Canada both showed that uncalibrated LLM-as-judge verdicts flip across identical runs and add noise rivaling the agent's own error rate.

> “The original design we could not evaluate it. We switched to something that we can actually evaluate because of that.” — Nathanael Weill (Write the Answer First: Generating Eval Datasets for Agents With No Benchmark, 00:17:13)

> “And you can say, in this particular trajectory, whether that is in any trajectory that doesn't have a ground truth, did the agent get into a situation in which this behavior was relevant?” — Mitchell Troyanovsky (Process Supervision for Agents That Do Long-Horizon Work, 00:12:01)

## Theme 02: Token Economics, Right-Sizing, and Open Foundations (10 talks, 25 claims)

**As frontier intelligence commoditizes while aggregate token bills surge, durable economics come from attributing spend per workload, routing subtasks to fast specialist or open-weight models, tuning serving concurrency and KV caches, and owning a model-swappable stack rather than renting lock-in from frontier labs.**

Practitioners attacked runaway inference costs across every layer below default frontier API calls. Featherless showed that splitting API keys by department, reserving superlinear low-latency serving (3x cost per 2x speed) for interactive paths, and leveraging higher tokens-per-second to entice developers onto smaller worker models deliver immediate ROI. Runpod's BenchPod tunes vLLM nightly builds, batch-token concurrency, and 4xH200 DeepSeek deployments live without 30-minute cold starts; Greptile routes 20 review subtasks across small and frontier models; Exa cuts trajectory tokens 95% via dynamic snippet highlights; Towards AI merges ten cheap GLM/Flash drafts with one high-thinking pass; and Ramp pairs frontier orchestrators with post-trained 35B Qwen models, 5x-cheaper open-weight security swarms, and semantic spend taxonomies—even as Apify warned that heavily subsidized flat-rate plans distort build-versus-buy incentives. Strategically, Nous Research argued that shrinking token margins force frontier labs to seek lock-in at the enterprise agent layer and compete vertically, making open, model-agnostic foundations essential. The counter-arguments cut both ways: naive turn-by-turn multi-model routing destroys prefix KV-cache hit rates, while falling frontier unit prices tempt teams to scale on frontier platforms rather than maintain custom post-training.

> “It's not even close, like a rule of thumb that I sometimes say, right: for every two x of speed, it's three x of cost” — Eugene Cheah (The AI Bill Is Too Damn High – Tokenomics 101, 00:28:40)

> “If you think back to those two slides I showed, where the choice of harness did not make a significant difference in eval scores, both of those studies actually found that there was a significant difference in costs for tasks.” — Jediah Katz (The Model Ate the Coding Harness. Now What?, 00:11:59)

## Theme 03: Sandboxed Computers, Context Architecture, and the Shrinking Harness (9 talks, 18 claims)

**As frontier models absorb prompt-level coding tricks through a user-trajectory data flywheel, the durable agent harness converges on two layers models cannot internalize: isolated create-run-delete VM sandboxes and outer-loop context engines that supply institutional intent, living codebase maps, and precomputed KV caches.**

OpenHands framed the central paradox of 2026 harness design: coding scaffolding makes harder tasks tractable, user trajectories feed model post-training, and models absorb those habits until harness choice barely moves coding benchmark scores—motivating self-cleaning guardrail shims that watcher bots delete once newer models stop triggering them. What models cannot absorb defines the lasting architecture. First is the execution boundary: Daytona showed that every competing framework reduces to create-run-delete VM primitives and is actively deleting local executors because embedded runtimes still expose host tools and a single allowed `python -c` command compromises the host; Arize and Greptile isolate every run in disposable sandboxes while persisting memory externally. Second is outer-loop context: Linear showed that five-cent intelligence shifts failure from coding capacity to product incoherence unless triage agents assemble customer value, logs, and prior decisions upfront; Greptile replaces grep with a living company wiki; Sonar Vortex feeds structural maps in-loop to cut token spend 36%; Ramp compresses 20–30x month-end context into offline KV-cache cartridges; GEICO routes edge-case HTML worksheets to domain owners; and Basis treats every working-window token as runtime training data. Yet as OpenHands noted in counter-point, entering unmastered domains like autonomous multi-agent colleagues immediately forces teams to re-add heavy prompting, coordinator hierarchies, and guardrails.

> “these tools that your agent will call inside that runtime will actually run on your device outside that runtime.” — Mislav Ivanda (Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On, 00:03:28)

> “really think of the context that agent is going to see as it's working as runtime training data. The word prompt, I think, trivializes it a bit, right?” — Mitchell Troyanovsky (Process Supervision for Agents That Do Long-Horizon Work, 00:09:16)

## Theme 04: Bounded Autonomy, Runtime Governance, and the Enterprise Diffusion Gap (8 talks, 24 claims)

**Outside software engineering, enterprise agents remain near 5% production adoption not for lack of raw model intelligence, but because non-deterministic workers require institutional trust infrastructure—automatic registries, build-time policy DAGs, risk-tiered entitlements, and opinionated workflows—between reckless autonomy and paralyzing lockdown.**

Tenex quantified the conference's starkest macro reality: across roughly 100 large enterprises, general-purpose LLM access sits near 90% and coding agents near 50%, yet autonomous agents in non-engineering business workflows sit around 5%. Anthropic, Apollo, GEICO, Basis, and Apify all traced that diffusion gap to governance, process, and trust friction rather than model IQ—with Apify showing that even after eighteen months of agent payment standards, 30-day volume sits near $1M on x402 and $1,500 on MPP because static API keys, untrusted endpoints requiring marketplace middlemen, and deferred-settlement double-spend risks dominate the funnel. The architectural remedy across regulated firms was bounded autonomy: Two Sigma replaces months-long manual review queues and rubber-stamp approval fatigue with automatic framework registration, risk-scored scrutiny, registry-compiled runtime entitlements, and conservative classifiers that escalate only ambiguous calls; Coinbase separates build-time normative policy ('the original institutional system prompt') from mutating runtime state inside compliance DAGs; Basis encodes opinionated, auditable tax and accounting workflows rather than 'Move 37' creativity; and Anthropic scopes financial agents with least-privilege identities and deterministic hooks gated on advisor or SME sign-off. Qualifying this optimism, Daytona showed that host-level policy allowlists collapse if an interpreter command is permitted, while GEICO's one-day war rooms proved outer-loop enterprise inertia can be broken when decision-makers sit inside the loop.

> “And then, if you just have policy documents that you just look at, or that are part of your specification for the prompts, that's also not very forceful at runtime. You can't guarantee that will be part of the enforcement controls.” — John Feminella (Balancing Acceleration and Safety for AI Agents, 00:05:13)

> “Nobody wants their agent to move thirty-seven their tax return. They want it done reliably at scale in a way that they can trust, and in a way that their people know how to work with.” — Mitchell Troyanovsky (Process Supervision for Agents That Do Long-Horizon Work, 00:17:21)

## Theme 05: Deterministic Verification Loops Over Line-by-Line Review (8 talks, 23 claims)

**Because coding agents generate pull requests far faster than humans can read them—and reviewers accept wrong AI output four times out of five—shipping confidence must come from independent, multi-layered verification harnesses and runnable behavioral proofs rather than manual line-by-line diff inspection.**

Software delivery talks confronted the review bottleneck head-on: Sonar reported a 2,450% explosion in AI-generated code yielding only 30% more releases because human reviewers succumb to 'cognitive surrender' (agreeing with wrong AI output 80% of the time) while multi-step agent accuracy decays exponentially across long horizons. Teams moving toward lights-on and dark software factories replaced manual line reading with executable proof loops. In the verification workshop, external MCP gates (`Ctx`) refuse agent self-reports until deterministic CLI and Playwright checks verify backend persistence, making verifier suites more durable than the application code itself. At Anthropic, merging 30,000 daily changes relies on automated first-pass reviews, edit hooks, and browser-driven screenshot and video evidence; Sonar pairs CPU static analysis with GPU generative checks and CVE scanning across every loop; Greptile inverts author and reviewer model families (+10% bug catch) and boots full-stack VM sandboxes for vision-model UI QA; Linear wires verification skills and product-history review agents into unattended bug fixes; GEICO enforces deterministic nine-step artifact gates; Untangle caps builder-reviewer loops at three iterations; and Coinbase runs parallel agent reviews inside gated DAGs. Against pure automation, Untangle insisted that a human product owner watching each feature video remains irreducible, and Featherless warned that unowned generation lobs 'slop grenades' onto peers.

> “A lights on factory is one where you have agents that are helping you with planning, building, checking, and shipping code again and again, but you as a person so apply your judgment and taste inside the picture” — Manish Kapur, Addy Osmani (Who verifies the software factory?, 00:01:45)

> “they agree with AI when AI is right, 93 percent of the time, and four out of five times, they agree with it when the AI is wrong.” — Tariq Shaukat (The Machine that Changed the World, vAI, 00:05:15)

## Theme 06: Self-Improving Fleets and the Agent Manager (8 talks, 21 claims)

**Software engineering is shifting from writing code locally to managing asynchronous cloud agent fleets and closing the trace-to-skill loop—centralizing transcripts and tool calls, grading runs post-merge, and letting meta-agents distill recurring failures and human corrections into versioned skills.**

Across Warp, Arize, Linear, Untangle, GEICO, Anthropic, and Runpod, the unit of engineering work moved from crafting individual features to operating and improving the agent factory itself. Warp demonstrated 'factory engineering': shared cloud Docker sandboxes automatically centralize conversation transcripts, MCP/tool calls, and diffs, exposing silent agent workarounds (like brute-force port probing) to post-merge markdown judge rubrics and daily meta-agents (`Skill Doctor`) that open measurable skill PRs. Linear runs a daily post-merge distillation job that turns PR review corrections and reverts into `agents.md` updates; Arize designs agent-first telemetry to wake scheduled sandbox sweeps while tracing both production agents and the coding harnesses behind them; Anthropic treats SME-authored plain-text skills as living, versioned code co-iterated by business teams and engineers; GEICO coordinates legacy transformations through Markdown FleetKit protocols; Runpod exposes GPU benchmark controls as FastAPI endpoints for agents to drive directly; and Untangle replaces local development with communicating builder, reviewer, and merge-manager sessions—extending the paradigm to hiring by stack-ranking candidates on 45-minute recorded agent-operating trials, echoing the Day 2 keynote's call to pair human company curation with career-research agents. In tension with universal 'agent management,' Basis warned that pushing prompt and skill authorship onto non-technical enterprise users creates a severe competency gap, and Day 2's keynote cautioned against letting agents automate personal outreach like resume submissions.

> “Takes a goal, breaks it down, dispatches leaders to do all the research and decide about the approach, puts everything into this like human loop cube.” — Ford Prior (Inside the Fable War Room, 00:08:10)

> “You can set up some scoring agents to score the quality of how those conversations went, so think of this like an LLM as a judge reviewing against rubrics that you define across metrics like efficiency, or code quality, or test coverage.” — Ben Holmes (Your agent needs a skill to improve its skills, 00:01:44)

## Theme 07: Governed Ontologies, Provenance, and Financial Workbenches (5 talks, 17 claims)

**In institutional investing and private markets, off-the-shelf web chatbots fail on stale or conflicting inputs; agents earn front-office trust only atop governed firm ontologies, validated golden sources, unified MCP connectors, and hybrid code-ML-LLM-human pipelines that write synthesis back into the vault.**

Every institutional finance talk located competitive advantage in governed data infrastructure and workflow design rather than raw model selection. Bridgewater contrasted an open-web chatbot answering a Korean won query from a single three-month-old note with Vault—which aligns 100M+ documents to a bitemporal ontology, serves 1,000+ QPS agent storms via turbopuffer cluster-local native filtering, migrates researcher email habits into saved collections, and writes human-agent workbench synthesis back into the corpus so knowledge compounds. At Apollo's Redding Ridge credit platform, engineers sat daily with portfolio managers to codify golden-source precedence across 20 conflicting systems, turning multi-hour weekly loan reconciliations into one-minute automated QA reports and cutting 200–400-name CLO portfolio construction from days in Excel to minutes for the first 80–90%. Coatue modeled the hedge fund as a composite state-machine function `(external_context, internal_context) -> (stock, size, timing)`, insisting that every pixel a human sees must be API-accessible while assigning each step whichever runner—deterministic code, classical ML, LLM, or human—maximizes quality. Exa supplied the external temporal layer with 400 billion dated web snapshots built for dense exploratory agent queries, while Anthropic standardized multi-system enterprise access behind a single MCP connectivity layer.

> “So at a high level, you can think about a hedge fund as a function that takes in two parameters — context external and context internal, and spits out one, two, volt selection size timing. What stock? How much? When?” — Frank Long (A Hedge Fund as a Function, 00:00:00)

> “We essentially use agents to do the work of data engineering, right information or reconciled data from across a variety of systems to the portfolio managers, traders, and so forth can make decisions faster and more accurately.” — Michael Manapat, Jack McDonald (AI in Practice: An Inside Look at Apollo's Approach, 00:00:00)

## Theme 08: Spatiotemporal World Models and Real-Time Simulation (2 talks, 11 claims)

**Scaling laws extend beyond turn-based text to continuous video and action streams, turning pixels-to-actions policies and next-frame predictors into real-time world simulators that internalize physics, control robots, and replace static 3D engines with interactive visual interfaces.**

General Intuition and Runway pushed AI engineering past autoregressive text into continuous space and time. General Intuition argued that real-time agents must observe while acting, leveraging Medal's gameplay pipeline—scaling toward three billion videos a year and 1.5 trillion monthly controller actions—because high-APM game controllers share the exact action space of low-DOF robot teleoperation and plug neatly as reactive control layers beneath frontier LLM planners. Runway bet on compute scaling laws for next-frame video prediction, demonstrating that models trained at scale internalize geometry, gravity, occlusion, and object permanence directly from pixels—unlocking action-conditioned robotics simulators, engine-free World Interface Models with no Unity or Blender mesh underneath, interactive Continuum video portals, and visual scratchpads where coding agents simulate spatial designs alongside code. Their sharpest technical disagreement sits on supervision: General Intuition contended that explicit controller action labels transfer far better to real-time control than passive video-only latent inference because subtle inputs like aircraft rudder adjustments leave almost no trace in raw pixel frames.

> “So what this means is that the action space for video games, often because of game controllers, and the action space for operations or the real world many cases are the same.” — Pim de Witte (Frontier Models for Acting in Space and Time, 00:02:33)

> “You're learning about physics. You're learning about object permanence. You're learning about gravity, you're learning about occlusion. You're learning about movements. You're learning about how the objects work in the real world.” — Cristóbal Valenzuela (Everything will be Simulated, 00:02:30)

## Five contested fault lines across the rooms

- **Can LLM-as-judge rubrics be trusted to grade production agent output?**
- **Do spatiotemporal world models learn control from passive video prediction alone, or do they require explicit action labels?**
- **Should enterprises own open, model-swappable foundations or scale atop frontier lab platforms?**
- **Where does human review belong once coding and workflow agents run autonomously?**
- **Will frontier models absorb the agent harness, or must builders keep engineering scaffolding and process around them?**
