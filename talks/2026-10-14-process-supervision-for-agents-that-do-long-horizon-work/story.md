---
title: "Process Supervision for Agents That Do Long-Horizon Work"
speakers: "Mitchell Troyanovsky (Basis)"
duration: "19:34"
source: transcript.md
video: "https://www.youtube.com/watch?v=JGtkTjn4120"
themes: [bootstrapping-domain-evals-without-public-benchmarks, sandboxed-computers-context-architecture-and-the-shrinking-harness, bounded-autonomy-runtime-governance-and-the-enterprise-diffusion-gap]
kind: talk-story
status: draft
---

# Nobody wants Move 37 on their tax return: scaling long-horizon agents with behavior specs

Individual engineers get 10x or 100x leverage from coding agents, yet average enterprise output barely moves. Basis co-founder Mitchell Troyanovsky argues that organizations already know how to scale non-deterministic workers through top-down, signed-off processes, and shows how encoding those workflow opinions into ground-truth-free "behavior specs," trajectory forking, and subagent simulations lets accounting firms trust multi-hour agent runs in production.

## How firms trust non-deterministic people, and where general agents break

Troyanovsky started with a puzzle familiar to everyone in the room: builders using Claude Code, Codex, or Cowork feel an order-of-magnitude jump in personal output, yet traditional companies see nothing close to that gain across their workforce (00:00:00). Looking at how an accounting firm operates explains why. A managing partner has no visibility into every keystroke made by junior preparers across dozens of clients, and human employees are non-deterministic too (00:00:00). The partner trusts the output anyway because leadership signs off on explicit processes, from the four-step month-end close down to which approved software extracts numbers from a bank PDF, that reliably generalize to sound work (00:00:00).

Dropping coding-style chat agents into an enterprise breaks that contract in two places (00:03:42). First is the **competency gap**: general-purpose agents outsource prompt crafting, memory management, skills, and a "theory of mind" over the model onto end users who have no training in agent engineering (00:03:42). Second is the **process gap**: letting every employee customize how their own agent extracts files or reconciles accounts inverts organizational governance, replacing firm-wide standards with ad hoc individual habits (00:03:42). Production agents have to hide the harness so using them feels as straightforward as asking a colleague, while following a single consistent process every day rather than acting brilliant on Monday and skipping a basic step on Tuesday (00:03:42).

**Key points**

- Accounting firms scale non-deterministic human staff by enforcing leadership-approved processes down to individual tasks like PDF extraction.
- General-purpose agents create a competency gap by pushing prompt, skill, and memory management onto everyday knowledge workers.
- They also create a process gap when individual employees invent separate workflows instead of executing a firm-wide standard.

> “The first problem is that there is a competency gap, because agents, as you think of them as you think of them today, they outsource the complexity to the user.”
> — 00:03:42

**Visual:** slide `experience/40-accounting-firm-org.jpg`, `experience/16-title-speaker-name.jpg`, `experience/52-month-end-close.jpg` ("How do organizations scale?" accounting-firm org chart; opening title card; decomposing month-end close and cash reconciliation)

## Reliability comes from explicit domain opinions, not open-ended choice

To make an agent both simple for the user and consistent for the firm, builders have to make opinionated workflow choices on the user's behalf (00:06:10). Troyanovsky emphasized that getting a right answer once is not the real bar; humans make mistakes too, and organizations can work around known limits so long as the worker fails and succeeds predictably (00:06:10).

Even a mundane step like reading a PDF bank statement exposes dozens of valid paths: passing pages straight to a vision-language model, writing Python against an open-source OCR library, calling a specialist OCR API, running one OCR pass verified by a vision model, or ensembling dozens of passes (00:06:10). Leaving that choice open-ended yields different behavior on every run. His slide shows Basis's concrete opinion for `mar_statement.pdf`: infer structure from the file, route to a specific OCR engine, and add vision-model verification whenever tables or diagrams could trip up text extraction, giving every PDF the exact same rule without asking the user to choose. Similar domain opinions come straight from practitioner common sense, such as reading primary tax statutes before answering a deduction question or snapshotting a generated PowerPoint slide to catch layout bugs, always weighing accuracy gains against added latency and cost (00:06:10).

**Key points**

- Leaving tool choice open-ended produces inconsistent runs even when each individual strategy is reasonable.
- Domain opinions, such as checking primary tax sources or routing table-heavy PDFs through vision verification, standardize execution without user prompting.
- Every opinion trades accuracy against latency and cost rather than chasing perfection at all expenses.

> “Not because the process it did was bad, but because the process it did was not opinionated.”
> — 00:06:10

**Visual:** slide `experience/56-pdf-reading-decision.jpg`, `experience/00-simple-agent-ocr.jpg` ("An example opinion: reading any PDF" routing diagram; five competing ways an unopinionated agent might extract a bank statement)

## Why outcome evals run out on long horizons, and why context is runtime training data

Outcome-based evaluations, meaning test cases paired with known ground-truth answers, remain useful for choosing initial opinions, yet they cover only a sliver of real-world accounting work (00:09:16). A benchmark of 100 or 1,000 labeled cases sits inside a production distribution of hundreds of thousands of client situations, and as long-horizon trajectories stretch across hours, the tree of intermediate decisions branches exponentially (00:09:16).

Troyanovsky walked through a concrete cash-reconciliation rule shown on his slide: when a bank statement ($48,210.55) and the books ($47,798.49) disagree by $412.06 because of an OCR misread, the agent must investigate and explain the discrepancy rather than posting an unsourced "plug" entry just to make the numbers tie (00:09:16). Enforcing that rule in a large harness takes far more than dropping two sentences into a system prompt. Behavior emerges jointly from the system prompt, progressive skill disclosures, tool definitions, and pretrained model instincts that badly want validation checks to pass (00:09:16). Builders should treat every token entering the working window not as a casual "prompt," he argued, but as **runtime training data** that shapes what the model optimizes for mid-flight (00:09:16).

**Key points**

- Static outcome evals with ground-truth answers cannot cover the exponential branching of multi-hour production trajectories.
- In cash reconciliation, a model eager to make checks pass may post an unsourced plug adjustment instead of investigating a variance.
- System prompts, progressive disclosures, and tool schemas act together as runtime training data governing agent decisions.

> “really think of the context that agent is going to see as it's working as runtime training data. The word prompt, I think, trivializes it a bit, right?”
> — 00:09:16

**Visual:** slide `experience/20-behavior-statement-cash.jpg` ("Here's a behavior we want": investigating a $412.06 bank-to-book variance instead of posting a plug entry)

## Behavior specs grade production trajectories without an answer key

Because a single desired behavior spans prompts, skills, and tools simultaneously, Basis separates intent from harness code using **behavior specs** (transcribed as "behavior stack" / "behavior step", and open-sourced with Braintrust at `agentbehavior.dev` on his slide) (00:12:01). Before editing prompts, the team writes down only its highest-leverage workflow opinions, acting like a concise product spec for agent conduct rather than duplicating every line of context (00:12:01).

Once written, a behavior spec doubles as a ground-truth-free rubric over any trajectory, including live customer runs where no answer key exists (00:12:01). An LLM judge inspects the run log and answers two questions: did the agent enter a situation where this spec applied, and if so, did it follow the behavior (00:12:01)? On his slide's log example, the agent searched for the missing $412.06, found nothing, posted an unsourced `Reconciling adjustment, $412.06`, got a `PASS` from `check_reconciliation`, and reported `$0.00 variance`. Without needing a labeled ground-truth workbook, the judge flagged `Applies? Yes`, `Followed? No`, turning ungraded production traffic into dense supervision signal far faster than hand-curating outcome datasets (00:12:01).

**Key points**

- Behavior specs capture a team's core workflow opinions outside the agent's prompt context.
- A model judge checks any trajectory for two things: whether the trigger situation arose and whether the agent followed the spec.
- Grading process directly catches silent failures, like an unsourced reconciling plug, on live runs that have no ground-truth answer key.

> “And you can say, in this particular trajectory, whether that is in any trajectory that doesn't have a ground truth, did the agent get into a situation in which this behavior was relevant?”
> — 00:12:01

**Visual:** slide `experience/40-behavior-spec-judge.jpg` ("The spec and the judge": catching an unsourced $412.06 adjustment in a production log with no answer key)

## Debugging thousand-call runs with trajectory forking and subagent simulations

Flagging a bad decision solves only half the problem when a trajectory spans five hours and 1,000 inference calls (00:13:40). Outcome evals tell you a five-hour run failed at the end without telling you where; pairing behavior specs with **trajectory forking** isolates the exact step where the agent went wrong (00:13:40). Replicating full database and cloud state at an arbitrary checkpoint is hard engineering, Troyanovsky noted, yet once built, engineers can fork right after the bad call to ask the agent why it acted that way, or fork right before the call to test harness fixes repeatedly (00:13:40). On his slide, running five forks across three candidate fixes revealed that tweaking skill wording or adding "Never force a reconciliation to tie" to the system prompt worked only "Sometimes", whereas changing the `check_reconciliation` review tool itself succeeded on every fork: "The fix was the tool, not the prompt."

Because cloud state forking is expensive to build and run, Troyanovsky also shared his favorite lightweight loop, which he used for over a year and a half before Basis built full forking: **subagent simulations** (00:13:40). Inside a coding agent, he renders the production agent's exact system prompt and skills, spawns a subagent instructed to role-play the production agent without cheating, and feeds it synthetic scenarios, such as the $412.06 OCR misread, a legitimate $35 bank fee, or a missing statement page shown on his slide, to smoke-test context and tool edits in seconds (00:13:40).

**Key points**

- Forking state right before a flagged violation pinpoints fixes inside thousand-call trajectories without re-running five-hour jobs from scratch.
- On Basis's slide experiment, modifying the `check_reconciliation` tool fixed the plug behavior reliably across forks where prompt edits only worked intermittently.
- Spawning a coding subagent with the rendered production prompt and skills provides a fast, cheap smoke test before full environment forking exists.

> “when working with coding agents, ask the coding agent to make a subagent that pretends to be your production agent. And you can tell it to not cheat, and give it the system prompt and the skills, and you render everything perfectly.”
> — 00:13:40

**Visual:** slide `experience/24-forking-comparison-three.jpg` ("Forking": comparing five forked runs across skill wording, system prompt edits, and fixing the `check_reconciliation` tool)

## Blast radius, earned trust, and why tax returns don't need Move 37

Returning to the accounting firm, Troyanovsky compared adopting an agent to reviewing pull requests from a coworker (00:17:21). Every review weighs two axes: the blast radius if the change is wrong, and the reviewer's earned trust in the author's competence. A junior engineer touching a core service gets line-by-line scrutiny; a trusted veteran editing an internal doc barely needs a glance (00:17:21). Agents diffuse through firms along the exact same grid, starting on narrow, low-stakes tasks where simple interfaces and opinionated consistency let reviewers build confidence over time (00:17:21).

He closed by answering the commonest objection from AI researchers: if you constrain an agent with human workflow opinions, won't you stop it from discovering a superhuman shortcut like AlphaGo's famous Move 37 (00:17:21)? Perhaps, he said, and in accounting that is a feature, not a loss. Economic output scales when organizations can audit, predict, and work beside their tools; as base models improve, the encoded opinions simply move up a level of abstraction while closing a self-improving loop in production (00:17:21).

**Key points**

- Organizational trust scales along two axes: the blast radius of a mistake and the agent's track record of consistent execution.
- Opinionated agents earn autonomy gradually, moving from line-by-line review on narrow steps to broader month-end workflows.
- Enterprises pay for auditable consistency at scale rather than creative "Move 37" surprises on client books or tax returns.

> “Nobody wants their agent to move thirty-seven their tax return. They want it done reliably at scale in a way that they can trust, and in a way that their people know how to work with.”
> — 00:17:21

**Visual:** slide `experience/08-trust-stakes-grid.jpg`, `experience/44-four-takeaways.jpg` ("Back to the firm" stakes-versus-trust supervision grid; closing four takeaways slide)
