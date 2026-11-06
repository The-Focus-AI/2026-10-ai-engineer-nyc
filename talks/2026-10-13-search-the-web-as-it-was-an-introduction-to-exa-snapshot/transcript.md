---
title: "Search the Web as It Was: An Introduction to Exa Snapshot"
speakers:
  - name: Ryan Ahern
    affiliation: Exa
room: "Shannon Room (NY Ballroom E)"
starts_at: "2026-10-13T11:30:00-04:00"
ends_at: "2026-10-13T11:48:00-04:00"
format: "talk"
recording: "2026-10-13_1130_Exa"
duration: "18m 53s"
source: "voice-memos-transcript"
---

# Search the Web as It Was: An Introduction to Exa Snapshot

### 00:00:00 — What Is Exa & Agentic Web Search

and today I'm going to give you an overview of 2 things. We already have a very strong amount of time. So the 1st one, I just want to motivate what is XA, what is agentic web search, just because you kind of need to believe in the dream of that, understand why you want to use it to do the 2nd thing I'm going to talk about, which is how to access financial models using that.

So 1st just to understand where I'm at in the room. Book here has heard of extra before or used it. Okay, like a good show of hands. Your hair has ever used, like, Google back in the day to, like, do some sort of work or personal use, just, like, type into Google to do some sort of search. Probably like everyone in the room, most people had pretty good market share you might have heard, but last one would be, how many of you now no longer really use Google?

You use ChatGPT or claw, or maybe an instinct or music, or, like, a cutting edge to actually do your searches. Yeah, most people right? So we're going to connect all of these things together. This last point where a lot of people now are like, hey, I don't even really use desktop to search anymore. I kind of ask an agent to do this.

It's something that we see more broadly in the market, right? And the idea is that like, agents tend to do a pretty good job at understanding how to search because they're allowed to try multiple, multiple times. They kind of don't get tired. It tends to be quite agreeable and work very, very hard. So when you say, like, this is the thing that I want, it's gonna go out and it's gonna do many, many different searches in order to satisfy, like, your objective.

And the other thing here is that they tend to search different types. So as a human, you might put in like a few keywords for the thing and then hope that you get the best results, like in the 1st couple. And otherwise, like maybe you try like a different query and then you kind of give up. Because Asians will be very reverse.

They tend to describe what they want to search and break these out, actually do many searches on understand this face, not fully before they response. And that means that they do way more sessions on iPad aspects. So generally, the idea is like, hey, nowadays, whereas humans, you're going to be using agency and rotio such tasks. And that's where X is kind of plugged in.

So when you're working with, like, many, many intensity systems or whatever cursor, wants to go and such plays documentation, help us creating agent computers to decorate, whenever you're like talking to Ghana, you're like, hey, it would be great. But I had just this like SEC data from like Apple in like 2018 to complete my slide. like that would make it brilliant. It's going to use an excessive dirt out.

search the full length of memory, crawling infrastructure, a database or inventing model or a retrieval, architecture. You get exactly what it needs to enter its query. This is like a couple of logos of like bigger companies, but because this is an AI engineer, I hear a few like kind of office types that we work across the financial space. I would really want hedge funds, asset managers, solar wealth funds, these days across like a bunch of different tasks because I also need like the latest information.

So if you're a head funder, you're going to be trading on information, you're looking in the market for alpha, right? Is there information that allows you to understand how you could position your organization better? You do an insurer, you probably understanding how the hobbies are working with or who you're insurance and make sure that ultimately you're making the determination. So you want to make sure you're making that all the best information under your wrist laws and the most accurate.

Raven degree in DC, I need the hottest startup. I need to know the index instinct before they blow up and they're not necessarily going to be like some structured data set. Like, I need to go and find them wherever they exist in the web. That's what they come to exercise to kind of support them for. And then the, kind of, to wrap up a lot, part of that I accept.

And the reason why, I think now you'd be like, okay, I'm building agents, I'm interested in agents. I definitely need a general website, FlyXer. And this feature is like we're a lap in the sense that we're very, very interested in the search market, and in the ways in which Asians search, then we're hyper focused on that problem. There's 3 like core tenets, and then we'll talk about how that goes into version 8, diseggling to the next part of the talk.

The 1st thing obviously is that quality, right? So, you want to make sure that when the agent does that, metrical and the retrieval, he gets what it needs. Because the fewer tool calls that it needs to make, the more cost-effective on your inference, and also just like, the more likely is to succeed on its overall trajectory. You not going to bring in something that misaligns it.

I'm really, really interested in the quality of the case we recently released like an impact, which we think what accurately assesses the performance of like the search tools separately to the impact. Because these 2 things can be compatible, like what age it, or what model is following the search, and what search is making form of. So that, you can kind of have a look at back to CLA is thinking that secondly, on cost.

So it's not just the line item of the tool call, right? Like, how much does one search cost? Because agents don many different seches. So the idea is both like, hey, what's the values list? What that you be through? But also, I mostly impact it is on the total cost of that data completing it. So that's actually the same that you care about, right?

Generally, that's entertained in that one school course, I have to this overall agent take. And that's why, like, we work on things like, say, dynamic highlights, which means that for every single result, it may not, one of us returning full pages. We're not even just taking one page, which is our previous highlight pictures, and figuring out what are the exact right snippers on that page that we need to send back to the context window to complete the trajectory?

We now do that across all of the search results, which means that you can actually get higher quality results at 95%, fewer tokens, and you would at full page text. They have a blog about this is very interesting. But basically means you'll save a lot of money downstream on all of the input tokens you'll be spending on inference for the agents to complete its rejectory.

Last one on latency. So because we were in our infrastructure, we can do very, very low latency search. I'm just going to touch on the other side of the spectrum, which is like very long running deep research. So we have exit age of Ultra, which we release, like not too long ago, maybe a few weeks ago, which is like state of the art on a lot of

### 00:06:02 — Exa Snapshot & Backtesting Financial Agents Without Lookahead Bias

benchmarks around like very, very long running search. And that's because we can do a lot of things under the hood. We have often we bring in search harness, so we could also be opinionated about that, how that interacts with the agentive products, doing this like very, very long-running research task. So I highly recommend you check those things out. This is just a segue to be like, okay, it's a really kind about this space.

I think that their search is going to be good to motivate the next part, which is really interesting, the topic of this talk, which is versioning. So just recently, we released X of Snapshot. It's 400000000000 plus snapshots of the win. And you can search on my day. And that's really, really interesting in the in the financial services. We're getting to that, but first.

We're just going to talk a little bit about like what this basically is. So where I search company, so we're constantly searching across the road for the latest information that we can add to our index. And every single time we do it, we check it, we're checking for freshness because ultimately you want to have the latest live up-to-date information at the point in which you're searching.

But they've been doing all of those checks, it means that we can capture a version of those URLs at the point where we checked it and have like a version of history. And you can access that in 2 ways. One is like, I know the URL, I want to find it as it was at or before a given date. And so you can give us a URL and you say, this is the date that I want it.

I've done it before and serve it to me as you would if I had requested it at that point. The 2nd one, which is even more exciting, is a positive fashion stretch. So where I said, ABI, any idea is like, hey, what would happen if I had executed that search? That it was a pride one, right? So I only get results I would have been done at that point or before.

That has very, like, interesting invitation, I'm just going to do one, like, very small example here. So, open AI, recently, I say, I was a black October 1st on the left-hand side, yeah, we see a screenshot search. as it was in October Festival. the rack design is a live search as like a couple of days ago when it is like. But at that time in barely October, like there were some discussions that like open AI had a like annualized, like run right around like the 70000000, right?

And that was leading to so the ways in which the market was projecting, how and where they would be valued. And then more recently, there was some, at that point, it was axios. And then more recently, there were some publications that were reporting, like, actually, it was close to 500000000 for fund and counting reasons for that. It turns out that they were having gross revenue when actually like some of their revenue was coming from plant providers and technically the way that you should account for that would be that there would be a member pass through their annualized revenue was better.

That's how what some other players are playing, et cetera, et cetera. But basically invented the, the net analyzed run ramp was a kind of downfall cost for 7000000000 down to 50 million, right? Now, this is just like a financial thing. That some of you may or may not find interesting. But for so what, for a version, such is like, let's say you're in the interest of creating a product or a solution or an agent that is made to, that the job is to define these things.

Right. You can now very back and be like, okay, before everyone figured it out, right? Before the market and before some financial analysts published the thing piece, it was like slamming down on this particular thing and everyone knew about it. What information existed on the internet, right? Like, was there an SEC filing that would have revealed this thing in an accounting footnote?

Like, was there some other reporting from some other vendor that maybe is like you would consider as like less refutable, but actually was able to find that kind of thing and maybe you should consider them differently. You can potentially, you can potentially like trace these things before like the rest of the market found it. But most importantly, like not only can you test that, but you could back test that, right?

You could then adjust the ways in which you are setting up your model. You can adjust the ways that you're setting up your agent to be able to be like, could it have found this discrepancy? And more importantly, couldn't have found that discrepancy in a way that is generalizable, right? Let's like create a set of like 50 sample sets, see if it can perform against that, check it against the whole and be like, okay, I think that my model is now to be pretty good at finding this kind of feature.

And that's something that's kind of new in the website space that you can backtest that. This is like a little diagram just to kind of motivate the idea. But at any live search that you do with like any existing social product, the idea is it's life. It has all of the information. So in this particular little example, where we're trying to predict where the company got acquired or not.

In this case, if you live search, you were very refined, like the deal was announced, right? Because that happened, it got released everywhere. You could be like, hey, I'm trying to train a model that's able to predict whether this company got acquired or not. So I'm gonna go like one day before the announcement, 7 days before the announcement. A month before the announcement and see whether I could or could not predict it, right?

And you can build a set of those companies and basically train your model or whatever system it is that's trying to do this prediction and see like, wasn't able to reliably, like, predict this particular feature? So I'm going to spend a little bit of time here, just talking about how different systems are currently being back tested with Snapshot. So there's like 3 kind of archetypes here.

The 1st one is I'm operating like a very traditional model, maybe it's ML, maybe it's even more simple than that, like a decision tree or something. And all I want to do is just gather, unstructured data from the version web into some sort of struction set of information. So it could be something like software prices, it could be some sentiment analysis. It could be like the terms and conditions of a particular site, whatever it is that like powers your model, not all information is continually available.

Like if you're trying to understand software prices, like, you know, the page of that software price is not necessarily stored in a version and a way for that. website in a way that you could reliably access. Or potentially like you have some like, you know, sentiment analysis that you want to do, but like that's going to be wired in like what point was that sentiment releasing time, right?

And you want to go when you get like a reliable set of those signals. And then you

### 00:12:26 — Point-in-Time Web Retrieval & Evaluation

can just transform it into some array. The signals that goes into your model, you can predict it. That's like the sort of basic space. And some people are just like enriching data that they wouldn't have had access to for their existing models. So that's just like sort of like the status quo +one. The interesting space is in like the next few areas.

So the 1st one is this idea of like adding an agentic feature. And here is like, okay, well, I have this existing model. It performs pretty well, but I have an idea that like if I add one or 2 like agentic features to this model, it would be able to perform better. So let's say something like an adverse media scan. Necessarily, like adverse media is going out into the web, searching across it for all the information that exists, potentially doing it in an agentic way, right?

Where you're doing multiple searches, you're exhausting multiple different trajectories, and then you're gonna take all of that and then condense it into some sort of structure. Another example here would be able to say like equity research in much the same way, like, hey, I want to go out. I want to look at the full universe of companies and I want to find, like, potentially all of their, like, estimated, like, revenue or headcount or all of the features that matter.

And the idea is that you'd be using something like exercise at the point where you're doing a prediction live, to go out and gather all of that information, but then send into your traditional model. And you can now use like extra snapshot to back test those particular features. So you can go back and be like, hey, if I was to do this, like adverse media scan, like one month or 4 or maybe I've already like onboarded a bunch of people into my portfolio like 4 months ago.

What would I have said at the point where they were going to enter my portfolio and how is that tracked against the net? And that kind of motivates, like, especially with more financial services, customers, like, you know me, I'll just have to believe that, like, searching better, you can actually go back and access that because your existing process is saying, hey, it was better.

So that's like maybe the next evolution is like once they've passed off on the far right-hand side here. is kind of like maybe the future. So there's some like startups that are working in this production space. And the idea here is that the full sort of like simulation or prediction is being managed by an agent. So in the middle is like an ML model that's maybe doing a prediction or some algorithmal decision trick on the right hand side, like it is like an agent.

that's just going off and doing a bunch of things. It can be such an internal knowledge. It can be accessing data phase. they can be doing whatever it is. But one of the things that it may do that is valuable is to football and access the web. And the idea is like now, you don't have to try and create some internal corpus that tries to represent what it would be like to access women.

You can just be like, hey, I want to make sure that I can control that feature. So I know that future information is not just going to lead directly into the model. Like, I'm trying to predict company acquisitions, these are very, very insane, like, agency processes, accessing everything, you can now be like, all right, let's just make sure that's not just gonna have one web search that finds that it will combine, comes back and predicts it with like 100% accuracy.

So that's kind of the sort of right hand side there It's just gonna be like a little example of like a little, just a round off this kind of study. So, yesterday we ran that extended workshop on Snapchat, and we had a bunch of, I read a 100 people in the group that were kind of running through, as you say, an example, kind of format, and I predict company information.

one thing that was kind of interesting is that, there this was like a lot of the example pages of the workshop for one of the people, that, that type of relevant as well. But the thing that was interesting here is like, you know, the, just the, just the, the 1st one was, this idea, they're like, hey, within the past year, they're doing the best stuff.

Or a significant channel, that probably fall for us. And the 2nd one, which is an interesting one, is like, hey, did this company share price? Because at least you've been said, well, it's higher. Past 5 years, the ideas, like, it's kind of digs down. The law, because you say, like, hey, is the company named Nick? Now, this is a little bit of opening.

people that are like back testing. like I mean idea here is like this could be something like an Asian food too, right? ' made on life said if it potentially this over bit the training have. So the idea with stamps, like, not only can you do it back, test for these things, you can go back and, like, set up your, you know, your details or your identity products, and that's the way that you can detect these things, but you know, so it's time to detect these generalizes.

And this is something that will be very, very hard to do if you're like dated by like testing time, like in production. And you can currently change the ways in which these features are described over time and check against real time, right? You might be waiting for months to try and see how and why your agent is set up and actually is predictable or is overfitting in different ways.

Then he's like, you can describe these like, quite complex features, like, these ones are like maybe if you could imagine trying to recreate in, in like some sort of like, like mountain anti-such. But you can go as crazy as you want within it, within existing, like, access semantic search world. You can say things like, hey, I want to see if there was any adverse media against like reputable VPs that are operating like that are operating within BC funds that have like been on the AI engineer podcast and they say something bad about it, right?

Like you feel very, as hard as you want on these features that you think you're going to be predicted, because that's what core access search allows. But then you can map test it and see if it's performative or not. then I'm still kind of like repacked. So the 1st thing that we talked about here is like, using Xer because it's quality plus effective agenda work search across every agency.

We have lots of blogs around this, so encourage you to not try XR to have them go with this. Because the 1st thing you want to know is like, hey, why actually think this is going to have some benefits, my mom? The 2nd thing we've talked about is like, hey, using extra snapshot, to be able to, like, back test these financial models, all general model, risk model prediction model with these web search features in order to say, like, hey, does adding it, add value to you, your agentive processes.

Thanks much.
