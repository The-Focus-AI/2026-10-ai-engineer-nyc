---
title: "The AI Bill Is Too Damn High – Tokenomics 101"
speakers: "Eugene Cheah (Featherless)"
duration: "55:04"
source: transcript.md
video: "https://www.youtube.com/watch?v=Ti-BmGU1_mQ"
themes: [token-economics-and-multi-model-routing, bootstrapping-domain-evals-without-public-benchmarks, the-diffusion-gap]
kind: talk-story
status: draft
---

# You are paying frontier prices for work that doesn't need them

Eugene Cheah's workshop is a method for cutting an AI bill in four moves, in order: measure it, right-size it, buy it well, check your processes. The claim underneath is that most of the money goes on the best model, at the fastest speed, for jobs that need neither, and that some of the rest buys output nobody uses.

Cheah runs an inference company and says so at the start. The examples are his customers', as he reports them. Model names and several figures here are taken from his slides, because the recording garbles them.

## What the floor looks like: two trillion tokens a day at three cents a million

Cheah opens with what his largest customer does. They serve about two trillion tokens a day on 512 AMD GPUs, running a private model he puts in the Opus 4.8 class, for roughly $60,000 a day (00:00:00). The slide gives the unit price: $0.03 per million tokens. He is clear that this is not a price anyone can buy off the public cloud. It comes from a setup built for that volume (00:00:00).

Two disclaimers follow. He sells inference, so the examples come from his own deployments, though he says the principles apply to any provider (00:00:00). And none of it is worth doing below about $10,000 a month of spend. Under that, a team is better off finding a strong use case than trimming the bill (00:00:00).

**Key points**

- One customer runs two trillion tokens a day for about $60K.
- That price depends on dedicated hardware and very high volume.
- Below roughly $10K a month, find use cases instead of optimizing.

> “That's what we mean by scale”
> — 00:00:00

**Visual:** slide `experience/scale.jpg`, `experience/who-this-is-for.jpg`, `experience/four-moves.jpg` (two trillion tokens a day; who the workshop is not for; the four moves)

## Measure first: one shared key tells you nothing

He asks the room who knows their total token spend, and about half the hands go up. Asked who can break it down by department, about half of those go down, and it keeps falling at team and use-case level (00:00:00). Thirty to forty percent of the customers who come to him start with a single API key shared by the whole organization (00:00:00).

The fix is not specific to any vendor: issue separate keys by department and by major use case (00:00:00). His slide lists four questions a bill should answer. Which team and workload spent it? Was a person waiting for it? What does a week of usage look like? Did the output get used? Each one feeds a later move. He says that if you are not measuring you can ignore the rest of the workshop, because measuring is where the biggest return is (00:08:48).

**Key points**

- Half the room knew total spend; far fewer knew it by team.
- Split keys by department and use case before anything else.
- Every later saving depends on knowing who spent what, and why.

> “A single shared key that every one in the organisation used”
> — 00:00:00

**Visual:** slide `experience/four-questions.jpg` (four questions your bill should answer)

## Why the bill jumped: five developers, $150K a month

AI workloads come in two kinds with opposite economics. Agentic work is long-running and multi-turn, with context that grows every step; coding agents are the main example. Process automation is short, predefined and isolated, and it is a volume game: call centers, email routing, document processing (00:00:00). One telco he works with peaks at ten million messages a minute, filtered for a child-safety feature, and New Year is the worst day (00:00:00).

The explosion most organizations hit first is on the agentic side. One team he supports had five developers running about eight agents continuously, on Opus through the API. That came to 116 billion tokens and about $150,000 a month (00:00:00). They moved to a single dedicated node running an open model and, by his account, saw no disruption (00:00:00). The slide puts the new cost under $10,000 a month. Knowing the workload also let them move background agents to run overnight, when the hardware was otherwise idle (00:00:00).

**Key points**

- Agentic and process workloads need opposite treatment.
- Agents that run for hours are where usage explodes.
- One five-person team went from about $150K to under $10K a month.

> “they were essentially spending like one hundred fifty k a month”
> — 00:00:00

**Visual:** slide `experience/more-agents.jpg`, `experience/two-tracks.jpg`, `experience/volume-game.jpg` (the five-developer team's numbers; agentic beside process automation; process automation as a volume game)

## Agents: keep the best model for judgment, and make the cheap one fast

His slide on where an agent's tokens go is the basis for this section. Output is under 1% of the tokens in a coding agent's month; over 80% of the spend is context, re-read at every step (00:08:48). So the price of output matters less than caching and what the worker costs.

The common pattern is to split the work. The best model plans, cheaper and faster models do the implementation, and the best model reviews (00:08:48). Implementation is where the tokens go, in the loop of editing, testing and checking, and he says open models are capable of it (00:08:48).

Getting people to use the cheaper model is the hard part. Where both models ran at the same speed and budgets were loose, nobody switched (00:08:48); the slide says 98% of traffic stayed on the best model. With a faster worker, 87% moved by choice. People feel latency, not the bill. His rule is to make the cheaper model the faster one (00:08:48). A tight budget does the opposite of what you want: the smart model is burned through in a day and then might as well not exist (00:08:48).

Two more controls. Use separate keys for agents a person is watching and for background jobs such as CI, so each can be bought at a different speed (00:08:48). And give departments labels such as "smart" and "fast" instead of model names, so the model behind a label can be changed in one place (00:18:04). Without that, he has found teams still running Llama 2 because nobody changed the setting (00:18:04).

**Key points**

- An agent's cost is mostly context it re-reads, not what it writes.
- Best model plans and reviews; fast, cheaper workers do the doing.
- People switch models for speed, never to save the company money.

> “nobody really switches their model to save the company”
> — 00:08:48

**Visual:** slide `experience/where-tokens-go.jpg`, `experience/plan-work-review.jpg`, `experience/nobody-switches.jpg`, `experience/two-key-sets.jpg`, `experience/labels.jpg` (where the tokens go; plan, work, review; nobody switches; two sets of keys; labels, not names)

## Process work: the smallest model that passes your test

His starting image is Maslow's hammer: AI is the new hammer and gets applied to everything, including jobs that need a smaller one or none (00:08:48). The slide sorts tasks into those that need the big model, those a smaller one handles, and those that are not AI problems at all.

Open models have closed much of the gap this year. He has seen them match or beat closed models on specialized benchmarks, including a model about ten times smaller reaching near-frontier quality on financial tasks (00:08:48). His field-guide slide names an open model per job and carries its own warning that it will be out of date within a month.

How do you know a smaller model is good enough? He calls it the wrong question. Write the tests and examples, then search for the cheapest model that passes most of them (00:18:04). One telco went from $250,000 to $7,600 a month this way (00:18:04).

Two further steps follow when volume justifies them. Much of this traffic is classification: the answer is a choice from a list. Classifier models that produce no text are commonly ten times cheaper (00:08:48, 00:18:04). And a model can be fine-tuned for the domain, as AT&T did in going from frontier-class models down to 27B and 7B ones (00:18:04). To bootstrap one, run the expensive model at small scale, collect its outputs as a dataset, fine-tune a small model, and shift traffic over. He adds that some labs' terms forbid this, so check (00:18:04). Keep a slice of traffic on the best model as a shadow, to keep building the dataset as models improve (00:27:04).

In the Q&A he puts evals ahead of tuning method. His own prompt-tuned model beat most fine-tuned ones of the same size on a public benchmark (00:45:24).

**Key points**

- Write the test first, then search for the cheapest model that passes.
- A lot of "AI work" is classification, which is far cheaper.
- Distil from a frontier model when volume is high and the task stays put.

> “it's also not that hard to just download ten models from Hugging Face and just try”
> — 00:18:04

**Visual:** slide `experience/hammer.jpg`, `experience/field-guide.jpg`, `experience/three-rungs.jpg`, `experience/multiple-choice.jpg`, `experience/telco-models.jpg`, `experience/distilled.jpg` (Maslow's hammer; open models by what they're good at; three rungs; classification; AT&T's telco models; distilling a specialized model)

## Buy it well: twice the speed costs three times as much

Customers are surprised that inference does not scale linearly. There is a steep trade between how fast one request runs and what it costs (00:27:04). His rule of thumb is that every doubling of speed triples the cost (00:27:04).

The same server shows it. One request alone runs fast. Sixteen in parallel each run at about half that speed, but the node's total output rises about tenfold, which he puts at nine to ten times lower cost per token (00:27:04). The slide's figures are 112 tokens a second alone, 64 each when shared, and about 9x lower cost.

So pay for speed only where a person is waiting, a developer or a customer. Most customers pick between 20 and 60 tokens a second, and a small step down can halve the cost with little effect on the user (00:27:04). Background jobs should never run at the fast tier (00:27:04).

Capacity follows the shape of usage. Most traffic is bursty over a base that never goes to zero. Dedicated capacity is the biggest saving available if you know your base load and use it fully; spikes can spill to on-demand (00:27:04).

A Q&A point belongs here. Routing each turn to a different model wrecks the cache unless it is held to two or three models, so he prefers routing by task (00:45:24).

**Key points**

- Twice the speed is about three times the cost.
- Sharing a node halves speed per request and cuts cost about ninefold.
- Buy dedicated capacity for the base load; leave spikes on demand.

> “For every two x of speed, it's three x of cost”
> — 00:27:04

**Visual:** slide `experience/share-a-node.jpg`, `experience/speed-where-waiting.jpg`, `experience/base-and-burst.jpg`, `experience/usage-shapes.jpg` (one agent on a node beside sixteen; speed only where a person waits; base load and bursts; four usage shapes)

## Tokens are not work done

The last move has nothing to do with inference. Organizations are asking why token spend is up ten or a hundred times without results to match, and he cites reports of productivity gains of six or seven percent (00:27:04). His slide's summary: people get faster, organizations don't. Individuals produce more, but review, CI and trust do not speed up with them (00:27:04, 00:36:10).

His example is the slop grenade. Someone has an agent generate a very large change and hands it over. The reviewer cannot process that much code, so they have their own agent work out what matters and rebuild it, discarding the first agent's work. The task has been paid for twice (00:36:10). The same happens with decks and reports generated in one shot and passed around for others to check (00:36:10). His own slides were designed by agents, and he went through every page about thirty times (00:36:10).

His rules are about ownership. Whoever hands something over owns it; a problem in the output is theirs, not the agent's (00:36:10). Measure outcomes instead of usage: tokens times price, divided by outcomes someone used (00:36:10). He flags the measure as flawed, since teams and tasks differ, and falls back on the first move: spend per team, set beside what each team gets done (00:36:10). The slide adds a third rule, pass the smaller thing.

He calls himself an optimist about all of this. Organizations are still working out what to use the hammer for (00:27:04, 00:36:10).

**Key points**

- More output moves the cost to whoever has to review it.
- An unreviewed AI-generated change gets rebuilt, and paid for twice.
- Own what you hand over; count outcomes someone used, not tokens.

> “tokens are not work done”
> — 00:36:10

**Visual:** slide `experience/slop-grenade.jpg`, `experience/people-faster.jpg`, `experience/tokens-not-work.jpg`, `experience/beyond-code.jpg`, `experience/three-rules.jpg`, `experience/cost-per-outcome.jpg`, `experience/six-questions.jpg` (how one task gets paid for twice; people get faster, organizations don't; tokens are not work done; decks and reviews; three rules; cost per accepted outcome; six questions for Monday)
