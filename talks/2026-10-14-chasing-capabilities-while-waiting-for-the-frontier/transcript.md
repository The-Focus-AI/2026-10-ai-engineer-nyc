---
title: "Chasing capabilities while waiting for the frontier"
speakers:
  - name: Alexander Shevchenko
    affiliation: Ramp
room: "Simons Room (Metropolitan East)"
starts_at: "2026-10-14T09:00:00-04:00"
ends_at: "2026-10-14T09:18:00-04:00"
format: "keynote"
recording: "2026-10-14_0901_Ramp"
duration: "13m 33s"
source: "qwen3-asr-1.7b"
---

# Chasing capabilities while waiting for the frontier

> Transcribed by qwen3-asr-1.7b with a schedule prompt. Possible prompt artifacts, names heard more often here than in the unprompted Voice Memos transcript (Qwen vs Voice Memos): Ramp (17 vs 1). Check them against the audio before quoting.

### 00:00:00 — The Bitter Lesson vs. Shipping Agents Today

The use of LLMs has increased 123 percent, while at the same time, a lot of our top features are growing in token spend, but on a unit economic basis, they're actually becoming cheaper because there are friendlier models that are being released all the time now, and these models are cheaper, faster, and better, and so we're able to provide the same level of accuracy at a much lower cost. And so this is a really bitter lesson-pilled pattern. And so, given all this, a question that I sometimes get: Why not just wait? Why not apply research function inside of?

And to answer that, I would like to draw a parallel to twenty three. Back in two thousand and twenty-three, you had access to kind of GPT four and creating an agent was a lot of work. You would have to create very strict guardrails. Models weren't or allowed to backtrack. They didn't have thinking tokens and so if it went in the wrong direction, we would just kind of charge ahead and not realize that I made the mistakes. You had to swipe over all of the problems, to the point where some synonyms could change the behavior of your agent because the they weren't R L properly on generalizing to the user's intent. You have to reduce and scope down the context as much as possible, giving too much context to the agent, which is confusing.

And even back then, we decided, well, we need to ship these — we can't wait for 54.5 or 55 to come out. We need to circle our financial professionals now, and we should things like Ramp or guided many other agents, even though it was not the easy thing to do. And fast forward now to 2026, building an agent is a lot easier. The models have gotten so much better that you can kind of give them MCPS and access to any context. They do a very good job of understanding what they need to do given a task. But I still believe that we can dig it layer down and create even better experiences for our users, is just it requires a bit more effort now.

### 00:02:20 — Post-Training a Specialist Model for Ramp Sheets

So, to present this, some of our work from Ramp Labs, three specific cases of how we research into Ramp itself, starting with creating a specialist model. So in November of last year, we launched Ramp Sheets, which was one of the really early spreadsheet agents. This was before the two Turing Labs launched their versions of spreadsheet agents, and we had a very good launch in November. A bunch of users from great companies in San Diego started using it, and we realized that, well, this is a very general-purpose spreadsheet handling agent, and a lot of the work that people do on Ramp, both inside of the company, but also all of our customers, accounting and finance professionals, are spending most of their days inside of spreadsheets, so we can kind of think the spread, the harness and the brains behind spreadsheets and added into a bunch of other surfaces within RAM.

And as we were building this out, we realized, well, we can probably apply some research from Grand Labs to make this even better, and we sat down and we started looking: where do models push towards — back then, this was like Opus 4.16, and the place that had the most friction was when you would drop in a lot of spreadsheets into Ramp sheets and would ask if the builders C F were or models and financial scenario, it would spend a lot of time creating a plan at first, and then researching all the sheets that have access to, try to get a good understanding of and the way the language. OVS four point six is a great model, but it was like pretty slow on the thinking tokens are also pretty expensive, and so we took a step back and decided to try train a retrieval model, kind of a financial question answering model that would help. Still, keeping these frontier models or as orchestrators would then be handed off to be this much faster model that would do financial question answering or that planning engine.

So we partnered with the company Prime Insights to post train a Quan 3.5, 35 billion model, and we actually got above Bitcoin six, which was the frontier back then, exact pass accuracy, while also being able to serve at a high crew level of latency. So much faster, but just a smart model that could then be used in tandem with the really smart frontier orchestrator, and so this was like a very successful example of post-training that we had actually sent to Prague.

### 00:05:09 — KV Cache Compression with Offline Cartridges

As part of our grand labs effort, the second big thing that we are actually exploring up to this day is KB cache tricks, and particularly cartridges are really interesting family of techniques where you're able to compress a lot of context, up to 20 to 30 times more context, into the KB cache offline and serve it for your agent.

And so, if you compare it to the Ramp sheets example, for example, there's a lot of tasks that you know are going to happen at some point, right? Like London close. A month finishes, and on the first of the next month, a financial professional will go and try to reconcile close their books. You know, kind of the ledger, the agent report, and the documents that they will need to be retrieving, and so we could prepare them out of context, but the agent will still need to intelligently retrieve and create a good picture and understanding of them. With cartridges, we're able to compress all that work and build one overnight before they financial professional starts to work on the first level, and once they open up the agent, it knows exactly what it needs to do because it has all of the context already open. Cartridges are also a much lower lift in post training because the way that they do self plays is a lot more generalizable.

The caveat with stuff like this is that compared to post-training, this is something that the labs might ship at some points in their APIs, therefore, into continuous learning. And even if they were to do it in the API, we would actually be happy because we are developing a lot of this tribal knowledge inside the company, and just learning how best to apply these techniques. So even if those techniques yard, we can just hit the ground running on day one, knowing how to use them.

### 00:07:03 — Agentic MapReduce & 10,000-Agent Security Swarms

And finally, the third example of applied research that we are sending to Prague is our work on agentic macrodeuce and kind of agentic swarms. So more concretely, we've published an article on the Ramp Labs blog on how we used 10,000 parallel agents to pentest all of Ramp. So at Ramp we have a cloud agent called Ramp Inspect, which helps out with setting up all the infrastructure and plumbing for something as ambitious as this, and we were able to spin up ten thousand parallel agents, and then kind of map this workout to try to find any vulnerabilities, and then also authentically reduce on the tickets that we would create, so deduplicate them with OMS, and I tried to reproduce them adversarially with labs that tried to make sure that vulnerabilities are real and important.

At the end of all of this, we have actually found seven high vulnerable high severity vulnerabilities that we all have. Interestingly, one of the vulnerability that was described in that article is a malicious script injection that you could send over via email, and no single component of that stack was unsafe, and the kind of swarm have to patch together multiple components and understanding of multiple components and to in order to be able to figure this out. And the other nice thing with this is that this is all running automatic automatically. You don't need to spend anyone's time. It's just you start it, and the only thing that fail, fail passes that get filtered out is the cost of the tokens.

The other thing that's interesting outside of just building Apple of the infrastructure to support these swarms is that we do research into how to best use models as part of these swarms. One of the interesting insights from that same article that we published is that you can actually use open weight models that are up to five times cheaper compared to the frontier reasoning, and because you're set, setting it up as a swarm, the detection rate is not five times lower, so you can kind of spend more on these cheaper tokens and have almost a good transaction rate.

### 00:09:22 — Token Spend Management & Latency Routing Products

If you follow through all of these examples, you kind of notice a pattern: of all of them, is accounts at saving on time and saving on money, so reducing latencies, which is time, and then reducing on token costs, which is money. That's actually Ramp's slogan: "Saving our customers' money." And so I'd like to point to two products that we actually offer from Ramp that have been influenced by Ramp's research. The first one is token spend management, next to a bunch of your API keys and is able to give you a really good picture of how LLMs being used inside of your company, not only who can spend on a API key basis or a user basis, but digging deeper, accounting categories, and even things like tax credit that you can get by analyzing the spend. It also goes deeper, and we created a taxonomy that contextually analyzes and semantically analyzes the LLM usage, so you can actually understand how LLMs are being used outside of just attributing it to a team or a person inside of your company.

And then the second one is Ramp Powder, which also leans into improving the latency of your agent, where we have a bunch of wrapping strategies that we work with Ramp Labs to develop — things like NVIDIA Switchyard, things like smart flex offloading of work, both improve latency and cost per tokens that you spend. And there's a bunch of different strategies already available for the routing, and even more coming out later. So, if you're interested in any of these two products, you can take a photo of the URLs or scan the QR codes there. Just a second.

### 00:11:16 — Cross-Model Transfer, Self-Improving Monitors & Semantic Tagging

And then I also invite you to check out our Ramp Labs blog, where we publish a bunch of really interesting articles that I haven't had a chance to cover as part of this presentation. Notably, one of the really interesting ones is Portal, where we figured out a way of transferring learnings from one post trained to another, so you could do something like Aurora post train on one model, so a Bitcoin 3.5 that I was describing, but then transfer it to newer versions of or even across different panels, you're posturing this latent event can be projected onto different models, and that's really amortizing the costs that you have to spend on post-training.

More blog posts on agentic approaches, so not only the pen testing stuff that we did, but things like realizing and creating economies of LLM usage, which is stuff that has gone into the tokens and product. Things like self-improving monitoring, where we use no less than automatically create monitors with Datadog on a lot of our product surfaces, and then, as the words come in, improve those monitors automatically without a person in the loop to try to basically create super robust and resilient software. And finally, semantic tagging, which is this interesting orient, creating this egnetic map produced over a bunch of user sessions, where we can annotate and create exonomies that are open-ended, so not knowing ahead of time, which what are the clusters of om usage and trying to create a taxonomy that can then be reconciled against the spend inside the companies.

So, if you're interested in this type of research, X.com/turinglabs, where you can go and check out more of our research. And is my Twitter. Do you have any other questions or want to talk about some use case as part of your applied research? And that's it. Thank you.
