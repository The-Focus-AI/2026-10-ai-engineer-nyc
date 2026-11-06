---
title: "How to build an AI code review agent: from the creators of Greptile"
speakers:
  - name: Daksh Gupta
    affiliation: Greptile
room: "Shannon Room (NY Ballroom E)"
starts_at: "2026-10-13T14:55:00-04:00"
ends_at: "2026-10-13T15:13:00-04:00"
format: "talk"
recording: "2026-10-13_1455_greptile"
duration: "18m 11s"
source: "voice-memos-transcript"
---

# How to build an AI code review agent: from the creators of Greptile

### 00:00:00 — Code Review at Scale: Signal vs. Noise

It's both my texts of the cookies. And by reviewing testing these for us, we reveal bugs, logical errors, code of quality concerns. Primarily from getting married? Now, do you use that to scale many 1000s of companies use from higher every day? By one% of all, under costs and get help go through us. And a variety of many from high school bases, whether it's Dakuda, Coda, Zenidia, or the wallet for basic conditions, and many others.

And every now and then we meet a company where you're actually not the right code review or code testing on it for them. Their needs are so specialized, it's so easy apparent, but it's actually more beneficial for them to build their own. And when that happens, we tend to help them for free. There's 2 reasons. for this. One, we have a lot of specialized knowledge about how to do this really well.

And second, we get to learn a lot about how we consider customers like those in vision. And in competition, RSLU, what means on damage, and how to build a really great AI code of religion to the south. Now, there's kind of 3 things that people like about our time. I'm gonna talk through how to implement those for yourself. The 1st one is Corpus Come Next.

When customers use graile on their photographs, they find it really understands their coaches. As a matter of fact, before we were a quote foundation company, we were to code this contacts company. We were teaching language models from 2023 how to understand a very large code basis. And as a result of that, we got very good at indexing code. The 2nd thing that people like about repellent, it runs your code in the sense it spins up your stack in a fully loaded dependency, your standbox, and then clicks around, it has things using computer use, or the pressure has the API involved.

And 3rd thing is we're actually very efficient allocators of events. We pick the right model, the right quantity of inference budget for each subtask in the review and validation process. As a result of that, we're able to get a lot more performance per moment than an internal tool code or any competitive code. So there's kind of 2 reasons that you would want this presentation.

The 1st one is you want to build your own review agent. And the 2nd reason is a bit more subtle is if you're trying to pick a review or testing agent for your company, and you want to understand what makes a good one, what makes you great one. All right, so let's start right. Now, violation, you are part of the platforms in your company, or you're just the local AI cyclonic member of your team, and you want to build the review validator of your company.

I'll be running lots of code, either a high pudding, you have, of course, engineers, high coding, some of them a little too close to the sun. You know, part of the people very good. And the new problem is the new model, violation, all that. And so that's what you mentioned us. The 1st thing that you should do is you get yourself a sandbox.

There's many companies here that will sell your signbox. You can also just use firecrop or something like that. And you'll want to put an agent in that sandbox. The Asians can be correct, circled, personally, a recommendation involved independent for reasons that are going to do. So you can use something like open folder pies, right? source. And you will need to then connect your demo, where you have, have your website, send it the contents of a Florida class when the forecast is opened.

The agent can have some type of promptage says, hey, review this and send back some B back. And then you can wire that back using 300 units. Really. In fact, many people think that geology takes in order of the issue. 's few things that are gonna go wrong, they try things. What will happen is you will, in fact, have a polarivascal live, the contents will be an agent, there are 5 minutes later, you will get some feedback on your Gold Coast.

But here's what's going to go wrong in the time they're taking those. The 1st one, you're going to miss a lot of problems. It turns out that actually bugs are interactively not clear. In fact, I saw a feat not very long ago, that said that bugs are fratly, but assume you will never have a bugs in a particular piece of code. The 1st thing that's going to go wrong is you're in response.

Of course, that's the one thing that your system needs to do is to prevent at least very catastrophic outages and is it. Second thing is going to happen, it's going to miss context, and it's going to misunderstand parts of how you put baseballs. Maybe you want to understand where you're going, with your code base, the 100 times, because then part of it works, it maybe will not understand how, but if the libraries works, it's possible you're one of those companies that never recovered from the microservices apocalypse of 20 times.

And so you just have 1000s and 1000s of repos and you have to have context all of them to be able to operate. So that's the 2nd thing it's going to go. The 3rd page, it will be very expensive. I think even a very surprised place. So, Generally, from people who see how to do this, they'll find their understanding between 3 and up to $25 per post, under viewing it, is important.

We focus in add freeway fast, very high clean but very sens. The 1st problem you'll find is nitvicky comments. Let's matter is really my thing. The big comments are technically correct, they're overly manic. There's 2 things that go wrong in emission times. If you are as a human reading those comments, you're very annoying, right? And they avoid it by both, you just see lots and lots of times going to be kind of annoying for you to just read through them, figure out which ones are just minor salistic complaints, and which ones are actually kind of strongly common.

The 2nd thing that could go wrong is, you know, crack your cookies, because typically you leave the new age work, you're going to leave times and get them, you're including these and picks them up and results, including these, you want to study, if you look at review concerts, you address all of them, and you'll end up with extremely, painfully defensive code, as you found in putting games are, particularly as used to writing.

The next thing you've got to go wrong is that every time you run a review agent on the same photo pass, you will somehow find new bugs in the sense that it will keep catching new things in the photographs. It's very annoyingly and will do, like I said, bugs will appear to be practically invited. So the 1st thing that you want to do, the lowest time group, as well, optimize the prompt.

We started a very simple problem, something like, review this ER, and then output the comments

### 00:05:53 — Iterative Architecture of Greptile's Review Agent

in GitHubs, EDS, even more. Generally, there's 2 themes in ones. Look for specific types. Exactly, it's written in X. And actually you want to orient your thongs around. You want the acid or specific contact, you kind of do some internal gain science on existing hydrogen and incidents that happen in your code-based, and figure out the checks of bottles, you know, the highest intensity increase.

create a catalog of them, and then have your prongs look for those physical bad tests. It's not going to do, you need to express, you've had it by nippings, and not a nipple. And if you see anything from asking why there isn't 3 years of events. I'm pretty sure it anymore. Why Eric handling is on a slightly shocking rate. Now, the thing that will run into you when you change these prompts is when you change a small thing in the prom, you'll have a really big impact on a number of comments that you're using to write it for purpose.

This is quite scary because these don't really know if he's missing a lot or not. You don't really have an actual. The foundation is a really good reviewer, Astra, and can tell you about the presence and bugs, but unfortunately, you can't tell you about the absence of that. That's the term limitation of. And what makes this particularly difficult, our mouths are extraordinarily rare, and getting better on there.

Not French hour, air fines. Only about 100,000 water costs and they generally have traffic buggage, right? running a 1000 l of co cr off webons. And so because these bouts are very rare, you might release a version of your agent that you think is very good, but it secretly gives us a catastrophic body in water past. You wouldn't know for a long time because you don't produce those about very long.

And that brings us the 2nd improvement. You will want a data set historical yard. This is relatively easy for one of those companies that very nicely catalogs every time something goes wrong in your cookies. If you have that, you have a list of polar paths that have caused allergies into this mass. We're going to catalog them, and then essentially have any version of your video agent run through those and see what frequency we have so thoughts.

Now, this will allow your team problems a little bit more content. But at the same time, the interesting thing about bugs is in a change of world, the topology and quality about changes of time. And so you need to have a real time on game isn't. It's tricky because unless you have 10000000000 quarterbacks, it's actually hard to have reasonably high coverage of other times.

It's true that part of the United States, it probably just repeats the prior mistakes, but increasingly, it's putting in the state. We're going to start making novel mistakes. They're failing new ways that we're not participating. And so this is where people start hitting it. Now, quick side note, this is kind of what we do about hyle, except we actually have a lot of coach, a lot of companies, and we can test to pass a very, very large part of the other tests, and therefore, in food, Asian is very complicated.

It's one of the reasons why we're able to eke out little bits of performance in our audience. It makes that internal reunions. But you can get decently marked, especially when you're a particular company, you do this with your initial brain. The next thing you want to do is longer. So, for, you give anyone who has asked, my software, this year, in San Francisco, ash, A engineer.

I talked a lot about the ways in the community is, yeah. And it started interesting pattern research is that the typ of monster these psychod models, the Cuddics model actually my different other. And they're different in a number of ways. An example, cloud models are something like 3 times more likely increased one off errors than GPT models. GT models, on the other hand, are significantly more likely to increase all 5 passes than problems.

And these are all the starters asking the post training. as far as I understand. Now, to read this, you find that if you're using the same model, to review the code written by same model, you actually have relatively fewer about talks, because they feel the same way as during review, what they do during program regime. And so much input more, if you do smart code to write code, you want to use the GPT model to review it.

Now, doing this is so much reform for EDF in highland. I'm quite truly the last one. So, if you're using corregated, you'll notice that he's some type of fingerprints to tell you what's coding unit is used for a particular podcast. For instance, codex, so meeting branches in aquodex stash, gradually important. Or, Claude is good, right, co-authored by a lot of fields, which in my decision.

Right, even the science isn't true. In final training, when you haven't decided, you say a ranch game, but there's some other reason that a different thing is perhaps used. It's significantly hard to figure out personalities these considerations. You have to have summed up of your state to figure out what the city jersey wants. Often you might have, in front of a catalog where people report directly into using these things.

You have some kind of inflammatory, somehow, your, that machines and your engineers. We found this 10% higher cash rate people. It's nice not very small, but yeah, no, I understand it, you know, it's honestly actually for a walk. It means that there's essentially a higher chance that something go wrong, if you're not using more emotion. you might catch. And so we highly recommend that you use some type of modern version in your processing.

The 3rd group that you made is glorious context. Now, this is something that I forgot, before we were doing quotation, we were doing all these contacts, we were trying to figure out better ways to drag over radar school bases. And even today, people consider correctly effectively solved all of Kobe's context. I think that's not fruit for number of meetings. One, grab is extremely imprecise.

And second, it's very expensive. The decent sense of scale, single digital percentage points of GDP both last year, very first. a very large inference the coding agents. And if you actually look at a pretty good trace, the vast majority of token of use by coronations are, like, all the same, rap, proudly, hash, right, for the nonmarkets. That means we launch 0% of GD growth, is rap probably massive.

That's very bad. And this thing is graph is very precise. Reading files, a very large quantities, and I don't know, it's perhaps a mid-verse incentive for companies paid by the token to figure out ways to burn the token. But you so you'll find that you'll need to use slightly more surgical methods by figuring out where you should be reading. And when we do this, we produce an internal model base, or essentially check across the target base, all the different parts, catalog them.

And the index saying, okay, well,

### 00:11:52 — Sandboxed Execution, Context Indexing & Evaluation

this is authentication, here's my words, here are the flows, here's diagram of flows, here's different problems. Well, example, where cookies context matters is, for instance, you're trying to catch an alpha class. It's actually very difficult to figure out a non-pact as a target. We need to have a pretty concrete understanding of whether you're an antique environment, you mean, that kind of cool base.

And that's what you should do. And so you'll find is that you need some type of, out-based context when it is. Yeah. I've been very centered around the concept of box, but wood can be very, very bad. For one, it can be terology, but a 2nd, you can just not fulfill the stress end of the offer. Recently, I saw a post that said that people are increasingly slack in their ID.

Now, I think it's a little funny. At the same time, there's not that much, it's, we expressed intent to any slack message. You're only saying maybe symptoms or two, if even, asking if you want to make something, which means there's a lot of ambiguity in your instruction. As a result of this, you might find, the putting it is either misinterpreting your instructions or just to videos and you can know exactly what to do.

And so your correct code you can actually I don't know. Now, one of the reasons we find this is by doing agents increasingly for context. We find the 2 types of contacts that matter most are dogs and pigs. And of course, the hobbies would be a hobbies in extra in all cases. You can remember to be far, if you give it access to your geo engineer, and then your confluencer notion, or whatever it is that you serve us.

You'll find that there's a lot of tribal knowledge, that some consciously helping you increase our code. and you have usually do the same thing, it feels like they just don't know what's happening. And so you underestimate how much depth and knowledge do yourself have. Now, the way that Kapala version of this problem is you actually just intrudates all of these context sources with a living wiki.

This wiki is essentially sort of world model of how your company is. It's everything there knows value. everything he knows about your application, to production manageries, involves everything he knows about your roadmap, from your documentation, and your video tickets, and so forth. And if you use it this way, you supply context, both making the Asian form context aware, and making it sports are just, you know, plastic, it will never be a file that it needs to be.

Last thing that you should do, part of something for now. The next thing we should do is aton assassin. One of the things that we think about a lot is that, virtually, you actually just, you might be able to read through a bunch of change files for a react code, and you include it. But in documentary, it might be, for instance, here in Ohio.

Now, this is one of the more techly difficult com software. With a view process, my time is we essentially build these dependency ridge sign boxes, which are completely complicable virtual machines. And we have customers, we work with them to essentially spin off their staff in these sandboxes, and then brought files, Asia, uses computer use, it has damage, and. If you haven't paid attention, the computers have gotten very good, and it's, like, far better in these new generations, the G models, the oldest models, analyzing ingredients.

For the 1st time the end 2A, the near resultved. The thing that you do, though, is you document all the flows of your application. And exactly, you need to be able to have a sufficiently simple bill script so that the agent can spin up your sack in your arms. You have to afford one engineers in color. Okay, do this. We found this one of the trickular parts.

And that's of course, you have very good dive boxes already, in which case, congratulations are a good side. So, this is an ad I mentioned. but yes, you'll leave that box, you'll need your branch and pen where you're running the app. and you'll need some time to full map that says, listen is the off code and then this is the sign code.

And easy this, you need to now attach your code, I'm saying, and use vision now to say, oh, this button technically appears is actually hidden on iPhones or it's not in the 1st fold on a iPhone duo, it's like. Now, if you all this, you'll find that the costs are still quite high. It can cost you anywhere from 30 bucks to 15 to 20 to do a single overcussion.

And the thing we want to solve for now is huge cheaper models for some things. Now, to me, our true models are still generally speaking capable of the ones as well. This is a good room from time, even though there are banks high. So, our shooter today is about 20% for your models, for the most critical tasks. And then the long deal of token, there is explored for a, violin, and so on, views of varieties on it.

And so if you do this, you actually reduce the cost of running your review agent, it's quite passive. So this is sort of an illustrative example or video, which is, if you use a small model for final contacts, We'll use a very likely computers model for testing user flows. It'll be a frontier model for things like analyzing bugs, a kind of review process and for submission.

In practice, we have actually 20 different subpaths, and each of them has a very specific size models that you used to. And we have some research team is constantly iterating exactly what normally means for the past. You probably get 78 from the way there using something that's time where you just swap out very small tasks. Now, this is another example of your new health tiring energy section.

You don't have a good data set, you might be able to have trigger how to be replaced a lot of different some Asians with smaller faster models. And you won't know that this Asian has, you know, kind of the worst catching body. you can only find out when it misses something then. And you also find that you can kind of combat this problem of overactive file rates using the G model that essentially looks through all VR context pieces and figures out which ones actually should be included.

In theory, you should give me the decision model of this, something like January, the decision DPR, to effectively rerankings on all the different things and deciding what should be, shouldn't be living in the country model. Which is, in some ways, most expensive, it's scares. If you know these things, the memory books are actually quite far in building your own good divisions. And if you do, these are not.

I know as Dakshikar, how to come. I love to help you. And if you choose not to build it, then, even also, these are one, which are free and in person. But thanks so much.
