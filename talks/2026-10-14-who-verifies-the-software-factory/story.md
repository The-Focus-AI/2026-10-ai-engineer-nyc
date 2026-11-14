---
title: "Who verifies the software factory?"
speakers: "Manish Kapur (Sonar), Addy Osmani (Anthropic)"
duration: "18:36"
source: transcript.md
video: "https://www.youtube.com/watch?v=AnsXWH2_EBU"
themes: [deterministic-verification-loops-over-line-by-line-review]
kind: talk-story
status: draft
---

# Writing code is no longer the constraint. Checking 30,000 changes a day is.

Sonar's Manish Kapur and Anthropic's Addy Osmani open with a room poll that exposes the modern review gap: nearly everyone had a coding agent open a pull request in the past week, and almost nobody read every line before merging. Moving from human-assisted "lights-on" workflows toward autonomous "dark" software factories takes zero-trust, multi-layered verification inside every loop, backed by agents that test their own UIs and hand humans behavioral evidence rather than raw diffs.

## CI throughput is up 59%, and 3 in 10 production merges fail

Kapur starts with a show of hands: nearly the whole room had a coding agent open a pull request in the past week, and only a few hands stayed up when he asked who reviewed every merged line manually (00:00:00). CircleCI's 2026 study of 28 million workflows captures what happens in that gap: CI throughput jumped 59%, the largest increase CircleCI has ever recorded, while roughly 3 in 10 attempts to merge into production now fail (00:01:45).

Quoting Osmani's July 2026 essay on software factories ("a software factory is harnessing loops at scale"), the two map an autonomy spectrum (00:01:45). In a **lights-on factory**, agents plan, build, check, and ship repeatedly while humans stay inside the loop applying taste and judgment (00:01:45). In a **dark factory**, agents scope, build, and check continuously like a robotic car plant, while humans step back to define intent and handle exceptions (00:01:45).

**Key points**

- CircleCI measured a record +59% jump in CI throughput alongside a ~3-in-10 failure rate on production merge attempts.
- Lights-on factories keep human judgment inside each agent loop; dark factories run autonomously while humans set intent and handle exceptions.
- Most engineering teams sit midway along that spectrum, bottlenecked by how much automation they can trust.

> “A lights on factory is one where you have agents that are helping you with planning, building, checking, and shipping code again and again, but you as a person so apply your judgment and taste inside the picture”
> — 00:01:45

**Visual:** slide `experience/writing-code-is-no.jpg` ("Writing code is no longer the constraint. Checking it is." with CircleCI's +59% throughput and ~3-in-10 merge failure figures)

## Coding is solved; 76% of developers cannot verify fast enough

Sonar's developer survey preview (n=1,026) puts numbers on the review bottleneck: 85% of organizations already use coding agents today and 95% expect to within a year, yet 76% of developers say they generate AI code faster than they can verify it, and 53% now spend more time reviewing code than writing it (00:03:41).

For Osmani, that shifts where engineering time belongs. Now that agents can also generate tests and benchmarks faster than before, the highest-leverage work is giving agents deterministic ways to check their own output for correctness and completeness before a human ever looks at the pull request, a practice he estimates can double or triple delivery outcomes (00:03:41).

**Key points**

- 76% of surveyed developers generate AI code faster than they can verify it, and 53% spend more time reviewing than writing.
- Raw code generation is largely commoditized; shipping faster with confidence is the leadership bottleneck.
- Giving agents self-verification suites and benchmarks can 2x to 3x engineering outcomes.

> “Like if you are hoping to get the best quality output from your agents, you need to give your agents a way to verify that the work is correct.”
> — 00:03:41

**Visual:** slide `experience/coding-is-solved-verification.jpg` ("Coding is solved. Verification is not." with Sonar survey adoption and review-burden stats)

## How Anthropic merges 30,000 code changes a day

Kapur brings up a figure from a recent Anthropic post: Anthropic now merges roughly 30,000 code changes every day, up from around 2,500 daily changes back in May (00:05:26). Osmani adds a concrete case study from a recent Claude refresh that tripled performance by landing roughly 3,000 pull requests in a short window across engineers, product designers, and other functions (00:05:26).

At 30,000 daily changes, manual line-by-line inspection cannot be the primary gate. Anthropic runs automated first-pass Claude code reviews guided by codified team playbooks, pairs them with edit hooks that inspect diffs as changes land to fix gaps immediately, and requires agents to exercise the product like a real user (00:05:26). When a change touches browser, desktop, or mobile UI, the agent opens the app, clicks through the flow, and attaches screenshots or video recordings so the human reviewer evaluates concrete verification evidence rather than raw lines of code (00:05:26).

**Key points**

- Anthropic scaled from roughly 2,500 daily merged changes in May to ~30,000 per day, including a 3x speed refresh across ~3,000 PRs.
- Automated first-pass Claude reviews consult shared team playbooks while diff-triggered hooks catch and repair issues early.
- Agents test web, desktop, and mobile flows live, handing reviewers screenshot and video proof instead of bare diffs.

> “If I care about mobile or desktop experience, maybe it generates me screenshots or videos of that, but basically, you want to get to a place where the AI is giving you as much verification evidence as possible.”
> — 00:05:26

**Visual:** diagram "Anthropic's automated PR verification loop scaling from 2,500 to 30,000 daily code changes"

## Unreviewed diffs are rising while light factories push to go dark

Industry-wide, delivery speed is outrunning verification discipline. On Sonar's slide (combining Sonar survey preview and Faros AI 2026 figures), 84% of respondents say AI gets features and fixes to production faster, pull requests have grown 51% larger, and 31% more code is reaching production with no review at all (00:08:20). At the same time, organizations running autonomous software factories expect to jump from 5% today to 34% within a year, and 39% on the slide for financial services (spoken as 29% on stage) (00:08:20).

Even with strong frontier models like Opus 5.5, Osmani warns that telling teams to "just verify the work" is useless without naming the exact test layers that justify automated merges (00:08:20). His shortlist is explicit: end-to-end tests, property-based tests, and visual verification suites that prove runtime behavior across edge cases so a factory can move safely toward lights-out operation (00:08:20).

**Key points**

- Pull requests are 51% larger and 31% more code reaches production unreviewed, raising sharp risk for regulated systems.
- Autonomous software-factory adoption is projected to climb from 5% today to 34% across industries within a year.
- Earning automated merges requires concrete behavioral checks: end-to-end tests, property tests, and visual verification.

> “We lean a lot on end-to end tests, property tests, any visual verification tests—things that can help us just get that confidence to merge those changeset automatically.”
> — 00:08:20

**Visual:** slide `experience/light-factories-want-go.jpg` ("Light factories want to go dark" bar chart showing autonomous factory adoption rising from 5% today to 34% in a year and 39% in financial services)

## Zero-trust multi-layer checks, and guide rails for agent sprawl

Kapur outlines Sonar's prescription: zero-trust, multi-layered verification inside every loop, including the inner agentic coding loop, the CI pipeline, and ongoing code maintenance (00:11:26). Rather than asking one tool to catch everything, Sonar tunes three distinct layers: a **deterministic layer** for syntax, SQL injection, buffer overflows, taint flows, architecture, and secrets; an **agentic review layer** for business logic, deep semantics, and intent mismatches; and a **software supply-chain layer** for CVEs, malware, and malicious packages (00:11:26).

Governance lags well behind adoption: 28% of surveyed companies run approved agents with few shared controls, while only 5% operate structured factories (00:11:26). Osmani describes talking to enterprises that let teams experiment freely and woke up to hundreds or thousands of untracked agents touching internal systems and data (00:11:26). Those organizations now converge on three controls (identity and telemetry, scoped permissions, and sandboxes), which Kapur pairs with proactive "guide rails" that keep agents on approved tracks inside the sandbox (00:11:26).

**Key points**

- Verify inside every loop (agent, CI, maintenance) across deterministic static analysis, agentic logic review, and supply-chain scanning.
- 28% of organizations have approved coding agents with few shared controls, creating untracked sprawl across hundreds of agents.
- Enterprise containment rests on telemetry and identity, scoped permissions, hard sandboxes, and in-loop guide rails.

> “We absolutely 100% believe that each company should adopt a zero trust multi-layered verification approach, and verification should be done in every loop”
> — 00:11:26

**Visual:** slide `experience/most-teams-have-agents.jpg` ("Most teams have agents. Fewer have guardrails." contrasting 28% uncontrolled agent adoption against 5% autonomous factories)

## Label agent PRs, keep a human on the hook, and count what stays shipped

In a closing lightning round, Osmani predicts most organizations at the end of 2027 will run "a light factory with some dark corners" rather than full lights-out autonomy, though frontier labs like Anthropic (transcribed as "Antopolis") will likely push further sooner (00:14:29). On governance, both speakers agree that agent-written pull requests should be explicitly labeled as coming from an agent: labeling strips away authorship ego, triggers stricter automated verification gates, preserves audit trails for regulated financial institutions, and still keeps a named human engineer accountable if production breaks (00:14:29).

Asked what skill leaders and junior engineers should build this year, Osmani points both groups to the verification gap: leaders should push teams to define what test suite lets an agent safely sign off on a merge, while juniors should build fluency across end-to-end and property-based testing (00:14:29). Kapur closes with three rules on his final slide: writing code is the fastest part, fast to write is not fast to ship (count what merges and stays healthy in production), and autonomy is earned only after independent verification sits inside every loop (00:14:29).

**Key points**

- Most teams in 2027 will run hybrid light factories with dark corners rather than full 24/7 lights-out pipelines.
- Labeling agent-authored PRs enables stricter verification policies and financial auditability while keeping a human owner accountable.
- Measure software factories by verified changes that stay healthy in production, not raw lines generated.

> “I personally think it's fine for the code to be written, labeled as being coming from an agent”
> — 00:14:29

**Visual:** slide `experience/shipping-fast-not-shipping.jpg` ("Shipping fast, not shipping blind" closing summary: writing code is the fastest part, fast to write is not fast to ship, and autonomy is earned)
