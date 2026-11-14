---
title: "The Model Ate the Coding Harness. Now What?"
speakers: "Jediah Katz (SpaceX Super Intelligence)"
duration: "18:02"
source: transcript.md
video: "https://www.youtube.com/watch?v=7Y4sbZgBdnc"
themes: [token-economics-right-sizing-and-open-foundations, sandboxed-computers-context-architecture-and-the-shrinking-harness]
kind: talk-story
status: draft
---

# Frontier models absorbed coding scaffolding. The harness just moved up a level.

Jediah Katz spent 2025 as Cursor's longest-tenured agent-harness engineer before joining SpaceX Super Intelligence through the Super acquisition. He agrees with the benchmark papers showing that elaborate coding prompts and edit shims no longer raise coding eval scores, because a user-driven data flywheel trained those habits straight into frontier model weights. What survives, and grows more important, is the harness that opens unmastered multi-agent domains, runs durably in the cloud with scoped permissions and lower token costs, and cleans up its own temporary shims as models catch up.

## Two layers of a harness, and the rise and fall of "peak harness"

Katz traces three job titles across three years: prompt engineer in early 2023, context engineer by mid-2025, and harness engineer at the start of 2026 (00:00:00). An agent harness gives a model eyes and hands, connecting user apps on one side to computers and MCP services on the other (00:01:22). Architecturally, he splits it into two layers: a foundational **runtime** that owns the core agent loop, durable state, transport, and resumability, and a **context orchestration** layer that governs model routing, prompts, tools, memory, compaction, and behavioral tricks (00:01:22).

Early 2026 marked what Katz calls "peak harness" when Cursor unveiled a 3-million-line browser built over a week by `Grind Swarm`, an expensive multi-model, multi-machine harness that knocked Cursor offline once or twice during the demo push (00:01:22). Within months, builders declared the harness dead: Anthropic's Thariq (transcribed as "To read") wrote about deleting much of Claude Code's system prompt, YC's Garry Tan argued harnesses would thin out to skills, and Katz and his colleague Stefan Heule published how they tore out small file-apply models and codebase-exploration instructions that smarter frontier models no longer needed (00:01:22).

**Key points**

- Every harness divides into a traditional software runtime (loop, resumable state) and a context orchestration layer (prompts, tools, routing, compaction).
- Cursor's week-long `Grind Swarm` browser run marked "peak harness" before teams began deleting prompt scaffolding.
- Small edit-application models and hand-written repo-search instructions disappeared as frontier weights improved.

> “The runtime is kind of like the foundation of the harness. It controls where the core agent loop runs and how state is stored so that work can resume.”
> — 00:01:22

**Visual:** slide `experience/desktop-capture-dark-small.jpg` (minimalist "Prompt Engineer" opener tracing the shift from prompts to context to harnesses)

## Bash, `secrets.env`, and why coding harnesses stopped adding intelligence

To test whether sophisticated coding scaffolding still buys accuracy, Katz poses a minimal baseline: give a frontier model nothing except `bash` and a `secrets.env` file holding every key it needs (00:04:14). Two independent studies tested nearly that question and came back flat.

A UC Berkeley benchmark ran frontier models across multiple coding harnesses, including Pi, Codex, and Claude Code (transcribed as "Py Codex and Cloud Code"), and found harness choice barely moved `SWE-bench Lite` (transcribed as "SuperIntLight") scores on newer models (00:04:14). A separate Apple and EPFL paper found that dedicated machine-learning harnesses did not beat a minimal harness on `MLE-bench` (00:04:14). Katz agrees with the verdict: tricks like teaching a model how to search a repo, persist via `/goal` loops, or run tests to verify edits have become native model muscle memory (00:04:14).

**Key points**

- UC Berkeley found harness choice barely changed `SWE-bench Lite` pass rates on newer frontier models.
- Apple and EPFL found dedicated ML-engineering harnesses failed to outperform a minimal loop on `MLE-bench`.
- Repository exploration, persistent loops, and running tests have moved from harness prompts into model weights.

> “A fancy harness in this day and age no longer adds coding intelligence.”
> — 00:04:14

**Visual:** slide `experience/left-bash-logo-plus.jpg` (the minimal harness thought experiment: `BASH +` paired with a `secrets.env` editor buffer)

## Grok Bot and the return of scaffolding in unmastered domains

If coding scaffolding no longer raises accuracy, why keep investing in harnesses? Katz's first answer is that the harness unlocks the next frontier of work that models have not yet mastered (00:06:55). His example is **Grok Bot** (transcribed variously as "Rockbot", "Grokbot", "Rafa", and "Rockwise"), an autonomous colleague built for general knowledge work rather than single-session coding (00:06:55).

Instead of one-off chats, Grok Bot runs long-lived **coordinator bots** that own strategy with the user and farm tasks out to a fleet of worker agents, like a lead attorney delegating to paralegals (00:06:55). While Cursor spent early 2026 deleting prompts and guardrails, the Grok Bot team found itself adding them right back because models have not yet internalized office workflows: completing brittle web flows like slide decks and travel booking, sending status updates without spamming, judging when to act versus ask before emailing colleagues, and maintaining long-term working memory (00:06:55).

**Key points**

- Grok Bot replaces single-turn chats with long-lived coordinator agents managing fleets of worker agents.
- Entering unmastered knowledge work forced engineers to reintroduce domain prompts and action-versus-asking guardrails.
- High-risk external actions like emailing colleagues or booking travel still depend on harness policy and memory.

> “So Rockbot has a new kind of harness that operates not based off of one-off chats, but long-lived coordinator bots that orchestrate a fleet of worker agents.”
> — 00:06:55

**Visual:** slide `experience/why-care-about-harness.jpg` ("Why care about the harness? 1. The harness unlocks the next frontier for the model to solve.")

## Closing the data flywheel, from single agents to software factories

Stepping back, Katz connects Cursor's deleted scaffolding and Grok Bot's new scaffolding into a single five-stage **data flywheel** (00:04:14, 00:06:55). First, a frontier harness makes previously intractable tasks usable; second, users attempt those tasks with agents; third, real trajectories become training data for model labs; fourth, newer models absorb the skill natively; fifth, the harness deletes its scaffolding and moves to the next unmastered tier (00:04:14, 00:06:55).

Inside software engineering, that next tier is the multi-agent **software factory**, which Katz describes as a "meta harness" coordinating specialized agents across the full delivery lifecycle (00:06:55). Internally, a bug posted to a chat channel triggers automated triage, dispatches a cloud agent that builds a fix and records before-and-after UI videos as proof, and then hands off after merge to a `Rollouts` agent that watches production telemetry during deployment (00:06:55).

**Key points**

- Harnesses make themselves obsolete on each capability tier by generating the user trajectories that train the next model.
- Once raw coding commoditizes, the flywheel restarts one abstraction higher on non-coding engineering and office work.
- Internal software-factory loops chain auto-triage, cloud fix agents with before/after video proof, and production `Rollouts` watchers.

> “when a capability like coding gets commoditized by the model, it's actually the harness which unlocks a new frontier for the model to then solve, and kicks off that flywheel again.”
> — 00:06:55

**Visual:** slide `experience/cycle-diagram-data-flywheel.jpg` (five-node Data Flywheel diagram cycling from "Harness unlocks capabilities" to "Harness deletes the scaffolding")

## What models cannot absorb: cloud runtimes, scoped security, and cost

Katz's second argument is that critical parts of the harness sit outside context orchestration and can never be absorbed into model weights (00:11:59). First is **cloud runtime**: as agent tasks stretch from minutes to hours and days, they cannot depend on a laptop staying awake; by the end of his talk he predicts 90% of agent work will run off the laptop within six months (00:11:59, 00:14:01). Second is **scoped security and spend control**: `bash` plus `secrets.env` passes a benchmark, but real organizations require per-user permissions, explicit tool approvals, and hard caps against catastrophic actions or surprise $10,000 API bills (00:11:59).

Third is **efficiency**. Both the UC Berkeley and Apple/EPFL benchmark studies that showed flat accuracy across harnesses found major differences in task cost (00:11:59). Spending a month tuning Grok Bot's token efficiency and model-routing mix brought down user costs and cut reply latency by 65% at P50 and 72% at P90 on his slide, with zero hit to quality (00:11:59).

**Key points**

- Multi-day autonomous colleagues require always-on cloud runtimes rather than sleeping laptops.
- Scoped credentials, permission prompts, and spend ceilings live in infrastructure, never inside model weights.
- Tuning token efficiency and model mix cut Grok Bot reply latency 65% at P50 and 72% at P90 at equal quality.

> “If you think back to those two slides I showed, where the choice of harness did not make a significant difference in eval scores, both of those studies actually found that there was a significant difference in costs for tasks.”
> — 00:11:59

**Visual:** slide `experience/two-social-posts-jediah.jpg` (Grok Bot latency telemetry posts showing reply time down 65% at P50 and 72% at P90)

## Designing to be deleted: Hyrum's Law, subscriptions, and self-cleaning shims

Because product ambition is temporarily moving faster than model checkpoints again, Katz expects harnesses to get messier before they get cleaner, so teams should engineer every harness feature to be easy to delete (00:14:01). Citing **Hyrum's Law** (transcribed as "Hayr's law"), he notes that users inevitably depend on any internal knob you expose; hiding inner harness mechanics behind outcome-focused interfaces cuts change-management friction when scaffolding gets ripped out (00:14:01).

For agents themselves, Katz favors **composable primitives** over bespoke integrations. Rather than maintaining separate wake-up plumbing for emails, Slack mentions, red CI checks, PagerDuty alerts, and cron timers, his team built a single `subscriptions` primitive so an agent subscribes to any trigger through one unified tool (00:14:01). And for the hacky deterministic guardrails that still patch current model quirks, called **shims** on his slide (transcribed once as "chains"), every firing is logged to a time-series dashboard watched by a cleanup bot. The moment a newer model stops triggering a shim, the bot opens a pull request to delete it (00:14:01).

**Key points**

- Hide internal harness mechanics from users so Hyrum's Law does not block deleting obsolete scaffolding.
- Replace one-off webhook integrations with a single event-subscription primitive that filters, dedupes, and wakes agents.
- Log every deterministic model-patch shim and let a watcher agent open a removal PR as soon as firings drop to zero.

> “So now we have a bot who watches this dashboard, and whenever a shim stops firing, that model or that agent will put up a PR and say this shim can be cleaned up.”
> — 00:14:01

**Visual:** slide `experience/firings-shim-stacked-bar.jpg` ("Firings by shim" stacked bar telemetry tracking live activations across MCP and tool-call compatibility shims)
