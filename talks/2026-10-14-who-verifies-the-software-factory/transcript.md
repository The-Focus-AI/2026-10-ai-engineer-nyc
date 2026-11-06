---
title: "Who verifies the software factory?"
speakers:
  - name: Manish Kapur
    affiliation: Sonar
  - name: Addy Osmani
    affiliation: Anthropic
room: "Sutton Room (NY Ballroom W)"
starts_at: "2026-10-14T11:30:00-04:00"
ends_at: "2026-10-14T11:48:00-04:00"
format: "talk"
recording: "2026-10-14_1130_Software-Factories"
duration: "18m 36s"
source: "voice-memos-transcript"
---

# Who verifies the software factory?

### 00:00:00 — The Code Review Bottleneck in AI Software Factories

Having a good event. I'm pretty excited to be here and talk about who verifies the software factory. Before we get started, can you give me a quick show of hands raise your hand with your ving agent has called openold request in the last one week. Almost every month. Thanks. And keep your hands raised up, if you have merge pulled at this and reviewed every line of code that was merged.

Oh, I do see a few people. That's exactly. So what I'm going to talk about is the gallery being the 2 camps, merging requests without reviewing memory and, you know, merging requests after doing some reviews. So my name is Manish Kapoor, and I mean the Border Consolution, developer relations team at Sonar. And I'm excited to be here with my guest speaker, Adios Mani, from Andropic, Adi has been had been at Google for about 14 years.

Most of you probably know him. And he's written lots and lots of contract and articles. I learn a lot from having friends. really fortunate to have beer stand next to me and share the wisdom with all of us here today. He recently joined antcropping, and at least so congratulations on your role and how... you like the team what you're talking on and your goal is?

So, I'm responsible for, like, really free, well, experience, building a live coach. and anytime we discover there are opportunities to be even smoother. You bring that right back into, we took a couple of times every single day, so we're very interested in talking for that you have the best possible experience. So let's start with some problem and context settings like. There are no numbers on this, like, Circle CI, analyze 28000000 CI will close this year, and they notice that the crew was done by over 59%.

but yet 3 in 10 attends to mer that more production period. And this is a start from one, the independence that from Circle CI. And I think I've seen the same trend from most of our customers that I speak to. This is a quote from Addy, a software vaccine is, how do you say, loops, that's a? This resonated quite a bit for me, but if you're not writing that article, you can look it up, it's pretty educational article and talking about future, how the future will look like in terms of software factories.

So I need we like to expand what you' thinking that you got this article mov of doopes and nursing loops that him. 2 ways. So a lot of books here probably heard the term software factories and there's 2 types of factories that are at least rep keeping in mind. You know, software factories, harnessing loops, and scale, a lights on factory is one where you have agents that are helping you with planning, building, checking, and shipping code again and again, but you, as a person, still apply your judgment and taste inside the picture.

And then you have a dark soccer factory, which is a little bit closer to how, you know, a car factory was revised, might be working. It's constantly doing the work. So it's scoping, building, checking, and you as the person will, further to think about the intent that you're pulling with. You're really increased that exactly, right? But that's sort of what I was thinking.

I think a lot of teams are somewhere on the spectrum and are on the stream to figure out like how do I get further and further into automation? way that I can trust it. So, AI poding is now basically a solid problem. We all know Indianents are there on 85% of the organizations are already using codic agents when you go to 95% raise 100%.

35% of the 36% of the developer, that are really EI4, they are saying that it's being used instead of speed, that it's impossible for them to verify. So they are spending more and more time between the code. So what do you think is the most pressing question that engineering leaders have right now? So I think that teams have gotten better working with Indians over the last year.

Models, harnesses have also gotten better. And what I see a lot of leaders being interested in is how do we enable you to ship code faster with confidence? And that confidence piece is very important. Agents can now generate weight in AI, Europe, much more quickly than ever before. You think about the things that enabled us to call good, oh, you know, high quality.

Those were things like good tests, vending arts, spec, anything that gives us confidence. So it is able to help us generate that a little bit more easily these days, you know, quickly. those things, but I think that those checks are one of the most important things we should be spending our time on these days. Like if you are hoping to get the best quality output from your agents, you need to give your agents a way to verify that the work is correct.

If you've got that in place and you can make sure that the companies both correct and complete, that can easily 2 to 3 by type of quality throughout house. gone on, I think old conference we've been running an ad for confidence, scars, and you really need to build it up. not the recordingoding problem so. So I, actually, I, yesterday 9, it was 90 year surprised.

I guess in a right I write a post from Anthropic and I direct all of you to read it. It comes to the scale at this and property is operated. Now they are merging about 30,000 code changes every single day. They used to do about 3000 or so, 3500 or so poor changes, just a few months back. They sc from 25004 changes to 3000,000 for changes per day.

That is mind boggling. So, I don't know what a sport do you do? A lot of good, and then popping and you got cooking, but it was in the... So we were we were emerging about 2500 changes all the way back to pay and even for our recent refressh of cloud. AI, we put out a case that saying that be kind of 3 byes the performance of it.

That was accomplished by merging about 3000 for requests in a very short space of time with engineers, product, designers, a number of different functions contributing to it. So our workflow for being able to get verification and code review in place is that we 1st of all have laws, like the 1st pass for you. What's very important in there is making sure that it has

### 00:06:35 — Multi-Layered Verification: Static Analysis, Tests & Agent Critics

a way to actually try the experience out. similar to our real user. So that can mean end to end, half, you know, opening up the experience, checking it in a grouse, or running any tools, doing any linting, doing any other checks that are necessary to build up that confidence. People usually ask us, okay, well, what happens if, you know, you discover a bug or a gap in functionality?

Well, we have hooks that will then go and run on any edits, they'll study the disc, and allow us to get this loop in place where we are correcting the PR as quickly as possible. So we have Claudio doing the review. We have a code review product that you can also check out. It's pretty good. And the idea there is we're trying to automate code review as much as possible.

This is something that we use ourselves. And increasingly what's important is for your teams to be thinking about, how can you, we talk about taste and judgment so much these days, right? It's important for you to be, try to codify what you consider best practice and take in your teams, sharers, like quad.ed, anywhere where the agent can then exult during code review.

And then people are responsible for checking on the agent's evidence. So how do we know? If I'm building out a piece of UI that's going to be, you know, used by a newspaper in the browser, I want to make sure that it's tested in the browser, maybe generated a video of that experience where it's been clicking around and gives me confidence. well, okay, well this works.

If I care about mobile or desktop experience, maybe it generates these screenshots and videos of that. But basically, we want to get to a place where the game's giving you as much verification as possible. Yeah, verificationhe. I think you need to verify everything that the software quality will produce, and that's what we are going to talk about today. So, another discuss, we stash, by the way, about the state of old survey report that will be coming off very soon from sooner.

We survey now, now in the world and also developers, and we found some interesting data which will give us insights as to what's happening in the industry today and then we are there. So 84% say AI teachers get features and pictures for production faster. The poor requests are getting larger and more complex. And, you know, get only 31% more code is reaching the production without review.

So that's a little bit of a scary fact, particularly for production applications in the regulated industries, in the mission political applications, where you absolutely need to make sure that, you know, you have to verify that port and you're confident in the court that is being shipped. So what are the what are the next games will come from? I think the next game is going to be a combination of us really nailing verification, right, as well as model quality.

But models were already like if you take a look at Opus 5.5, modeln quality has already gotten to a place where it's pretty good. And I would say that us being able to share best practices about that verification stuff is going to become increasingly more important, because if you tell people, yeah, just like verify the work, you know, the next question, what does that even mean?

Right? And so, I think that the conversation needs to evolve into specifically what kinds of tasks are useful. We lean a lot on end-to-end tasks, property tests, any visual verification tests, things that can help us just get that confidence to reverse those changes automatically. You mentioned light factories. What about dark and that's the way the direction we are headed Our survey results show that, you know, today 5% of the companies are using software factories that they get to 34%.

And surprisingly, 39% in the financial services. Only up to using subware factories is just here. A handful of you. And how many are planning to use S factories by next year? I Yeah, that's a good question. Who need to find a software factories? Would you like to take that question? Yeah, sure. So we talked definition of software factories just a little bit earlier.

The software factory is basically loose in scale, and when we think about this, it's all about, like, what end of the spectrum are you at in terms of how much people are still involved in the process? The more that the agents are able to generate verification and give you confidence, the more that you can get to that place where you go dark, and I think that, yeah, most people are still somewhere in that spectrum or not quite as this data shows.

that dark point just yet. Just to add to what Addie said, I think it's software back, you think of it like a production line, where you start defining the intent, then your specifications, that you start writing the code. So it's an assembly line that each of these software developing nice cycle steps happen. And automating them at the area, when there's pretty much in a dark pack, back in India, there would be no lines on its autonomously working, fully autonomously working.

A line factory has, is where people are involved in the process and at least that, or most steps, Nugget of the NAR factory, the goal would be to turn off the lights and let the factory run independently, 34 by six. All right, so you talked about verification. I'll talk a little bit about what you think at Sonar or great occasions. If you saw a theme of re play from a CEO, we talked about verification should be multagated.

we absolutely 100% believe that each company should adopt a 0 trust mult veification of work and verification should be done in every loop. Whether you're operating inside the agentic group, or whether you're working inside the CI verification room, or whether you're doing port maintenance, in each and every loop, it is important to verify the output of the factories or the agents that vote that the agents are producing.

So we look at it in terms of layers. And think of it like, you know, this 1st player, which is a deterministic player, which catches burns, security issues, things like sequel injection, puffer of plots, all of those are caught. And then there's a 2nd layer where agentic review happens, where agents are used to like, and it was October, 80s reviews review that course, and in that agentic review, they catch logic and intent issues, which the deterministic layers are well suited to catch.

So

### 00:12:38 — Scaling Trusted Autonomy with Sonar & Anthropic

we use each layer targeted at capturing the specific types of issues, and then the 3rd layer could be a software supply chain security there. Where do you look at all the CDs, all your malware detection happens, all your malicious package detection happens. All of that happens in the 3rd day. So it's a layer of approach where each layer is tuned and optimized to catch a certain type of meat.

So, we will absolutely recommend doing a multi-read verification modules. So there's another start here. 28%, you know, companies have approved agents and shared controls. A very few shared controls. And 5% are operating in Dr. Kakis alone. What are your thoughts there? And, I mean, terms of, so I thought there's so many companies where a couple of months ago, and the biggest worry was there were a lot of there in your team to go off and play around with native, and the guests were a place where there were 100s of 1000s of agents in cases.

They just didn't know what they were doing. What did they didn't actually do? They were touching all of our systems, accessing all kinds of data, maybe in the current production. And so a lot of enterprises think about concerns like, between the ancillary tree, being able to track what's actually happening. And then's either the 3 biggest things for a lot of money are other than about control, I thinking about permissions, and how do you think about the sandbox?

Like, how are we making sure that the agent isn't jumping out of the sandbox and doing anything? Yeah. Yeah, we, I, Sonar, we call it guide whales, so instead of guard whales, we're thinking of calling it as guide whales, where we guide the agents to follow the rail tracks, right? A specific park to take and prevent them from going out of bounds.

So when all the time about like. So it's very, very important to have dime rail for an Indian, and it's about the regions that you work with. So let's we come into a globe now, and my timer is doing, we just have a 2 minutes left. Let's go get to a lightning rout. One sentenceonse for each of these scurches and you've seen the questions already on the slide.

So anybody non-sentences? as long as the time of its light or dark factory for most them by end of 2027 yes or no. I think we're going to see a life factories with some dark corners. I don't think we're going to get everybody through using dark backory entirely, but it's gonna be something most I would get I'm probably would do it the the.

All right. 2nd question. Should agent written code be labeled in the BRU? I personally think it should. Historically, we've felt a great deal with ownership around our code, pride around the fact that, hey, I wrote this thing. I'm putting my name on it. And it's dropping, like, we think about this a little bit differently. We, multiple the point where we don't really mind, you know, the clause is like labeled as, hey, I'm the one that wrote this thing, because we're a little bit more focused on the outcomes and making sure that the code, the features, like what we're shipping to users, is the right thing.

And so I personally think it's fine for the code being written, labeled as being coming from an agent. And that can also help us with things like figuring out, okay, well, the agent wrote it, what are some of the constraints and extra checks that we need to keep in place? I have the same board of view. I think in the short run, at least in the foreseeable, you know, 6 to 9 months, a BTO label that we are, there will be a policent in our in our factory.

We do want to know a tracking, and it's also important for the financial customers here in terms of quantity. I think, you know, if you label it, you know who's writing the code, because we are, at the end of the day, you can account. Yeah, absolutely. ability is the most important part here. Like, we still label it, who is the owner for this game?

I might have kicked off a lot around to play a piece of work, but I'm still on the book. If something goes wrong, I have to look at that. Yep, the keyboard. Yep. The next question, actually I'll employ with here because this is the leadership session. once you know a junior developer or leaders should build on this here. I think that you should push your teams.

If you're a leader, you should push your teams to really take hard level verification means. How are you already approaching things like testing? What is the gap between that? And you getting to a place where you're very comfortable with the age of being able to sign off on the road being good enough to murder on their own. And so figuring that out, if you're a junior, it's the other side of that, like actually getting more experience, different flavors of tests, whether it's like end-to-end test, property tests, et cetera.

And the last, you actually not following the rules, you're going beyond one single, but I suppose. 30 seconds left. We could go. The agent opened the PR. It has saved too much when you have full confidence that he's going to learn about, or that you've mitigated how it's much impossible. No. All right. Here's my last flight and then we drop it off.

So what's the great teams that are shipping fast but not shipping blind? I think that's 3 key take away for you, though. writing quote is the pastest part and the salt. It's strong renewal verification for all these scenario, but it's just that. Fast to right has not passed to shift. You have to basically found what is getting worse, looked at what is getting worse and make sure it doesn't escape the sandbox and do things like that before it gets into the produ.

verify everything. And autonomy is earns. you people get to software facteries very soon if not next year. You need to put an independent automated verification inside each loop of your pantry. Make sure that you can trust the output that the factory is producing. With that, I'll wrap it up. Thanks for attending us talk today. ansociation with Ad. Again, having appreciation taking the time and joining us here.

Thanks for having. Visit us at the Big Red Bull, the solar boat in the expo hall, if you have any further questions, I want to like to come over. Thank you again.
