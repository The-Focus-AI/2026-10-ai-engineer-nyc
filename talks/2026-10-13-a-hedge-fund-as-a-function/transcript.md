---
title: "A Hedge Fund as a Function"
speakers:
  - name: Frank Long
    affiliation: Coatue
room: "Simons Room (Metropolitan East)"
starts_at: "2026-10-13T16:30:00-04:00"
ends_at: "2026-10-13T16:48:00-04:00"
format: "keynote"
recording: "2026-10-13_1630_korean-news"
duration: "14m 02s"
source: "qwen3-asr-1.7b"
---

# A Hedge Fund as a Function

> Transcribed by qwen3-asr-1.7b with a schedule prompt. Possible prompt artifacts, names heard more often here than in the unprompted Voice Memos transcript (Qwen vs Voice Memos): Qodo (2 vs 0), Coatue (5 vs 0), General Intuition (1 vs 0). Check them against the audio before quoting.

### 00:00:00 — High-Conviction Bets & A Hedge Fund as a Function

Hello. Exciting to be here. My name is Frank. I work at Coatue, which is a technology investment firm across public and private markets. So, in our business, what you really need to do is be able to take high conviction bets on big themes and watch this play out. I think, honestly, it careers the same way.

And last year when I joined Coatue, the bet that I wanted to make was, I think that agents will have an even bigger impact in investing than they did at coding. I know that's a big statement. We're all here because of the transformative impact the AI has had in coding, but I really believe it strongly, and today I want to talk a little bit about the framework that we use to actually realize that impact.

So at a high level, you can think about a hedge fund as a function that takes in two parameters — context external and context internal, and spits out one, two, volt selection size timing. What stock? How much? When?

Right, and I think this is a good framework to actually to ground our work, which is we're trying to solve this compression problem of how do you take all the information in the world and spit out this one simple tuple? And the product that we that we provide is essentially a time series of this pool that constructs the portfolio.

### 00:01:25 — API-Accessible Inputs: External & Internal Context

So let's start from the top, which is the inputs. Very simple philosophy. We use our screens. We look at stuff. We do work. Every single thing that a human can see in pixels on the screen, an agent in your building should be able to see via API. The analogy I use is: imagine you brought the smartest people ever, the greatest investors alive, and you brought them into your company, but you gave them a computer without logins to 75% of your services. It's almost immaterial how smart the system is if it doesn't have the tools to actually action that.

So the two parts: external context, right? No surprises here. Think the news, prices, filings, all of that should be easily accessible, and not via dragging and dropping, copy and pasting, like directly via API. Internal context is just as important, right? So this is your own firm situation. So that might be our current positions, potential liquidity and risk requirements we have around certain names, and past case studies or you know history with a certain sector or stock or management team. That's what's also super important.

So this is the foundation, and I think no credit to me. Coatue has been an amazing leader on this for over a decade. It's both technological and cultural. We have an amazing data science team. Amazing, amazing processes. Amazing, amazing systems that bring all this in, and just as importantly, we have a culture that is super rigorous and built from the ground up to capture all this insight. For decades, we filed every single note about every single trade, about every single decision we made or didn't make, about what went well and what didn't go well, and that's poised us to expose us to AI.

### 00:03:13 — Decomposing the Function: Gather, Analyze, Decide

So if you think about it, I probably can't just take all of those things, jam them into a context window, and get my magic three numbers and go home, right? It can't be that easy. You probably have to break down dysfunction a bit further, right?

So maybe the first step is I take in that external environmental context, and I gather it, right? I want to gather it. I want to filter out what's relevant and not relevant. Okay, well, I've pulled some news articles about the NBA. That probably isn't material to stocks, but, oh well, this is actually related to some local permitting that might actually impact data centers, like — there's a lot of nuance in this gallery stuff.

Then you'll see, probably next step is I need to analyze that information and form a view, right? I actually need to think about what that means for the markets — public and private. And then I need to take that view and turn it into a decision. A decision object has these three primitives, right? These three sort of sub pieces. So you can see every single step has an input and an output, and the input for the subsequent step is the output that the previous function generated. I think, as an engineer, this is a way for me to conceptualize the problem in a way that makes a lot of sense.

But even this, it really can't be as simple as writing three functions, right? So let's just — to really appreciate the scope and understand the full complexity of the problem, let's look into the first step.

### 00:04:53 — Case Study: Interpreting Korean Semiconductor News

A tiny subpiece of tiny subpiece. We're just gathering information. Let's do a case study on interpreting the news, right? So it's probably no secret to you guys that, you know, news from Asia and Korean media outlets has been super important this year because Semi's AI have been a huge, huge theme in the market. Huge thing, and I think this is an area where AI is poised to have a lot of impacts, reading Korean language news better than our completely non-Korean speaking staff, right? I think I have a good thesis that this might be a good use case, so.

Because the first step is, I have articles. We collect the articles, right? So this could be an MCP. This could be a CLI. License the data feeds. Clean the data feeds. There's actually a lot of ways to do this, and a lot of dimensions of freedom for how you can even just write this simple piece.

How do I chunk it? When I pass it to the LLM, do I want to pull the images as images? Do I want to hold the images and then turn the images into text? There's actually a lot of knobs here, and I almost think about those knobs — it's like hyperparameters in a traditional machine learning system, right? I think about each of these knobs as something for me to tune and optimize against.

Obviously, filtration. We talked about it. Korean, they're probably Korean NBA fans, right? There's probably a bunch of stuff that's not necessarily material to the names and themes and stocks in our portfolio really, really not right. So I want to make sure that there's this like translate slash extract slash — should I summarize? Should I extract this into some sort of structured form? Again, so many ways to do this. So many ways to experiment, how to expose information to the model. And one of the reasons this is hard is it keeps changing.

And obviously, checking like our own internal notes, our own internal views, potential conversations we've had, meeting recordings against these things. We actually need to cross-reference those things. Actually, the idea of pulling information from disparate sources and cross-referencing them — that's super powerful. So you'll see on the right here, I have Code L M L M code person. There's many ways to run these functions. I think about — oh yeah, and finally, update. Eventually, we update our views.

### 00:07:29 — Four Function Runners: Code, ML, LLMs & People

So there's many ways to run these functions. I think of each line as having a runner, and the most obvious one is Qodo. Qodo is very good. It's fast. It's cheap. It's reliable. So for something like, if the prices to earnings ratio is less than 15, I should just use the deterministic code for that.

Runner number two is statistics, classical machine learning, and imagine fitting a line to a regression for a specific pattern. This is very powerful because you can model much more complex relationships than just pure determinants of code, right?

And for even more complex relationships, the reason we're all here, LLMs, AI agents—that's another type of runner, right? So for something like summarization, that's the state of the art, right? It's probably totally impossible to build a bunch of their statements that can summarize better than modern LLM.

And of course, people, people are important runners in the system, right? So imagine a function meetings the management team of a company. I probably don't want to send — I mean, I like the new unitary robots, but I probably don't want to send an LLM or an AI agent in to do that. I probably don't want to send an if statement into that meeting. I think there's many cases where, because of judgment and the ability to navigate the real world and all these things, a person is the best runner for a given piece of the function.

And I think this is like a super important point. There is no glory in automating things for the sake of automating things. The goal is not to take as many things and make them LLMs as possible. For us, the goal is for any given piece of dysfunction, what can I do to maximize absolute quality?

### 00:09:20 — Branching Control Flow & Tuning Hyperparameters

And if you actually think about function, it probably looks something like this. It's probably not just a linear statement of a bunch of different things. There are probably all kinds of branching logic and all kinds of ways to actually support this.

So maybe I want to collect the information and then translate it. And my main goal is to extract quotes and check those against sources to make sure that these are actually things that people said and that's my approach. But that might be totally wrong. Maybe actually what I want to do is actually dedupe, I might want to filter, and then I want to pull external figures, or maybe I want to do something totally different. I actually want to — I'm passing in a note first, and I actually just want to find other confirmatory data points, or maybe I'm trying a red team.

There's a million different ways to configure this, so yet again, more hyperparameters within the control flow, right? So, so many ways to think about just this very simple problem: a polling, filtering, summarizing, navigating the news for all of us.

And each of these boxes probably has an optimal runner, right? So the optimal runner might be deterministic code for collection, right? I'm pulling last 24 hours for a given source. That's deterministic code. Filtration, decision models, maybe LLMs, statistical methods, a combination, right?

So this probably understates the complexity. The reality is most things are multi-runner. Most things have deterministic code plus LLM plus statistical method, or a human with LLM in conjunction. The reality is, it's probably combinatorics between my four buckets, and there's even more buckets than that, because within the LLM category, I can tune the model. I can choose big model, small model, medium model. I can tune thinking effort, x high, high, medium. General Intuition harness. I can choose the harness. I can choose which skills load with the harness. I can choose which hooks load with the skills.

So yet again, more hyperparameters within my search space. I have an absolutely enormous amount of hyperparameters within my search space, and this is just for this one tiny problem, right, of just filtering the news. So the way to think about breaking down these problems is, what can I actually compartmentalize in a way that we can understand and evaluate?

Because that's what I'm hill climbing against, right? Otherwise, I'm just tuning these things, I'm okay, well, that should actually be a machine learning system instead of an LLM. That should be a little model that we train. Oh no, that should actually shouldn't be a model at all. That should be an if statement or, oh man, LMs are really bad at translating that to portfolio impact. It should really be a human on that step, but they're using a deterministic system to help them search and pull information. Can be all different things, right? And if you don't have a north star to help climb against, you're just kind of you're just fidgeting around.

### 00:12:16 — The Full Firm Graph & State Machines Beyond Investing

And I think I cannot convey enough that this is just one tiny thing we do — imagine every single data source that we pull in. There's probably more than just three transformations to get them to the intermediate output. So the actual graph of Coatue and funds like Coatue, it actually probably looks kind of like this. This is my screen saver. The actual graph probably looks something like this, right? It's probably massively complex.

In each of those nodes, we just talked about, at least ten hyperparameters with at least 20 different valid values for them. So the search space is basically infinite. And figuring out how to actually lay this out in a way that you can comprehend, both from technical perspective, but also absorb culturally, organizationally, that is the great talent of applying AI in investing.

And beyond investing, what we're really talking about is creating a state machine that can take information from the world and understand it well enough to make coherent decisions. There's use cases for this far and above, wider than just investment firms, in policy and non-profits, in drug discovery and corporate strategy. I think one of the most exciting things for me about being in forums like this, talking to other people in different spaces with different problems that kind of congeal on the same problem space. I'd love to keep talking about this. I'll hang out in the hallway afterwards. Here are my socials, and thank you, everyone, for your time.
