---
title: "The Machine that Changed the World, vAI"
speakers:
  - name: Tariq Shaukat
    affiliation: Sonar
room: "Simons Room (Metropolitan East)"
starts_at: "2026-10-14T09:18:00-04:00"
ends_at: "2026-10-14T09:36:00-04:00"
format: "keynote"
recording: "2026-10-14_0915_Sonar"
duration: "16m 47s"
source: "voice-memos-transcript"
---

# The Machine that Changed the World, vAI

### 00:00:00 — From Lean Manufacturing to Enterprise Software Factories

Morning, everybody. my name is Tara Chuck, and I'm just you, as you just heard, and we're here to talk today about how we have been, helping companies build software factories that actually work for enterprises. And I thought it'd be an interesting way to start to start looking at actual factors, because we know how to build actual factors. And for those of you who have a little bit of the gray hair and all of this sort of thing, you may remember the 1980s.

And in the 1980s, you could find cars that were really good cars. But if you look at the picture here, and if you remember those times, the cars, like, didn't quite get together perfectly, right? You'd have different pieces that would leave big gaps. It would be really good cars that just didn't kind of work the way they were supposed to. And then, Toyota, particularly Lexus, came out with a commercial, and it showed something very simple, which was a ball bearing, running across the seams of this car, and it was kind of our missionary at the time, because it showed that you could actually build a car that fit together perfectly.

Instead of building for volume and building, and then fixing the old mindset, you could actually have a mindset focused on ship it right, on no rework, on customer happiness. And there was not, this was not a single change. What happened was that people really started thinking about the factories differently. They started engineering, building factories that were engineered to deliver quality. And there's a number of different pieces that I think still resonate today.

First is, you prioritize quality instead of volume. The second is that you fix the system, not just individual symptoms that you see. The third is that you design for something that can be built as opposed to designing the wheels and designing the washer bottles and whatever it is, and then hoping it fits together. You solve problems as they occur, as opposed to kicking a canyon on the road and fixing it in the end.

And you empower everybody, anyone could stop the line, not just the boss. Now, why am I talking about this? actually because modern software development actually embraced all of these principles. If you think about how we build software today, what is considered best practice, a lot of the terms and the practices came from that idea of material production system. And to our combine error budgets, if you're in the SRE, will continuous integration.

These ideas, all kind of sprung from this notion of how do you build factories at work? And it's worked really well for us to software development so far. But agents, as we all know, you wouldn't be sitting here if you didn't understand that agents are changing the game. And as agents are changing their game, weird things start to happen. First of all, this is research that was published last month.

What of the effect of implementing asynchronous agents in your development lifestyle? And I'm sure many of you have seen this, you have an explosion of the number of lines of code written of 2,450 percent. You have an increase in the number of commits, so the volume, co creation, is now easy, and it is now abundant. And, by the way, more and more people, I'm sure, any people in this room are saying, okay, if it's easy and abundant, how do I automate it?

How do I build factories, agenda software factories, that help automate and skillless? And today, we just finished our what we call state of code developer survey. It'll be out next month. This is a preview. Today, 5% of developers that we spoke to say that they're running agenting software factories, but 34%, Saturday, and year days, back to win 39% in financial services. So people are thinking about how do you actually build these next generation factories, and there's a couple of gotchas in here, security risk.

The agents can work really well, help you build stuff. It can also work really well to help you tax, to help you attack stuff, find all of those fine quality issues, et cetera. And so, as I was writing this presentation, I went over the weekend, got a little just in time, again, the entire production system. It's actually Adele posted this article on X.

If you haven't read it, I think it's a great article that, I think, everyone we've actually internalized. One of this, he was talking about inside the risk of models inside of companies. One of the things that he talked about was the need for an engineering approach to containment in governments, built around strong deterministic, system design, human controls, and reliable operating procedures. And this really resonated with me because what we are seeing is a paradigm shift in software factory design or software development.

Let's call it more grounded, that we need to engineer, we need to build systems that engineer confidence, and quality into engineering, identical software factors. So to start doing that, I think it's important to understand the limitations that we're facing. So what's the hard thing about this? And there's fine that I'm gonna call out. The first is that human in the loop doesn't scale.

And this may be, I know, to this room, it may not be all that controversial,

### 00:05:34 — Why Unverified AI Code Creates Hidden Debt

but every personally every company I talk to, I say, what's your AI government strategy? And they give me all the stuff and I say, but don't worry, we have humans to lose. And the problem with humans in the loop, as I mentioned earlier, 2450% increase in lines of code, 240% increase in commits, but the same study showed only a 30% increase in releases.

We haven't figured out how to scale from producing stuff to shipping stuff. There's automation needed, there's new tools needed, and really important. This is a concept that really, I see it every day. Now, I'm sure many of you do as well. called Condness Writer. I necessarily was published a couple months ago, and I looked at how often do humans agree with AI?

And it turns out, they agree with AI when AI is right, 93% of the time. And 4 out of 5 times, they agree with it when the AI is wrong. Right? So it's not that human in the loop is, yeah, we just need to make things faster. It's actually that it doesn't work. in the agentic Europe. So that's the problem, one. Problem 2 is that agents struggle with large complex code cases.

They are very, very smart, but you need to understand what happens in a code base in order to work on it. The left hand side is a study that was not in code translation. And what it shows is that the agents were able to get it right. 91% of the time when the code base was 10,000 lines of code. And by the time it got to even 50,000, I'm sure everyone in this room operates out much bigger code bases.

When they're trying to translate 50,000, the accuracy collapse. Similarly, another study looked at how many tokings does it take on a large complex code base to complete the same task? And the variance was 30 x, not 30%, but 30 x. And the reason is because the agent spends a huge amount of their tokens trying to understand how to navigate the code based structure of the code based things like this.

And it's kind of like if I'm trying to go from, from LA to here, and if I have to pick a random starting point, if I have them, your white planes, I will get to New York pretty quickly. I pick Albuquerque is gonna take me a long time and a lot of costs. Same thing happens with agents. Errors compound. This is another important concept.

This is study on meters, and meter looks at, and you can find this on their website, they look at how effective our agents are completing tasks that humans can do. And the way they look at this is, can you completely test that takes X number of hours? So, you can see here, the prognos preview, which is the latest version that they published, was good at completing tasks to take a human 16 hours.

Actually, that's really good, but there's an important copy, I've been fine print here, which is, this is at 50% accuracy. When you add it, when you dial up the accuracy to 80%, it, the curve flat, is potentially, because as you do long writing tasks, errors compound. If you have 95% accuracy on each task, by the 100 or 20 steps, you have 30 steps, 36% accuracy.

Right? And so that is another issue we have to deal with in software factors. Probably the most aggressive headline, but here is this 4th point that LLMs are unreliable, reward seeking judges. you know, so the question that we always get is, well, can't we just ask an LLM? And so people have been sending this as well. And this is all, again, the 1st left-hand side is from PayPal, AI, is a research object, published a paper this month, actually, and found that, depending on the model and the situation, between 7 and 17% of verdicts change across what they call identical replications, ask the same question, get a different answer between 7 and 17% of the time.

And if you start challenging, this is a study out of meta. Now, you start challenging the LLM, are you sure? Very simple challenge. It'll actually change its mind 7 to 34%, again, depending on the model. So you ask the AI judge twice, and you may get a different answer. And then lastly, I won't dig into this one too much. I think it's probably self evident.

To everyone, as the time to exploit near zero, the ability for us to respond is incredible challenge. And so prevention is something legally responsible factory has to take in to the design, the engineer, into the factory. So, as we thought through this, we have, written down what we call the co confidence student formula, which is basically how do you build, how do you think about a software factory that delivers what we all want, which is outcomes that we can feel confident in.

Right now, you can trust, not by trust or anything like that. But out comes that we can feel comfortable with, that we can sit and tell our executives, our customers, our shareholders, our CEO reports, that, yes, I believe this factory is working well. And we think this for components, too. The first is being crystal clear about the intact. If you

### 00:11:05 — Building Verification and Quality Gates into the Factory

don't know what you're trying to build, you can't tell the agent what it's built, and you will not get down what you want. The second is guide rails. And we very specifically talk about agros, not gargos, bargos, or something from going off the road. That goes I'll keep you on it. And I think what agents need are the small nutches a guy in government, those agents.

The third party is verification, that needs to be independent, thorough, and issues fixed as opposed to just cans kick down the road. And then, lastly, Evans, trust, but verifying, trust, but understand that it was done with proof. God is consistent, audible, repeatable, and we multiply these together because we've seen a number of situations where one of these elements is missing. And if it's zero, the confidence goes to zero.

If you do all of this, you don't have evidence, you go to zero, you don't have confidence in the outcome. So we really think about factory design is requiring these four elements. And as we put together factors, as we help customers, I'm not going to want for every box on this page, but as we help our customers and partners build, these software factories, we're very deliberate about how do you get the intent, bottom, left hand side, and purple.

How do you put the gargils in place? How do you do verification in a way that's their own independent, and how do you produce the evidence? And by doing this, we see amazing results. So these are real results now from our customers. The 1st one is focusing on the intent and gyros. And intendant guide grows, we have a product called sonar vortex, which gives intent guide growth in the agenda, which starts to do verification.

Again, nothing, the agents. And what we see when we provide agents in long running, in large complex flow bases, with long running tasks, with this information, is a 36% production in token costs, because you're putting it in white planks, you actually, you're putting it close to the answer. helping it understand the map. You don't have to burn okay on things we already know.

And 92% reduction in issues in the commitment, right? So it's cheaper, and we can get a better outcome to go into that verification stage. This is, again, all because we're not doing the agent to keep on track. Then you get verification, and we started life as a verification company. This is how we see the world as through a verification lens. And we have a very strong point of view, independent verification has to cover the full range of issues that is both precise and cost effective, right?

Use CPUs when you can use CPUs, GPUs, then you need to do. So we look at the terministic mixture of methods, and then you add in agenda, mixture of methods, and it comes up with what we think is the gold standard of verification. And what we see is when you apply this, our product is called sonar Q. So we talk to our customers over a 1000 customers recently.

And we said, are you, how lightly are you, or how often have you seen these issues from ejecting coding? And the statement to read here, stoner confusions are X percent more likely, and non-users, terrorists seem a very positive impact. So 81% more likely to have seen, to believe that AI coding has had a very positive impact on code security if you have that old standard verification.

34%, more likely to have seen an impact on time to market 76% on outage frequency. So again, as I come back to, how do we have confidence to ship, what we're seeing is that if you put these pieces together, and you build verification incredibly, as strongly as a first class citizen, in the factory, you are actually building confidence, and you're seeing results, better security, more confident, in our time to market, improved for reduction, in the number of hours to improve reliability.

And, of course, as I mentioned, you have to do this with, make sure you pass the quality made, make sure, whenever there's lots of acronyms up here, whichever ones you need to pass, whether that is your IT General controls inside of your internal controls and operations, whether that's misery, if you're building cars, or any of the other ones that are on here, producing the evidence is what let you so you can make.

It's what gives you confidence that you can do both. So that, in essence, is how we think about the challenge in the future, that code is above us. that continence is scarce. And really the goal that we have, and that we think that everyone should have as we think about the future of soccer development, is how we deliver confidence. And the factories of the future need to be able to build our products.

So with that, I want to say thank you to everybody. We have thank you. It's a big red booth. on the floor, right over that way. And would love to talk to you more about all of this. Thank you very much. I have a great morning. Where should AI agents take control? And when should humans stay in charge? Here to explore that balance and policy driven overflows, please welcome Evan Cormos.
