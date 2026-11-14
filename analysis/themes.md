# AI Engineer New York 2026 — Cross-Talk Themes

> Rendered from the `conference-themes` world-model. Every quote is a claim atom from `talk-insights`; each citation names the `### HH:MM:SS` section of the talk's transcript that holds it.

## Corpus

- **Recorded talks with atoms**: 31
- **Cleaned word count**: 94,952 words (Qwen3-ASR transcripts, re-cleaned 2026-11-14)
- **Claim atoms**: 173
- **Themes**: 11; **contested questions**: 4; **singletons**: 26
- **Unassigned talks**: 2026-10-13-closing-remarks, 2026-10-14-welcome-back-featured-keynotes
- **Last touched**: 2026-11-14T10:01:10-05:00

## Themes

### 1. Bootstrapping Domain Evals Without Public Benchmarks — 10 talks

**Claim**: Public benchmarks do not measure a team's own task, so teams must build their own evals, often constructing the answer first or mining historical failures, because an agent you cannot evaluate is an agent you cannot improve.

Speakers built evals from what they already knew: a question generated from a known source page, a contract clause that breaks a known rule, a catalog of historical bug-causing changes, a 200-question hand-built search benchmark, SME suites with a baseline, and behavior specs that grade any trajectory without ground truth. Exa's point-in-time search lets prediction features be backtested without leakage. Evaluating many drafts per task and judging with a different model family were used to control variance and self-preference. The counter-position is about the grader: LLM-as-judge verdicts proved too noisy or unstable for some teams to rely on.

- **Also called**: write the answer first, golden datasets, evaluate the evaluators, backtesting
- **Talks (10)**:
  - [The AI Bill Is Too Damn High – Tokenomics 101](../talks/2026-10-12-the-ai-bill-is-too-damn-high-tokenomics-101/transcript.md) (### 00:18:04 — Token Pricing, Batching & Memory Bandwidth): Instead of asking whether a smaller model is good enough, build evals and search for the cheapest model that passes them, then fine-tune from there.
    > "Make sure you set up your test cases, your e-dos, and your examples, and then subsequently just do the search."
  - [A Hedge Fund as a Function](../talks/2026-10-13-a-hedge-fund-as-a-function/transcript.md) (### 00:09:20 — Compounding Institutional Knowledge at Coatue): Pipelines must be compartmentalized into evaluable pieces with a clear metric, or tuning becomes aimless.
    > "And if you don't have a north star to help climb against. You're just kind of you're just fidgeting around."
  - [Anthropic: Accelerating frontier AI in Financial Services.](../talks/2026-10-13-anthropic-accelerating-frontier-ai-in-financial-services/transcript.md) (### 00:12:09 — Live Financial Workflow Demonstrations & Outlook): SME-defined eval suites with a baseline are what tell you whether a new model or skill change improved the agent or caused a regression.
    > "To any variable, you'll be able to determine whether that variable change actually improved."
  - [Can Any Model Write Like Me? Building a Benchmark for Creative Writing](../talks/2026-10-13-can-any-model-write-like-me-building-a-benchmark-for-creative-wr/transcript.md) (### 00:00:00 — Defining AI Writing Slop & Why It Happens): Slop persists as models improve, so fixing it requires measurement rather than just more training.
    > "It just Keeps on scaling, so we need something different than just training the models more."
  - [How to build an AI code review agent: from the creators of Greptile](../talks/2026-10-13-how-to-build-an-ai-code-review-agent-from-the-creators-of-grepti/transcript.md) (### 00:05:48 — Iterative Architecture of Greptile's Review Agent): Because catastrophic bugs are rare, prompt changes must be evaluated against a catalog of historical bug-causing changes rather than judged by comment volume.
    > "The validation against really any reviewer can tell you about the presence of bugs, but unfortunately can't tell you about the absence of bugs."
  - [Search the Web as It Was: An Introduction to Exa Snapshot](../talks/2026-10-13-search-the-web-as-it-was-an-introduction-to-exa-snapshot/transcript.md) (### 00:12:22 — Point-in-Time Web Retrieval & Evaluation): Snapshot lets teams check that a search feature generalizes rather than overfits, without waiting months for live results.
    > "Detect these things, but you've also got to check that it generalizes."
  - [Vault: Making Unstructured Data Work for Investing](../talks/2026-10-13-vault-making-unstructured-data-work-for-investing/transcript.md) (### 00:04:53 — Inside Vault: Architecture for Investment Research): A hand-built benchmark of about 200 questions confirmed users' complaint that search was bad (about 60% precision at ten) and gave the team a way to measure fixes up to about 95%.
    > "The key metric we were looking at is precision at ten, which is of the top ten results, how many are the right documents."
  - [What does an AI engineer do?](../talks/2026-10-13-what-does-an-ai-engineer-do/transcript.md) (### 00:09:45 — Continuous Improvement & Agent Observability): Engineers should spend their time defining what good is, building golden datasets and evaluating the evaluators until LLM judges agree with human judgment before shipping them.
    > "Verify them against the human output, and then try to align to make sure that the judge actually agrees with the human."
  - [Write the Answer First: Generating Eval Datasets for Agents With No Benchmark](../talks/2026-10-13-write-the-answer-first-generating-eval-datasets-for-agents-with/transcript.md) (### 00:00:00 — Shipping Enterprise Agents Without Pre-Existing Benchmarks): Enterprise agent tasks are too specific for existing benchmarks, and the builders are not the domain experts, who have limited time and data access.
    > "We don't have any particular benchmark we can rely on that's the main problem we I'm trying to address in this presentation."
  - [Process Supervision for Agents That Do Long-Horizon Work](../talks/2026-10-14-process-supervision-for-agents-that-do-long-horizon-work/transcript.md) (### 00:06:54 — Process Supervision vs. Outcome-Only Evaluation): Behavior specs double as rubrics that can grade any trajectory, even without ground truth, scaling supervision signal far beyond outcome-based evals.
    > "then you can also use them as a rubric. And you can say, in this particular trajectory, whether that is in any trajectory that doesn't have a ground truth."
- **Claims (17)**: `1cbc625f-7f07-49bb-9c5c-57c95f07ba77:414:0fd03d`, `68a1e78b-569e-4314-a56f-f20508123cbe:729:3f6281`, `736edd83-bb08-49f1-90ed-722b7ed07eb2:0:b9883c`, `736edd83-bb08-49f1-90ed-722b7ed07eb2:372:304cc5`, `736edd83-bb08-49f1-90ed-722b7ed07eb2:372:76c699`, `9a9dfcd0-459f-43eb-b3f8-004864b4ad2a:560:0c4109`, `a84ca3a8-cc2f-4b50-a635-fc380f6f04f6:293:02931c`, `b2ed4456-5671-4e8e-83fd-684c012fef8c:585:538673`, `b8bb725d-daf0-4ac0-8095-5737841c89e5:742:4e5d5c`, `b8bb725d-daf0-4ac0-8095-5737841c89e5:742:e896cc`, `bdab432a-0538-4431-ad5a-62653affd9da:348:fc4c36`, `c4ba0138-6f6d-4780-93a1-4d8f0c478339:0:1bbd2d`, `c4ba0138-6f6d-4780-93a1-4d8f0c478339:0:79b9f2`, `c4ba0138-6f6d-4780-93a1-4d8f0c478339:0:ab2ce6`, `c4ba0138-6f6d-4780-93a1-4d8f0c478339:389:c2f846`, `c4ba0138-6f6d-4780-93a1-4d8f0c478339:755:8fb189`, `c901e963-5be9-4a1d-86a3-d9354374bbcd:1084:ad7897`
- **Counter-claims**:
  - [The Machine that Changed the World, vAI](../talks/2026-10-14-the-machine-that-changed-the-world-vai/transcript.md) (### 00:05:31 — Why Unverified AI Code Creates Hidden Debt): LLMs are unreliable judges for verification since their verdicts change across identical replications and when challenged.
    > "Ask the same questions, get a different answer between seven and seventeen percent of the time."
  - [Write the Answer First: Generating Eval Datasets for Agents With No Benchmark](../talks/2026-10-13-write-the-answer-first-generating-eval-datasets-for-agents-with/transcript.md) (### 00:12:35 — Production Rollout & Lessons Learned): Teams should be willing to re-engineer an agent's design so it can be evaluated, and LLM-as-judge scoring proved too noisy to rely on.
    > "The original design we could not evaluate it. We switched to something that we can actually evaluate because of that."

### 2. Self-Improving Agents and Agent Management — 7 talks

**Claim**: The engineer's job is shifting from writing features to managing fleets of agents and the loop that improves them: traces are centralized, scored, and turned into skill and context changes that compound.

Warp, Arize, Ryan Carson, GEICO, Anthropic and Linear each described the same loop: keep receipts of every agent run, score them against rubrics, have an agent find the common failures and open PRs against the skills, and distill human review corrections back into agents.md. Engineers own the system that builds, evaluates, ships and monitors, and spin up as many agents as the merge queue allows. Business users can correct agents directly while engineering ships the change as a versioned skill. The counter-position is that the outer loop of human decisions has not kept pace, and that pushing skill and process design onto users creates competency gaps.

- **Also called**: agent manager, skill-improving skills, always-on loop, fleet manager
- **Talks (7)**:
  - [Beyond “Done”: Building Verification Loops for AI Agents](../talks/2026-10-12-beyond-done-building-verification-loops-for-ai-agents/transcript.md) (### 00:35:55 — Scaling Agent Verification in CI & Production): Keeping receipts of every agent run builds a dataset that drives fixes today and future self-improving loops.
    > "It's very valuable data right now because you can feed it into and get fixes, I think it's incredibly valuable data in the future."
  - [Anthropic: Accelerating frontier AI in Financial Services.](../talks/2026-10-13-anthropic-accelerating-frontier-ai-in-financial-services/transcript.md) (### 00:06:12 — Enterprise Deployment Patterns & Governance): Business rules and processes from subject-matter experts should be encoded as skills and maintained like frequently updated, versioned code.
    > "we think about skills. As living, breathing, versioned code, essentially, even though they're just plain text."
  - [Inside the Fable War Room](../talks/2026-10-13-inside-the-fable-war-room/transcript.md) (### 00:06:39 — Inside the Fable War Room: Multi-Agent Incident Response): A Markdown fleet manager that breaks down a goal, dispatches researchers, queues work for human approval and then dispatches builders makes expensive agent fleets steerable.
    > "So Fleetkit is this tight structured collection of rules, protocols, instructions, all written in Markdown."
  - [What does an AI engineer do?](../talks/2026-10-13-what-does-an-ai-engineer-do/transcript.md) (### 00:00:00 — The Evolving Role of the AI Engineer): Telemetry should be designed for agents as its primary readers, so observability data becomes the trigger that wakes always-on agents.
    > "How do you set up your telemetry data so that agents are the primary consumers of that data?"
  - [Your agent needs a skill to improve its skills](../talks/2026-10-14-your-agent-needs-a-skill-to-improve-its-skills/transcript.md) (### 00:00:00 — Why Agents Repeat Mistakes Across Sessions): Self-improvement needs the whole team's agent traces centralized, including transcripts, tool and MCP calls, and resulting diffs, which shared cloud runners provide for free.
    > "you got the transcript of what was said, you've got the tool calls that show what the agent did, and then you have the output"
  - [Your Coding Agent Has a Context Problem](../talks/2026-10-14-your-coding-agent-has-a-context-problem/transcript.md) (### 00:14:17 — Human-Agent Collaboration in the Issue Tracker): A daily automation distills review corrections and reverts into agents.md and docs so human judgment compounds instead of being repeated.
    > "Extract learnings, and then inject them back into the codebase."
  - [Your job is now "agent manager"](../talks/2026-10-14-your-job-is-now-agent-manager/transcript.md) (### 00:00:07 — Managing a Fleet of Builder, Reviewer & Manager Agents): Engineers still coding or running local dev hold their teams back; work should run as communicating cloud agent sessions.
    > "if you're running local dev, you are screwing up. You're holding yourself back."
- **Claims (16)**: `0a0cbd67-23fa-4a3d-a8dc-06e3caa3ab2f:0:19fc85`, `0a0cbd67-23fa-4a3d-a8dc-06e3caa3ab2f:0:2942bd`, `0a0cbd67-23fa-4a3d-a8dc-06e3caa3ab2f:396:fe5d47`, `0a0cbd67-23fa-4a3d-a8dc-06e3caa3ab2f:772:01b12f`, `0a0cbd67-23fa-4a3d-a8dc-06e3caa3ab2f:772:573747`, `4b33ac12-ed84-4e32-be63-6a4f9f3acb32:857:2b7fcf`, `68a1e78b-569e-4314-a56f-f20508123cbe:372:5080f2`, `68a1e78b-569e-4314-a56f-f20508123cbe:729:336895`, `6b92fb75-064e-4cb5-8aa3-7c7f211e7420:399:e5acee`, `b2ed4456-5671-4e8e-83fd-684c012fef8c:0:3d0fab`, `b2ed4456-5671-4e8e-83fd-684c012fef8c:0:629389`, `b2ed4456-5671-4e8e-83fd-684c012fef8c:585:f11361`, `edb4f982-0cb8-48ee-8bf7-410255a40cb3:2155:990a7a`, `f7204e6d-a47c-4535-804e-16b4db579b95:306:d26af4`, `f7204e6d-a47c-4535-804e-16b4db579b95:7:75ba49`, `f7204e6d-a47c-4535-804e-16b4db579b95:7:7a98aa`
- **Counter-claims**:
  - [Process Supervision for Agents That Do Long-Horizon Work](../talks/2026-10-14-process-supervision-for-agents-that-do-long-horizon-work/transcript.md) (### 00:00:00 — Long-Horizon Accounting Agents at Basis): Coding-style agent products fail to raise enterprise productivity because they push skill, memory and process design onto users, creating a competency gap and a process gap.
    > "The first problem is that there is a competency gap because agents, as you think of them as you think of them today, they outsource the complexity to the user."
  - [Inside the Fable War Room](../talks/2026-10-13-inside-the-fable-war-room/transcript.md) (### 00:00:00 — SDLC Velocity vs. Incident Operations at GEICO): AI has collapsed the coding phase, but at a risk-managed company the outer loop of decisions and approvals has not kept pace.
    > "So while we've seen this interloop speed up to use. Jean Kim's concept, we find ourselves seemingly stuck."

### 3. The Diffusion Gap — 7 talks

**Claim**: Model capability has outrun adoption: outside coding, agents barely reach real enterprise work, and the bottleneck is process, trust and setup friction rather than intelligence.

Tenex reported general-purpose LLMs in about 90 percent of large enterprises but agents in non-engineering work at about 5 percent. Anthropic said capability is no longer the constraint in financial services; Apollo called finance early; Basis said coding-style agent products push process design onto users; GEICO said the outer loop of decisions has not kept pace; Featherless traced rising token spend without productivity to process bottlenecks; and agent payment protocols see negligible volume because friction at every funnel stage suppresses demand. The counter-evidence is concrete production wins: Apollo's automated reconciliation and portfolio construction, and GEICO's one-day war room outcomes.

- **Also called**: enterprise agents are at day one, adoption over capability, outer-loop bottleneck
- **Talks (7)**:
  - [The AI Bill Is Too Damn High – Tokenomics 101](../talks/2026-10-12-the-ai-bill-is-too-damn-high-tokenomics-101/transcript.md) (### 00:36:10 — Open-Weight Deployment & Cost Optimization): Rising token spend without matching productivity comes from process bottlenecks and slop handed downstream, so people must own what they generate and teams should measure outcomes, not usage.
    > "So, and this goes back into saying like tokens are not work done."
  - [Agents can pay. So why don’t they?](../talks/2026-10-13-agents-can-pay-so-why-don-t-they/transcript.md) (### 00:00:00 — Why Agentic Payments Matter for Tool Marketplaces): Real transaction volume on the leading agent payment protocols is negligible despite more than a year of availability.
    > "And on MPP, only like one point five thousand dollars. I mean, it's basically nothing. It's like non-existent."
  - [Anthropic: Accelerating frontier AI in Financial Services.](../talks/2026-10-13-anthropic-accelerating-frontier-ai-in-financial-services/transcript.md) (### 00:00:11 — Introduction: Frontier AI in Financial Services): Model capability is no longer the constraint in financial services; the opportunity is building a foundation that takes agents from one-by-one builds to many.
    > "And our opportunity here is scale. Is not the model. Our opportunity here is scale."
  - [Inside the Fable War Room](../talks/2026-10-13-inside-the-fable-war-room/transcript.md) (### 00:00:00 — SDLC Velocity vs. Incident Operations at GEICO): AI has collapsed the coding phase, but at a risk-managed company the outer loop of decisions and approvals has not kept pace.
    > "So while we've seen this interloop speed up to use. Jean Kim's concept, we find ourselves seemingly stuck."
  - [Welcome Back - Featured Keynotes](../talks/2026-10-13-welcome-back-featured-keynotes/transcript.md) (### 00:00:00 — Afternoon Keynote Block Welcome & Tenex Reflections): Diffusion falls off sharply past training (about 60%) and coding agents (about 50%), with agents in non-engineering workloads at roughly 5%, so enterprise agents are still at day one.
    > "Is agents actually working in non-engineering workloads in an organization that is around? Five percent right now."
  - [AI in Practice: An Inside Look at Apollo's Approach](../talks/2026-10-14-ai-in-practice-an-inside-look-at-apollo-s-approach/transcript.md) (### 00:06:34 — Reconciling Fragmented Deal & Portfolio Data with Agents): Finance, especially asset management and institutional banking, is still early in AI adoption, with today's research and model-building uses being lower value.
    > "I still think it's very early."
  - [Process Supervision for Agents That Do Long-Horizon Work](../talks/2026-10-14-process-supervision-for-agents-that-do-long-horizon-work/transcript.md) (### 00:00:00 — Long-Horizon Accounting Agents at Basis): Coding-style agent products fail to raise enterprise productivity because they push skill, memory and process design onto users, creating a competency gap and a process gap.
    > "The first problem is that there is a competency gap because agents, as you think of them as you think of them today, they outsource the complexity to the user."
- **Claims (10)**: `1cbc625f-7f07-49bb-9c5c-57c95f07ba77:0:292f75`, `44e9d04a-e8b4-418c-8a85-02fbb9263dd0:394:715deb`, `68a1e78b-569e-4314-a56f-f20508123cbe:11:9b6376`, `6b92fb75-064e-4cb5-8aa3-7c7f211e7420:0:5865c6`, `8d348b6c-25cc-45de-8dc4-aaa3d7130918:0:c70a90`, `8d348b6c-25cc-45de-8dc4-aaa3d7130918:450:0a32d9`, `8d348b6c-25cc-45de-8dc4-aaa3d7130918:450:e17034`, `c34c075b-c695-4227-bf8e-3b4eeb3460d9:0:f3c18d`, `c34c075b-c695-4227-bf8e-3b4eeb3460d9:0:fa3d07`, `c901e963-5be9-4a1d-86a3-d9354374bbcd:2170:49e9ef`
- **Counter-claims**:
  - [AI in Practice: An Inside Look at Apollo's Approach](../talks/2026-10-14-ai-in-practice-an-inside-look-at-apollo-s-approach/transcript.md) (### 00:00:00 — Rowspace & Apollo: AI for Institutional Investment Data): Portfolio construction that took a PM two to three days in Excel now takes minutes to reach 80-90%, leaving the last stretch to the manager's judgment.
    > "that allows these PMS to kind of build something to call it eighty, ninety percent completion, and then kind of use their judgment and their thought to further refine that portfolio"
  - [Inside the Fable War Room](../talks/2026-10-13-inside-the-fable-war-room/transcript.md) (### 00:06:39 — Inside the Fable War Room: Multi-Agent Incident Response): Across three legacy claims domains the one-day war room experiments delivered concrete outcomes, from an extended rentals API to a vetted salvage migration plan that also surfaced a production bug.
    > "Connect a couple dots and save ourselves. Eight and a half thousand calls per month by giving the customer up-to-date rental information."

### 4. Token Economics and Multi-Model Routing — 7 talks

**Claim**: Production AI cost is controlled by measuring spend per use case and matching each task to the cheapest, fastest model and serving configuration that passes its evals, not by defaulting to the frontier model.

Featherless, Runpod, Greptile, Ramp, GEICO, Towards AI and Exa each showed a cost lever below the model choice: per-team API keys to see spend, fast cheap models to drive adoption, batching background work, tuning vLLM against measured latency, reserving frontier models for critical steps, cheap open-weight swarms, precomputed KV-cache cartridges, many cheap drafts merged by a stronger model, and returning only relevant snippets to cut downstream tokens. The qualification is that naive turn-by-turn routing across many models destroys cache hit rates.

- **Also called**: tokenomics, right-sizing, frontier orchestrator + fast sub-agent, live benchmarking
- **Talks (7)**:
  - [The AI Bill Is Too Damn High – Tokenomics 101](../talks/2026-10-12-the-ai-bill-is-too-damn-high-tokenomics-101/transcript.md) (### 00:00:00 — Workshop Introduction & Featherless Background): Most organizations cannot see where their token spend goes, so the first and highest-ROI step is issuing separate API keys per department and use case.
    > "Like you need to start splitting up your keys. Start splitting up by departments. Start splitting up by major use cases."
  - [Can Any Model Write Like Me? Building a Benchmark for Creative Writing](../talks/2026-10-13-can-any-model-write-like-me-building-a-benchmark-for-creative-wr/transcript.md) (### 00:12:33 — Evaluating Style, Voice & Model Findings): At scale, many cheap drafts merged by a stronger high-thinking model beat a single expensive generation, with a long detailed prompt and human review still required.
    > "What I suggest is to generate several drafts."
  - [From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod](../talks/2026-10-13-from-model-to-metrics-serving-and-benchmarking-any-llm-live-with/transcript.md) (### 00:00:00 — Why Live LLM Serving & Benchmarking Is Hard): Sizing should start from the use case and expected concurrency, including KV cache use, rather than the cheapest GPU or the maximum context window.
    > "But if you're going to be going to more concurrent users, you need to start thinking about like how Am I going to be utilizing the KV cache?"
  - [How to build an AI code review agent: from the creators of Greptile](../talks/2026-10-13-how-to-build-an-ai-code-review-agent-from-the-creators-of-grepti/transcript.md) (### 00:11:50 — Sandboxed Execution, Context Indexing & Evaluation): Reserving frontier models for critical steps and routing the long tail of subtasks to small models cuts review cost drastically, provided an eval set guards against regressions.
    > "In practice, we have actually twenty different subtasks, and each of them has a very specific sense model to be used."
  - [Inside the Fable War Room](../talks/2026-10-13-inside-the-fable-war-room/transcript.md) (### 00:12:33 — Production Results & Cultural Takeaways): Once the context was built, a cheaper model wrote legacy code as well as the frontier model, making model selection a major cost lever.
    > "Data and found out that Fable or Sonnet five wrote it just as good as, if not better than Fable."
  - [Search the Web as It Was: An Introduction to Exa Snapshot](../talks/2026-10-13-search-the-web-as-it-was-an-introduction-to-exa-snapshot/transcript.md) (### 00:00:00 — What Is Exa & Agentic Web Search): Search cost should be measured over the agent's whole trajectory, and returning only the relevant snippets cuts downstream input tokens dramatically.
    > "All of the search results, which means that you can actually get higher quality results. At ninety-five percent fewer tokens than you would at full-page text."
  - [Chasing capabilities while waiting for the frontier](../talks/2026-10-14-chasing-capabilities-while-waiting-for-the-frontier/transcript.md) (### 00:00:00 — Token Economics & Capability Growth at Ramp): Pairing a frontier orchestrator with a post-trained, much faster financial question-answering model beat the frontier on exact-pass accuracy at lower latency for spreadsheet work.
    > "we took a step back and decided to try. Train a retrieval model, kind of a financial question answering model that would help."
- **Claims (16)**: `6b92fb75-064e-4cb5-8aa3-7c7f211e7420:753:ce2611`, `736edd83-bb08-49f1-90ed-722b7ed07eb2:753:cc5919`, `b8bb725d-daf0-4ac0-8095-5737841c89e5:0:3711a1`, `bdab432a-0538-4431-ad5a-62653affd9da:710:81e0f2`, `c901e963-5be9-4a1d-86a3-d9354374bbcd:0:a6de48`, `c901e963-5be9-4a1d-86a3-d9354374bbcd:1624:2b9f11`, `c901e963-5be9-4a1d-86a3-d9354374bbcd:2170:49e9ef`, `c901e963-5be9-4a1d-86a3-d9354374bbcd:528:1a15d5`, `caecd5f6-b352-4868-a995-f0f71679caf0:0:e3b1f0`, `caecd5f6-b352-4868-a995-f0f71679caf0:263:80421d`, `caecd5f6-b352-4868-a995-f0f71679caf0:531:98b36e`, `fca86857-d079-46a6-94a7-62b0bb8e5d31:0:3b1667`, `fca86857-d079-46a6-94a7-62b0bb8e5d31:0:6a4155`, `fca86857-d079-46a6-94a7-62b0bb8e5d31:315:2be108`, `fca86857-d079-46a6-94a7-62b0bb8e5d31:672:2f538a`, `fca86857-d079-46a6-94a7-62b0bb8e5d31:672:36e4e4`
- **Counter-claims**:
  - [The AI Bill Is Too Damn High – Tokenomics 101](../talks/2026-10-12-the-ai-bill-is-too-damn-high-tokenomics-101/transcript.md) (### 00:45:24 — Workshop Q&A & Practical Takeaways): Turn-based auto-routing across many models destroys cache hit rates, so routing should be task-based or limited to two or three models.
    > "Your low cash heat rate will start to wreck your optimization."

### 5. Verification Loops Over Human Review — 6 talks

**Claim**: Because agents now produce code and work faster than people can read it, trust has to come from independent, deterministic verification loops that prove each outcome with evidence, not from humans reviewing every line.

Speakers from software factories, code review, and agent-fleet management agreed that line-by-line human review no longer scales with agent output. They replaced it with runnable verifiers: app-specific scripts, layered zero-trust checks inside every loop, a reviewer of a different model family, and agents that exercise changes like a user and hand back screenshots, videos and test results. With verifiers in place, the verification harness becomes the durable asset and confidence becomes the product. The counter-position is that some human step stays irreducible: watching the feature video or approving an action before it lands.

- **Also called**: software factory verification, zero-trust verification, confidence over volume, receipts
- **Talks (6)**:
  - [Beyond “Done”: Building Verification Loops for AI Agents](../talks/2026-10-12-beyond-done-building-verification-loops-for-ai-agents/transcript.md) (### 00:00:00 — Why 'Done' Is Not Enough for Production Agents): Line-by-line human code review cannot keep pace with how fast agents generate code, so trust has to come from another mechanism.
    > "But that takes a long time and these agents can write code a lot faster than us, so we don't want to rely on that."
  - [How to build an AI code review agent: from the creators of Greptile](../talks/2026-10-13-how-to-build-an-ai-code-review-agent-from-the-creators-of-grepti/transcript.md) (### 00:05:48 — Iterative Architecture of Greptile's Review Agent): Models fail the same way when reviewing as when generating, so the reviewer should be a different model family than the one that wrote the code.
    > "If you use hard code to write the code, you want to use the GPT model to review it."
  - [The Machine that Changed the World, vAI](../talks/2026-10-14-the-machine-that-changed-the-world-vai/transcript.md) (### 00:05:31 — Why Unverified AI Code Creates Hidden Debt): Human-in-the-loop review does not scale: code volume has exploded while releases barely rose, and reviewers exhibit 'cognitive surrender' by agreeing with wrong AI output.
    > "they agree with AI when AI is right, 93 percent of the time. And four out of five times, they agree with it when the AI is wrong."
  - [Trusting Agents in Policy-Driven Workflows](../talks/2026-10-14-trusting-agents-in-policy-driven-workflows/transcript.md) (### 00:00:18 — Policy-Driven Workflows & Deterministic Controls at Coinbase): Agents make parallel independent reviews affordable within a gated workflow modeled as a DAG, without dropping required checks.
    > "Now we can run independent reviews alongside each other. Bring results together, but keep the required checks in place."
  - [Who verifies the software factory?](../talks/2026-10-14-who-verifies-the-software-factory/transcript.md) (### 00:00:00 — The Code Review Bottleneck in AI Software Factories): Nearly everyone's coding agents now open pull requests, but only a few people review every merged line, and that gap is the problem the talk addresses.
    > "If you have merged pull requests and reviewed every line of code that was merged. I do see a few people."
  - [Your job is now "agent manager"](../talks/2026-10-14-your-job-is-now-agent-manager/transcript.md) (### 00:00:07 — Managing a Fleet of Builder, Reviewer & Manager Agents): Each builder agent loops with its own reviewer agent up to three times, then escalates unresolved bugs to a manager agent and finally to the human.
    > "We typically stick to a three-review max. Where we allow the builders to loop about three times with reviews."
- **Claims (16)**: `11b98f47-dcc2-4524-8c06-d1f6c3ff044b:0:58294f`, `11b98f47-dcc2-4524-8c06-d1f6c3ff044b:0:cb990a`, `11b98f47-dcc2-4524-8c06-d1f6c3ff044b:392:b97bed`, `11b98f47-dcc2-4524-8c06-d1f6c3ff044b:392:c7f31c`, `11b98f47-dcc2-4524-8c06-d1f6c3ff044b:757:ae0b24`, `4add802c-6a68-4e9c-93fb-9c1e017193bc:331:99cfeb`, `4add802c-6a68-4e9c-93fb-9c1e017193bc:662:2fde74`, `4add802c-6a68-4e9c-93fb-9c1e017193bc:662:7d03e0`, `bdab432a-0538-4431-ad5a-62653affd9da:348:f6dc24`, `bdab432a-0538-4431-ad5a-62653affd9da:710:a14518`, `edb4f982-0cb8-48ee-8bf7-410255a40cb3:0:ab47cd`, `edb4f982-0cb8-48ee-8bf7-410255a40cb3:1048:655786`, `edb4f982-0cb8-48ee-8bf7-410255a40cb3:1048:eec6d4`, `edb4f982-0cb8-48ee-8bf7-410255a40cb3:535:07dad8`, `ee927042-2ba1-44c3-b304-d001ae247839:18:454c89`, `f7204e6d-a47c-4535-804e-16b4db579b95:7:ccd30f`
- **Counter-claims**:
  - [Anthropic: Accelerating frontier AI in Financial Services.](../talks/2026-10-13-anthropic-accelerating-frontier-ai-in-financial-services/transcript.md) (### 00:06:12 — Enterprise Deployment Patterns & Governance): The trust layer scopes agents with an identity and least-privilege permissions and has them propose actions that a human approves before anything changes.
    > "We want it to just propose new amendments to our owner's data. Not actually make those amendments"
  - [Your job is now "agent manager"](../talks/2026-10-14-your-job-is-now-agent-manager/transcript.md) (### 00:00:07 — Managing a Fleet of Builder, Reviewer & Manager Agents): The irreducible human step is watching each builder's recorded feature video and understanding the PR; this is where corners must not be cut.
    > "This is the part of the bottleneck you have to engage in as. A product owner gotta watch the video, gotta pay attention."

### 6. Bounded Autonomy — 5 talks

**Claim**: Agents become trustworthy the way organizations already trust non-deterministic people: through declared permissions, written policy, risk-tiered review and opinionated process, not by locking them down or approving every action.

Two Sigma composes an automatic agent registry, risk-tiered review, declared tool entitlements enforced at runtime and classifiers that escalate only ambiguous calls. Coinbase treats written policy as the institution's original system prompt and places agents inside gated workflow DAGs. Basis encodes opinionated processes as behavior specs because customers value predictability over novelty, and Anthropic scopes agents with identity and least privilege. The counter-position: procedures, warnings and approvers can all be in place and still fail, and command allow-lists do not bound a compromised model.

- **Also called**: agent registry, risk-tiered review, policy as the original system prompt, behavior specs
- **Talks (5)**:
  - [Anthropic: Accelerating frontier AI in Financial Services.](../talks/2026-10-13-anthropic-accelerating-frontier-ai-in-financial-services/transcript.md) (### 00:06:12 — Enterprise Deployment Patterns & Governance): The trust layer scopes agents with an identity and least-privilege permissions and has them propose actions that a human approves before anything changes.
    > "We want it to just propose new amendments to our owner's data. Not actually make those amendments"
  - [Balancing Acceleration and Safety for AI Agents](../talks/2026-10-13-balancing-acceleration-and-safety-for-ai-agents/transcript.md) (### 00:00:00 — Balancing Innovation Speed and Institutional Trust): Agents, like humans, are non-deterministic, so the answer is bounded autonomy with visibility and controls rather than lockdown, making safety and innovation compatible.
    > "We allow them a certain amount of autonomy, along with a certain amount of control."
  - [Process Supervision for Agents That Do Long-Horizon Work](../talks/2026-10-14-process-supervision-for-agents-that-do-long-horizon-work/transcript.md) (### 00:00:00 — Long-Horizon Accounting Agents at Basis): Organizations already trust non-deterministic workers at scale by imposing processes, and agents should be made trustworthy the same way.
    > "It doesn't happen through deterministic systems, right? People are not deterministic; they're intelligent entities. And instead, there are processes that are put in place"
  - [Trusting Agents in Policy-Driven Workflows](../talks/2026-10-14-trusting-agents-in-policy-driven-workflows/transcript.md) (### 00:00:18 — Policy-Driven Workflows & Deterministic Controls at Coinbase): Policy is defined at build time while the system changes constantly at run time, so the two must be treated separately even as the system stays bound by policy.
    > "Ultimately, we separate this from the run state and the build state."
  - [Who verifies the software factory?](../talks/2026-10-14-who-verifies-the-software-factory/transcript.md) (### 00:12:37 — Scaling Trusted Autonomy with Sonar & Anthropic): Agent-written code should be labeled in the PR because it signals which extra checks apply and preserves auditability, while a human still owns the outcome.
    > "I personally think it's fine for the code to be written, labeled as being coming from an agent."
- **Claims (13)**: `11b98f47-dcc2-4524-8c06-d1f6c3ff044b:757:08de08`, `1cbc625f-7f07-49bb-9c5c-57c95f07ba77:0:fe9e1d`, `1cbc625f-7f07-49bb-9c5c-57c95f07ba77:414:be670f`, `1cbc625f-7f07-49bb-9c5c-57c95f07ba77:802:7cd61b`, `68a1e78b-569e-4314-a56f-f20508123cbe:372:36f132`, `73badd10-6f8c-4c95-b5e7-55fc3d7bafc1:0:a19b6e`, `73badd10-6f8c-4c95-b5e7-55fc3d7bafc1:381:4af013`, `73badd10-6f8c-4c95-b5e7-55fc3d7bafc1:381:697aa7`, `73badd10-6f8c-4c95-b5e7-55fc3d7bafc1:758:1b1695`, `73badd10-6f8c-4c95-b5e7-55fc3d7bafc1:758:edc3e2`, `ee927042-2ba1-44c3-b304-d001ae247839:18:30da97`, `ee927042-2ba1-44c3-b304-d001ae247839:18:454c89`, `ee927042-2ba1-44c3-b304-d001ae247839:18:4be36f`
- **Counter-claims**:
  - [Balancing Acceleration and Safety for AI Agents](../talks/2026-10-13-balancing-acceleration-and-safety-for-ai-agents/transcript.md) (### 00:00:00 — Balancing Innovation Speed and Institutional Trust): The Citibank–Revlon payment error shows that procedures, warnings and human approvers can all be in place and still fail, which is the failure mode agent controls must anticipate.
    > "So the three approvers who were supposed to approve that looked at it and said, "Yep, that's the right thing that's supposed to happen.""
  - [Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On](../talks/2026-10-13-give-the-model-a-computer-the-one-thing-every-ai-agent-framework/transcript.md) (### 00:00:05 — Why Every Agent Framework Converges on Sandboxed Computers): Command allow-lists and approval prompts on a local machine do not bound what a compromised model can do, since one allowed interpreter command opens everything.
    > "you essentially defined what. Your model should use, but you didn't define what your model can actually use"

### 7. Provenance and Grounding in Financial AI — 5 talks

**Claim**: In finance, an agent earns a role in real decisions only when it runs on the firm's own governed, time-scoped data with a validated golden source, because the data and its connectors matter more than the model.

Bridgewater, Apollo, Exa, Coatue and Anthropic's financial-services team all located the hard problem below the model: cleaning and aligning unstructured data to the firm's ontology, finding the golden source among many, giving agents direct access to every source a human sees through one connectivity layer, and serving the web as it looked on a past date so a backtest cannot see the future. A generic web-searching agent answering from one stale source was the cautionary example.

- **Also called**: golden source, point-in-time search, institutional grounding, owning your data
- **Talks (5)**:
  - [A Hedge Fund as a Function](../talks/2026-10-13-a-hedge-fund-as-a-function/transcript.md) (### 00:00:00 — Investment Thesis: Modeling the Hedge Fund as a Function): Agents need direct API access to every data source humans see, or their intelligence is wasted.
    > "Every single thing that a human can see in pixels on the screen. An agent in your building should be able to see via API."
  - [Anthropic: Accelerating frontier AI in Financial Services.](../talks/2026-10-13-anthropic-accelerating-frontier-ai-in-financial-services/transcript.md) (### 00:06:12 — Enterprise Deployment Patterns & Governance): Hand-wiring each agent to each source system does not scale, so agents should reach business data through a single secure MCP connectivity layer.
    > "You'll want to have those agents work on one secure connectivity layer which is MCP."
  - [Search the Web as It Was: An Introduction to Exa Snapshot](../talks/2026-10-13-search-the-web-as-it-was-an-introduction-to-exa-snapshot/transcript.md) (### 00:06:00 — Exa Snapshot & Backtesting Financial Agents Without Lookahead Bias): Because Exa's crawler versions every page it checks for freshness, it can serve a URL or run a whole search as it would have looked on a past date.
    > "It's 400 billion plus snapshots of the web, and you can search them by day."
  - [Vault: Making Unstructured Data Work for Investing](../talks/2026-10-13-vault-making-unstructured-data-work-for-investing/transcript.md) (### 00:00:00 — From Structured Time Series to Unstructured Data at Bridgewater): A generic web-searching chat agent answered an investment question from one stale source, while the same query against Vault found 52 time-scoped candidates and drew on seven, showing data and connectors matter more than the model.
    > "it takes great data and the right connectors to make AI powerful."
  - [AI in Practice: An Inside Look at Apollo's Approach](../talks/2026-10-14-ai-in-practice-an-inside-look-at-apollo-s-approach/transcript.md) (### 00:06:34 — Reconciling Fragmented Deal & Portfolio Data with Agents): General-purpose LLMs help with research but cannot carry trading decisions, because trust comes from owning your data with a platform on top of it.
    > "it's all general information that that's being worked off of, and none of your own actual data."
- **Claims (9)**: `44e9d04a-e8b4-418c-8a85-02fbb9263dd0:394:551a7b`, `44e9d04a-e8b4-418c-8a85-02fbb9263dd0:394:d52172`, `68a1e78b-569e-4314-a56f-f20508123cbe:372:67b586`, `9a9dfcd0-459f-43eb-b3f8-004864b4ad2a:0:0eb6d7`, `a84ca3a8-cc2f-4b50-a635-fc380f6f04f6:0:919c3d`, `a84ca3a8-cc2f-4b50-a635-fc380f6f04f6:0:b31643`, `a84ca3a8-cc2f-4b50-a635-fc380f6f04f6:293:b8188f`, `b8bb725d-daf0-4ac0-8095-5737841c89e5:360:0aeb1e`, `b8bb725d-daf0-4ac0-8095-5737841c89e5:360:fd226e`
- **Uncontested**: No speaker argued that a general-purpose model without the firm's own governed data could carry a trading or investment decision; Apollo grants general LLMs only a research role, which restates the theme rather than opposing it.

### 8. The Sandboxed Computer and Evolving Harness — 5 talks

**Claim**: Agent harnesses are converging on a separate, disposable sandboxed computer as the execution boundary, while the prompt scaffolding they once added is being absorbed into the models.

Every agent framework, however much they disagree, integrates the same create-run-delete sandbox primitives, because allow-lists and embedded runtimes do not bound a compromised model and a throwaway VM does. Greptile, Arize and Ryan Carson run their agents in cloud sandboxes for the same reason, and that boundary must be chosen before the framework. Meanwhile the harness's intelligence tricks are being learned by the models through a data flywheel, so harnesses should ship and unship features easily. The counter-position, from the same talks, is that the harness keeps infrastructure, trust and efficiency, and must re-add prompting and guardrails in every new domain.

- **Also called**: give the model a computer, the model ate the harness, execution boundary, cloud agent sessions
- **Talks (5)**:
  - [Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On](../talks/2026-10-13-give-the-model-a-computer-the-one-thing-every-ai-agent-framework/transcript.md) (### 00:00:05 — Why Every Agent Framework Converges on Sandboxed Computers): Competing agent frameworks disagree on what an agent even is, yet all integrate sandboxes through the same create, run, delete primitives, which signals necessity rather than fashion.
    > "But under the hood, all of these ways speak the three same lines, so it's. Sandbox creation, running some code or task inside the sandbox, and sandbox deletion."
  - [How to build an AI code review agent: from the creators of Greptile](../talks/2026-10-13-how-to-build-an-ai-code-review-agent-from-the-creators-of-grepti/transcript.md) (### 00:11:50 — Sandboxed Execution, Context Indexing & Evaluation): Spinning up the customer's full stack in a sandbox and driving it with computer-use models catches issues, like UI regressions, that reading the diff cannot.
    > "Is we essentially build these dependency-rich sandboxes, which are completely configurable virtual machines."
  - [What does an AI engineer do?](../talks/2026-10-13-what-does-an-ai-engineer-do/transcript.md) (### 00:04:53 — The Build-Eval-Ship-Monitor Loop): Each Signal run uses a disposable sandbox behind a single proxy, while issues, traces and learned skills persist outside it so runs are durable and resumable.
    > "All of the output is actually saved off in some kind of memory, so that the next time an agent gets spun up, it doesn't have to start from ground zero."
  - [The Model Ate the Coding Harness. Now What?](../talks/2026-10-14-the-model-ate-the-coding-harness-now-what/transcript.md) (### 00:00:00 — Evolution of the Coding Agent Harness): The harness makes itself obsolete through a data flywheel: it brings harder tasks within reach, users generate data, and models learn those skills natively.
    > "It turns out the harness. Is actually making itself obsolete through what I call the data flywheel."
  - [Your job is now "agent manager"](../talks/2026-10-14-your-job-is-now-agent-manager/transcript.md) (### 00:00:07 — Managing a Fleet of Builder, Reviewer & Manager Agents): Engineers still coding or running local dev hold their teams back; work should run as communicating cloud agent sessions.
    > "if you're running local dev, you are screwing up. You're holding yourself back."
- **Claims (12)**: `29083884-87dc-44f8-b412-b494afca8856:0:167207`, `29083884-87dc-44f8-b412-b494afca8856:0:68bd81`, `29083884-87dc-44f8-b412-b494afca8856:396:5fdb8c`, `29083884-87dc-44f8-b412-b494afca8856:733:8b6ee0`, `8d424512-c7f0-483c-9094-ca899d7bb1fd:308:132808`, `8d424512-c7f0-483c-9094-ca899d7bb1fd:308:62a5a5`, `8d424512-c7f0-483c-9094-ca899d7bb1fd:5:6a2dc1`, `8d424512-c7f0-483c-9094-ca899d7bb1fd:5:eae03a`, `8d424512-c7f0-483c-9094-ca899d7bb1fd:620:117bf8`, `b2ed4456-5671-4e8e-83fd-684c012fef8c:293:9e2978`, `bdab432a-0538-4431-ad5a-62653affd9da:710:a14518`, `f7204e6d-a47c-4535-804e-16b4db579b95:7:75ba49`
- **Counter-claims**:
  - [The Model Ate the Coding Harness. Now What?](../talks/2026-10-14-the-model-ate-the-coding-harness-now-what/transcript.md) (### 00:06:36 — What Happens as Models Absorb Harness Scaffolding): Infrastructure for long-running cloud agents, trust and security controls, and cost efficiency remain harness responsibilities the model cannot absorb.
    > "There are some parts of the harness that the model can't absorb."
  - [The Model Ate the Coding Harness. Now What?](../talks/2026-10-14-the-model-ate-the-coding-harness-now-what/transcript.md) (### 00:06:36 — What Happens as Models Absorb Harness Scaffolding): In new domains like an autonomous colleague product, the team is re-adding prompting and guardrails because models have not yet mastered those tasks.
    > "Curiously, in Grokbot, we've actually found ourselves putting back a lot of these things, adding new prompting, adding new guardrails."

### 9. Owning Open Foundations vs. Renting the Frontier — 4 talks

**Claim**: Companies should own their agent stack on open, model-swappable foundations rather than rent it from frontier labs, because models are commoditizing and the labs will recoup their spend by locking customers in or competing with them.

Nous Research made the case most directly: frontier models are interchangeable, so labs move up to the agent layer and into lucrative domains, and whatever platform a company roots its agentic processes in hardens into its organization. Ramp, Daytona and Arize argued the practical half: go a layer below the frontier APIs, use open-weight models where they keep most of the quality, and keep the harness model-agnostic so models can be swapped. The counter-position is that frontier capability already outpaces adoption and keeps getting cheaper, so building on a lab's foundation, or simply waiting, is the rational move.

- **Also called**: owned vs. rented land, open-weight sovereignty, model-agnostic harness, go a layer below the frontier
- **Talks (4)**:
  - [Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On](../talks/2026-10-13-give-the-model-a-computer-the-one-thing-every-ai-agent-framework/transcript.md) (### 00:10:20 — Patterns from Integrating Across Agent Harnesses): Asking which framework to pick is the wrong question because models, prompts, features, and even sandbox providers are swappable.
    > "And based on this whole story, I think this is essentially the wrong question."
  - [Hermes gives you wings: Build on open foundations.](../talks/2026-10-13-hermes-gives-you-wings-build-on-open-foundations/transcript.md) (### 00:00:00 — The Economics of Frontier Labs vs. Open Foundations): Frontier models are becoming interchangeable, so the margin labs need to recoup hundreds of billions in spend is narrowing.
    > "The problem is, though, that the models have begun to commoditize."
  - [What does an AI engineer do?](../talks/2026-10-13-what-does-an-ai-engineer-do/transcript.md) (### 00:04:53 — The Build-Eval-Ship-Monitor Loop): Making the agent harness- and model-agnostic lets the team compare quality across models and cut cost without losing rigor.
    > "we built Signal to also be. You know, agnostic of the model or the harness."
  - [Chasing capabilities while waiting for the frontier](../talks/2026-10-14-chasing-capabilities-while-waiting-for-the-frontier/transcript.md) (### 00:00:00 — Token Economics & Capability Growth at Ramp): As in 2023, when Ramp shipped agents despite weak models, there is still value in going a layer below the frontier APIs instead of waiting.
    > "But I still believe that we can dig it layer down. And create even better experiences for our users is just it requires a bit more effort now."
- **Claims (9)**: `871cd5c8-13f4-4fe9-ac49-c8b25d970add:0:08b17c`, `871cd5c8-13f4-4fe9-ac49-c8b25d970add:0:4cc3fb`, `871cd5c8-13f4-4fe9-ac49-c8b25d970add:0:4efad3`, `871cd5c8-13f4-4fe9-ac49-c8b25d970add:313:3f0544`, `871cd5c8-13f4-4fe9-ac49-c8b25d970add:621:a02383`, `8d424512-c7f0-483c-9094-ca899d7bb1fd:620:3ea2f9`, `b2ed4456-5671-4e8e-83fd-684c012fef8c:293:18eac8`, `caecd5f6-b352-4868-a995-f0f71679caf0:0:f4a6e2`, `caecd5f6-b352-4868-a995-f0f71679caf0:531:98b36e`
- **Counter-claims**:
  - [Anthropic: Accelerating frontier AI in Financial Services.](../talks/2026-10-13-anthropic-accelerating-frontier-ai-in-financial-services/transcript.md) (### 00:00:11 — Introduction: Frontier AI in Financial Services): Model capability is no longer the constraint in financial services; the opportunity is building a foundation that takes agents from one-by-one builds to many.
    > "And our opportunity here is scale. Is not the model. Our opportunity here is scale."
  - [Chasing capabilities while waiting for the frontier](../talks/2026-10-14-chasing-capabilities-while-waiting-for-the-frontier/transcript.md) (### 00:00:00 — Token Economics & Capability Growth at Ramp): Total token spend grows but per-unit cost falls as newer, cheaper, faster models ship, which raises the question of why not just wait.
    > "on a unit economic basis, they're actually becoming cheaper because there are friendlier models that are being released."

### 10. The Context Problem — 4 talks

**Claim**: Once code is cheap, agents fail for lack of intent, history and tribal knowledge rather than intelligence, so teams must build systems that assemble that context before and around the agent.

At Linear, agents read the code yet miss intent, prior decisions, owners and recent reverts, so a triage agent enriches each issue and a context-aware reviewer catches product-level mistakes. GEICO found that synthesized context and the right decision makers, not coding speed, rate-limited legacy modernization, and that once context was built a cheaper model wrote as well as the frontier. Greptile replaces imprecise RAG with a maintained codebase wiki; Ramp precomputes predictable context into KV-cache cartridges. The counter-position is the data flywheel: what the harness supplies today the model learns natively tomorrow.

- **Also called**: context engineering, tribal knowledge, outer loop, cartridges
- **Talks (4)**:
  - [How to build an AI code review agent: from the creators of Greptile](../talks/2026-10-13-how-to-build-an-ai-code-review-agent-from-the-creators-of-grepti/transcript.md) (### 00:11:50 — Sandboxed Execution, Context Indexing & Evaluation): Plain RAG is imprecise and token-hungry, so a maintained wiki of how the codebase, telemetry, docs and roadmap fit together gives the agent the tribal knowledge it lacks.
    > "The way that Greptile approaches this problem is we actually disintermediate all of these context sources with a living wiki."
  - [Inside the Fable War Room](../talks/2026-10-13-inside-the-fable-war-room/transcript.md) (### 00:00:00 — SDLC Velocity vs. Incident Operations at GEICO): Major changes are rate-limited by getting the right decision makers and the right synthesized context together, so GEICO built a war room of people, a driver, AI tools and agent fleets.
    > "So to solve for this, we create a multiplayer AI native war room."
  - [Chasing capabilities while waiting for the frontier](../talks/2026-10-14-chasing-capabilities-while-waiting-for-the-frontier/transcript.md) (### 00:04:23 — Combining Frontier Orchestrators with Specialized Financial Models): Cartridges precompute predictable context (such as month-end close documents) into the KV cache overnight, and the tribal know-how is worth having even if labs later ship it.
    > "you're able to compress a lot of context, up to 20 to 30 times more context. Into the KB cache offline and serve it for your agent."
  - [Your Coding Agent Has a Context Problem](../talks/2026-10-14-your-coding-agent-has-a-context-problem/transcript.md) (### 00:00:00 — Why Coding Agents Fail Without Product & Issue Context): Because agents now run for hours or days without humans steering them, context has to be managed by systems in the outer loop rather than supplied interactively.
    > "Kind of moves out of that inner loop and largely into the outer loop."
- **Claims (9)**: `4b33ac12-ed84-4e32-be63-6a4f9f3acb32:0:2d0eb2`, `4b33ac12-ed84-4e32-be63-6a4f9f3acb32:0:8b99d0`, `4b33ac12-ed84-4e32-be63-6a4f9f3acb32:417:11b6ad`, `4b33ac12-ed84-4e32-be63-6a4f9f3acb32:417:cba17c`, `4b33ac12-ed84-4e32-be63-6a4f9f3acb32:857:11ce27`, `6b92fb75-064e-4cb5-8aa3-7c7f211e7420:0:352496`, `6b92fb75-064e-4cb5-8aa3-7c7f211e7420:753:ce2611`, `bdab432a-0538-4431-ad5a-62653affd9da:710:d389e1`, `caecd5f6-b352-4868-a995-f0f71679caf0:263:80421d`
- **Counter-claims**:
  - [The Model Ate the Coding Harness. Now What?](../talks/2026-10-14-the-model-ate-the-coding-harness-now-what/transcript.md) (### 00:00:00 — Evolution of the Coding Agent Harness): The harness makes itself obsolete through a data flywheel: it brings harder tasks within reach, users generate data, and models learn those skills natively.
    > "It turns out the harness. Is actually making itself obsolete through what I call the data flywheel."

### 11. Spatiotemporal World Models and Simulation — 2 talks

**Claim**: Models trained to predict video frames and actions at scale will learn physics and real-time control, becoming simulators and agents that act in space and time rather than in turns of text.

General Intuition and Runway both bet on scaling laws for video: General Intuition on action-labeled gameplay that maps onto robot teleoperation, Runway on next-frame prediction that learns gravity, occlusion and object permanence and can render an interactive interface with no 3D engine. Both expect the result to unlock robotics and new businesses. They differ on supervision: General Intuition argues explicit action labels transfer better than inferred ones.

- **Also called**: everything will be simulated, pixels to actions, world interface model
- **Talks (2)**:
  - [Frontier Models for Acting in Space and Time](../talks/2026-10-13-frontier-models-for-acting-in-space-and-time/transcript.md) (### 00:00:09 — From Internet Text to Spatiotemporal World Models): Unlike turn-based LLMs, agents in space and time must continuously observe while acting, which calls for purpose-built pixels-to-actions models.
    > "Constantly, part of that behavior is that it's constantly observing as it is acting."
  - [Everything will be Simulated](../talks/2026-10-14-everything-will-be-simulated/transcript.md) (### 00:00:00 — Ten Years of Generative Media & World Models at Runway): Runway bets that scaling laws hold for video models just as they do for language models, and is ramping compute accordingly.
    > "I think we believe in scaling loss. Not only applied for language models, but also for video, and this has been true."
- **Claims (10)**: `af8422e8-d5f8-4dbd-a918-6360f5bfba80:0:201036`, `af8422e8-d5f8-4dbd-a918-6360f5bfba80:0:c1119d`, `af8422e8-d5f8-4dbd-a918-6360f5bfba80:341:9a3499`, `af8422e8-d5f8-4dbd-a918-6360f5bfba80:341:b0bd96`, `af8422e8-d5f8-4dbd-a918-6360f5bfba80:341:d2dc40`, `af8422e8-d5f8-4dbd-a918-6360f5bfba80:682:734bc0`, `cada670e-c5ea-4977-b3c2-9a68dda26abb:439:92e4f5`, `cada670e-c5ea-4977-b3c2-9a68dda26abb:804:e9beb3`, `cada670e-c5ea-4977-b3c2-9a68dda26abb:9:43fbe1`, `cada670e-c5ea-4977-b3c2-9a68dda26abb:9:a385db`
- **Counter-claims**:
  - [Frontier Models for Acting in Space and Time](../talks/2026-10-13-frontier-models-for-acting-in-space-and-time/transcript.md) (### 00:13:24 — Transferring Spatial Intelligence to Real-World Control): Training on explicit action labels rather than inferred ones, unlike JEPA, transfers better to action prediction and is more practical in the short term.
    > "Our mode of having the action data really transfers better to action sequences than it does to world models and to generate the pixels."

## Contested Questions

### Can an LLM judge be trusted to grade agent output?

- **Yes, once the evaluator has been evaluated until it agrees with human judgment on golden datasets.** — [What does an AI engineer do?](../talks/2026-10-13-what-does-an-ai-engineer-do/transcript.md) (### 00:09:45 — Continuous Improvement & Agent Observability)
  > "Verify them against the human output, and then try to align to make sure that the judge actually agrees with the human."
- **Yes, as short markdown rubrics with pass/fail thresholds applied to each conversation.** — [Your agent needs a skill to improve its skills](../talks/2026-10-14-your-agent-needs-a-skill-to-improve-its-skills/transcript.md) (### 00:06:36 — A Meta-Skill for Mining Past Runs & Updating Skills)
  > "Where you can define what thing you're trying to score with an LLM as a judge."
- **No: LLM verdicts change across identical replications and when challenged, so they are unreliable verifiers.** — [The Machine that Changed the World, vAI](../talks/2026-10-14-the-machine-that-changed-the-world-vai/transcript.md) (### 00:05:31 — Why Unverified AI Code Creates Hidden Debt)
  > "Ask the same questions, get a different answer between seven and seventeen percent of the time."
- **No: LLM-as-judge scoring proved too noisy to rely on; redesign the agent so it can be evaluated by construction.** — [Write the Answer First: Generating Eval Datasets for Agents With No Benchmark](../talks/2026-10-13-write-the-answer-first-generating-eval-datasets-for-agents-with/transcript.md) (### 00:12:35 — Production Rollout & Lessons Learned)
  > "The original design we could not evaluate it. We switched to something that we can actually evaluate because of that."

### Should a human approve agent actions before they take effect?

- **Yes: agents propose actions with scoped identity and least privilege, and a human approves before anything changes.** — [Anthropic: Accelerating frontier AI in Financial Services.](../talks/2026-10-13-anthropic-accelerating-frontier-ai-in-financial-services/transcript.md) (### 00:06:12 — Enterprise Deployment Patterns & Governance)
  > "We want it to just propose new amendments to our owner's data. Not actually make those amendments"
- **No: approving every action causes review fatigue; deterministic rules and classifiers handle routine calls and escalate only ambiguous ones.** — [Balancing Acceleration and Safety for AI Agents](../talks/2026-10-13-balancing-acceleration-and-safety-for-ai-agents/transcript.md) (### 00:12:38 — Production Architecture at Two Sigma)
  > "When explicit rules apply, we want deterministic fast paths."
- **Only at one irreducible step: the human watches each feature video and understands the PR.** — [Your job is now "agent manager"](../talks/2026-10-14-your-job-is-now-agent-manager/transcript.md) (### 00:00:07 — Managing a Fleet of Builder, Reviewer & Manager Agents)
  > "This is the part of the bottleneck you have to engage in as. A product owner gotta watch the video, gotta pay attention."

### Should agent reliability live in the harness or be absorbed into the model?

- **Newer models score about the same in any harness, so harness scaffolding no longer adds coding intelligence and the model absorbs it.** — [The Model Ate the Coding Harness. Now What?](../talks/2026-10-14-the-model-ate-the-coding-harness-now-what/transcript.md) (### 00:00:00 — Evolution of the Coding Agent Harness)
  > "A fancy harness in this day and age no longer adds coding intelligence."
- **Builders must encode opinionated process around the agent, because open-ended agents produce inconsistent results.** — [Process Supervision for Agents That Do Long-Horizon Work](../talks/2026-10-14-process-supervision-for-agents-that-do-long-horizon-work/transcript.md) (### 00:06:54 — Process Supervision vs. Outcome-Only Evaluation)
  > "Right not because the process it did was bad, but because the process it did was not opinionated."
- **In each new domain the harness has to re-add prompting and guardrails until the model masters those tasks.** — [The Model Ate the Coding Harness. Now What?](../talks/2026-10-14-the-model-ate-the-coding-harness-now-what/transcript.md) (### 00:06:36 — What Happens as Models Absorb Harness Scaffolding)
  > "Curiously, in Grokbot, we've actually found ourselves putting back a lot of these things, adding new prompting, adding new guardrails."

### Should enterprises build on owned open foundations or on the frontier labs' stack?

- **Whatever platform roots a company's agentic processes hardens into its organization, so it should be an open foundation the company controls.** — [Hermes gives you wings: Build on open foundations.](../talks/2026-10-13-hermes-gives-you-wings-build-on-open-foundations/transcript.md) (### 00:05:13 — Hermes & Owning Your Intelligence Stack)
  > "I implore you: Do not build on quicksand foundations. Build on open foundations."
- **Model capability is no longer the constraint; the opportunity is a reusable agent foundation built on frontier models.** — [Anthropic: Accelerating frontier AI in Financial Services.](../talks/2026-10-13-anthropic-accelerating-frontier-ai-in-financial-services/transcript.md) (### 00:00:11 — Introduction: Frontier AI in Financial Services)
  > "And our opportunity here is scale. Is not the model. Our opportunity here is scale."
- **Going a layer below the frontier APIs pays now rather than waiting for the labs.** — [Chasing capabilities while waiting for the frontier](../talks/2026-10-14-chasing-capabilities-while-waiting-for-the-frontier/transcript.md) (### 00:00:00 — Token Economics & Capability Growth at Ramp)
  > "But I still believe that we can dig it layer down. And create even better experiences for our users is just it requires a bit more effort now."

## Singletons

Claims only one talk makes. Often the most distinctive thing a talk said.

- [A Hedge Fund as a Function](../talks/2026-10-13-a-hedge-fund-as-a-function/transcript.md) (### 00:00:00 — Investment Thesis: Modeling the Hedge Fund as a Function): Agents will transform investing even more than they have transformed coding.
  > "I think that agents will have an even bigger impact in investing than they did at coding."
- [A Hedge Fund as a Function](../talks/2026-10-13-a-hedge-fund-as-a-function/transcript.md) (### 00:00:00 — Investment Thesis: Modeling the Hedge Fund as a Function): A hedge fund can be modeled as a function compressing external and internal context into a what/how much/when decision.
  > "So at a high level, you can think about a hedge fund as a function that takes in two parameters."
- [A Hedge Fund as a Function](../talks/2026-10-13-a-hedge-fund-as-a-function/transcript.md) (### 00:04:30 — Deploying Agents Across Public & Private Market Research): Every design choice in even a simple news-ingestion step is a hyperparameter to tune and optimize.
  > "There's actually a lot of knobs here, and I almost think about those knobs. It's like hyperparameters in a traditional machine learning system, right?"
- [A Hedge Fund as a Function](../talks/2026-10-13-a-hedge-fund-as-a-function/transcript.md) (### 00:04:30 — Deploying Agents Across Public & Private Market Research): Each step should be assigned whichever runner (deterministic code, statistics, LLM, or human) maximizes quality, not automated by default.
  > "There is no glory in automating things for the sake of automating things. The goal is not to take as many things and make them LLMs as possible."
- [Agents can pay. So why don’t they?](../talks/2026-10-13-agents-can-pay-so-why-don-t-they/transcript.md) (### 00:07:30 — Payment Protocols, MCP & x402 Friction): Subsidized flat-rate model plans remove agents' incentive to buy services instead of building from scratch, and their end would boost demand.
  > "This is crazy because then the agents have no incentives whatsoever. To, you know, to look for existing services because they can build anything from scratch because it costs nothing."
- [Agents can pay. So why don’t they?](../talks/2026-10-13-agents-can-pay-so-why-don-t-they/transcript.md) (### 00:13:38 — Real-World Agent Monetization Lessons at Apify): Fixed price per call is insufficient; agent payments need variable pay-per-use billing, which early protocols handled poorly.
  > "But to complete a real job, you actually need like paper use."
- [Agents can pay. So why don’t they?](../talks/2026-10-13-agents-can-pay-so-why-don-t-they/transcript.md) (### 00:13:38 — Real-World Agent Monetization Lessons at Apify): Agents will discover trustworthy paid services through networks of trust and curated directories and marketplaces.
  > "Or basically using trusted directories and marketplaces, and we can already see this happening."
- [Can Any Model Write Like Me? Building a Benchmark for Creative Writing](../talks/2026-10-13-can-any-model-write-like-me-building-a-benchmark-for-creative-wr/transcript.md) (### 00:00:00 — Defining AI Writing Slop & Why It Happens): Slop is more than overused words: it is generic, says nothing, repeats, hallucinates, and above all lacks a distinctive voice.
  > "Endlessly, the worst to me is that it usually has the wrong tone, or at least it has no tone and like everyone's tone at the same time"
- [Can Any Model Write Like Me? Building a Benchmark for Creative Writing](../talks/2026-10-13-can-any-model-write-like-me-building-a-benchmark-for-creative-wr/transcript.md) (### 00:12:33 — Evaluating Style, Voice & Model Findings): For creative writing the right choice is the model that gets you to your target with the least friction, since no model one-shots good prose.
  > "You just want to find a model that will be the least annoying to you."
- [Closing Remarks](../talks/2026-10-13-closing-remarks/transcript.md) (### 00:00:00 — Day 1 Closing Remarks & Keynote Recap): The closing keynotes covered pixels-to-actions world models, owned versus rented foundations for agents, and applied AI in investment decisions.
  > "We had him talking about world models going from pixels to actions."
- [Closing Remarks](../talks/2026-10-13-closing-remarks/transcript.md) (### 00:00:00 — Day 1 Closing Remarks & Keynote Recap): The conference's content matters most as surface area for attendees to connect and talk with one another.
  > "Again, that is surface area for you to be able to connect with others."
- [From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod](../talks/2026-10-13-from-model-to-metrics-serving-and-benchmarking-any-llm-live-with/transcript.md) (### 00:00:00 — Why Live LLM Serving & Benchmarking Is Hard): Restarting images and waiting on cold starts for every config change makes iteration slow, which a live-reconfigurable benchmark harness removes.
  > "You set up a config, but then you have to restart the image. You have to wait for cold starts to happen."
- [Frontier Models for Acting in Space and Time](../talks/2026-10-13-frontier-models-for-acting-in-space-and-time/transcript.md) (### 00:07:19 — Learning Action Policies from Billions of Gameplay Trajectories): Gameplay is far more action-dense than teleoperation data, which brings fine-grained control tasks like drone piloting within reach.
  > "so you want a model that can predict really high APM."
- [Hermes gives you wings: Build on open foundations.](../talks/2026-10-13-hermes-gives-you-wings-build-on-open-foundations/transcript.md) (### 00:05:13 — Hermes & Owning Your Intelligence Stack): Proprietary software is no longer a moat because agents can reproduce features quickly, so durable advantage moves to network effects, reputation and reliability.
  > "The most of yesterday were in proprietary IP. The modes of tomorrow are in network effects, reputation, and reliability."
- [Vault: Making Unstructured Data Work for Investing](../talks/2026-10-13-vault-making-unstructured-data-work-for-investing/transcript.md) (### 00:09:53 — Grounding, Evaluation & Iterative Deployment): Adoption required migrating researchers' email habits into Vault, turning subscriber lists into saved searches and folders into saved collections before opening new workflows.
  > "No matter how amazing the tools are, we can't just drop them on our investors' desks and expect them to be used."
- [Vault: Making Unstructured Data Work for Investing](../talks/2026-10-13-vault-making-unstructured-data-work-for-investing/transcript.md) (### 00:09:53 — Grounding, Evaluation & Iterative Deployment): The goal is proactive always-on agents in an investor workbench, with the synthesis from human-agent collaboration captured back into Vault so the research loop compounds.
  > "the vault enables compounding because it provides the right evidence, the right internal and external information at the fingertips of our investors and agents"
- [AI in Practice: An Inside Look at Apollo's Approach](../talks/2026-10-14-ai-in-practice-an-inside-look-at-apollo-s-approach/transcript.md) (### 00:00:00 — Rowspace & Apollo: AI for Institutional Investment Data): A weekly manual trade reconciliation built from bank statements became a repeatable automated report the team only QAs.
  > "now all of that is automated, and then from our team's perspective, we are just QAing that and checking it each day to make sure that looks right."
- [AI in Practice: An Inside Look at Apollo's Approach](../talks/2026-10-14-ai-in-practice-an-inside-look-at-apollo-s-approach/transcript.md) (### 00:12:48 — Governance, Auditability & Deployment Lessons at Apollo): AI used well becomes a durable competitive edge in private markets because accurate information at your fingertips drives process and decisions.
  > "I think if it's adapted and utilized. Properly, it will make you more competitive."
- [Chasing capabilities while waiting for the frontier](../talks/2026-10-14-chasing-capabilities-while-waiting-for-the-frontier/transcript.md) (### 00:04:23 — Combining Frontier Orchestrators with Specialized Financial Models): A 10,000-agent pentest swarm found seven high-severity vulnerabilities, including one that only emerged from combining individually safe components.
  > "no single component of that stack was unsafe, and the kind of swarm have to patch together multiple components"
- [Process Supervision for Agents That Do Long-Horizon Work](../talks/2026-10-14-process-supervision-for-agents-that-do-long-horizon-work/transcript.md) (### 00:13:22 — Scaling Multi-Step Reliability in Production): Forking a trajectory at the failing decision, or cheaply simulating the production agent with a subagent, lets builders diagnose and fix behavior failures quickly.
  > "Ask the coding agent to make a subagent that pretends to be your production agent."
- [The Machine that Changed the World, vAI](../talks/2026-10-14-the-machine-that-changed-the-world-vai/transcript.md) (### 00:00:06 — From Lean Manufacturing to Enterprise Software Factories): Lean manufacturing principles of quality over volume and fixing the system already shaped modern software practice and should guide agentic software factories.
  > "First is you prioritize quality instead of volume. The second is that you fix the system. Not just individual symptoms that you see."
- [The Machine that Changed the World, vAI](../talks/2026-10-14-the-machine-that-changed-the-world-vai/transcript.md) (### 00:05:31 — Why Unverified AI Code Creates Hidden Debt): Agent reliability drops on large codebases and long-running tasks because errors compound across steps.
  > "It the curve flattens potentially because as you do long-running tasks, errors compound."
- [Welcome Back - Featured Keynotes](../talks/2026-10-14-welcome-back-featured-keynotes/transcript.md) (### 00:00:07 — Day 2 Afternoon Keynote Block Welcome): Hiring, for both companies and speakers, is one of the strongest reasons people come to the conference.
  > "And what I've noticed is that one of the strongest incentives to come to this conference is hiring."
- [Welcome Back - Featured Keynotes](../talks/2026-10-14-welcome-back-featured-keynotes/transcript.md) (### 00:00:07 — Day 2 Afternoon Keynote Block Welcome): Attendees can build an agent that ranks speakers' companies, matches open roles and compensation, and lets them update their preferences on the evidence.
  > "So I suggest you build an agent. That takes the conference program and makes a list of all the speakers and their companies."
- [Welcome Back - Featured Keynotes](../talks/2026-10-14-welcome-back-featured-keynotes/transcript.md) (### 00:00:07 — Day 2 Afternoon Keynote Block Welcome): The agent should inform in-person conversations with the people whose work you liked, not automate applications.
  > "And please don't make your agents send out your resume automatically."
- [Your job is now "agent manager"](../talks/2026-10-14-your-job-is-now-agent-manager/transcript.md) (### 00:05:06 — Continuous 15-Minute Heartbeats & Escalation Loops): Hiring should skip interviews and screens and judge candidates from recorded agent-operating sessions, ranked with model help, because operating agents is what matters.
  > "All that matters is can they operate an agent."

## Limits

- **Thin talks** (3): 2026-10-13-closing-remarks (173 words); 2026-10-14-trusting-agents-in-policy-driven-workflows (502 words); 2026-10-14-welcome-back-featured-keynotes (569 words). A thin talk cannot carry a theme alone.
- **Unassigned**: 2026-10-13-closing-remarks, 2026-10-14-welcome-back-featured-keynotes — keynote-block welcomes and closes that recap or introduce other talks and argue nothing a second talk argues; their atoms are listed as singletons.
- **Coverage**: 31 of the conference's scheduled sessions were recorded; themes count only these talks, so an argument made mostly in unrecorded sessions is invisible here.
- **ASR**: transcripts are Qwen3-ASR output, cleaned but not corrected. Quotes keep ASR garble verbatim; known garbles are recorded in `talk-insights` coverage gaps, not fixed here.
- **Counting**: themes count talks, not mentions. A talk may sit in several themes; a claim may support one theme and qualify another.
- **Claim ids**: every id was re-derived on 2026-11-14 when all claims were re-extracted (85 → 173); ids cited by earlier versions of this report no longer resolve.
