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
source: "voice-memos-transcript"
---

# Anthropic: Accelerating frontier AI in Financial Services.

### 00:00:00 — Introduction: Frontier AI in Financial Services

morning. I'm Belinda. This is Keon. I'm working from Metropic. We work with Canangial serviceservices first. As Keogh can sit up here, we'll stop with a little bit of background. My name's Olivia New. and I'm the managing director of Financial Service and Centropy. Previously, you're joining us for because year, I work with Golden Saxon 19, is Crossing Engineering, Global Office, and everybody research.

Why will it, Adam Torme, sits in influence about industry, a product, a research, and a very multitapes, really in accelerating the adoption of AI and financial services. Yeah. Good morning, everyone. Thanks for being here. My name is Keon Shahan. I'm an applied AI architect. I am anthropic. prior tech topic. I spent 5 years at data breaks, helping financial services companies, modernize their data and AI and architecture.

So we're excited to speak to you this morning, and our talk is going to cover 3 ideas. Firstly, the frontier of intelligence. How is this room taking the frontier models and applying it in ways that create our hub or edge in your phone? The 2nd is the function of adoption. How do you scaling what you build based on the foundation of a few to many?

And then last, how we applying it to financial services, we're going to bring an example here about how we're being innovating the world industry, the world intentionalizes. And that paramount can panels, potentially got all the areas of them, so it's slow. Sorry, let's get started and talk about country of intelligence. So every settlement, all crosses the threshold. and then it does, the way of working changes.

When you first saw this encoding last June, over this 4 x 5, I called her. Many of you in the room, they're using these walls, and you want, order your plate and curry, to manage a place of agents, where you're really driving, accelerating, a multiple tech, how you're doing verdict. We also saw this threshold across this year. And so I walked with full of my most preview.

and many of you also spending time on the site of programs in your first. What's best? Finest. We've started now to point out the early agents that bring Paul into the piles and services that you say today. One example here, the citizen told us, at our breaking event event, that there are invested professionals, starting to use school for itself, and it gives them a step change option, and now they can test, build, and stereo.

We're really tired with the potential involved within the tools and these cases. There's a shot. Intelligence is kind of doggy. Where all the doors are is stopping every 12 months. Do you understand published early this year, that the capabilities of AI are going to train fors of companies, sorry, three fors of the economic days, they are, directors to the economies. This is what we call this you should have.

If you're not building close enough to the curve, there's opportunity for you to take the frontier and be able to apply it in your workplace. We work with firms across financial services across our model family, most of which roofly is rooms. We have hiker, for speed and volume, sold it for every day. Focus as a daily dryer, but the animal services, one place tiles in the Jersey Code.

And fable, up frontier model, that can effectively be used for the hogs to wipe in your clothes. One example here from a millennium, on our most recent model blog, was a PM used fable to find a piece of code that had above, and it was unexplained in 5 years. Maybe people were able to find it. We're starting to see our models get used to this industry in new and creative ways, and we believe the frontier intelligence is just getting started.

Every one release, you get a spot up, cheaper, and safe up. So it's really important to take a minute to pull out how the mole frontiers continue to develop here. Mostly, the intelligence is going on. Now, a model can work for 16 plus hours on its own. This is up from just minutes in 2023. In terms of cost, it's going down. The most recently, it was 5.5, overs 5.5 model, was 40% more cost efficient than overs five.

You can also see those impact metros for a high hypersonic fable. and mostly safety. This is something we care a lot about on the tropic. In the most recent model of farm, they will buy my home, only one% property injection tax was successful. This is relative to other frontier models in the range of non to 53%. So we really invested in safety almost capability of color.

And the next service, the law's most recent evident AI 2026 report that came out whilst we showed off, the banks are 26% ahead of the AI maturity scores. We're really investing in today in applying technology to our industry. A few use cases to pull out from this report, which are publicly cited all these cases that are being reported. It's mostly not eras like draw.

One bank found, but with border lines, they were able to reduce $120 million, 10 to 40, in 12 months. In another area, interest in research, a drop to report was able to be generated in 15 minutes relative to 45 minutes. And you can see other new spaces here, and the whole day, most industries itself, both about the value of AI and the crack for generating on that business.

So where are we? In 2023, we build chapels. Everyone was Austin in question and going backwards and forwards with the model. In 2024, we brought pilots to firms and we started to get more knowledge bases and data into these AI systems. From 2025 to now, we're now building agents. And in the most case, in this world, we're going to, hand by hand, one by one, and an opportunity here is stable, is not the local opportunity here to stale, is doing the foundation of agents that can go from one to many.

So the next part of the talk, we want to just send time focus on how you do the Asian foundation that will allow you to stay on the frontier. Sorry, initiating. Amazing.

### 00:06:06 — Enterprise Deployment Patterns & Governance

They put up. So, when as you've just said, there's no hard time now to start experimenting the building agents. For this portion of the talk, we want to talk a little bit about how you can go from that experimentation phase towards productionizing and scaling agents, or just the computer. A personal observations that we've seen across the industry. A year ago, we couldn't think about this as the Europe expiration, where engineers were working on a handful of use cases, they were in POC and pilot owned, and they took their learnings and transition died this year, where we're seeing this be the age of production.

We've seen these handful of agents go to production. A lot of them have been built by hand. What I think will happen next year is we'll go into the age of scale. But of many agents, they'll become one, solidified foundation. And as Belinda just mentioned, the models are now the easiest part of the inrovation here. We know that the models can handle high quality tasks, but we're confident about that.

What people want to talk about here is building this 5 layer framework for scaling productionizer agents. Starting from the bottom, we 1st want to look at what the agent can do. So we can give it context for business use cases via connectors so that it can reach our systems and data. Then we want to give the context for our actual business rules and processes, view deals.

Once that's done, we want to think about the trust layer for the agents. We can think about that in 3 general steps. Who the agent is acting as with an identity and permission slayer? How can they send us and determine the approval layer of the agent? Someone is signing off for X. And lastly, how we know the agent will still work, once we adjust any variables over time.

So that's okay. Each of these. Alright. So if you started building agents already, you may think of giving those agents access to your underlying systems and data, manually wiring them by hand, do a handful of different source systems. And that can work for 5 agents, 5 systems, then you'll have 25 systems to maintain and manage. But as you think about scaling up your agents into new specialized various tasks, you will want to have those agents work off of one secure connectivity level layer, which is MCB.

That'll make it a lot easier for me to build a scale with one more cable framework. Next, let's say now we have the agent have context or underlying business data. systems. Now we want to give it more complex into our actual business rules and processes. And that's done through skills. And this is where the SMEs not really do the work and understand the process and the work coming to the picture.

And from here on, we're going to look at a agent use case for a trade break investigation agent, and we're going to follow us across for the next steps. In this case, a train group agent is meant to look at 2 records of the same tree that don't match. And it's here you can see steps one through three, a little bit of a simplified version, but this is the business context that an SME provides.

And we think about skills as living, breathing, version, code, essentially, even though they're just plain text. They're meant to be dynamic, they're meant to be updated frequently. All right, so now we have our context layer for the agent. We have the agent having access to our source systems and data. We have the agent that understands how to go from a generalized model to a specialized agent with skills.

Now people want to talk about building the trust layer, but that agent. And first, let's start with the identity of permission player. So here you can see the identity of the agent. We're going to assign it is going to be the trade rate investigator. We gonna give it a role with permission. It's called Ops Access. And you can see here once that agent needs to go and reach our source systems, our order data, our market data, we don't have permission to read.

If it tries to go RCRM data, it'll need denied. It we'll do that on purpose so they won't overreach for sources of data that it should have access to. And lastly, we don't necessarily want this agent to perform on behalf of us. We wanted to just repose new amendments to our owners data, not actually make those amendments. And that's where I would look at it on the next slide, how we can keep the human group here.

All right. So this is kind of the layer of who signs off before the agent acts, right? Many of you have heard the term sentbox. We can use that terminology here as well for putting an approval layer around the agent. So that you can see here in the 4 step process, the agent will actually go and propose a booking amendment. It'll actually try to proceed through the process with the context that has and source the source systems and data that has access to it.

But then for a human, an SME, someone in Duluth in the process to approve, right? Once they prove, then that man will be made and the change will be applied. This is a way where you can also put guardrails, deterministic guardrails, called pokes, around our agent, so that it's never overreaching beyond what you would like it to do within its confines. All right.

So now we have a full agent. Let's say a 10 production is working great. And let's say that we want to make an adjustment to this agent. Let's say that a new model is shed or you want to make an adjustment to the business context on your, with the skills. How would we actually know if these adjustments are improving the agent or if they're causing our regression?

So that's our eight dollars later. This is where your SMEs, your business users, who are in the loop, who understand the process, help determine a set of test cases to test the agent against with a benchmark or a baseline,

### 00:12:10 — Live Financial Workflow Demonstrations & Outlook

so that you, once you apply any change to any variable, you'll be able to determine whether that variable will change, actually proved, the behavior that the agent, or it caused it to regress, how social security, some of the examples. All right, so hopefully you've seen a building once with a layer and a foundational layer that you trust, you can work at speed that deploy many agents at scale.

For us, financial services and regulated industries doesn't mean slow. It means that we're seeing a lot of innovation from the financial sector, and we're seeing it go hand in hand with security and safety as well. And those 3 layers that we just walk through through, who the agent is acting as, who signs off, and how we still know that agent works, are the key components of building a safe and security check framework.

And once you have this framework, you can use it to apply to any new agent that you want to build for any specialty use case. So you can see at the top you'll have your accommodation. And at the bottom, you will see where you can actually bring in more special GA along the way, and as you continue to scale. That specialty is worked in combination with the business and the engineering to make sure that the proper business rules and context are being integrated into the Asian car flow.

And might be wondering, we haven't mentioned anything like a lot of COVID yet. Well, everything that we talk about so far has, let's say, 4 different doors that you can access it from. So a business person can access it from a coworker, an engineer can access it from a phone code, or you can take this to the next the next steps. And give the agent more work to do in your own UI environment, via things like managed Asians or agent SDK.

Now, so far, we've talked about building a secure, trustable Asian foundation framework. Now let's talk a little bit about the operating model. Some observations that you've seen, especially financial services, is that the business is now becoming closer to engineering. And the way that we're observing this is that the business will directly work the agent that engineering has built. They'll have direct capabilities to correct that agent or amend it.

proposed adjustments, and that's where engineering is in the loop. Once you see it, the list of post adjustments, you can solidify that as a small change after you were reviewed and tested all that within your email framework. And then the other chef goes right back to the business, and they'll go through the same loop again to continuously improve the overall agent and the process.

All right. So, so far we've talked about building an agent framework, and you may, you can build ones per scale. We talk about how we can turn the generalized highly intelligent model into a specialized agent. Now, when I hand it off the board, I shop later, we're seeing industry by building some of the foundations ourselves for the next step here, which is called for financial advisors.

Thank you. So what we were just saying is, I'll spill in a foundation once. Now I want to talk about how we could take that same approach to the industry. This foundation, we've been in full financial advisors. I will see my own mercy, the world, the Bible space, but we take this as a path, an opportunity to solve an email, how we can actually coordinate an issue level.

So in September we will more national advisors. They all the Shreya across the staff with an advisor. This was built on the foundation that advises only spare approximately 20% of their time was fired. We wanted to find a way where advisors could spend more time with clients and more time growing in franchise. So what do we do? We went through the Leb E Foundation and found ways to scale.

Probably a one. We've walk connected in. The industry system, the journalistic numbers, as a scale system, advised trust, we wanted to be assisted. Later, we build skills. We built to, that's available on get home. The bills, 8 skills and low flows that an advisor can take out the box, use today, and a benefit tomorrow. Play a full, approval, the advisor proves everything that comes out applause.

Nothing is saved or sent without the advisor, and that trust principle holds here too. And so you can see if you're on the diagram on the left, see around, vulgar data, custodians, all the tools of foundations and advisor needs. So let's go through layer one, the connectors. We brought in 25 platforms, custody, portfolio, planning, data, the serum, things such a small, adocal, sales form, and all.

and there's more connectorsors you can find upon the place. This is where the industry builds wants, the advisor can integrate ones, and the small app looks like. Layer 2 skills. These are the workflows we build for the advisor of, but they can start with an adjusted amount. For example, previous prep allows an advisor to bring a full family plan into my brief for possible assistance.

The follow-up allows the advisor to bring those, enter them into the ZRO system, and actually follow through these systems and tools. Nothing goes out until the advice of the bruiser. And this skill foundoundation is a baseline, which we imagine advises we start to innovate and re involved into more and more they work close allow them to start impact in their business. So, in closing, the 28 seconds on the clock.

Three questions to take to your phone today. The 1st one is the work floor. How are you applying the frontier intelligence to your phone? How are you gaining edge and alcohol from the frontier models to today? The same thing is the foundation. Do you all have foundation that you trust for building and scaling agents in the future as things become more and more specialized?

One connector, how are you actually building a foundation is that always can use, that you've only connects and skills, but your users feel for, and for the extreme? With that, thank you so much for having us. Enjoy the rest of the conference.
