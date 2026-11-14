---
title: "Theme 03: Sandboxed Computers, Context Architecture, and the Shrinking Harness"
theme_id: "sandboxed-computers-context-architecture-and-the-shrinking-harness"
kind: theme-deep-dive
phase: archive
talks: 9
claims: 18
---

# Sandboxed Computers, Context Architecture, and the Shrinking Harness

As frontier models absorb prompt-level coding tricks through a user-trajectory data flywheel, the durable agent harness converges on two layers models cannot internalize: isolated create-run-delete VM sandboxes and outer-loop context engines that supply institutional intent, living codebase maps, and precomputed KV caches.

OpenHands framed the central paradox of 2026 harness design: coding scaffolding makes harder tasks tractable, user trajectories feed model post-training, and models absorb those habits until harness choice barely moves coding benchmark scores—motivating self-cleaning guardrail shims that watcher bots delete once newer models stop triggering them. What models cannot absorb defines the lasting architecture. First is the execution boundary: Daytona showed that every competing framework reduces to create-run-delete VM primitives and is actively deleting local executors because embedded runtimes still expose host tools and a single allowed `python -c` command compromises the host; Arize and Greptile isolate every run in disposable sandboxes while persisting memory externally. Second is outer-loop context: Linear showed that five-cent intelligence shifts failure from coding capacity to product incoherence unless triage agents assemble customer value, logs, and prior decisions upfront; Greptile replaces grep with a living company wiki; Sonar Vortex feeds structural maps in-loop to cut token spend 36%; Ramp compresses 20–30x month-end context into offline KV-cache cartridges; GEICO routes edge-case HTML worksheets to domain owners; and Basis treats every working-window token as runtime training data. Yet as OpenHands noted in counter-point, entering unmastered domains like autonomous multi-agent colleagues immediately forces teams to re-add heavy prompting, coordinator hierarchies, and guardrails.

## Give the model a disposable VM computer and decouple durable state

- **Jediah Katz (The Model Ate the Coding Harness. Now What?, 00:04:14)**: Coding harnesses obsolete their own context-layer scaffolding through a data flywheel in which scaffolding makes harder tasks tractable, user trajectories train frontier models natively, and harness choice stops changing coding benchmark scores.
  > “It turns out the harness is actually making itself obsolete through what I call the data flywheel. So in this process, the harness brings harder and harder coding tasks within reach.”

- **Jediah Katz (The Model Ate the Coding Harness. Now What?, 00:01:22)**: An agent harness divides architecturally into a foundational runtime layer—managing core loop execution and durable state persistence—and a context orchestration layer governing model routing, tools, memory, compaction, and behavioral guardrails.
  > “The runtime is kind of like the foundation of the harness. It controls where the core agent loop runs and how state is stored so that work can resume.”

- **Jediah Katz (The Model Ate the Coding Harness. Now What?, 00:14:01)**: Teams can ship deterministic guardrail shims for current model flaws without accumulating permanent codebase debt by logging every shim activation and having an automated watcher agent open a removal PR once newer models stop triggering it.
  > “So now we have a bot who watches this dashboard, and whenever a shim stops firing, that model or that agent will put up a PR and say this shim can be cleaned up.”

- **Jediah Katz (The Model Ate the Coding Harness. Now What?, 00:14:01)**: To iterate rapidly without Hyrum's Law lock-in or integration sprawl across Slack messages, CI status alerts, and timers, harnesses should hide internal mechanics from users and expose composable agent primitives like a unified event-subscription tool.
  > “Now, rather than having one separate integration, or you having separate integrations for each of these things, we have one framework and one tool that the model can use, that the agent can use to subscribe to an event.”

- **Mislav Ivanda (Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On, 00:03:28)**: Host-level command allowlists and approval prompts fail to bound what a compromised model can do because permitting a single interpreter command like `python -c` grants unrestricted socket, filesystem, and code execution access.
  > “when you allow your cloud agent to run Python command with Python dash C, he can literally open any sockets, modify a file system, execute code, or do basically everything”

- **Mislav Ivanda (Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On, 00:07:40)**: Across 2026 releases, agent frameworks such as CrewAI and AG2 are actively deleting legacy local code executors and forcing execution into isolated VM or process sandboxes that can be discarded upon compromise.
  > “And you can notice that they are not adding sandboxes, they already had them, but they are deleting all the alternatives”

- **Mislav Ivanda (Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On, 00:09:18)**: Sandboxes have evolved from short-lived single-snippet executors into full agent runtimes and massively parallel fleets of thousands of concurrent environments powering reinforcement learning post-training, evaluations, and subagents.
  > “if they can run thousands of these executions environments concurrently, they can do really interesting stuff, especially regarding reinforcement learning, fine-tuning, post-training benchmarks, evals.”

- **Mislav Ivanda (Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On, 00:00:05)**: Whether exposed as a tool, an external plugin, or a subclassed internal API, competing agent frameworks all reduce sandbox integration to the same three lifecycle primitives: create, execute, and delete.
  > “But under the hood, all of these ways speak the three same lines, so it's sandbox creation, running some code or task inside the sandbox, and sandbox deletion.”

- **Aparna Dhinakaran (What does an AI engineer do?, 00:06:32)**: Signal decouples ephemeral compute from durable state — tearing down sandboxes, credentials, and repo access after each run while checkpointing step state, detected issues, traces, and learned skills externally across model- and harness-agnostic runners.
  > “What stays is that if it found any issues, all of the output is actually saved off in some kind of memory, so that the next time an agent gets spun up, it doesn't have to start from ground zero.”

## Outer-loop context engines: living wikis, structural maps, and triage

- **Tariq Shaukat (The Machine that Changed the World, vAI, 00:10:56)**: Supplying structural codebase maps and verification guide rails inside the agentic loop via Sonar Vortex reduces token spend by 36% and cuts commit-time issues by 92% on large, long-running tasks.
  > “And what we see when we provide agents in long-running, large, complex databases with long-running tasks, with this information is a 36 percent reduction in token cost because you're putting it in white claims.”

- **Tom Moor (Your Coding Agent Has a Context Problem, 00:02:20)**: As intelligence that cost $100 three years ago drops to five cents and agents run unattended for hours or days, context can no longer be hand-fed interactively and must be orchestrated by outer-loop systems.
  > “I think one of the main reasons is that the context kind of moves out of that inner loop and largely into the outer loop.”

- **Tom Moor (Your Coding Agent Has a Context Problem, 00:06:18)**: Cheap, abundant code shifts the core failure mode to product incoherence because agents reading source code alone miss user intent, prior design trade-offs, parallel org work, decision ownership, and recent revert risks.
  > “Implementation is not the bottleneck now. The failure mode here isn't an inability to build. The failure mode is like an inability to maintain coherence, to have a product that makes sense as a whole.”

- **Tom Moor (Your Coding Agent Has a Context Problem, 00:08:47)**: Linear's triage agent deduplicates multi-channel intake and enriches issues via internal MCPs with customer value, request frequency, Datadog logs, stack traces, live bug reproductions, and prior related decisions before coding starts.
  > “It's been enriched with the customer information. Hey, this is a high value customer, this is the third time they've requested this in a month. Any stack traces, maybe if it's a bug, logs from DataDog that are associated.”

- **Daksh Gupta (How to build an AI code review agent: from the creators of Greptile, 00:10:45)**: Replacing imprecise, token-heavy grep searches with a continuously maintained wiki that synthesizes codebase architecture, production telemetry, docs, and tickets gives review agents surgical tribal context.
  > “Now, the way that Greptile approaches this problem is we actually disintermediate all of these context sources with a living wiki. This wiki is essentially a sort of world model of how your company works.”

## Runtime training data: KV-cache cartridges and interactive SME worksheets

- **Mitchell Troyanovsky (Process Supervision for Agents That Do Long-Horizon Work, 00:09:16)**: In long-horizon agent harnesses, behavior emerges jointly from system prompts, progressive disclosures, tool descriptions, and model weights, so every token entering the working window must be engineered as runtime training data.
  > “really think of the context that agent is going to see as it's working as runtime training data. The word prompt, I think, trivializes it a bit, right?”

- **Ford Prior (Inside the Fable War Room, 00:11:18)**: At each milestone, the war room generates interactive HTML worksheets and editable architecture diagrams that route sharp edge-case questions to domain owners and ingest human edits back into agent context.
  > “It was like, wow, that's actually a great question that we've never thought about identifying an edge case either in the business with technology.”

- **Alexander Shevchenko (Chasing capabilities while waiting for the frontier, 00:05:09)**: Offline KV-cache cartridges compress 20x to 30x more predictable context—such as ledgers and aging reports prepared overnight before month-end close—with lower engineering lift and broader generalizability than post-training.
  > “cartridges are really interesting family of techniques where you're able to compress a lot of context, up to 20 to 30 times more context, into the KB cache offline and serve it for your agent.”

