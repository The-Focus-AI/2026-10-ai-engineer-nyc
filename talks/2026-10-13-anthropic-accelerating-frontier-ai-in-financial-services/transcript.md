---
title: "Anthropic: Accelerating frontier AI in Financial Services."
speakers:
  - name: Belinda Neal
    affiliation: Anthropic
  - name: Keon Shahab
    affiliation: Anthropic
room: "Simons Room (Metropolitan East)"
starts_at: "2026-10-13T09:18:00-04:00"
ends_at: "2026-10-13T09:36:00-04:00"
format: "keynote"
recording: "2026-10-13_0919_Anthropic"
duration: "18m 46s"
source: "qwen3-asr-1.7b"
---

# Anthropic: Accelerating frontier AI in Financial Services.

> Transcribed by qwen3-asr-1.7b with a schedule prompt. Possible prompt artifacts, names heard more often here than in the unprompted Voice Memos transcript (Qwen vs Voice Memos): Belinda Neal (1 vs 0), Anthropic (7 vs 1), Keon Shahab (1 vs 0). Check them against the audio before quoting.

### 00:00:11 — Speaker Introductions & Three Frontiers in Finance

I'm Belinda. This is Keon. We're from Anthropic. We work with financial services firms. As Keon gets set up here, start with a little bit of background. My name is Belinda Neal, and I'm the managing director of Financial Services at Anthropic. Previously, you're joining Anthropic this year, I worked at Goldman Sachs for 19 years across engineering, global offices, in every research. My role at Anthropic sits at the confluence of our industry, our product, our research and our global market teams, really in accelerating the adoption of AI within financial services here.

Good morning, everyone. Thanks for being here. My name is Keon Shahab. I'm an applied AI architect at Anthropic. Prior to Anthropic, I spent five years at DataBricks helping financial services companies modernize their data and AI infrastructure. So we're excited to speak to you this morning, and our talk is going to cover three ideas. Firstly, the frontier of intelligence: how is this room taking the frontier models and applying it in ways that create alpha, or edge, or inferfa? The second is the frontier of adoption. How are you scaling what you built based on the foundation that you to many? And then last, how are we applying it to financial services? We're going to bring an example in here about how we'll be innovating the wealth industry, and that paradigm compounds potentially a lot of areas of consciousness as well.

### 00:01:32 — The Frontier of Intelligence & Model Thresholds

So let's get started and talk about the frontier of intelligence. So every so often, the model crosses a threshold, and when it does, the way of working changes. We first saw this encoding last year, Focus 4.5, AI card. Many of you in the room are using these tools, and we want to order complete and current to managing fleets of agents, where you're really driving, accelerating a multiple effect, higher doing everything.

We also saw this threshold cross this year in cyber with Claude Metals preview, and many of you are also spending time on the side of programs in your firms. What's next? Finance. We've started now in finance with early agents and bring it forward into the products and services that you use day to day. One example here, the Citadel told us at our recent event in May, that their investment professionals started to use four per cell, and it gives them a step change function in how they can test, build, and trust their work. We're really excited for within the tools and the use cases that this framework supports.

Intelligence is ahead of adoption. What a model can do on its own is doubling every four months. PwC published early this year that the capabilities of AI are going to three quarters of companies, sorry, three quarters of the economic data available comes from companies. This is what we call diffusion now. If you're not building close enough to the curve, there's opportunity for you to take the frontier and be able to apply it in your workflows.

We work with firms across financial services, across our model family, most of which hopefully is room for development. We have haiku for speed and volume, Sonnet for everyday work, Opus as the daily driver, financial services complex tasks and urgent periods, and fable, our frontier model that can effectively be used for the hardest work in your firms. One example here from the Millennium on our most recent blog was a PM used fable to find a piece of code that had a bug, and it was unexplained for years. They were able to find it. We're starting to see our models get used in this industry in new and creative ways, and we believe the frontier of intelligence is just getting started.

Every model release gets smarter, cheaper, and safer. So it's really important to take a minute to call out how the model frontiers continue to develop here. Firstly, the intelligence is going up. Now a model can work for 16 plus hours on its own. This is up from just minutes in 2023. In terms of cost per task, it's going down. The most recent Opus five point five, Opus 5.5 model was 40% more cost efficient than Opus 5. You can also see those impact metrics or haiku, sonnet, fable.

And lastly, safety. This is something we care a lot about at Anthropic. In the most recent model of Fable Five Point One, only one percent of injection attacks was successful. This is relative to other frontier models in the region of nine to fifty-three percent. So we're really investing in safety, alongside capability and autonomy.

And the banks know this. The law's most recent evident AI twenty six report that came out last week showed us that banks are 26% ahead of their AI maturity scores. We're really investing in state in applying this technology to our industry. A few use cases to call out from this report, which are publicly citeable use cases that have been reported, is most areas like fraud. One bank found that with auto loans, they were able to reduce 120 million dollars. In another area, in pursuing research, a draft of a report was able to be generated in 15 minutes relative to 45 minutes. And you can see other use cases here, and the whole diagnostic industry itself talk about the value of AI and the impact we're generating on our business.

So where are we? In 2023, we built chatbots. Everyone was asking a question and going backwards and forwards with the model. In 2024, we brought pilots to firms, and we started to get more knowledge bases and data into these AI systems. From 2025 to now, we're now building agents, and in the worst case, in this room, we're building them hand by hand, one by one. And our opportunity here is scale — is not the model, our opportunity here is scale, is building the foundation for agents that can go one to many. So the next part of the talk, we wanted to spend time focusing on how you build the agent foundation that will allow you to scale the frontier of evolution. So, over two years.

### 00:06:12 — From Experimentation to the Five-Layer Agent Framework

For this portion of the talk, we want to talk a little bit about how we can go from that experimentation phase towards productionizing and scaling agents. But first, some observations that we've seen across the industry. A year ago, we could think about this as the Europe exploration, where engineers were working on a handful of use cases. They were in POC and pilot mode, and they took their learnings and transitioned that this year, where we're seeing this be the age of production. We've seen these handful of agents go to production, a lot of them have been built by hand. What I think will happen next year is we'll go into the age of scale, over how many agents built on one solidified foundation.

And as Belinda just mentioned, the models are now the easiest part of the equation. Here, we know that the models can handle high-quality tasks, and we're confident about that. But what we want to talk about here is building this five-layer framework for scaling and productionizing your agents.

Starting from the bottom, we first want to look at what the agent can do — we can give it context for our business use cases via connectors, so that it can reach our systems and data. Then we want to give it context for our actual business rules and processes, business rules. Once that's done, we want to think about building the trust layer for the agents. We can think about that in three general steps — who the agent is acting as, with an identity and permissions layer, how we can sandbox and determine the approval layer of the agent that someone is signing off before acts, and lastly, how we know the agent will still work once we adjust any variables over time. So let's look at each of these five.

### 00:07:57 — Context Layers: MCP Connectors & Living Skills

All right. So, if you started building agents already, you may think of giving those agents access to your underlying systems and data manually wiring them by hand to a handful of different source systems, and that could work for fifty-five agents and five systems. Then you'll have twenty-five systems to manage, maintain and manage, but as you think about scaling up your agents into new specialized, various tasks, you'll want to have those agents work on one secure connectivity layer, which is MCP. That'll make it a lot easier for you to build at scale with one repeatable framework.

Next, let's say now we have the agent have context to our underlying business data systems. Now we want to give it more context into our actual business rules and processes, and that's done through skills. And this is where the SMEs that really do the work and understand the process and the work come into the picture.

And from here on, we're going to look at a agent use case for a trade break investigation agent, and we're gonna pull this across for the for the next steps. In this case, a trade agent is meant to look at two records of the same tree that don't match, and it's here. You can see steps one through three, a little bit of a simplified version, but this is the business context that an SME provides, and we think about skills as living, breathing, versioned code, essentially, even though they're just plain text. They're meant to be dynamic. They're meant to be updated frequently.

### 00:09:35 — Trust Layers: Identity, Sandboxed Approvals & Evals

All right. So now we have our context layer for the agent. We have the agent having access to our source systems and data. We have the agent that understands how to go from a generalized model to a specialized agent with skills. Now we want to talk about building the trust layer with that agent, and first, let's start with the identity and permissions layer. So here you can see the identity of the agent, we're going to assign it. It's going to be the trade break investigator. We're going to give it a role with permissions called ops analyst.

You can see here once that agent needs to go and reach our source systems, our order data, and our market data, we don't have permission to read. If it tries to go through our CRM database, it'll be denied, and we will do that on purpose, so that it won't overreach for sources of data that it shouldn't have access to. And lastly, we don't necessarily want this agent perform on behalf of us. We want it to just propose new amendments to our owner's data, not actually make those amendments, and that's the part we'll look at on the next slide.

So this is kind of the layer of who signs off before the agent acts, right? Many of you have heard the term sandbox. We can use that terminology here as well, for putting an approval layer around the agent, so that you can see here the four-step process, the agent will actually go and propose a booking amendment. It'll actually try to perceived through the process with the context that has and source data, source systems, and data that has, but then I look for a human, an SME, someone in the loop in the process to approve, right? Once they approve, then that amendment will be made, and the change will be applied. Guardrails, deterministic guardrails, called hooks around your agent, so that it's never overreaching beyond what you'd like it to do within its confines. All right. So now we have a full agent.

Let's say it's in production. It's working great, and let's say that we want to make an adjustment to this agent. Let's say that a new model is shifted, or we want to make an adjustment to the business context layer with the skills. How do we actually know if these adjustments are improving the agent, or if they're causing our regression? So that's our evals layer. This is where your SMEs, your business users who are in the loop who understand the process, help determine a set of test cases to test the agent against with a benchmark, our baseline, so that you once you apply to any variable, you'll be able to determine whether that variable change actually improved the behavior of the agent, or if it caused it to regress, as we'll see here in some of the examples.

### 00:12:25 — Scaling Across Doors & the Business-Engineering Loop

All right. So hopefully you've seen, by building ones with a layer with a foundational layer that you trust, you can work at that speed to deploy many agents at scale. For us, financial services and regulated industries doesn't mean slow. It means that we're seeing a lot of innovation from the financial sector, and we're seeing it go hand in hand with security and safety as well, and those three layers that we just walked through—who the agent is acting as, who signs off, and how you still know that agent works—are the key components of building a safe and secure AI framework.

And once you have this framework available, you can use it to apply to any new agent you want to build or any special use case. So you can see at the top, you'll have your foundation. Then at the bottom, you will see where you can actually bring in more specialized data along the way, and as you continue to scale, that specialty is worked in combination with the business and engineering to make sure that the proper business rules and context are being integrated into the agent workflow.

And you might be wondering, we haven't mentioned anything like Claude Cove yet. Well, everything that we've talked about so far has, let's say four different doors that you can access it from. So a business person can access it from a coworker, an engineer can access it from Cloud Code, and four, you can take this to the next the next step, and give the agent more work to do in your own UI environment via things like managed agents or agent SDK.

Now, so far we've talked about building a secure, trustable agent foundation framework. Now let's talk a little bit about the operating model. Some observations that we've seen, especially in financial services, is that the business is now becoming closer to engineering, and the way that we're observing this is that the business will directly work the agent that engineering has built. They'll have direct capabilities to correct that agent or amend it, propose adjustments, and that's where engineering is in the loop as well. Once you see the list of post adjustments, you can solidify that as a skill change after you have reviewed and tested all that within your VEL framework, and then anything new that you ship goes right back to the business, and they'll go through the same loop again to continuously improve the overall agent and the process.

Right. So far, we've talked about building the agent framework in a way that you can build once for scale. We talk about how we can turn a generalized highly intelligent model into a specialized agent. Now I want to hand it off to Belinda to talk a little bit more about what we're seeing in the industry by building some of the foundations ourselves for the next step here, which is called for financial advisors.

### 00:15:33 — Industry Coordination: Claude for Financial Advisors

Thank you. So what you're just saying is us building a foundation once and for all. Now I want to talk about how we could take that same approach. This foundation we built empowers financial advisors, and whilst you might not all the rooms sit in the world for the advisor space, I want you to take this as a pattern and opportunities for other things out, how we can actually coordinate at an industry level.

So in September we launched all the financial advisors. We orchestrated across staff of an advisor. This was built on the foundation that advisors only spend approximately 20% of their time with clients. We wanted to find a way where advisors could spend more time with clients and more time growing their franchise.

So what did we do? We went through the Leibniz Foundation and found ways to scale. Layer one, we've brought connectors in — the industry system, the journalistic numbers, and the scaled system that advises trust—we brought it to you, sister. Lane two, we built skills. We built a plugin that is available on GitHub that builds eight skills and workflows that an advisor can take out of the box, use today, and implement tomorrow. Layer four approval, the advisor proves everything that comes out of Claude. Nothing is saved or sent without the advisor, and that trust principle holds here too. And so you can see here on the diagram on the left, CRM market data, all the tools and foundations and advisor needs. So let's go through layer one, the connectors.

We brought in twenty-five platforms across custody, portfolio planning, data, and CRM, things such as Schwab, PayPal, Salesforce, and more. And there's more connectors you can find on the platform. This is where the industry builds once, the advisor can integrate once, and this is what one path looks like.

Layer two skills. These are the workflows we built for the advisor that they can start with and adjust and amend to their own. For example, premium prep allows an advisor to bring a full family plan into one brief across multiple systems. The follow-up allows the advisor to bring those meeting notes, enter them into the CRM system and actually follow through with the existing systems and tools. Nothing goes out until the advisor approves it, and this skill foundation is a baseline of which we imagine advisors will start to innovate and bring forward into more and more of their workflows, allowed them to drive impact in their business.

So, in closing, with twenty-eight seconds on the clock, three questions to take your phone today. The first one is the workflow. How are you applying the frontier intelligence to your phone? How are you gaining edge and alpha from the frontier models to today? The second is the foundation. Do you all have a foundation that you trust for building and scaling agents for the future, as things become more and more specialized? One connector. How are you actually building the foundations that others can use? Are you building connectors and skills where users feel firm for the industry? With that, thank you so much for having us. Enjoy the rest of the conference.
