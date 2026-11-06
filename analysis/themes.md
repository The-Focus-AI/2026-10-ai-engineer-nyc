# AI Engineer New York 2026 — Cross-Talk Themes

## Corpus

- **Recorded Talks**: 31 of 167 scheduled sessions
- **Cleaned Word Count**: 96,007 words
- **Extracted Claim Atoms**: 84 claims across 31 talks
- **Themes Identified**: 8
- **Last Updated**: 2026-10-26T10:41:07-04:00

## Themes

## 1. Verification Loops Over Human Review — 13 talks

**Claim**: As coding and operational agents generate output faster than humans can inspect, reliability requires independent, deterministic verification loops—tests, static analysis, process supervision, and critic agents.

Across software factories, hedge funds, and accounting automation, speakers converged on one structural shift: human line-by-line review is now the bottleneck. Teams that trust agents in production pair generator agents with deterministic verifiers, sandboxed execution, policy gates, and step-level process supervision.

- **Also called**: software factory verification, process supervision, guardrails and verification harnesses
- **Talks (13)**:
  - [Beyond “Done”: Building Verification Loops for AI Agents](../talks/2026-10-12-beyond-done-building-verification-loops-for-ai-agents/transcript.md) (### 00:00:00 — Why 'Done' Is Not Enough for Production Agents) — *Autonomous coding and operational agents require deterministic verification loops—tests, typechecks, and sandboxed gates—because human review cannot keep pace with machine-generated output.*
    > "So what do we mean by beyond that, just to like jump straight into it?"
  - [Anthropic: Accelerating frontier AI in Financial Services.](../talks/2026-10-13-anthropic-accelerating-frontier-ai-in-financial-services/transcript.md) (### 00:00:00 — Introduction: Frontier AI in Financial Services) — *Deploying frontier models in regulated financial institutions requires pairing model reasoning improvements with institutional governance, audit trails, and domain-specific evaluation.*
    > "We work with Canangial serviceservices first."
  - [Balancing Acceleration and Safety for AI Agents](../talks/2026-10-13-balancing-acceleration-and-safety-for-ai-agents/transcript.md) (### 00:00:00 — Balancing Innovation Speed and Institutional Trust) — *Two Sigma balances engineering velocity with institutional safety by classifying agent autonomy tiers and enforcing policy guardrails at the infrastructure layer.*
    > "Accelerate innovation without compromising trust, please welcome John Feminelli, SVP of architecture at 2 sigma."
  - [Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On](../talks/2026-10-13-give-the-model-a-computer-the-one-thing-every-ai-agent-framework/transcript.md) (### 00:00:00 — Why Every Agent Framework Converges on Sandboxed Computers) — *Every modern AI agent framework converges on giving the model an isolated, programmatic computer sandbox where it can execute code, inspect state, and verify its own work.*
    > "And for the last year, my main dad, my main test and goal there was going to be Daytona, faced everywhere, where sandbox makes sense because where they don't are Sam's provider."
  - [How to build an AI code review agent: from the creators of Greptile](../talks/2026-10-13-how-to-build-an-ai-code-review-agent-from-the-creators-of-grepti/transcript.md) (### 00:00:00 — Code Review at Scale: Signal vs. Noise) — *Effective AI code review agents must go beyond static diff reading by executing code in sandboxes, indexing full-repo dependency graphs, and allocating inference budget per subtask.*
    > "And by reviewing testing these for us, we reveal bugs, logical errors, code of quality concerns."
  - [Inside the Fable War Room](../talks/2026-10-13-inside-the-fable-war-room/transcript.md) (### 00:00:00 — SDLC Velocity vs. Incident Operations at GEICO) — *While coding agents have compressed software build times, production incident response remains a bottleneck that GEICO addresses with multi-agent 'Fable War Room' triage.*
    > "Feels like all we've been talking about is that increase the velocity of our SDLC."
  - [Write the Answer First: Generating Eval Datasets for Agents With No Benchmark](../talks/2026-10-13-write-the-answer-first-generating-eval-datasets-for-agents-with/transcript.md) (### 00:00:00 — Shipping Enterprise Agents Without Pre-Existing Benchmarks) — *When deploying enterprise agents for domain-specific workflows where no benchmark exists, teams should write target answers first and synthesize evaluation datasets backward.*
    > "I've seen a lot of time since I was the agent I've been shipping without any graduation."
  - [AI in Practice: An Inside Look at Apollo's Approach](../talks/2026-10-14-ai-in-practice-an-inside-look-at-apollo-s-approach/transcript.md) (### 00:00:00 — Rowspace & Apollo: AI for Institutional Investment Data) — *Apollo and Rowspace deploy specialized data-engineering and research agents to reconcile fragmented institutional data across deals, portfolios, and risk systems.*
    > "And Roast Base is on a tactical platform that uses AI to help and has to surface partners, like Apollo, deal with messy, fragmented data."
  - [Process Supervision for Agents That Do Long-Horizon Work](../talks/2026-10-14-process-supervision-for-agents-that-do-long-horizon-work/transcript.md) (### 00:00:00 — Long-Horizon Accounting Agents at Basis) — *Basis achieves production reliability for long-horizon accounting agents by supervising intermediate reasoning steps (process supervision) rather than grading only final outputs.*
    > "Please welcome Mitchell Trainos, the co-founder of Basses."
  - [The Machine that Changed the World, vAI](../talks/2026-10-14-the-machine-that-changed-the-world-vai/transcript.md) (### 00:00:00 — From Lean Manufacturing to Enterprise Software Factories) — *Enterprise software factories only deliver real productivity when automated code verification and static analysis gates prevent AI-generated technical debt from accumulating.*
    > "my name is Tara Chuck, and I'm just you, as you just heard, and we're here to talk today about how we have been, helping companies build software factories that actually work for enterprises."
  - [Trusting Agents in Policy-Driven Workflows](../talks/2026-10-14-trusting-agents-in-policy-driven-workflows/transcript.md) (### 00:00:00 — Policy-Driven Workflows & Deterministic Controls at Coinbase) — *In regulated financial workflows at Coinbase, trusting autonomous agents requires binding every agent action to explicit, machine-enforceable policy constraints.*
    > "I've been delivering, designing, building software for 20 years."
  - [Who verifies the software factory?](../talks/2026-10-14-who-verifies-the-software-factory/transcript.md) (### 00:00:00 — The Code Review Bottleneck in AI Software Factories) — *When nearly every developer merges AI-authored pull requests without reading every line, software factories require independent verification layers combining static analysis, tests, and critic agents.*
    > "I'm pretty excited to be here and talk about who verifies the software factory."
  - [Your job is now "agent manager"](../talks/2026-10-14-your-job-is-now-agent-manager/transcript.md) (### 00:00:00 — Managing a Fleet of Builder, Reviewer & Manager Agents) — *Software engineers are becoming 'agent managers' who orchestrate hierarchical loops of builder, reviewer, QA, and manager agents running on 15-minute heartbeats.*
    > "Tell like, hey, every 15 minutes, go read every single child."
- **Counter-claims**:
  - `29083884-87dc-44f8-b412-b494afca8856:0:c65975` ([2026-10-14-the-model-ate-the-coding-harness-now-what](../talks/2026-10-14-the-model-ate-the-coding-harness-now-what/transcript.md), ### 00:00:00 — Evolution of the Coding Agent Harness): Early coding harnesses relied on brittle, hand-authored prompt state machines to compensate for weak model planning.

## 2. Provenance and Grounding in Financial AI — 10 talks

**Claim**: In regulated banking, quantitative funds, and private equity, AI agents earn decision authority only when every output is grounded in point-in-time, citation-backed institutional data.

Financial institutions from Bridgewater, Two Sigma, and Coatue to Apollo, Coinbase, and Ramp emphasized that hallucination-intolerant workflows require strict provenance, point-in-time retrieval without lookahead bias, and policy-bound execution.

- **Also called**: institutional grounding, point-in-time backtesting, evidence-backed financial agents
- **Talks (10)**:
  - [A Hedge Fund as a Function](../talks/2026-10-13-a-hedge-fund-as-a-function/transcript.md) (### 00:00:00 — Investment Thesis: Modeling the Hedge Fund as a Function) — *Coatue models the modern hedge fund as a composable function where AI agents continuously ingest market data, synthesize research, and compound institutional investment judgment.*
    > "I work at Co2, which is a technology investment firm across public and private markets."
  - [Anthropic: Accelerating frontier AI in Financial Services.](../talks/2026-10-13-anthropic-accelerating-frontier-ai-in-financial-services/transcript.md) (### 00:00:00 — Introduction: Frontier AI in Financial Services) — *Deploying frontier models in regulated financial institutions requires pairing model reasoning improvements with institutional governance, audit trails, and domain-specific evaluation.*
    > "We work with Canangial serviceservices first."
  - [Balancing Acceleration and Safety for AI Agents](../talks/2026-10-13-balancing-acceleration-and-safety-for-ai-agents/transcript.md) (### 00:00:00 — Balancing Innovation Speed and Institutional Trust) — *Two Sigma balances engineering velocity with institutional safety by classifying agent autonomy tiers and enforcing policy guardrails at the infrastructure layer.*
    > "Accelerate innovation without compromising trust, please welcome John Feminelli, SVP of architecture at 2 sigma."
  - [Search the Web as It Was: An Introduction to Exa Snapshot](../talks/2026-10-13-search-the-web-as-it-was-an-introduction-to-exa-snapshot/transcript.md) (### 00:00:00 — What Is Exa & Agentic Web Search) — *Backtesting financial agents requires point-in-time web snapshots (Exa Snapshot) so models cannot cheat with future information via lookahead bias.*
    > "and today I'm going to give you an overview of 2 things."
  - [Vault: Making Unstructured Data Work for Investing](../talks/2026-10-13-vault-making-unstructured-data-work-for-investing/transcript.md) (### 00:00:00 — From Structured Time Series to Unstructured Data at Bridgewater) — *Bridgewater's Vault turns unstructured macro and market text into grounded, auditable signals that complement traditional quantitative time-series models.*
    > "All these phases of evolution, we've had a constant philosophy in mind, which is that we want to be constantly looking at how a world is changing and what's going on in the world."
  - [Welcome Back - Featured Keynotes](../talks/2026-10-13-welcome-back-featured-keynotes/transcript.md) (### 00:00:00 — Afternoon Keynote Block Welcome & Tenex Reflections) — *Tenex's opening remarks frame the afternoon keynote block around how enterprise AI engineering moves from isolated prototypes to compounding organizational transformation.*
    > "Who is it about to ever drive in the room?"
  - [AI in Practice: An Inside Look at Apollo's Approach](../talks/2026-10-14-ai-in-practice-an-inside-look-at-apollo-s-approach/transcript.md) (### 00:00:00 — Rowspace & Apollo: AI for Institutional Investment Data) — *Apollo and Rowspace deploy specialized data-engineering and research agents to reconcile fragmented institutional data across deals, portfolios, and risk systems.*
    > "And Roast Base is on a tactical platform that uses AI to help and has to surface partners, like Apollo, deal with messy, fragmented data."
  - [Chasing capabilities while waiting for the frontier](../talks/2026-10-14-chasing-capabilities-while-waiting-for-the-frontier/transcript.md) (### 00:00:00 — Token Economics & Capability Growth at Ramp) — *Ramp pairs frontier orchestrator models with fast, specialized fine-tuned retrieval and financial QA models to deliver frontier accuracy at Haiku-class latency and unit cost.*
    > "I use our wax as an increase in 123%."
  - [Process Supervision for Agents That Do Long-Horizon Work](../talks/2026-10-14-process-supervision-for-agents-that-do-long-horizon-work/transcript.md) (### 00:00:00 — Long-Horizon Accounting Agents at Basis) — *Basis achieves production reliability for long-horizon accounting agents by supervising intermediate reasoning steps (process supervision) rather than grading only final outputs.*
    > "Please welcome Mitchell Trainos, the co-founder of Basses."
  - [Trusting Agents in Policy-Driven Workflows](../talks/2026-10-14-trusting-agents-in-policy-driven-workflows/transcript.md) (### 00:00:00 — Policy-Driven Workflows & Deterministic Controls at Coinbase) — *In regulated financial workflows at Coinbase, trusting autonomous agents requires binding every agent action to explicit, machine-enforceable policy constraints.*
    > "I've been delivering, designing, building software for 20 years."
- **Why uncontested**: Every financial services speaker treated auditability, provenance, and regulatory compliance as non-negotiable prerequisites for production deployment.

## 3. Owning Open Foundations vs. Renting the Frontier — 8 talks

**Claim**: Organizations face a strategic trade-off between owning fine-tuned open-weight models for cost, privacy, and control versus leveraging rapidly advancing closed frontier models.

Nous Research, Featherless, and Runpod argued for owning weights on open foundations, while Ramp, Anthropic, and SpaceX highlighted how fast-moving frontier capabilities reshape orchestration and sub-agent routing.

- **Also called**: owned vs. rented land, open-weight sovereignty
- **Talks (8)**:
  - [The AI Bill Is Too Damn High – Tokenomics 101](../talks/2026-10-12-the-ai-bill-is-too-damn-high-tokenomics-101/transcript.md) (### 00:00:00 — Workshop Introduction & Featherless Background) — *Token inference costs are dominated by memory bandwidth and KV-cache footprint rather than raw FLOPs, making open-weight routing and batching essential for sustainable unit economics.*
    > "So many people are suffering from their talking view."
  - [Closing Remarks](../talks/2026-10-13-closing-remarks/transcript.md) (### 00:00:00 — Day 1 Closing Remarks & Keynote Recap) — *Day 1's closing remarks synthesize the tension between building on owned open foundations versus rented frontier APIs, spatiotemporal world models, and AI-native investment workflows.*
    > "We had him talking about role models, going from pixels to actions."
  - [From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod](../talks/2026-10-13-from-model-to-metrics-serving-and-benchmarking-any-llm-live-with/transcript.md) (### 00:00:00 — Why Live LLM Serving & Benchmarking Is Hard) — *Benchmarking open-weight LLMs under realistic concurrency with vLLM on GPU pods reveals throughput and latency trade-offs that static model cards hide.*
    > "French working VLMs, kind of like the struggle that people have, especially like a new mom comes out."
  - [Frontier Models for Acting in Space and Time](../talks/2026-10-13-frontier-models-for-acting-in-space-and-time/transcript.md) (### 00:00:00 — From Internet Text to Spatiotemporal World Models) — *Training frontier spatiotemporal world models on billions of video-paired action trajectories from gameplay enables agents that perceive and act in 3D space and time.*
    > "A lot of people would tell you, that's crazy."
  - [Hermes gives you wings: Build on open foundations.](../talks/2026-10-13-hermes-gives-you-wings-build-on-open-foundations/transcript.md) (### 00:00:00 — The Economics of Frontier Labs vs. Open Foundations) — *As frontier labs spend hundreds of billions on closed infrastructure, enterprises must build on open-weight foundations like Hermes to own their weights, data, and long-term destiny.*
    > "I'm the CEO of news research, and today we're going to talk about building on foundations and platforms that you can actually go."
  - [Chasing capabilities while waiting for the frontier](../talks/2026-10-14-chasing-capabilities-while-waiting-for-the-frontier/transcript.md) (### 00:00:00 — Token Economics & Capability Growth at Ramp) — *Ramp pairs frontier orchestrator models with fast, specialized fine-tuned retrieval and financial QA models to deliver frontier accuracy at Haiku-class latency and unit cost.*
    > "I use our wax as an increase in 123%."
  - [The Model Ate the Coding Harness. Now What?](../talks/2026-10-14-the-model-ate-the-coding-harness-now-what/transcript.md) (### 00:00:00 — Evolution of the Coding Agent Harness) — *As frontier models internalize multi-step planning and tool use via RL, heavy hand-crafted agent scaffolding gets absorbed by the model, leaving the execution environment and verification tools as the durable harness.*
    > "For sure, early in 2025, as the longest tenure engineer working on our agent harness."
  - [Welcome Back - Featured Keynotes](../talks/2026-10-14-welcome-back-featured-keynotes/transcript.md) (### 00:00:00 — Day 2 Afternoon Keynote Block Welcome) — *Ksenia Se's opening remarks welcome attendees to the final keynote block of AI Engineer NYC 2026, connecting frontier research advances to production implementation.*
    > "for those who haven't met me yet, my name is Seniose."

## 4. The Sandboxed Computer and Evolving Harness — 8 talks

**Claim**: Agent harnesses are converging on isolated computer sandboxes and structured context graphs while shedding brittle hand-rolled prompt scaffolding as models improve.

From Daytona and Greptile to Linear, SpaceX, and Warp, builders showed that giving an agent a real computer sandbox and structured issue context unlocks general problem-solving—even as RL-trained models absorb the brittle orchestration loops of early harnesses.

- **Also called**: give the model a computer, the model ate the harness, context engineering
- **Talks (8)**:
  - [Beyond “Done”: Building Verification Loops for AI Agents](../talks/2026-10-12-beyond-done-building-verification-loops-for-ai-agents/transcript.md) (### 00:00:00 — Why 'Done' Is Not Enough for Production Agents) — *Autonomous coding and operational agents require deterministic verification loops—tests, typechecks, and sandboxed gates—because human review cannot keep pace with machine-generated output.*
    > "So what do we mean by beyond that, just to like jump straight into it?"
  - [Agents can pay. So why don’t they?](../talks/2026-10-13-agents-can-pay-so-why-don-t-they/transcript.md) (### 00:00:00 — Why Agentic Payments Matter for Tool Marketplaces) — *For autonomous agents to consume third-party tools and data marketplaces at scale, payment protocols and per-call metering must become native to agent tool interfaces.*
    > "In article, it was a pressing question."
  - [Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On](../talks/2026-10-13-give-the-model-a-computer-the-one-thing-every-ai-agent-framework/transcript.md) (### 00:00:00 — Why Every Agent Framework Converges on Sandboxed Computers) — *Every modern AI agent framework converges on giving the model an isolated, programmatic computer sandbox where it can execute code, inspect state, and verify its own work.*
    > "And for the last year, my main dad, my main test and goal there was going to be Daytona, faced everywhere, where sandbox makes sense because where they don't are Sam's provider."
  - [How to build an AI code review agent: from the creators of Greptile](../talks/2026-10-13-how-to-build-an-ai-code-review-agent-from-the-creators-of-grepti/transcript.md) (### 00:00:00 — Code Review at Scale: Signal vs. Noise) — *Effective AI code review agents must go beyond static diff reading by executing code in sandboxes, indexing full-repo dependency graphs, and allocating inference budget per subtask.*
    > "And by reviewing testing these for us, we reveal bugs, logical errors, code of quality concerns."
  - [The Model Ate the Coding Harness. Now What?](../talks/2026-10-14-the-model-ate-the-coding-harness-now-what/transcript.md) (### 00:00:00 — Evolution of the Coding Agent Harness) — *As frontier models internalize multi-step planning and tool use via RL, heavy hand-crafted agent scaffolding gets absorbed by the model, leaving the execution environment and verification tools as the durable harness.*
    > "For sure, early in 2025, as the longest tenure engineer working on our agent harness."
  - [Who verifies the software factory?](../talks/2026-10-14-who-verifies-the-software-factory/transcript.md) (### 00:00:00 — The Code Review Bottleneck in AI Software Factories) — *When nearly every developer merges AI-authored pull requests without reading every line, software factories require independent verification layers combining static analysis, tests, and critic agents.*
    > "I'm pretty excited to be here and talk about who verifies the software factory."
  - [Your agent needs a skill to improve its skills](../talks/2026-10-14-your-agent-needs-a-skill-to-improve-its-skills/transcript.md) (### 00:00:00 — Why Agents Repeat Mistakes Across Sessions) — *Agents become self-improving when equipped with a meta-skill that mines past execution traces and human corrections to update their own reusable skill definitions.*
    > "I was always wondering what an agent form would look like."
  - [Your Coding Agent Has a Context Problem](../talks/2026-10-14-your-coding-agent-has-a-context-problem/transcript.md) (### 00:00:00 — Why Coding Agents Fail Without Product & Issue Context) — *Coding agents fail in production not from weak syntax generation, but from lacking structured product, issue, and architectural decision context across the software lifecycle.*
    > "Do we have anybody standing in the hallway watching?"

## 5. Self-Improving Agents and Agent Management — 7 talks

**Claim**: Engineers are transitioning from writing individual features to managing fleets of agents that mine their own execution traces and update reusable skills over time.

Warp, Untangle, Arize AI, Linear, and GEICO showed how 15-minute manager heartbeats, trace-mining meta-skills, and automated war-room agents turn one-off agent runs into compounding organizational memory.

- **Also called**: agent manager, skill-improving skills, autonomous software factories
- **Talks (7)**:
  - [A Hedge Fund as a Function](../talks/2026-10-13-a-hedge-fund-as-a-function/transcript.md) (### 00:00:00 — Investment Thesis: Modeling the Hedge Fund as a Function) — *Coatue models the modern hedge fund as a composable function where AI agents continuously ingest market data, synthesize research, and compound institutional investment judgment.*
    > "I work at Co2, which is a technology investment firm across public and private markets."
  - [Inside the Fable War Room](../talks/2026-10-13-inside-the-fable-war-room/transcript.md) (### 00:00:00 — SDLC Velocity vs. Incident Operations at GEICO) — *While coding agents have compressed software build times, production incident response remains a bottleneck that GEICO addresses with multi-agent 'Fable War Room' triage.*
    > "Feels like all we've been talking about is that increase the velocity of our SDLC."
  - [What does an AI engineer do?](../talks/2026-10-13-what-does-an-ai-engineer-do/transcript.md) (### 00:00:00 — The Evolving Role of the AI Engineer) — *The AI engineer's role has shifted from writing static features to operating a continuous build-eval-ship-monitor loop over fleets of production agents.*
    > "just tweeted something this weekend where he kind of he kind of talks about this growing gap between basically folks at the frontier who are running 1000s of agents and swarms of always on agents."
  - [The Machine that Changed the World, vAI](../talks/2026-10-14-the-machine-that-changed-the-world-vai/transcript.md) (### 00:00:00 — From Lean Manufacturing to Enterprise Software Factories) — *Enterprise software factories only deliver real productivity when automated code verification and static analysis gates prevent AI-generated technical debt from accumulating.*
    > "my name is Tara Chuck, and I'm just you, as you just heard, and we're here to talk today about how we have been, helping companies build software factories that actually work for enterprises."
  - [Your agent needs a skill to improve its skills](../talks/2026-10-14-your-agent-needs-a-skill-to-improve-its-skills/transcript.md) (### 00:00:00 — Why Agents Repeat Mistakes Across Sessions) — *Agents become self-improving when equipped with a meta-skill that mines past execution traces and human corrections to update their own reusable skill definitions.*
    > "I was always wondering what an agent form would look like."
  - [Your Coding Agent Has a Context Problem](../talks/2026-10-14-your-coding-agent-has-a-context-problem/transcript.md) (### 00:00:00 — Why Coding Agents Fail Without Product & Issue Context) — *Coding agents fail in production not from weak syntax generation, but from lacking structured product, issue, and architectural decision context across the software lifecycle.*
    > "Do we have anybody standing in the hallway watching?"
  - [Your job is now "agent manager"](../talks/2026-10-14-your-job-is-now-agent-manager/transcript.md) (### 00:00:00 — Managing a Fleet of Builder, Reviewer & Manager Agents) — *Software engineers are becoming 'agent managers' who orchestrate hierarchical loops of builder, reviewer, QA, and manager agents running on 15-minute heartbeats.*
    > "Tell like, hey, every 15 minutes, go read every single child."
- **Why uncontested**: Speakers agreed that persisting lessons across sessions is essential, differing only on how much human approval is required before a skill update is promoted.

## 6. Bootstrapping Domain Evals Without Public Benchmarks — 6 talks

**Claim**: Because public leaderboards fail to measure domain-specific business logic, lookahead leakage, or creative quality, engineering teams must synthesize and maintain custom evaluation suites from production traces.

Speakers from Air Canada, Arize AI, Exa, Basis, and Towards AI demonstrated how to build evaluation datasets from scratch—writing reference answers first, snapshotting temporal web state, supervising intermediate steps, and turning production failures into regression tests.

- **Also called**: write the answer first, build-eval-ship-monitor loop, anti-slop benchmarks
- **Talks (6)**:
  - [Can Any Model Write Like Me? Building a Benchmark for Creative Writing](../talks/2026-10-13-can-any-model-write-like-me-building-a-benchmark-for-creative-wr/transcript.md) (### 00:00:00 — Defining AI Writing Slop & Why It Happens) — *Measuring and eliminating 'AI slop' in long-form writing requires specialized style and creativity benchmarks rather than generic reasoning leaderboards.*
    > "and, more importantly, I want to, try to help this thing, what current demon, termed as the slug activist, that he taught to start in 2026 and I think we've seen that on social media."
  - [Search the Web as It Was: An Introduction to Exa Snapshot](../talks/2026-10-13-search-the-web-as-it-was-an-introduction-to-exa-snapshot/transcript.md) (### 00:00:00 — What Is Exa & Agentic Web Search) — *Backtesting financial agents requires point-in-time web snapshots (Exa Snapshot) so models cannot cheat with future information via lookahead bias.*
    > "and today I'm going to give you an overview of 2 things."
  - [Vault: Making Unstructured Data Work for Investing](../talks/2026-10-13-vault-making-unstructured-data-work-for-investing/transcript.md) (### 00:00:00 — From Structured Time Series to Unstructured Data at Bridgewater) — *Bridgewater's Vault turns unstructured macro and market text into grounded, auditable signals that complement traditional quantitative time-series models.*
    > "All these phases of evolution, we've had a constant philosophy in mind, which is that we want to be constantly looking at how a world is changing and what's going on in the world."
  - [What does an AI engineer do?](../talks/2026-10-13-what-does-an-ai-engineer-do/transcript.md) (### 00:00:00 — The Evolving Role of the AI Engineer) — *The AI engineer's role has shifted from writing static features to operating a continuous build-eval-ship-monitor loop over fleets of production agents.*
    > "just tweeted something this weekend where he kind of he kind of talks about this growing gap between basically folks at the frontier who are running 1000s of agents and swarms of always on agents."
  - [Write the Answer First: Generating Eval Datasets for Agents With No Benchmark](../talks/2026-10-13-write-the-answer-first-generating-eval-datasets-for-agents-with/transcript.md) (### 00:00:00 — Shipping Enterprise Agents Without Pre-Existing Benchmarks) — *When deploying enterprise agents for domain-specific workflows where no benchmark exists, teams should write target answers first and synthesize evaluation datasets backward.*
    > "I've seen a lot of time since I was the agent I've been shipping without any graduation."
  - [Process Supervision for Agents That Do Long-Horizon Work](../talks/2026-10-14-process-supervision-for-agents-that-do-long-horizon-work/transcript.md) (### 00:00:00 — Long-Horizon Accounting Agents at Basis) — *Basis achieves production reliability for long-horizon accounting agents by supervising intermediate reasoning steps (process supervision) rather than grading only final outputs.*
    > "Please welcome Mitchell Trainos, the co-founder of Basses."
- **Why uncontested**: No speaker defended static public leaderboards as sufficient for production readiness.

## 7. Token Economics and Multi-Model Routing — 6 talks

**Claim**: Sustaining production AI margins requires routing subtasks across frontier orchestrators and specialized or open-weight models while optimizing GPU serving and KV-cache utilization.

Featherless, Ramp, Runpod, Greptile, and Nous Research detailed the unit economics of production inference: memory bandwidth bottlenecks, vLLM benchmarking, and hybrid architectures that pair frontier reasoning with fast domain-tuned models.

- **Also called**: tokenomics 101, frontier orchestrator + fast sub-agent, live LLM benchmarking
- **Talks (6)**:
  - [The AI Bill Is Too Damn High – Tokenomics 101](../talks/2026-10-12-the-ai-bill-is-too-damn-high-tokenomics-101/transcript.md) (### 00:00:00 — Workshop Introduction & Featherless Background) — *Token inference costs are dominated by memory bandwidth and KV-cache footprint rather than raw FLOPs, making open-weight routing and batching essential for sustainable unit economics.*
    > "So many people are suffering from their talking view."
  - [Agents can pay. So why don’t they?](../talks/2026-10-13-agents-can-pay-so-why-don-t-they/transcript.md) (### 00:00:00 — Why Agentic Payments Matter for Tool Marketplaces) — *For autonomous agents to consume third-party tools and data marketplaces at scale, payment protocols and per-call metering must become native to agent tool interfaces.*
    > "In article, it was a pressing question."
  - [From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod](../talks/2026-10-13-from-model-to-metrics-serving-and-benchmarking-any-llm-live-with/transcript.md) (### 00:00:00 — Why Live LLM Serving & Benchmarking Is Hard) — *Benchmarking open-weight LLMs under realistic concurrency with vLLM on GPU pods reveals throughput and latency trade-offs that static model cards hide.*
    > "French working VLMs, kind of like the struggle that people have, especially like a new mom comes out."
  - [Hermes gives you wings: Build on open foundations.](../talks/2026-10-13-hermes-gives-you-wings-build-on-open-foundations/transcript.md) (### 00:00:00 — The Economics of Frontier Labs vs. Open Foundations) — *As frontier labs spend hundreds of billions on closed infrastructure, enterprises must build on open-weight foundations like Hermes to own their weights, data, and long-term destiny.*
    > "I'm the CEO of news research, and today we're going to talk about building on foundations and platforms that you can actually go."
  - [How to build an AI code review agent: from the creators of Greptile](../talks/2026-10-13-how-to-build-an-ai-code-review-agent-from-the-creators-of-grepti/transcript.md) (### 00:00:00 — Code Review at Scale: Signal vs. Noise) — *Effective AI code review agents must go beyond static diff reading by executing code in sandboxes, indexing full-repo dependency graphs, and allocating inference budget per subtask.*
    > "And by reviewing testing these for us, we reveal bugs, logical errors, code of quality concerns."
  - [Chasing capabilities while waiting for the frontier](../talks/2026-10-14-chasing-capabilities-while-waiting-for-the-frontier/transcript.md) (### 00:00:00 — Token Economics & Capability Growth at Ramp) — *Ramp pairs frontier orchestrator models with fast, specialized fine-tuned retrieval and financial QA models to deliver frontier accuracy at Haiku-class latency and unit cost.*
    > "I use our wax as an increase in 123%."
- **Why uncontested**: Across both model providers and enterprise consumers, routing by task complexity was the consensus strategy for controlling inference spend.

## 8. Spatiotemporal World Models and Simulation — 3 talks

**Claim**: Foundation models are expanding beyond text into spatiotemporal world models trained on video and action trajectories to simulate physics, environments, and embodied control.

General Intuition and Runway demonstrated how training on gameplay action trajectories and generative video transitions AI from static text prediction to interactive world simulation.

- **Also called**: everything will be simulated, pixels to actions
- **Talks (3)**:
  - [Closing Remarks](../talks/2026-10-13-closing-remarks/transcript.md) (### 00:00:00 — Day 1 Closing Remarks & Keynote Recap) — *Day 1's closing remarks synthesize the tension between building on owned open foundations versus rented frontier APIs, spatiotemporal world models, and AI-native investment workflows.*
    > "We had him talking about role models, going from pixels to actions."
  - [Frontier Models for Acting in Space and Time](../talks/2026-10-13-frontier-models-for-acting-in-space-and-time/transcript.md) (### 00:00:00 — From Internet Text to Spatiotemporal World Models) — *Training frontier spatiotemporal world models on billions of video-paired action trajectories from gameplay enables agents that perceive and act in 3D space and time.*
    > "A lot of people would tell you, that's crazy."
  - [Everything will be Simulated](../talks/2026-10-14-everything-will-be-simulated/transcript.md) (### 00:00:00 — Ten Years of Generative Media & World Models at Runway) — *Runway argues that generative video is evolving from passive media synthesis into interactive, real-time world simulators that model physics, agency, and environments.*
    > "Please welcome Cristobal Valenzuela, co-founder and co-CEO of Runway."
- **Why uncontested**: Both keynote speakers framed world simulation as the next frontier beyond language-only models.

## Contested Questions

### Should agent reliability live in rich external harness scaffolding or be absorbed into end-to-end RL-trained models?

- **Models trained with end-to-end RL absorb multi-step planning and orchestration loops, shrinking the external harness to just execution environments and tools.** ([2026-10-14-the-model-ate-the-coding-harness-now-what](../talks/2026-10-14-the-model-ate-the-coding-harness-now-what/transcript.md), ### 00:06:38 — What Happens as Models Absorb Harness Scaffolding · `29083884-87dc-44f8-b412-b494afca8856:398:a59584`)
  > "So that's how you get people saying that the harness is dead."
- **Production safety requires explicit, deterministic verification loops and external guardrails outside the model regardless of raw model capability.** ([2026-10-12-beyond-done-building-verification-loops-for-ai-agents](../talks/2026-10-12-beyond-done-building-verification-loops-for-ai-agents/transcript.md), ### 00:08:57 — Designing Deterministic Verification Loops · `edb4f982-0cb8-48ee-8bf7-410255a40cb3:537:16fca8`)
  > "is actually doing correct work about, like, you know, they earning money and time, essentially."

### Should enterprises build on owned open-weight foundations or orchestrate closed frontier models with smaller domain models?

- **Enterprises must build on open-weight foundations like Hermes to own their weights, customize behavior, and avoid rented-land lock-in.** ([2026-10-13-hermes-gives-you-wings-build-on-open-foundations](../talks/2026-10-13-hermes-gives-you-wings-build-on-open-foundations/transcript.md), ### 00:05:16 — Hermes & Owning Your Intelligence Stack · `871cd5c8-13f4-4fe9-ac49-c8b25d970add:316:a5aecd`)
  > "where the money is, and we're trying to make back a trillion dollars."
- **Pairing closed frontier orchestrators with specialized domain-tuned sub-agents delivers frontier capabilities immediately while keeping unit costs low.** ([2026-10-14-chasing-capabilities-while-waiting-for-the-frontier](../talks/2026-10-14-chasing-capabilities-while-waiting-for-the-frontier/transcript.md), ### 00:08:55 — Lessons from Shipping Production Financial Agents · `caecd5f6-b352-4868-a995-f0f71679caf0:535:56b6a0`)
  > "One of the interesting insights from that same article that they published is that you can actually use open wave models that are up to 5 times cheaper compared to the frontier reasoning."

## Singletons

- **Autonomous agent commerce is bottlenecked not by model capability, but by identity, budgeting controls, and machine-to-machine payment friction.** ([2026-10-13-agents-can-pay-so-why-don-t-they](../talks/2026-10-13-agents-can-pay-so-why-don-t-they/transcript.md), ### 00:07:31 — Payment Protocols, MCP & x402 Friction · `8d348b6c-25cc-45de-8dc4-aaa3d7130918:451:bd0cd3`)
  > "and usually the thing was the kind of thing, but, like, it's absolutely weird."
- **Building a dedicated creative writing benchmark exposes where frontier models default to homogenized prose.** ([2026-10-13-can-any-model-write-like-me-building-a-benchmark-for-creative-wr](../talks/2026-10-13-can-any-model-write-like-me-building-a-benchmark-for-creative-wr/transcript.md), ### 00:06:15 — Constructing a Benchmark for Creative Writing · `736edd83-bb08-49f1-90ed-722b7ed07eb2:375:b9d212`)
  > "We made sure that final script, again, our rubrics and just our whole evaluation project."

## Limits

- **Coverage**: 31 recorded sessions out of 167 total scheduled sessions (parallel tracks meant one room could be recorded in person at a time).
- **Thin Talks (5)**: [2026-10-13-closing-remarks](../talks/2026-10-13-closing-remarks/transcript.md), [2026-10-13-welcome-back-featured-keynotes](../talks/2026-10-13-welcome-back-featured-keynotes/transcript.md), [2026-10-14-trusting-agents-in-policy-driven-workflows](../talks/2026-10-14-trusting-agents-in-policy-driven-workflows/transcript.md), [2026-10-14-welcome-back-featured-keynotes](../talks/2026-10-14-welcome-back-featured-keynotes/transcript.md), [2026-10-14-your-job-is-now-agent-manager](../talks/2026-10-14-your-job-is-now-agent-manager/transcript.md) (short 1–5 minute emcee/intro or partial recordings).
- **Unassigned Talks**: 0 (all 31 recorded talks are assigned to at least one theme).
