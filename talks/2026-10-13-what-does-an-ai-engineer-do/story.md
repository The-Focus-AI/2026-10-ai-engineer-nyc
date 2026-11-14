---
title: "What does an AI engineer do?"
speakers: "Aparna Dhinakaran (Arize AI)"
duration: "14:59"
source: transcript.md
video: "https://www.youtube.com/watch?v=ImnZ7s68jw8"
themes: [bootstrapping-domain-evals-without-public-benchmarks, self-improving-agents-and-agent-management, the-sandboxed-computer-and-evolving-harness, owning-open-foundations-vs-renting-the-frontier]
kind: talk-story
status: draft
---

# Stop writing the feature. Build the loop that writes it.

On the main stage on Oct 13, Aparna Dhinakaran came with a funnel and a job description. A few thousand people already run swarms of agents; almost everyone else is still working feature by feature. Her answer to "what does an AI engineer do?" is that the job has moved up one level: you build, and then evaluate, the system that does the work.

## A few thousand people are already running the factory

She starts from a funnel making the rounds that weekend: roughly six billion people who have barely touched an LLM, one to two billion casual free-tier users, about twenty million professionals for whom an agent compresses weeks of work into days, and around five thousand people at the frontier running thousands of agents at once (00:00:00). The slide puts Andrej Karpathy's post beside her own reply: labs work on problems that have data and are testable, and businesses mostly do not.

The first question anyone asks of that funnel, she says, is where they sit on it, and how they get to the top in the next couple of years (00:00:00). She closes the talk on the same gap: business data is messier than a lab's constrained, testable problems, and the AI engineer is the role that has to close the distance (00:09:45).

**Key points**

- A tiny fraction of users already run thousands of agents; most work is still done one feature at a time.
- The gap is partly about problem type: labs pick testable problems with data, businesses rarely have them.
- The AI engineer's job is to close that gap inside a business.

> “AI engineers are kind of the role to close that gap.”
> — 00:09:45

**Visual:** photo `photos/PXL_20261013_141544817.jpg` (the "1000x Agent Engineer" funnel with Karpathy's post and her reply)

## The unit of work is now the loop

The abstraction layer has been rising for decades, she argues, and faster in the last few years: from high-level languages, to copying code out of chat, to local agents, to cloud agents, to the expectation that every engineer runs a team, or a factory, of agents (00:00:00).

That changes the job row by row. You no longer just write the feature; you build the loop that writes it. You no longer just read the diff; you set up agents to do the code review, and evals to judge the non-deterministic paths. You no longer just set up metrics; you have agents read the observability data and find the patterns. The familiar cycle of build, eval, ship, monitor and improve is still there, but the engineer now owns the system that runs each step rather than running the steps by hand (00:00:00).

**Key points**

- Each step up the abstraction ladder ends at the same place: running agents, not writing code.
- Code review, testing and monitoring each become something an agent does and the engineer sets up.
- The engineer owns the loop: build, eval, ship, monitor, improve.

> “As an AI engineer, your job is no longer to just write the feature, write a bad feature. It's about how do you build the loop.”
> — 00:00:00

**Visual:** photo `photos/PXL_20261013_141729014.jpg` ("The AI engineer, then and now": last year a feature, now a system to run the loop) · photo `photos/PXL_20261013_141707558.jpg` ("How we got here": high-level languages to a factory of agents)

## Telemetry is now written for agents to read

Arize's own example is Signal, an always-on agent that reads traces, finds patterns in the telemetry and, with access to the repo, puts up a fix as a PR (00:00:00). It has to remember what it has already seen: an issue it flagged before, or one that looked minor and becomes critical as more data arrives.

Building it taught them that the consumer of telemetry has changed. It is not humans, and not humans with agents helping; the question is how to shape telemetry so that agents are its primary readers (00:00:00). Once that is true, observability data becomes the trigger. Signal can run on a cadence, pulling the last few hours of traces every three or six hours; it can wake on an event, such as a user complaining in Slack; or it can fire on a metric (00:04:53).

**Key points**

- Signal reads traces, tracks issues across runs, and can open a PR with a fix.
- Telemetry should be designed with agents, not people, as its main consumer.
- Schedules, Slack messages and metrics are all triggers that wake the agent.

> “How do you set up your telemetry data so that agents are the primary consumers of that data?”
> — 00:00:00

**Visual:** photo `photos/PXL_20261013_142020914.jpg` ("What triggers the agent": Slack, messages, a schedule, a metric, a meeting, another agent)

## What a run keeps, and what it throws away

Each run is assembled fresh. When the agent wakes, everything it needs goes into a sandbox: the traces and context, third-party APM logs and metrics, the repo, and the keys it requires (00:04:53). One proxy is the only way in or out, and everything inside the sandbox is traced.

When the run ends, some things stay on purpose: the issues it found, saved to memory so the next run does not start from zero; the traces of what the agent did, including any PR; and skills it learned, saved back to the repo. The rest is thrown away: the sandbox is torn down, credentials are removed, repo access is revoked (00:04:53). State lives outside the sandbox, so a failed sandbox or harness can be relaunched and pick up from the step that failed.

Signal is also deliberately agnostic. It started on Claude Code, now supports Cursor and Codex, aims at the major open-source harnesses, and can run different models. That, she says, is how they measure the agent's quality each time and keep its cost in check without losing rigor (00:04:53).

**Key points**

- Every run gets a fresh sandbox behind a single proxy, and everything inside is traced.
- Findings, traces and learned skills persist; sandbox, credentials and repo access do not.
- Supporting several harnesses and models lets them trade cost against quality and measure it.

> “The only way to get information in and out of the sandbox is by this single proxy.”
> — 00:04:53

**Visual:** photo `photos/PXL_20261013_142240994.jpg` ("What happens after each run": kept on purpose versus thrown away)

## Defining good: evaluate the evaluators

Every time Signal puts up a PR, evals run on top of it (00:09:45). This is where she thinks an AI engineer should spend much of their time: looking at traces with their agents, finding the common errors, and turning them into evals that agree with human judgment. (The transcript hears "evals" as "emails" and "e-bells" in this section.) Arize ships an evaluator skill for building and aligning them.

The question teams ask her is how to trust the evaluator. Arize's answer for its own products is to build golden datasets, run the evals, check them against human labels, and only ship a new evaluator once the judge agrees with the human (00:09:45). The same evals then run offline on each change and online over production telemetry. And "trace everything" now includes the coding agents that build the agents, so you can see what happened inside the factory (00:09:45).

**Key points**

- Evals run on every agent-made PR; aligning them with human judgment is the engineer's core work.
- A judge is shipped only after it agrees with human labels on a golden dataset.
- Trace both the agents and the coding agents that build them, then evaluate online.

> “We actually evaluate the evaluators.”
> — 00:09:45

**Visual:** photo `photos/PXL_20261013_142631564.jpg` ("Creating an eval": look at traces, find errors, build the eval, align the judge)
