---
title: "Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On"
speakers: "Mislav Ivanda (Daytona)"
duration: "15:26"
source: transcript.md
video: "https://www.youtube.com/watch?v=WWIFiQi9U4w"
themes: [token-economics-right-sizing-and-open-foundations, sandboxed-computers-context-architecture-and-the-shrinking-harness]
kind: talk-story
status: draft
---

# Agent frameworks agree on nothing except giving the model a separate computer.

Mislav Ivanda spent a year integrating Daytona's sandbox across competing AI agent frameworks, workflow tools, and developer products. Frameworks that disagree on what an agent is, what language to write in, and whether humans or models control the flow all reduce sandbox integration to the exact same three operations: create a computer, run code inside it, and delete it. Because your execution boundary dictates how every tool in your stack is built, Ivanda argues you must commit to that boundary before picking a framework.

## Six competing frameworks, the same three lines of code

Ivanda opened with a short quiz: a `@tool(name="run_code")` snippet that spins up a sandbox, runs generated code, and tears it down, asking the audience which framework it belonged to (00:00:05). Guesses ranged across LangChain, LangGraph, and Google ADK, and his point was that any of them would fit (00:00:05). Across LangChain, CrewAI, Google ADK, Pydantic AI, OpenAI Agents SDK, and Mastra, the Daytona integration code is almost indistinguishable (00:00:05).

Surface plumbing varies: one framework registers a `@tool`, another loads an external plugin, and a third subclasses an internal sandbox base class. Underneath every wrapper sit the same three lifecycle calls: `create`, `code_run`, and `delete` (00:00:05). That convergence stands out because these projects are direct competitors that otherwise share almost no design opinions (00:01:58). LangGraph models an agent as a traversable graph, CrewAI treats agents as autonomous role-players, OpenAI's Agents SDK wraps a loop around a model, and Anthropic's Claude Agent SDK ships a packaged runtime with minimal customization, split across Python and TypeScript and divided over whether developers or models steer control flow (00:01:58). When rivals that agree on nothing else land on the same primitive, Ivanda noted, it is a necessity rather than a passing fashion (00:01:58).

**Key points**

- Integrating sandboxes across six major agent frameworks comes down to the same three calls: create, run, and delete.
- Competing frameworks disagree on agent abstractions (graphs, crews, loops, packaged runtimes), languages, and control flow.
- Universal convergence among competitors signals an unavoidable infrastructure requirement rather than a trend.

> “But under the hood, all of these ways speak the three same lines, so it's sandbox creation, running some code or task inside the sandbox, and sandbox deletion.”
> — 00:00:05

**Visual:** slide `experience/28-six-framework-logos.jpg`, `experience/16-daytona-title-card.jpg`, `experience/12-frameworks-agree-nothing.jpg` (six frameworks sharing the same three sandbox lines; the Daytona title card; how frameworks disagree on everything else)

## Why host allowlists and embedded runtimes still expose your machine

Any useful agent eventually needs to run generated scripts, shell commands, package installs, or tests, raising the question of where that execution happens (00:03:28). Ivanda walked through three isolation postures. The first is running on the developer's or server's own machine behind command allowlists, approval prompts, and interception hooks. Most users click "yes" without reading, and allowing `python -c` quietly hands the model raw socket creation, filesystem mutation, and arbitrary execution (00:03:28). A permission prompt states what the model **should** run, not what a prompt-injected or misbehaving model **can** reach (00:03:28).

The second posture moves generated scripts into an embedded engine such as V8 or QuickJS (00:03:28). While that restricts direct filesystem and network calls from the script itself, the subtlety lies in tool bindings: when the sandboxed glue code invokes `query_database` or `send_email`, those registered tools execute outside the runtime on the host machine, letting a compromised agent act maliciously through privileged host credentials (00:03:28). Only the third posture, a separate container or microVM reached over an API, keeps execution off your infrastructure so a compromised step never becomes a compromised application; you throw away the tainted VM and boot a fresh one (00:03:28).

**Key points**

- Approving an interpreter like `python -c` defeats host command allowlists by unlocking arbitrary sockets and file edits.
- Embedded V8 or QuickJS runtimes isolate glue scripts while still running database or email tools on the host.
- A separate microVM or container over an API ensures a compromised step can be discarded without compromising the app.

> “when you allow your cloud agent to run Python command with Python dash C, he can literally open any sockets, modify a file system, execute code, or do basically everything”
> — 00:03:28

**Visual:** slide `experience/40-separate-computer-isolation.jpg` ("Answer No.3: On a separate computer" — container or microVM over an API so a compromised step is not a compromised app)

## In 2026, agent frameworks started deleting their local executors

To show that the ecosystem has already voted on this boundary, Ivanda put up a receipts table of 2026 framework releases (00:07:40). In April 2026, CrewAI removed its local `CodeInterpreterTool` and deprecated `allow_code_execution`, pointing users to dedicated sandbox services instead (00:07:40). In July 2026, AG2 1.0 retired its legacy `autogen.coding` local executors in favor of a sandbox tool class requiring an explicit execution environment (00:07:40).

Other SDKs drew similar lines: the Claude Agent SDK uses OS-level process sandboxing such as Bubblewrap on Linux for Bash commands, OpenAI's Agents SDK introduced `SandboxAgent` with Docker and hosted sandbox clients while explicitly flagging the risks of local execution, and Mastra's docs tell builders to choose their execution boundary deliberately (00:07:40). Crucially, these frameworks already had optional sandbox integrations; what changed in 2026 is that maintainers started deleting the unsafe local alternatives (00:07:40).

**Key points**

- CrewAI (April 2026) and AG2 1.0 (July 2026) removed built-in local code executors in favor of explicit sandboxes.
- OpenAI Agents SDK, Claude Agent SDK, and Mastra now surface explicit sandbox boundaries or process isolation.
- Frameworks are not merely adding sandbox plugins; they are actively removing host-level execution paths.

> “And you can notice that they are not adding sandboxes, they already had them, but they are deleting all the alternatives”
> — 00:07:40

**Visual:** slide `experience/56-receipts-table-framework.jpg` ("Receipts: The frameworks already voted" — 2026 changelog table across CrewAI, AG2 1.0, Claude Agent SDK, OpenAI Agents SDK, and Mastra)

## One ephemeral tool call grew into fleets of thousands of computers

Alongside stricter isolation, how teams use sandboxes expanded through three distinct stages (00:09:18). Early integrations treated a sandbox as a disposable calculator: spin up a short-lived machine for a single tool call, analyze a CSV or run a snippet, return stdout, and destroy the VM immediately (00:09:18).

As models grew more capable, teams moved the entire agent loop inside the sandbox so it could operate as a persistent runtime with full filesystem, shell, and network access (00:09:18). Most recently, one computer became a thousand: teams fan out thousands of concurrent isolated environments for parallel evaluations, reinforcement learning rollouts, post-training benchmarks, bulk multi-repo refactors, and agents spawning subagents (00:09:18).

**Key points**

- Stage one used ephemeral sandboxes for single-shot code snippets and CSV analysis.
- Stage two moved the whole agent inside the VM as a full-featured workspace runtime.
- Stage three fans out thousands of parallel sandboxes for RL post-training, evals, and subagent fleets.

> “if they can run thousands of these executions environments concurrently, they can do really interesting stuff, especially regarding reinforcement learning, fine-tuning, post-training benchmarks, evals.”
> — 00:09:18

**Visual:** slide `experience/05-one-many-tree.jpg` ("Then one computer became a thousand" — fanning out concurrent sandboxes for parallel evals, RL rollouts, bulk refactors, and subagents)

## Most framework decisions are swappable; execution posture locks you in

Developers routinely start new projects by asking which agent framework to pick, which Ivanda called the wrong first question (00:10:16). Almost every axis people agonize over during framework selection can be changed later at manageable cost: switching between two Python or TypeScript frameworks is a bounded refactor, swapping models and prompts takes regression testing, missing observability or memory features can be added via plugins (with cloud durable execution as the one notable architectural exception), and even sandbox vendors are interchangeable because they all speak `create`, `run`, and `delete` (00:10:16).

What you cannot easily swap later is your execution posture: whether code and tools run on the host, in-process, or on a separate computer (00:10:16). Teams that prototype locally write every tool assuming direct access to the application process and local filesystem without separation, then carry that proof-of-concept straight into production until a security incident threatens the product (00:10:16).

**Key points**

- Frameworks, models, prompts, plugins (aside from durable execution), and sandbox providers can all be swapped later.
- Local POCs silently couple every custom tool to the host process and unseparated filesystem.
- Retrofitting isolation onto host-coupled tools in production requires rewriting your system architecture.

> “if you're guessing that you'll use first approach, where everything runs locally, then you write all your tools to use your host or app process environment, using your file system without separation and stuff like that.”
> — 00:10:16

**Visual:** slide `experience/57-swappable-vs-committed.jpg` ("What actually locks you in: Swappable decisions vs. a commitment")

## Pick the execution boundary before you pick the framework

Ivanda closed with a concrete rule of thumb, printed on his final takeaway slide as "Frameworks are opinions. The boundary is a commitment" (and transcribed slightly garbled in the room audio as "framers our opinions and the boundary the commitment") (00:13:41). Before choosing an orchestration library, define an execution interface under your own control that targets a separate computer from day one (00:13:41).

With that boundary fixed up front, untrusted code and tools stay quarantined behind an API you own, security is addressed structurally rather than bolted on with regex filters, and every layer above or below (framework, model, or sandbox provider) stays straightforward to swap as the ecosystem shifts (00:13:41).

**Key points**

- Define your own execution boundary interface before adopting any agent framework.
- Target a separate computer from the first prototype so tools never depend on host state.
- Isolating execution behind a clean interface keeps frameworks, models, and providers swappable.

> “And as I like to say, and the sentence I would maybe like for you all of you to remember out of this talk is, framers our opinions and the boundary the commitment.”
> — 00:13:41

**Visual:** slide `experience/57-pick-boundary-before.jpg` ("Pick the boundary before the framework. Frameworks are opinions. The boundary is a commitment.")
