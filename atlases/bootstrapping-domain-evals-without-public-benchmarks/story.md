---
title: "Theme 01: Bootstrapping Domain Evals Without Public Benchmarks"
theme_id: "bootstrapping-domain-evals-without-public-benchmarks"
kind: theme-deep-dive
phase: archive
talks: 11
claims: 21
---

# Bootstrapping Domain Evals Without Public Benchmarks

Public benchmarks never measure a team's real task, so builders must engineer bespoke evaluation loops—synthesizing inputs from known answers, replaying historical outages, backtesting dated web snapshots, and grading trajectories with behavior rubrics—or redesign the agent until it is evaluable.

Across enterprise RAG, legal review, creative writing, code review, accounting, and quantitative investing, speakers converged on the same wall: off-the-shelf benchmarks tell you nothing about whether your agent works, and domain experts cannot hand-grade thousands of runs. Air Canada inverted dataset creation by generating questions from known source pages and populating legal templates with clauses engineered to breach or pass rules, even re-architecting an agent purely to make it deterministically evaluable. Greptile benchmarks prompt changes against historical outage-causing PRs; Bridgewater hand-labeled 200 investment queries in a week to lift precision@10 from 60% to 95%; Exa Snapshot backtests predictive agents against 400 billion dated web pages without lookahead leakage; Towards AI runs five drafts per prompt under a two-stage cross-family rubric; and Basis grades ground-truth-free production runs with behavior specs and trajectory forking. The sharp counter-position centers on the grader itself: Sonar and Air Canada both showed that uncalibrated LLM-as-judge verdicts flip across identical runs and add noise rivaling the agent's own error rate.

## Inverting the dataset: write the answer first and replay real outages

- **Ford Prior (Inside the Fable War Room, 00:15:44)**: Benchmarking against recent production code as golden data revealed that once rich domain context is synthesized, smaller Sonnet-class models generate legacy code as well as frontier models at much lower cost.
  > “we ran benchmarks against like using our existing code recently written as the golden data and found out that Fable or Sonnet five wrote it just as good as, if not better than Fable.”

- **Daksh Gupta (How to build an AI code review agent: from the creators of Greptile, 00:05:41)**: Because catastrophic bugs occur in roughly one in a thousand pull requests and live review output cannot prove bug absence, prompt changes must be benchmarked against a catalog of historical outage-causing PRs.
  > “the validation against really any reviewer can tell you about the presence of bugs, but unfortunately can't tell you about the absence of bugs.”

- **Nathanael Weill (Write the Answer First: Generating Eval Datasets for Agents With No Benchmark, 00:05:31)**: Generating synthetic questions from known source pages and checking retrieval in code accelerated iteration from one experiment per week to one per business day while eliminating brittle pipeline rules.
  > “So the impact of that is we went from one iteration week to business day, and we start to see the accuracy or the rating from the experts going up and up, and actually, removing a lot of complexity.”

- **Nathanael Weill (Write the Answer First: Generating Eval Datasets for Agents With No Benchmark, 00:13:36)**: Populating existing legal contract templates with synthetic clause arrays engineered to either violate or satisfy known rules creates ground-truth breach labels by construction and runs evaluations in five minutes.
  > “instead of trying to fill them, we generate an array for each of those blanks, which — some covers break some wood. Some covers doesn't. We know that. So we know what actually should be tagged as a breach or not.”

- **Nathanael Weill (Write the Answer First: Generating Eval Datasets for Agents With No Benchmark, 00:01:29)**: In enterprise Q&A over roughly 10,000 telecom vendor documents, retrieving the right source page produces the right answer 90% of the time, reducing evaluation primarily to deterministic page-retrieval verification.
  > “And for those that actually tried it, if you found the right page or the right documents, ninety percent of the time, you have actually the right answer.”

## Point-in-time backtesting and golden domain corpora

- **Frank Long (A Hedge Fund as a Function, 00:04:53)**: Ingestion design choices—such as chunking, raw image versus OCR input, translation versus structured extraction, and cross-referencing internal notes—act as tunable hyperparameters over an evolving search space.
  > “There's actually a lot of knobs here, and I almost think about those knobs — it's like hyperparameters in a traditional machine learning system, right? I think about each of these knobs as something for me to tune and optimize against.”

- **Frank Long (A Hedge Fund as a Function, 00:09:20)**: Because real steps combine multiple runners and tune model size, thinking effort, harness, skills, and hooks, workflows must be compartmentalized into evaluable units with a clear north-star metric.
  > “So the way to think about breaking down these problems is, what can I actually compartmentalize in a way that we can understand and evaluate?”

- **Aaron Linsky, Sam Green (Vault: Making Unstructured Data Work for Investing, 00:06:23)**: Hand-labeling roughly 200 representative investment queries in under a week established a baseline of 60% precision at ten and enabled systematic agentic search iterations that pushed precision to roughly 95%.
  > “The key metric we were looking at is precision at ten, which is of the top ten results, how many are the right documents, and we were hitting about sixty percent.”

- **Ryan Ahern (Search the Web as It Was: An Introduction to Exa Snapshot, 00:07:50)**: Testing predictive models on live web search leaks post-event outcomes, whereas querying snapshots at fixed horizons before an event evaluates what signals were genuinely discoverable without lookahead bias.
  > “So I'm gonna go like one day before the announcement, seven days before the announcement, a month before the announcement, and see whether I could or could not predict it, right?”

- **Ryan Ahern (Search the Web as It Was: An Introduction to Exa Snapshot, 00:11:18)**: Across traditional ML feature enrichment, hybrid models adding agentic adverse-media or equity scans, and end-to-end prediction agents, point-in-time snapshots let teams empirically prove historical lift over baseline processes.
  > “You can actually go back and back test that against your existing processes and say, hey, it was better.”

- **Ryan Ahern (Search the Web as It Was: An Introduction to Exa Snapshot, 00:15:36)**: Without historical web snapshots and holdout sets, iterating on expressive semantic search features requires waiting months in live production to tell whether an agentic signal generalizes or overfits.
  > “You might be waiting for months to try and see how and why your agent set up actually is predictive or is overfitting in different ways.”

## Rubrics, process supervision, and firm-wide unit testing for agents

- **Mitchell Troyanovsky (Process Supervision for Agents That Do Long-Horizon Work, 00:12:01)**: Distilling core workflow opinions into 'behavior specs' creates a ground-truth-free rubric that grades any production trajectory whenever a relevant trigger arises, scaling supervision signal far faster than static outcome evals.
  > “And you can say, in this particular trajectory, whether that is in any trajectory that doesn't have a ground truth, did the agent get into a situation in which this behavior was relevant?”

- **Mitchell Troyanovsky (Process Supervision for Agents That Do Long-Horizon Work, 00:13:40)**: When a multi-hour, thousand-call trajectory violates a behavior spec, builders can iterate on context fixes rapidly either by forking state right before the bad decision or by cheaply simulating the production prompt and skills in a coding subagent.
  > “when working with coding agents, ask the coding agent to make a subagent that pretends to be your production agent. And you can tell it to not cheat, and give it the system prompt and the skills, and you render everything perfectly.”

- **Louis-François Bouchard (Can Any Model Write Like Me? Building a Benchmark for Creative Writing, 00:00:00)**: AI writing slop persists as models scale not merely through overused vocabulary, repetition, and hallucination, but fundamentally because generated prose collapses into a generic, voiceless average rather than matching a specific author's tone.
  > “Endlessly, the worst to me is that it usually has the wrong tone, or at least it has no tone and like everyone's tone at the same time, so it just doesn't really talk back to you.”

- **Louis-François Bouchard (Can Any Model Write Like Me? Building a Benchmark for Creative Writing, 00:05:34)**: Generating five drafts per prompt across ten published and held-out scripts captures intra-model variance—which widens as model quality drops and masks lucky one-in-five outlier drafts—without making benchmark runs prohibitively expensive.
  > “But yeah, it's we found that five drafts seems to be the good middle ground in terms of cost for us to execute and to measure this disparity.”

- **Louis-François Bouchard (Can Any Model Write Like Me? Building a Benchmark for Creative Writing, 00:08:55)**: Structuring 14,000-word judge prompts as a two-stage rubric—classifying prose into one of six qualitative buckets before scoring across nine metrics—outperforms binary or direct percentage grading on subjective voice matching.
  > “Then, the judge will categorize between six categories first, and after having found the category, it will give a rating. We found that this is the best way to measure for this more qualitative task.”

- **Louis-François Bouchard (Can Any Model Write Like Me? Building a Benchmark for Creative Writing, 00:08:55)**: Because LLM judges exhibit strong family-wide self-preference—especially OpenAI models favoring all OpenAI outputs—creative-writing evaluations require cross-family judges spot-checked against over a thousand human pairwise comparisons.
  > “And the problem with AI judges is that they have references. Some models prefer themselves, all of those for themselves, and particularly open AI.”

- **John Feminella (Balancing Acceleration and Safety for AI Agents, 00:11:58)**: Because model upgrades act like changing runtime dependencies that can silently alter output quality, firms should provide shared self-serve evaluation infrastructure—analogous to unit testing rather than centralized sign-off queues—where teams supply only agent-specific assertions.
  > “we wouldn't ship software without unit tests. So agents need evaluations for the same reason. And we want to provide this stuff at the level of the firm that's going to be the same for everybody.”

- **Aparna Dhinakaran (What does an AI engineer do?, 00:09:45)**: Because automated PR and production gates are only useful if trusted, AI engineers must curate golden datasets and meta-evaluate LLM judges until they align with human judgment before deploying them offline or online.
  > “We run evals, verify them against the human output, and then try to align to make sure that the judge actually agrees with the human and they're in agreement before we actually ship out a new evaluator.”

- **Eugene Cheah (The AI Bill Is Too Damn High – Tokenomics 101, 00:20:26)**: Right-sizing high-volume process workloads starts with building task-specific eval suites and searching open-weight models for the cheapest passing baseline before prompt-tuning or distilling down to 7B–27B domain models.
  > “You just need to make sure you set up your test cases, your e-dos, and your examples, and then subsequently just do the search process from there.”

