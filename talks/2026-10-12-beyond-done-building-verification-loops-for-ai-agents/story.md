---
title: "Beyond “Done”: Building Verification Loops for AI Agents"
speakers: "Nick Nisi (WorkOS), Zack Proser (WorkOS)"
duration: "56:47"
source: transcript.md
themes: [deterministic-verification-loops-over-line-by-line-review]
kind: talk-story
status: draft
---

# Status comes from receipts, not from an agent saying it is done.

Nick Nisi and Zack Proser from WorkOS opened with a nine-second horror story: an unsupervised agent wiping a production database. Their 57-minute workshop makes the case that reading every line of every pull request cannot scale when one engineer drives eighteen agent tabs at once, so each application needs its own deterministic verifier CLI, external completion gates, and saved run receipts.

## The UI says saved, and reload wipes it clean

Reviewing generated pull requests line by line breaks down once agents write code faster than humans can read it (00:02:47). Engineers write less of the underlying code themselves, lose familiarity with its internals, and split their attention across parallel chat sessions and terminal tabs (00:02:47). Under those conditions, a build that compiles and passes a shallow browser check still ships broken behavior (00:02:47).

Nisi and Proser demonstrated the failure mode on a small workshop app called Midnight Snack Club (00:02:47). Submitting an email address on the waitlist form updates the page and displays a confirmation message, enough for a naive Playwright assertion to pass and for an agent to report the task complete (00:02:47). Reloading the browser reveals an empty list because nothing wrote the address to storage (00:02:47).

**Key points**

- Line-by-line human review loses signal when one engineer runs a dozen or more parallel agent lanes.
- Optimistic DOM updates let shallow browser tests pass even when backend or local persistence is missing.
- Self-reported agent success is untrustworthy unless verification checks both visible UI state and durable storage.

> “And yes, it did do something to the UI, but we didn't check the other half. And so it was never persisted, and we lost that email.”
> — 00:02:47

**Visual:** diagram "Optimistic UI check passing on DOM update vs. reload check exposing missing storage persistence"

## Put the completion gate outside the agent

Quoting engineer Lauren Tan on stage, Nisi framed verification as the prerequisite for everything else an agent does, especially as teams experiment with recursive self-improvement loops across multiple codebases (00:07:02). Left with a vague prompt, an agent fills every unspecified detail with its own assumptions, burns tokens over multi-day sessions, and declares victory in prose (00:07:02, 00:10:45).

Both speakers built internal harnesses at WorkOS to separate doing the work from grading it (00:10:45). Proser built `Ctx`, a Cloudflare-hosted web service connected over MCP that starts as cross-agent memory and secret handoff, then acts as a centralized verification authority (00:10:45). When an agent asks whether a workflow step is finished, `Ctx` invokes an external CLI verifier against the GitHub API to confirm the pull request exists, is healthy, and passes merge checks before marking the node satisfied; otherwise it sends the failures back to the agent (00:10:45). Nisi built `Riker`, an engineering harness that babysits pull requests through review comments and test fixes, assembling screenshots, smoke tests, and logs before alerting a human (00:10:45).

**Key points**

- Decomposing work into tasks with explicit verification criteria beats multi-day open-ended agent sessions.
- `Ctx` centralizes completion authority behind an MCP service so agents cannot mark their own workflow nodes done.
- `Riker` automates the final ten percent of pull request babysitting while preserving proof artifacts for review.

> “Show me the actual tangible proof that it actually did it, what I expect.”
> — 00:10:45

**Visual:** diagram "Centralized MCP verification gate checking live API and merge state before marking work done"

## Build a custom verifier CLI more durable than the app

Telling thirty agents in plain text to check the browser, reload the page, and inspect console logs produces thirty slightly different interpretations (00:16:07). Collapsing those instructions into a single deterministic command backed by shell scripts gives every agent and every teammate the same pass-or-fail loop (00:16:07, 00:19:52).

For the workshop repository, Nisi and Proser built `snack`, an application-specific CLI template organized around four groups of commands (00:19:52). Health commands (`up`, `down`, `doctor`) confirm Node, Chromium, build artifacts, network, and database readiness; drive commands (`join`, `reload`, `reset`) exercise the waitlist; inspection commands (`snapshot`, `storage`, `console`, `screenshot`) expose live browser state as JSON or images; and verification commands (`prove`, `judge`) grade the result (00:19:52). Once those verifiers exist, Nisi argued, the verification suite matters more than the application source code itself because a team can rewrite or port the software into another language and prove behavioral equivalence (00:19:52).

**Key points**

- Prompt checklists drift across runs; a single repo-specific CLI enforces uniform checks for every agent on the team.
- The `snack` CLI separates health checks, user-action drives, state snapshots, and pass/fail proofs into composable subcommands.
- Strong behavioral verifiers let teams port or regenerate an entire application while proving it still works.

> “So when you want that, if you have all those verifiers in place, then your software doesn't matter as much. You can write it again and prove that it works.”
> — 00:19:52

**Visual:** diagram "Structure of the snack verifier CLI across health, drive, inspect, and prove subcommands"

## Surface state in errors and specify the destination, not the path

An LLM cannot debug what it cannot observe (00:25:36). Borrowing an example from the Amp team of a ball bouncing out of a canvas circle, Nisi noted that a model with no way to watch canvas frames can still spot a physics bug immediately if each loop prints ball coordinates and reveals a multi-pixel jump (00:25:36). The same rule applies to pull request screenshots: a static image is not proof unless an executable Playwright script drove the app from an empty state through form submission and reload to reach it (00:30:02).

When a verification run fails, terse messages like `System error 9` stall the loop, whereas errors that dump exact state let the agent diagnose and repair its own mistake while the developer works on another task (00:30:02). With reliable proof commands in place, Proser warned against micromanaging step-by-step implementation instructions, which can degrade frontier model performance (00:33:40). What Nisi calls outcome-driven development hands the agent the target proof command and lets it choose how to get that command green (00:33:40).

**Key points**

- Printing internal state and storage snapshots turns invisible UI or runtime bugs into text an agent can reason over.
- Detailed, state-rich error messages convert failed test runs into closed self-healing loops.
- Defining the executable proof command constrains the outcome while leaving frontier models free to find edge cases.

> “It's more about giving it the map, saying you must get here. You'll know you're here when this command returns to us.”
> — 00:33:40

**Visual:** diagram "Outcome-driven self-healing loop: proof command, state-rich failure output, autonomous repair, and verified pass"

## Pair deterministic proofs with fast System 1 judges

Purely static assertions break when harmless copy changes land (00:38:07). After fixing local storage persistence in Midnight Snack Club, changing the confirmation banner from `waitlisted` to `you're in, your seat is confirmed` causes a literal string-matching proof to fail even though the user is properly signed up and persisted (00:38:07).

To check semantic intent without brittle string coupling, `snack` pairs its deterministic state checks with a `judge` subcommand backed by ultra-fast "System 1" models, including Cloudflare's low-latency inference endpoints (00:38:07). Borrowing Daniel Kahneman's distinction between fast automatic perception and slow deliberation, Proser described using cheap System 1 calls for instant semantic checks (does this rendered state confirm waitlist signup?) while reserving heavier reasoning for code changes (00:38:07). Every verification pass and failure is also written out as a structured receipt for future runs to inspect (00:38:07).

**Key points**

- Exact text matching creates brittle tests that fail whenever UI confirmation copy is reworded.
- Fast, inexpensive System 1 judge models evaluate semantic UI state without tight coupling to literal strings.
- Combining deterministic persistence checks with a semantic judge catches real bugs without false-alarm churn.

> “So how would we fix that without adding a lot of tight coupling to everything that we're doing? The answer is the System One models, which we'll get into here.”
> — 00:38:07

**Visual:** diagram "Dual-check verifier combining deterministic storage assertions with a fast System 1 semantic UI judge"

## Test the verifier with injected bugs and overnight receipt loops

A verifier needs its own adversarial test (00:41:54). In their "saboteur vs. detective" exercise (`snack up --bug random`), a saboteur mode injects a random hidden fault (memory-only storage, overpromised confirmation copy, silent console errors, or no bug at all) and challenges the detective agent to isolate the defect and attach fresh proof (00:41:54). During the live demo, `snack doctor` flagged that the stored failure receipt belonged to source code that had changed since the previous run, preventing stale receipts from masquerading as current evidence (00:41:54).

Zooming out to production web and mobile apps, Proser urged teams to give agents visibility into network traffic, rendering, Chrome DevTools, and full user-journey receipts, from login and seven-second catalog loads to cart abandonment (00:48:23). Accumulated receipts let an overnight agent spot eight recurring cache failures, open a pull request, run the verifier CLI to prove the fix, and attach a recorded browser walkthrough so an engineer reviewing fifteen pull requests in the morning can watch the behavior before reading code (00:48:23).

**Key points**

- Random fault injection (`saboteur` vs. `detective`) tests whether a verifier actually catches bugs or passes on stale receipts.
- Binding each receipt to the current source state stops yesterday's test output from validating today's changed code.
- Saving user-journey and test receipts enables overnight agents to aggregate failures, ship verified fixes, and attach video proof.

> “the common foundation here across all of them is that you need to give your agent the ability to see absolutely everything that you see as a developer.”
> — 00:48:23

**Visual:** diagram "Saboteur fault injection, source-bound run receipts, and overnight autonomous fix PRs"
