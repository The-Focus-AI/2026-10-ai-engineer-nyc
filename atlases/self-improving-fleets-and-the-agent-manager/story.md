---
title: "Theme 06: Self-Improving Fleets and the Agent Manager"
theme_id: "self-improving-fleets-and-the-agent-manager"
kind: theme-deep-dive
phase: archive
talks: 8
claims: 21
---

# Self-Improving Fleets and the Agent Manager

Software engineering is shifting from writing code locally to managing asynchronous cloud agent fleets and closing the trace-to-skill loop—centralizing transcripts and tool calls, grading runs post-merge, and letting meta-agents distill recurring failures and human corrections into versioned skills.

Across Warp, Arize, Linear, Untangle, GEICO, Anthropic, and Runpod, the unit of engineering work moved from crafting individual features to operating and improving the agent factory itself. Warp demonstrated 'factory engineering': shared cloud Docker sandboxes automatically centralize conversation transcripts, MCP/tool calls, and diffs, exposing silent agent workarounds (like brute-force port probing) to post-merge markdown judge rubrics and daily meta-agents (`Skill Doctor`) that open measurable skill PRs. Linear runs a daily post-merge distillation job that turns PR review corrections and reverts into `agents.md` updates; Arize designs agent-first telemetry to wake scheduled sandbox sweeps while tracing both production agents and the coding harnesses behind them; Anthropic treats SME-authored plain-text skills as living, versioned code co-iterated by business teams and engineers; GEICO coordinates legacy transformations through Markdown FleetKit protocols; Runpod exposes GPU benchmark controls as FastAPI endpoints for agents to drive directly; and Untangle replaces local development with communicating builder, reviewer, and merge-manager sessions—extending the paradigm to hiring by stack-ranking candidates on 45-minute recorded agent-operating trials, echoing the Day 2 keynote's call to pair human company curation with career-research agents. In tension with universal 'agent management,' Basis warned that pushing prompt and skill authorship onto non-technical enterprise users creates a severe competency gap, and Day 2's keynote cautioned against letting agents automate personal outreach like resume submissions.

## Factory engineering: centralizing traces so meta-agents patch skills daily

- **Ben Holmes (Your agent needs a skill to improve its skills, 00:01:44)**: Factory engineering treats the agent harness itself as an optimization target by using LLM-as-judge scoring agents to evaluate past runs against custom rubrics for efficiency, code quality, and test coverage.
  > “You can set up some scoring agents to score the quality of how those conversations went, so think of this like an LLM as a judge reviewing against rubrics that you define across metrics like efficiency, or code quality, or test coverage.”

- **Ben Holmes (Your agent needs a skill to improve its skills, 00:03:12)**: Introspecting team-wide agent performance requires centralizing three artifacts per session—dialogue transcripts, external tool/MCP/filesystem calls, and resulting code diffs—which shared cloud Docker sandboxes capture automatically without syncing local laptop folders.
  > “you got the transcript of what was said, you've got the tool calls that show what the agent did, and then you have the output, which is something that you may want to grade for quality purposes.”

- **Ben Holmes (Your agent needs a skill to improve its skills, 00:06:06)**: Because unattended agents silently brute-force around broken environment instructions—such as probing local port numbers when test skills are stale—scoring tool-call efficiency over full traces uncovers harness bottlenecks hidden by passing PRs.
  > “these AIs are very persistent and will work around whatever roadblock that they run into, and they won't tell you about it.”

- **Ben Holmes (Your agent needs a skill to improve its skills, 00:08:55)**: Triggering markdown-defined judge rubrics upon PR merge produces structured pass/fail scores and failure rationales that a daily cron-scheduled self-improvement agent mines to propose targeted skill and codebase updates.
  > “So automatically, usually the trigger being a PR merged, kick in an agent to review that conversation across your grading criteria.”

- **Ben Holmes (Your agent needs a skill to improve its skills, 00:13:43)**: A single-player batch audit skill (`Skill Doctor`) crawls local Claude, Codex, and Pi logs to produce a rubric report card and concrete skill edits, such as upfront port-discovery instructions and prescriptive changelog formatting.
  > “But this is a skill that you can run on your single-player setup, and it'll crawl through all of your agent conversations in Claude, Codex, Py, or whatever else and just do a one-time grading.”

- **Ben Holmes (Your agent needs a skill to improve its skills, 00:16:10)**: Unlike opaque overnight memory or dreaming loops, continuous rubric dashboards let teams attribute measurable score inflections directly to merged skill and config fixes such as enabling missing subagent permissions.
  > “So the agent's constantly scoring setups and it's giving grades of like 50%, 60% on average, and you can attribute changes that you made in your agent setup to inflections in the score.”

- **Tom Moor (Your Coding Agent Has a Context Problem, 00:18:47)**: A daily post-merge automation mines review corrections and reverts across merged PRs and distills actionable lessons into `agents.md` and documentation so human product judgment compounds across subsequent agent runs.
  > “It will find actionable lessons, places where these types of comments happened in the PRs, and changes were made, or reverse happened, extract learnings, and then inject them back into the codebase, either in the agents.md or in the related documentation”

- **Belinda Neal, Keon Shahab (Anthropic: Accelerating frontier AI in Financial Services., 00:07:57)**: Domain-specific workflows such as trade-break investigations should be captured from subject-matter experts as plain-text skills that are version-controlled, frequently iterated, and governed like living production code.
  > “this is the business context that an SME provides, and we think about skills as living, breathing, versioned code, essentially, even though they're just plain text. They're meant to be dynamic. They're meant to be updated frequently.”

- **Belinda Neal, Keon Shahab (Anthropic: Accelerating frontier AI in Financial Services., 00:12:25)**: Agent deployment reshapes the financial-services operating model into a tight loop where business SMEs directly correct live agents and propose changes that engineering validates against baseline evaluation suites before shipping as updated skills.
  > “Some observations that we've seen, especially in financial services, is that the business is now becoming closer to engineering, and the way that we're observing this is that the business will directly work the agent that engineering has built.”

## Agent-first telemetry, FastAPI control planes, and Markdown FleetKit queues

- **Aparna Dhinakaran (What does an AI engineer do?, 00:00:00)**: Out of roughly six billion people who have touched LLMs and 20 million professionals accelerating multi-week tasks into days, only about 5,000 frontier practitioners currently operate swarms of thousands of concurrent always-on agents.
  > “But really, those at the frontier labs are just super small percentages, like five thousand users are the ones who are running thousands and thousands of agents at once.”

- **Aparna Dhinakaran (What does an AI engineer do?, 00:01:43)**: AI engineering shifts from manually writing code, reviewing diffs, and checking dashboards to constructing automated build-eval-ship-monitor-improve systems where agents review non-deterministic execution paths and analyze telemetry.
  > “As an AI engineer, your job is no longer to just write the feature, write a bad feature. It's about how do you build the loop to write that feature.”

- **Aparna Dhinakaran (What does an AI engineer do?, 00:04:10)**: Designing telemetry for agents as primary consumers turns scheduled 3-to-6-hour trace sweeps, metric thresholds, and Slack user complaints into automated triggers that wake isolated sandbox runs behind a single traced proxy.
  > “how do you set up your telemetry data so that agents are the primary consumers of that data? And what that does is that observability data can become the trigger for actually running and triggering these always-on agents”

- **Aparna Dhinakaran (What does an AI engineer do?, 00:12:10)**: End-to-end observability must cover both production agents and the coding harnesses that build them (Claude Code, Cursor, Codex), using online evaluations over live traces to feed newly detected failures back into the improvement loop.
  > “And tracing everything now means not just tracing the agents, but also tracing the coding agents behind the agents that build this.”

- **Chris Vela (From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod, 00:06:31)**: Exposing GPU telemetry, error scans, and vLLM configuration reloads over backed-up FastAPI endpoints enables coding agents to run serving benchmarks and optimize flags programmatically without human UI intervention.
  > “It's all based fast API calls, so your agent easily just call all those things. You can actually just serve everything. Like you don't even have to use the UI.”

## Multi-session merge managers and hiring for how engineers run fleets

- **Ksenia Se (Welcome Back - Featured Keynotes, 00:02:12)**: A high-signal job-search pipeline combines human curation—first ranking conference speakers' companies by technical interest—with an agent that scrapes career pages to match open roles and extract published compensation ranges for updating rankings.
  > “The next step is to send your agent to those companies' careers pages, right, and find them open positions to match them to your experience, and collect the published compensation ranges.”

- **Ksenia Se (Welcome Back - Featured Keynotes, 00:02:12)**: Hiring serves as a primary two-sided incentive for attending AI Engineer, extending even to conference speakers who are simultaneously recruiting talent and exploring new roles themselves.
  > “I spend the day talking to other speakers and participants, and what I've noticed is that one of the strongest incentives to come to this conference is hiring, to the point that even some speakers are hiring and also looking for work.”

- **Ryan Carson (Your job is now "agent manager", 00:03:38)**: A dedicated merge-manager agent session coordinates the wave of concurrent pull requests to prevent shared-state collisions such as conflicting database migration numbers.
  > “Like if all the agents are trying to grab these things, you constantly collide, right? So the merge manager just helps all that go away, but also is a little more intelligent about how the merge deals happen.”

- **Ryan Carson (Your job is now "agent manager", 00:03:38)**: Engineers who still code in local development environments bottleneck their teams because local workflows cannot orchestrate fleets of parallel, inter-communicating cloud agent sessions.
  > “I don't care whatever it is, but if you're running local dev, you are screwing up. You're holding yourself back. You're holding your team back. You're holding everything back, because you can't do this.”

- **Ryan Carson (Your job is now "agent manager", 00:06:23)**: Untangle eliminates resumes, pre-screens, and video interviews to avoid interpersonal bias, evaluating candidates instead by having models stack-rank unguided 45-minute screen recordings of them operating agents to ship a PR.
  > “You'll like their hobbies. You'll like the way they talk to you. You'll think they're interesting, and it's all noise. None of it is real, right? All that matters is can they operate an agent?”

- **Ryan Carson (Your job is now "agent manager", 00:08:39)**: The top five stack-ranked candidates complete paid 16-hour recorded trials shipping a real PR under NDA, with AI and human video review selecting finalists before any phone conversation happens.
  > “Then we basically pick the top five, and we invite them to a paid project. So we pay a fixed fee for sixteen hours at a time.”

