---
title: "Trusting Agents in Policy-Driven Workflows"
speakers: "Evan Kormos (Coinbase)"
duration: "4:35"
source: transcript.md
video: "https://www.youtube.com/watch?v=_4Ph2dhmUFI"
themes: [bounded-autonomy-runtime-governance-and-the-enterprise-diffusion-gap, deterministic-verification-loops-over-line-by-line-review]
kind: talk-story
status: draft
---

# Deterministic outside, adaptive inside: putting agents inside regulated workflows

Evan Kormos has spent fifteen of his twenty years in software inside enterprise financial services, and now works as a player-coach at Coinbase. His argument is straightforward: regulated institutions already have a system prompt in their written risk and compliance policies, and the safe way to deploy agents is to embed bounded, evaluated loops inside deterministic workflow graphs rather than letting agents invent the process.

The in-room audio recording cuts off four and a half minutes into an eighteen-minute talk, mid-sentence during the discussion of directed acyclic graphs. The official video captures Kormos's slides for the full talk, so details from the second half are explicitly attributed to his slides while every blockquote is verbatim from the room transcript.

## Policy is the institution's original system prompt

Kormos starts with written policy because in financial services it sets the rules for how work gets done, particularly around risk and compliance (00:00:18). Written well, policy uses normative terms with distinct operational weight: `Must` for what is required, `May` for what is permitted, and `Should` for what is recommended, as his slide spells out alongside a later reference to RFC 2119 (00:00:18). Those rules act as the organization's original intent before any code or prompt is written (00:00:18).

The first architectural separation he draws is between build-time policy and the running production system (00:00:18). Policy changes deliberately at discrete moments, while the live system mutates constantly under product-driven changes (00:00:18). Keeping policy explicit and separate from runtime state gives teams a stable boundary that changing services and agents still have to obey.

**Key points**

- Written risk and compliance policy acts as the organization's foundational system prompt.
- Normative language (`Must`, `May`, `Should`) distinguishes hard requirements from permissions and recommendations.
- Build-time policy definition stays separate from the continuously changing runtime system.

> “Think of policy as the original institutional intent, or the original system prompt.”
> — 00:00:18

**Visual:** slide `experience/16-must-may-should.jpg`, `experience/16-title-speaker-byline.jpg` ("Start with the policy: Must / May / Should" and the opening title slide)

## Agents cut across people, process, and technology

Enterprise governance usually divides a running system into three layers: people, process, and technology, though the room transcript hears the phrase as "people processing technology" (00:02:29). On Kormos's slide, those three layers appear as an isometric stack of grey cubes, which then light up in yellow across every row when agents enter the picture.

He rejects treating agents as just another tool sitting in the technology row (00:02:29). An agent works alongside human staff, executes steps of the process on its own, and both uses and is built out of technology (00:02:29). Because agents cross all three layers at once, the practical governance questions sit where agent behavior meets process rules: what work you delegate, what boundaries you enforce, and how you verify the result (00:02:29).

**Key points**

- Agents are not confined to the tooling layer; they span people, process, and technology simultaneously.
- They collaborate with staff, execute workflow steps directly, and run on top of existing technical infrastructure.
- Governance centers on scoping agent tasks, setting explicit process boundaries, and verifying outputs.

> “So I see them as an operational model cutting across all three. They work with people, execute parts of the process themselves, and they use and are made up of technology.”
> — 00:02:29

**Visual:** slide `experience/20-people-process-technology.jpg` (the isometric People, Process, and Technology stack)

## Parallelizing reviews inside a gated DAG

Regulated workflows move in a strict, gated order: a code change needs approval before going live, and a customer must clear verification before an account opens (00:03:19). Kormos argues that introducing agents makes it worth mapping those flows explicitly as directed acyclic graphs, or DAGs, citing Apache Airflow right before the room recording ends (00:03:19). A DAG fixes the forward dependencies and compliance gates without allowing the process to loop backward past a required check (00:03:19).

Within that fixed graph, agents change the economics of parallel review (00:03:19). Independent checks that used to cost too much or take too much coordination to run side by side can now execute concurrently and merge their findings at a downstream gate (00:03:19). His slide titled "A process" illustrates the split: a `Change request` fans out in parallel to `Code review` (marked with an internal agent loop) and `Security scan` before converging at `Release approval`, separating the inner flow of people and agents from the outer policy boundary.

**Key points**

- Modeling workflows as DAGs preserves forward dependencies and mandatory approval gates.
- Agents make previously cost-prohibitive parallel reviews practical to run side by side.
- The outer graph enforces the policy boundary while people and agents collaborate inside individual nodes.

> “Previously, some work used to cost too much or be too complex to coordinate in this way. Now we can run independent reviews alongside each other, bring results together, but keep the required checks in place.”
> — 00:03:19

**Visual:** slide `experience/04-change-request-release.jpg` (parallel code review and security scan converging on release approval inside a policy boundary)

## Inside the loop: checking variable outputs with datasets and evals

Once the outer graph is fixed, Kormos's slides turn to the question he posed earlier on stage: how to bound agent work and build trust in its outputs (00:02:29). His "What's hard?" sequence zooms into a single adaptive node built as a three-step `draft -> check -> refine` loop. A draft only exits the node when the check diamond passes; a failure routes back to `refine`, shaped by four context inputs listed on the slide: prompt, model, MCP and tools, and memory.

Isolating that check diamond exposes why unit tests alone cannot govern an agent step. On his "Quality" slide, Kormos contrasts traditional deterministic software, where fixed `test cases` feed `unit tests` to establish confidence in expected behavior, with probabilistic agents whose outputs vary across runs. Trusting an adaptive loop requires representative `datasets` paired with `evals` that run repeatedly and apply statistical checks rather than expecting byte-identical answers.

**Key points**

- According to the slides, each adaptive workflow node runs a bounded `draft -> check -> refine` cycle gated by an explicit check step.
- Context inside that loop spans four moving parts: prompt, model, MCP/tools, and memory.
- Because agent outputs vary across runs, the slides pair traditional unit tests on the outer system with datasets and statistical evals on the agent.

> “So for our talk today, we're going to be focusing here where agents need process, what work we give them, what boundaries we set, and how we build trust in their outputs.”
> — 00:02:29

**Visual:** slide `experience/52-draft-check-refine.jpg`, `experience/56-traditional-tests-vs.jpg` (the draft-check-refine loop; traditional unit tests vs. probabilistic agent datasets and evals)

## Scoping the agent node and ramping down human review

Two closing examples on Kormos's slides apply this architecture to financial underwriting and production rollout, keeping runtime execution bound by institutional policy (00:00:18). On the slide "Where does the agent belong?", an underwriting DAG runs from `intake` through parallel `KYC` and `financials` nodes into a highlighted `credit memo` stage, followed by `risk review` and `decision`. Rather than handing the whole credit decision to an autonomous model, the slide scopes the agent to assembling the credit memo under four checked controls: `policy check`, `bounded loop`, `traced`, and `human fallback`.

His "Turning it on" chart then maps how human oversight changes once that bounded node goes live. At launch, staff review `every output` while eval scores climb; once measured performance crosses a `0.90` (`>= 0.9`) threshold line on the chart, supervision shifts to `sampled` review, and eventually to `exceptions only`. Kormos's final slide summarizes the whole talk in three lines: "Deterministic outside. Adaptive inside.", "Quality through evaluation.", and "People, Process, Technology."

**Key points**

- In the credit-underwriting slide example, the agent owns `credit memo` synthesis between parallel KYC/financials checks and human risk review.
- Every agent-driven node on the slide carries four explicit controls: policy check, bounded loop, full trace, and human fallback.
- Human supervision scales down along an eval curve: reviewing every output at first, sampling above a `0.90` threshold, and handling exceptions only once confidence holds.

> “Everything is expected to still be roughly bound by policy, but ultimately, we separate this from the run state and the build state.”
> — 00:00:18

**Visual:** slide `experience/12-credit-memo-workflow.jpg`, `experience/08-supervision-ramp-chart.jpg`, `experience/48-three-takeaways.jpg` (the credit-memo workflow node; the 0.90 supervision ramp chart; the three closing takeaways)
