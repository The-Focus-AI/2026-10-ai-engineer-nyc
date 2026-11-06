---
title: "Balancing Acceleration and Safety for AI Agents"
speakers:
  - name: John Feminella
    affiliation: Two Sigma
room: "Simons Room (Metropolitan East)"
starts_at: "2026-10-13T09:36:00-04:00"
ends_at: "2026-10-13T09:54:00-04:00"
format: "keynote"
recording: "2026-10-13_0938_Two-Sigma"
duration: "19m 16s"
source: "voice-memos-transcript"
---

# Balancing Acceleration and Safety for AI Agents

### 00:00:00 — Balancing Innovation Speed and Institutional Trust

Accelerate innovation without compromising trust, please welcome John Feminelli, SVP of architecture at 2 sigma. Hey, everyone. All right, I've been curiously, now, it's my water over there. My name's John Pmanella. I work on the AI architecture and engineering SCCM, since I had time here in New York. Before I get too far into things, I have a legal disclaimer slide that I have to show you that says 2 things.

One, I promise not to sell or market or offer you any securities in any way that would stop. And so you do everything, and this is my own opinion, and not the opinion that you signal. Thanks for indulging me if I don't say those magic words, the 5G microchips implanted and they will explode. Thank you. So that slides a big example of actually how our industry is regulated.

And as a regulated company, with lots of controls, I think one thing that's always interesting to explore, what happens when controls fail, because that gives you a good idea about why the controls were there in the 1st place. And so I'd like to tell you a story about that as showing you on other people's lives. After August 2020, a very interesting contract clause suddenly started showing up in a bunch of commercial loaning, everyone else.

And this part essentially tries to prevent a certain scenario from happening. And it's complicated but I'll explain it like this. Let's say that you're a lemonade standard dismiss, and you borrow money from a lender, that much money to do stand. And the bank that's overseeing that transaction is in the middle between the bar and the language, sends the lender all of the money that you owe in a catastrophic decision.

You probably be mad, I want the money back, but the library might also say, no takes, you take us back and we're all good. So we. Something like this happened in August 2020. Revlon, the cosmetics company, had borrowed money under a big 2016 term well. And that loan was split up into a bunch of pieces across 300 plus winners, pass, transcribed classes, you know, those other things.

In the middle is Citibank, Citibank. The agent, the standard transaction means that you're performing the plumbing that connects the bars with the lenders and managing the lifecycle of the lung. So, this transaction, where, on K City, and then city pays the letters, a city is not lending its own money. it's just in a mineral of moving people's money around. So here's a plan for August 11th, 2020, where Fong would pay about 8000000 bucks that accrued interest to both groups, and the lenders who would fall into this new facility.

That's an exchange of paper, not cash. So the remaining lenders principle would stay put. And the idea here is that only interest should be coming out. The principles should not be really at all. In the bedpad, a piece of internal processing software called flex view. Isn't that fun? Everybody's operating. So it reflects you, the easiest way to do this kind of transaction is to pretend to record it life by long or paying off the entire loan.

And that favors the correct interest payment calculations to everyone. You can probably ask about to happen next. So they're supposed to send the principal portion to an internal wash account that you own as the bank. So it is closed and reported correctly, that never leaves the bank square every time. So keep your eye on wash. What was supposed to happen is that the box is labeled front and fund and principal should all include the washing account number, and they should all have a checkbox, check next.

So unfortunately, it turned out that was what needed to happen, but for various hard game reasons, the boxes were not checked. And all those flats view pops up a warning verification, it says, uh-oh, why do you gradually debate? Are you sure you want to do this? That was black money was, it was silly to me, because they were making the interest payments.

So the 3 approvers, you were supposed to approve that, looked at it, and said, yep, that's the right thing, it's supposed to happen. And although that morning notification pop up, this human operators carry out the transaction overote that. Remember, grandma was making that interesting. So the principal never went to the Washington, and instead, lets you send the entire outstanding principal of the loan to all of the 300 lenders, about $900 million instead of $800 million.

So, I mean, like your God, the amount that they would have been owed, if I wanted to pay the loan in full. but didn't want to be off the line because they wanted to hold onto it's funny. That was a great deal with the lenders because, remember, Bam was in trouble at the time. So as long as we're in trading and face value, and getting all your money back on a deal that you thought was only worth ¢60 on a dollar, is it waiting over you?

So they didn't want to give the money back even after city college and said, these episodes of state were money back, and their argument was. have to get the money back because you paid us to follow, and that's how it goes work. We eventually paid them back. And just because she paid it back at a different time, then you were supposed to, doesn't mean that reached out to give it back now.

And so to prevent that from happening, emotional only weakness, everything we are starting to, including a class like that one. So was it payment error at a bank, have to do with AI? Well, the bank had this procedure, have these controls, and I really did what they thought the right thing to do, but was. But as a problem, I want to talk about where the rest of us talk, every day, we're getting real Asians, real autonomy, over systems like FlexQ.

And how do you prevent accidents like that one? I'm either or happening without blocking everything down or just hoping we'll get tough even if they won't have. So here's the question of the issue. You can't really know what it means, but an agent will right he's noneterministic systems. And that sounds scary until you remember that humans are also very successful, so they're going to make states soon.

And so most firms don't choose to say, well, in order to reduce the risk of human state in the state, we don't like lock them in rooms, and then we're talking to each other, and they're all gonna double check. everybody else's work, right? We allow them at a certain amount of autonomy along with this orthographic people. So we give them boundaries, visibility, and feed proof now, big sisters and controls, it led to be your jobs, actually.

So in this sort of model, safety and innovation are not, obviously, negative spectrum, and you must trade off what you're, you can have at the same time. So I didn't even have your gig and you, too. And when we were thinking about

### 00:06:23 — Risk Taxonomies & Guardrails for AI Agents

my controls, we wanted to apply to agents. We also looked at some approaches. It didn't work for us. We don't want to stand box, lock down everything. It's a standbox but nobody able access to systems. This same, but it's not very interesting or useful. If you let the agents go around and do whatever they want, that's, you know, maybe powerful and freeing from a cognitive perspective, but the isolation is very big there.

I think that was generally not suitable. I make their advices. And then if you just have policy documents that HS look at or that are part of your specification for the prompts, that's also not very enforceable at my time, and here is you that will be part of the enforcement rituals. So it did work for us, was thinking about what makes the controls, the gas, both safety and renovation at the same time.

So I have to combine, you know, reason stop problems, but don't hinder folks from operating correctly. Do you have a number of these switch photos, but today I'll talk about 5 times. When I say which tools here, what I mean are the guardrails and sheer capabilities that lack teams or move in waves that don't hinder what they're trying to do. And we want to, we don't want to reach some chasms that we need to pass to, to let people get their work done, cook for, and then make everyone wait while they build the bridge together.

So these controls are composable. Each one does one job, and then together, they last run agents with real autonomy at an appropriate level of safety. So the 1st problem is that agents were showing up everywhere. We have big games with lots of agents running. We have small teams in the pew, we have individual people running stuff in an uncontrolled way. And these come in every shape, they'll be right.

Shackpots, the baby, at least these are nervously together, in a spring and sign, high Tod, to be cool, though, we can start, especially, you know, so where tools are bought. But it's hard to answer when you look back, a few simple questions, like, who owns this? What tools does have access to? what should be doing? what should not be doing? If you can't answer those kinds of questions, you can't get random, then you can't really also reuse that.

So you're tempted to build multiple solutions to the same file that you don't know about what exists already. I mean, the firm can't also generate if it was in any kind of legible way. So one thing that firms sometimes do hear is at some kind of gig, like don't let anything run until everything is registered and food, and it's gone to this very onerous process.

And that sound safe, but if you look at what it does, every idea, even some simple noted experiment, there's no wing in mind behind something that's really escape. We don't, you don't want to subject everybody who's, you know, diversity of agents to exactly the same process. So most people are going to give out, or they'll just get pushed to some shadow, AC, flats, gathering, path, that is less visible, and we don't have to see anything at all.

It's actually motivated the 1st control is an Asian question. You can't go around, you can't see. So the Asian registry, the Asian slash, and it registers the trees and discoveries to key backs about Asians, that we want to know for any instance. So those are things like which tools it declares, what NYS is going to talk to, which product does it belong to?

And humans, other programs, other agents can then use the Asian registry to decide what's available at the firm, whether that's useful for them, and to go use that as a source of truth for other questions. So it doesn't require extra equity on your artists. It's when you use one of the arts improved, Asian building frameworks is automatically registered on the information support there for you.

And if you want to do a manual registration with a certain, do that. So, the 2nd problem we have is that now we got all these agents doing all these things. We quickly noticed that what they're doing is really different. And that means our agents carry really different risks, right? So I think that summarizes to our linears, I guess, is really different than a production, deployment agent, and touch a running system.

And if we use the same, we try to use the same review process to cover all of these agents, then Paris Asian is waiting on the same queue for weeks for human review, and if people are gonna wrap around slow processes, then we wind up in the same situation that we had before. So again, you might be interested to say, being answered is something like really detailed, how you manual review might all be certain constituencies, right?

Again, I feel safe, but now we've got a trivial summarizer waiting 2 months for the same sign-offs as an HFB discussion production system. And most of them are good in HIA, most of the ones that have value right away start out as small experiments. So you don't want those people to await in the same mind as the stuff is such a production, right, right?

So the reviewers are drowning in these, like, low, where it's progressed, and the highness ones have to show that attention. So we don't want to straight away that speed, you know, everything. So again, that's not every agency, it's the same review. And because both cases are purpose built, rather than open-ended, why is it open-ended here? You can imagine coding agents like pi or pot of many volt in that when you start typing, pi doesn't know what you're about to ask.

It doesn't, it doesn't circumscribe this purpose in any way. But most of the Asians that are deploying enterprises do have very specific purposes. When you're engaging in that agent, it's to do something specific, that's well known in our ownership. So they have a very specific reason for existing and very circumspect purpose. And you can tell these agents apart from each other by looking at what they declare, I find their tools, the pendpoints, they access, the controls, etc.

So the 3rd problem is that if you know about your agents and what they're doing, you'll bring the notice that many agents don't talk to each other. They don't talk to just one thing, right? Just one capacity. The more open-ended, the Asian has more looks like a clock lower high. or it can do a variety and a diversity or different things. Call an internal API, run a local web search, that sort of thing.

And each one goes to a different, opening a different door to a different kind of rest. And if you give an agent, another title in it for a role account, then you allow for damage and something that's just going to be a part of webpage. The question is not, can this agent do apps? But what's the granularity that

### 00:12:41 — Production Architecture at Two Sigma

we need to solve or for the agent to act successfully? And again, one tempting answer is going to be heavy-handed here or to give every Asian the same short allow list of stuff that seems to do and then block everything else. That's safe, but it's also useless. An agent that can't that can't search or can't follow an API or can't do any of those things without asking somebody 1st.

Can't really do the work that it was intended for. And he, entire, give up on those HMs, when they find a way around the wall, and both atoms are constant. So why ended up blanking block on everything, trades away the innovation that you want to reserve, and the boys being a real physician about things. And it's author of John Chen, a shit in Barbara State, but that's not what shifts on.

So the fixed year is to let the HS declare their purpose out front and say what tools they're going to use or what tools they need access to. So in a sense, here we might say that the research summarizer is going to be allowed to use a web tool to access research. But for a release deployer, agent, we're not ready to allow them to do that because they have no reason to use that tool.

And so they try to ask for it, they will get a price problem. So you don't need to make tennis position at every tool. the agents just have to say which tools they want, right? And you're, as the Asian honor, you're in your best position to say, I need these 4 things out of the biometers that are available. So the way we need to enforce that is that when patients run in our managed environments, they look at the rescue we talked about before, to look up what policy is applying to, at that initialization time, and that policy is translated into enforceable statements, like, which I might be allowed to access, but those are you allowed to access, what other types of resources are available or now available?

And in this way, nobody's trying to say it every time they need to change the access. Nobody's going to talk to IT or some other outside of your team. As long as you conform to the risk or if you talked about before, and you're in the Asian registry, you're, you're. So this is how we keep the cost to team. It's really low for deploying, noting, running, issues.

And the same controller architecture works in a variety of settings. The next thing we notice was the teams were building a ton of different ways to evaluate agents, and every stack was different. And some kids don't know anything at all. Sometimes you build, like, this really detailed snack, right how your models work, sometimes, sometimes there's nothing. And I think in general, we'd be upset if teams were not writing unit tests, right?

And we consider any vowels to be kind of the same thing. If models are changing, that's like a fun time dependency, then your application has, and if your agent is going to change models, it doesn't know without any vowels what's going to happen to its to its outlets, it's a quality of its outlets. So again, one tempting answer here is, let's have some kind of central evaluation, methodology, that weighs for people, you know, speeding, and they sign off.

But now every, like, prompt tweet, every one line change is going to sit in that safety. So we don't want to put more decisions on more reviewers or things like that. We don't want to take it, we have iteration. So, again, when chips software, we got units has, so HSD, your nominations for the same reason, and we want to provide this stuff at the level of firm.

That's going to be the same for that you need. So, TA, right, eating out, TV, or anything else? they're both going to have many of the same features. So we want to have one sheer approach to how we do evals, and I'm a sure approach to be something that's run by the firm and available to every money or do anger emails. So that covers all the common parts of.

All you've got to do is just write what true evaluation. And finally, maybe you'd have the experience of being asked to approve lots and lots of individual agent actions when there's a human in the loop. That's fine, in a small scale, but once you're operating agents in parallel or in production, this program is completely onerous and review requests, I mean, bashing anybody can be expected to improve them.

And after the 1st few times it is happening, you succumb to rebupity. we just see the SS, yes, yes. And eventually, I think yes on something that's, you know, actually, you, you don't want to, like, yes, 5 reflex, but that's when you have to activate. One reason, for example, I guess, is earlier this year to graduate an AI research lab, told her open claw, I need to suggest emails, leave number Abox, then wait for her approvals, but her inbox was so large, and eventually the Asian combat this context and lost the part that said, wait for my approval.

and then the leaders might emails and didn't stop and she told it to stop under. So it might be tempted here to make a human improve her reaction, but that's not the right way to do it. A better refer to select these independent, conservative classifiers, make decisions, about regime calls, and then send the person only the requests that are most important, the quests are most by integrated.

If you're saying, yes, 99.999% of time. And that's probably just a rule of the age to follow that request. You need to ask being a provision for them. And it's that it's unclear or a dangerous or potentially dangerous. Yes, certainly stat or is a dangerous denying it out right. So this is a way to not have to do all the review work all the time.

So we don't want to take the same approach for both explicit, like explicit rules apply. we want to determministic fast paths when explicit rules don't find's some ambiguity. You want to classifiers do that work instead. So putting those 5 pieces back together, you can read your registries, so if April every Asian's based a little in the day is created, you score each patients, so if you interview those in the right spots, you provide agents on dark mail so that they all be touch what they need, you share evals, matrics, or everybody who's reaching the same bar without making sure we invent the wheel, then by need, donor, your bedtime, to make sure that classification happens there and not somewhere else.

So each of these controls works together. So I'll leave you with one question. Why cars at brakes? It's not just your human stock, so you can go fast and stop seeing. So controls for our agents for the same thing. Thank you very much. time job out.
