---
title: "Theme 02: Token Economics, Right-Sizing, and Open Foundations"
theme_id: "token-economics-right-sizing-and-open-foundations"
kind: theme-deep-dive
phase: archive
talks: 10
claims: 25
---

# Token Economics, Right-Sizing, and Open Foundations

As frontier intelligence commoditizes while aggregate token bills surge, durable economics come from attributing spend per workload, routing subtasks to fast specialist or open-weight models, tuning serving concurrency and KV caches, and owning a model-swappable stack rather than renting lock-in from frontier labs.

Practitioners attacked runaway inference costs across every layer below default frontier API calls. Featherless showed that splitting API keys by department, reserving superlinear low-latency serving (3x cost per 2x speed) for interactive paths, and leveraging higher tokens-per-second to entice developers onto smaller worker models deliver immediate ROI. Runpod's BenchPod tunes vLLM nightly builds, batch-token concurrency, and 4xH200 DeepSeek deployments live without 30-minute cold starts; Greptile routes 20 review subtasks across small and frontier models; Exa cuts trajectory tokens 95% via dynamic snippet highlights; Towards AI merges ten cheap GLM/Flash drafts with one high-thinking pass; and Ramp pairs frontier orchestrators with post-trained 35B Qwen models, 5x-cheaper open-weight security swarms, and semantic spend taxonomies—even as Apify warned that heavily subsidized flat-rate plans distort build-versus-buy incentives. Strategically, Nous Research argued that shrinking token margins force frontier labs to seek lock-in at the enterprise agent layer and compete vertically, making open, model-agnostic foundations essential. The counter-arguments cut both ways: naive turn-by-turn multi-model routing destroys prefix KV-cache hit rates, while falling frontier unit prices tempt teams to scale on frontier platforms rather than maintain custom post-training.

## Measure by workload first, then right-size to cost per accepted outcome

- **Louis-François Bouchard (Can Any Model Write Like Me? Building a Benchmark for Creative Writing, 00:13:56)**: Across 120 evaluated models, GLM 5.3 Flash offers competitive low-friction drafting at 50x lower cost than top-ranked Opus 5.5 extra high, while Opus 5.5 extra high matches Max Thinking quality at 2.5x lower cost.
  > “It's 50 times cheaper than the best one, which is Opus 5.5 extra high, which is two point five times cheaper than Max Thinking, but with same results.”

- **Louis-François Bouchard (Can Any Model Write Like Me? Building a Benchmark for Creative Writing, 00:16:06)**: For production writing at scale, generating ten drafts with a cheap model like GLM or Flash and merging the strongest passages with a single high-thinking Opus pass beats a single frontier generation on both cost and quality.
  > “ten drafts of one specific thing with a cheaper model like GLM or Flash, and then have a smarter high thinking job like Office, or whatever you want, pick and merge the best parts of each of these drafts”

- **Ryan Ahern (Search the Web as It Was: An Introduction to Exa Snapshot, 00:03:31)**: Because search cost compounds across an agent's downstream inference trajectory rather than a single tool call, returning dynamic snippet highlights across results delivers higher accuracy at 95% fewer context tokens than full-page text.
  > “we now do that across all of the search results, which means that you can actually get higher quality results at ninety-five percent fewer tokens than you would at full-page text.”

- **Daksh Gupta (How to build an AI code review agent: from the creators of Greptile, 00:02:19)**: Naive sandboxed PR review agents burn $3 to $25 per pull request while flooding diffs with banal nitpicks that obscure catastrophic bugs for humans and push coding agents into writing overly defensive code.
  > “You just see lots and lots of comments and it's kind of annoying for you to just read through them, figure out which ones are just minor stylistic complaints and which ones are actually catastrophic problems.”

- **Daksh Gupta (How to build an AI code review agent: from the creators of Greptile, 00:15:45)**: Decomposing review into twenty specialized subtasks—reserving frontier models for the critical 20% like deep bug analysis while routing context reranking and flow checks to small models—slashes inference cost when guarded by evals.
  > “In practice, we have actually twenty different subtasks, and each of them has a very specific sense model to be used, and our small research team is constantly iterating exactly what models we need for the task.”

- **Eugene Cheah (The AI Bill Is Too Damn High – Tokenomics 101, 00:02:54)**: Issuing separate API keys per department and use case is the highest-ROI first step in cost optimization because 30–40% of organizations share a single key that hides workload economics.
  > “Like you need to start splitting up your keys. Start splitting up by departments. Start splitting up by major use cases so that you know where all your token spends are”

- **Eugene Cheah (The AI Bill Is Too Damn High – Tokenomics 101, 00:13:04)**: Developers rarely switch from frontier planners to cheaper worker models to save company budget, so serving the cheaper model at higher tokens-per-second is the incentive that actually drives adoption.
  > “People want to get their work done fast. If the model is smart enough to get it done, and it's cheaper, they will just use it because it's faster, not because it's cheaper.”

## Going a layer below frontier APIs: post-trained specialists and live vLLM tuning

- **Jediah Katz (The Model Ate the Coding Harness. Now What?, 00:11:59)**: Even when benchmark studies show harness choice no longer changes coding accuracy, harnesses drive major differences in task cost and speed, making token efficiency and model-mix routing durable differentiators alongside cloud runtimes and scoped secret permissions.
  > “If you think back to those two slides I showed, where the choice of harness did not make a significant difference in eval scores, both of those studies actually found that there was a significant difference in costs for tasks.”

- **Alexander Shevchenko (Chasing capabilities while waiting for the frontier, 00:02:20)**: Pairing a frontier orchestrator with a post-trained 35B Qwen specialist model for financial question-answering surpassed the frontier model on exact-pass accuracy while serving Ramp Sheets at much lower latency.
  > “we partnered with the company Prime Insights to post train a Quan 3.5, 35 billion model, and we actually got above Bitcoin six, which was the frontier back then, exact pass accuracy”

- **Alexander Shevchenko (Chasing capabilities while waiting for the frontier, 00:07:03)**: In Ramp's 10,000-agent MapReduce pentesting swarm—which uncovered seven high-severity vulnerabilities including a multi-component email script injection—open-weight models up to 5x cheaper retain most of frontier detection accuracy when scaled across parallel runs.
  > “you can actually use open weight models that are up to five times cheaper compared to the frontier reasoning, and because you're set, setting it up as a swarm, the detection rate is not five times lower”

- **Alexander Shevchenko (Chasing capabilities while waiting for the frontier, 00:09:22)**: Ramp's token spend management product applies semantic taxonomy classification to API traffic so enterprises can attribute LLM spend to accounting categories and R&D tax credits rather than raw per-user or per-key totals.
  > “we created a taxonomy that contextually analyzes and semantically analyzes the LLM usage, so you can actually understand how LLMs are being used outside of just attributing it to a team or a person inside of your company.”

- **Alexander Shevchenko (Chasing capabilities while waiting for the frontier, 00:11:16)**: Ramp Labs' Portal projects latent post-training updates from an older specialist model onto newer model versions or families, amortizing post-training investment across base-model upgrades.
  > “Notably, one of the really interesting ones is Portal, where we figured out a way of transferring learnings from one post trained to another”

- **Chris Vela (From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod, 00:03:28)**: Restarting container images on every vLLM flag change stalls tuning behind 30-minute weight downloads and GPU cold starts, motivating BenchPod's live YAML reload and multi-node self-healing watchdog.
  > “You have to wait for cold starts to happen. It's all this loading, and you're not moving as fast. You're waiting like 30 minutes like for Kimi K3 to like download the weights, loading the GPU.”

- **Chris Vela (From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod, 00:09:46)**: Under concurrent Kimi benchmark loads, raising vLLM's max batched tokens leaves time-to-first-token largely unchanged while substantially cutting inter-token latency and end-to-end completion time on long agentic jobs.
  > “But an interesting thing that I did notice of increasing that is like the inter-token latency actually decreases quite a bit when you increase that batch tokens”

- **Chris Vela (From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod, 00:01:14)**: Teams deploying newly released open models frequently trigger serving errors, hallucinations, and KV-cache exhaustion by running stale vLLM releases instead of nightly builds and over-allocating context windows without sizing for concurrency.
  > “A lot of times, I see people are using the wrong v11 version. They might they're probably not using the nightly version. They have the wrong size for the contacts window.”

- **Chris Vela (From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod, 00:14:05)**: Right-sizing self-hosted inference means matching model scale to workload complexity—serving DeepSeek on four H200 GPUs handles routine production traffic cost-effectively, reserving frontier models like Kimi for long-horizon tasks.
  > “And just because it's the frontier model, it doesn't make sense. Like I said, like guy runs deepseek on a 48200s and does a really good job. Kimmy's more for like long tasks that I'm trying to solve something like very detailed.”

- **Chris Vela (From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod, 00:16:10)**: While multi-node vLLM pods suffice for roughly 50 internal users, scaling self-hosted inference to millions of users requires disaggregated prefill-decode serving over Ray clusters paired with dedicated KV-caching layers like LMCache.
  > “But once you start serving to, you know, millions of users, that's where I think, I mean, desired serving, and also like your caching mechanism is important.”

## Owned vs. rented foundations and subsidized token distortions

- **Dillon Rolnick (Hermes gives you wings: Build on open foundations., 00:00:00)**: As practitioners switch readily among competing frontier models, falling per-token prices against flat serving infrastructure costs are compressing model inference margins despite surging total token spend.
  > “There was some charts going around Twitter this week showing the average cost of a token going down while the total spent on tokens surges, and the infrastructure costs associated with serving those tokens have stayed flat”

- **Dillon Rolnick (Hermes gives you wings: Build on open foundations., 00:02:31)**: Frontier labs are moving up the stack to embed at the enterprise agent layer because owning workflows—where 70% of business output may soon be agentic—creates switching-cost stickiness and pricing leverage.
  > “If you're in front of the user, you have an opportunity for stickiness. Stickiness means margin. This is why the fight has largely shifted to the agent layer lately.”

- **Dillon Rolnick (Hermes gives you wings: Build on open foundations., 00:04:04)**: Rather than selling commoditized API tokens at shrinking margins, frontier labs are partnering in sectors like finance to acquire domain context before solving lucrative vertical markets directly to recoup trillion-dollar investments.
  > “The best shot at earning it back is not to sell it for an ever-decreasing margin of others to solve these hard and lucrative problems — the best shot is to solve them yourselves.”

- **Dillon Rolnick (Hermes gives you wings: Build on open foundations., 00:08:01)**: Frontier model capability advantages come primarily from data quality and scale rather than proprietary model architectures, allowing open builders to close capability gaps rapidly through synthetic model distillation.
  > “And the advantage in a model is very rarely in the architecture or some novel system that was created proprietary way for that model. In fact, it's usually in the quality of the data and the scale.”

- **Dillon Rolnick (Hermes gives you wings: Build on open foundations., 00:11:05)**: Agents act as application operating systems combining deterministic code and data sources with non-deterministic model judgment, so enterprises should own an open, model-agnostic harness like Hermes Agent rather than rebuilding AI stacks.
  > “The next thing that you need to know about agents and about the new world is that agents are like operating systems, and they're like frameworks, and they're a lot more like those than they are like chatbots.”

- **Jan Curn (Agents can pay. So why don’t they?, 00:07:35)**: Subsidized flat-rate LLM subscriptions—such as $100 monthly plans yielding $14,000 worth of tokens—destroy the build-versus-buy incentive for agents to pay external APIs when they can code bespoke tools from scratch at zero marginal cost.
  > “This is crazy because then the agents have no incentives whatsoever to, you know, to look for existing services because they can build anything from scratch because it costs nothing.”

- **Mislav Ivanda (Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On, 00:10:16)**: While models, prompts, plugins, frameworks, and sandbox providers remain swappable, execution posture locks in system architecture because building a local POC couples every tool directly to the host process and filesystem.
  > “if you're guessing that you'll use first approach, where everything runs locally, then you write all your tools to use your host or app process environment, using your file system without separation and stuff like that.”

