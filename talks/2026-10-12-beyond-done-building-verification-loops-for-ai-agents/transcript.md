---
title: "Beyond “Done”: Building Verification Loops for AI Agents"
speakers:
  - name: Nick Nisi
    affiliation: WorkOS
  - name: Zack Proser
    affiliation: WorkOS
room: "Sutton Room (NY Ballroom W)"
starts_at: "2026-10-12T13:15:00-04:00"
ends_at: "2026-10-12T14:15:00-04:00"
format: "workshop"
recording: "2026-10-12_1315_Beyond-Done"
duration: "56m 47s"
source: "voice-memos-transcript"
---

# Beyond “Done”: Building Verification Loops for AI Agents

### 00:00:00 — Why 'Done' Is Not Enough for Production Agents

So what do we mean by beyond that, just to like jump straight into it? you probably saw a tweet about this incident that happened a while back, where an agent just started deleting production database. And in 9 seconds, everything was gone. That is what we want to help you prevent here today. While still trusting your agents and not having to look at every new line, you can look at every PR, like, this is where we think things are going and how do we get there, how do we make this reality?

Where instead of having that broken beast, we can have you calm, have everything work and let you, to some degree, trust your agents, but build that trust over time. On sale, so it's not just about preventing errors, right? But this is also what we're gonna look at today foundational to achieving true scale the interest of the. So I'm like you see, I'm an engineering manager at work OS.

I live in Omaha, Nebraska, and I've been there for about 2 years, and I do a lot of my kids. I've written codes since July 30, 2025. I know because that's the day I got back from Larricon. I saw PHP and I was like, I'm 3 AM. And with me, as my best friend, Zach. Hey, I'm Zach, I'm an engineer in the fighting IT 4 bus.

appreciate. Now, we had this up in the morning. This rainbow is your workbench. All the slides are in this repo. You can get it from here. You can also view it at workalift.cloud slash John dash Dunn. I know that's a mouthful, but the NP or the next PR code, I believe will take you there. Sorry, the songs that we're going with, SoundCloud, slash beyond done.

And I just wanted to call it out because on that, I'll switch to it real quick. All of the signs are out there. There's also a page for the workshops, like the exercises that we're going to go through. and so for each piece of it, you can go through it, you know through them your own time, you look through it later. This is a step by step guide to go to do that.

There's also a glossary, covering all of the terms, big and small, familiar with. Hopefully most people are coming out. But if there's any that you're not, you can talk in here. Oh, sorry, you can look at the dewalsory for those terms. There's also an ask anything button and you can talk to Iraq that's trained on this slide deck. and hopefully get your answers there.

But you can also just talk to a human. Yeah, we'll leave this up as well. We find that a lot of folks want to ask questions and whatever reason can, so be sure to check it out and get us. some cameras onto the QR codes. security would be so bad, I think. All right. so, when we're thinking about being done, good work, A is being done, there's lots of things that go into us trusting them, and easily the 1st one is just, is the number.

Because I knew what I would have written, did generate a 50R. and I go through that like a normal code reviewer. But that takes a long time, and these agents can come a lot faster than us, so we don't want to rely on that too much because it's, it just, there's a signal little noise ratio that starts coming into play, and we just have too much approach to review.

You're not writing any code anymore. And, well, less familiar with that code, so we become further abstracted away from it. So need to find other ways to do that. And there's plenty of ways that you can do that. you know, using tools like browser pools, like playwright, for example, to say like, hey, I have this website. and I submitted a form to submit work.

I checked that, and it showed me a success message. That's a great test to write. Not even knowing anything that I think about it, but it is something that Amy can use to verify their work. And they can self-report that. And you can trust us oftentimes, but not all the time. And so that's really what we want to drive is like how do we make it so that we can actually trust these report store code?

Absolutely. So, everything that we've got here for you today in this workshop, as they mentioned, is backed by Rico and is interactive. So, feel free to take an opportunity, but actually run the experiment with it, and take something back that you might, you know, use it for or at least, experience. Oh, in this, so, like, if you just go into the recover, like, are you doing it?

And you're PNPM, snack up, snack up? this is why I have a truck that's growing. P is my TNP. It will pop up the browser, and we can look at it, and we can see this midnight snack club. that we made. And you can play with it right now, and I can test this myself. Let me just put in my email address.

I'll put in Zach at Spam. Yep. And look at that. success. Save the email, the email is here. I can see it. If I had a test that was looking to confirm that the email in on the page, it worked great. So that's what these examples look like. You can kind of see it as you're going. But if you reload that page, just like this, there's nothing there.

So even though whoops... I would be off therapy, kind of, and wickedly with a rant, and they were off to the north, so... If you reload that, it shows that nobody's here. I can't drive the ch apparently. And that's because it did update, but it didn't. So we didn't have any kind of verification. We're just checking UI. seeing, oh, did that actually do anything?

And yes, it did do something to the UI, but we didn't check the other half. and so it was never persisted. And we want to study now. So sorry you're not signed up later. Yeah, I think this is a really critical point. So, just show of hands who in this room is building a ton of agents, just to start with the 1st question.

That'll be, like, more than that. How many boats are running multiple terminal tabs, or multiple chat sessions? Hopefully, just like everybody's cut to their next one person, right? And so this is what we're all experiencing, at least what I'm experiencing, I'm basically curious, and this is the 18th, you know, way of work that you're driving today, and you have, like, you know, the frack of attention to actually spend on it.

These are the subtle bugs that will creep in because the agent's like, yeah, I know what you said, the code looks good. It builds and runs and test pass, and it's still wrong. And so what we're gonna ask an explorer is a workshop together is how do we actually fix this problem so that the agents that were now all managing is like herds of insane COVID machines?

I can actually figure out what they need to themselves and what they need. You know, so we are not really looking at the code for this. We're not really going to live on a coach too much for this because, like I said, I saw PDP in this case. So, it won't kick on me. But all of this builds up to this great quote by a famous potato on X called, Currently, Florin, Tan.

because has this one. Sorry, definitely, you can verify its own work. I mean, if you can't verify its own work, nothing else matters. Yeah, another way to say is that, and I think this is true in my experience, others as well is that we're kind of converging a point that verification now, especially as model king goalies advance rapidly. is one of the key foundational things focus on?

Reliability, verification, and emails, especially as we're starting to see more and more harnesses come online that have the concept of RSI or for you, precursor self-improvementation to them. It feels like we're shifting to a world where they all be making multiple sets of all of the bases, right? And in that world, how do you set the evil foundation? So that the agent actually knows what it looks like and can do those all times on its own.

How are we going to get the agent, the feedback at least? I'm telling you, it's all back. we're not gonna trust these agents to really accelerate our work too. It's coolistics. And so we need to solve that. In various degrees. And it's not just going from 0 to one, but integration and getting us closer to one to where we can fully trust these agents is the goal.

And I'll also just share that, you know, again, anecdotally, this is what we're all experiencing at workless. we thought to by I team was building stuff for other teams for ourselves. And there's just a night and day experience when you're iterating a co-base that has, you know, the foundation keybound in the place. So many times when we run across this, you know, the ability to actually see that data cannot do something correctly, in the same way that we were as human followers, right?

So we're, you know, as a man, we, the metaphor of us all becoming agent, artists, managers, as it is, you know, well done. This is how we ensure that each one of them

### 00:08:57 — Designing Deterministic Verification Loops

is actually doing correct work about, like, you know, they earning money and time, essentially. Yeah, be cool. This is the equivalent ends up saying, like, no mistakes, right? If you want to have some verification in there, you can't just, like, guess at what it needs to be. You need to give it clear, defined goals to get to, and give it away to observe and check those goals.

If not, Aiden's gonna do something and it's gonna spend some of those things in it, might get to the end that you expect it to. But there's no guarantee of that. Every detail that you don't fill in is in terms of an outcome and what you actually want to get to, it's just going to infer that or make something up. And that assumption that it makes may not be the assumptions that you make.

or they do were expecting because you're a rational, logical human. and you're just not align on that yet. And so, you need to have these connection systems in place to allow for it to observe. Understand what you want, observe that, repair that, and then recheck that. And I mean, just, again, I can't really throw my name back, that the tired way to do it is to have a tiny massive yard at one age of session is running through 4 days and say, fix this, fix this, make it better.

And what is working, you know, essentially is perfectly proposed, is decomposing tasks, really making, giving each past age of, you know, probably exactly what it needs to do to know that it is actually done. It's a fair final state done. And those will just go. I mean, we have people on our team that are 900 players a month and those would be like improving people guys for the soccer.

So, just anecdotally, it is, something that we all kind of have to take a step back and think about, I'm not approaching this code base anymore in a traditional way. I'm almost gardening multiple code bases and letting themselves hold. And this is something that we build and we hold our own tools too, as well. because I Zach and I stay productive at work class and how we get our own work done.

We've each built kind of our own examples of this and our own ways of approaching this. And we really think that that's like a good thing right now, clearly, really pacified on anything. So experimentation is key. Finding what sticks and then running with that. And one thing that we're both running with is the verification piece. So like deriving everything from that verification loop, because as it says in this quote here, for mine, status comes from records, not model pros.

So it's, you know, show me the receipts. Show me the actual tangible group that it actually did it, what I expect. Don't just tell me if classes it looks good because there's nothing to back that up. I need actual screenshots, videos, test results, smooth tests, I mean, all of the above, to prove to me without any other Olympic code, is actually doing what I want.

Because at the end of the day, I don't care about the code as much. I care about the result and what it's doing and what value it's delivering. And it can have bad go, honestly, and deliver that result pretty well. or a really good code that doesn't give me that result at all. And I need to find the right balance in that, which is...

getting the results that I want, nothing. as I've been doing this as well, I built a tool that I called Context or CTX. It started out as a cross agent, harness memory layers and rapidly experimenting as well as our, like, ChatGPT, plug code, pie, et cetera. And I wanted them to all deal to write and read from memories. And that started working.

And then the more than 20, the multiple agents and, you know, an average day of like 18 or 30 times off, the more that I realized, it might be an interesting experiment to try to centralize authority or verification in electric service. CTXes. Similar by that, the run of the public, the 5 code, initially, and it works. The start of memory, I was able to hand off secrets to agents without them ever seeing it, forgetting the credential.

And that worked too. And then that was an additional experiment, I'm creating verifiers. And the way that works is if agents are assigned work as we're all doing, they promise they go on and do that where they come back through the MCP connection to CTX and say, this is what I've completed. And I thought, can you please verify it? So let's say in the example of one of the workflows needs to verify that PR was created correctly.

And so that is going to run an evaluator on a known verifier. That could just be a simple CLI to start with as it is in my repo. And then that becomes a hardened piece that you can then use and then again, it's going to be how the AI and verifying that PR truly does exist, it's healthy, and then all the merchandise pass.

And only then will it mark that as those satisfied in the workplace. Otherwise, it will redirect to the we'll redirect the Asion. So these are the things that are still famous, right? And so again, an experiment, but this is kind of how we eat and trying to play around with this and see which patterns are interested and what works and whatnot. But it's also just kind of a fun time to do that by cooking because I require a weird pixel art across all of them.

So you can see in this case, there was a simple workflow, and one of the verification gates is that requires that all requests were burned. And so that work is done by the centralized Authority. It goes out and uses a terrifier, checks the API, or whatever the artifact is, and then finally delivers the status over your, right? Statmography, please. and references the actual repository check and the PR, right?

So simple example, you could imagine having standardized verifiers, library, or skills, or tooling that you share amongst your order. And this could be one of the ways that you start to build toward accelerating, you know, VRs and less and less. And then a similar tool that I've noticed called Riker. This is more like a engineering focused crocodile videos that's trying to be extremely flexible in how you hand work to it, but then once you hand work to it, its job is to babysit.

And so I don't want to have to babysit all the yards that I'm bringing to fruition. At some point, there's a like this level of diminishing returns for me and my focus on the work that I'm doing, because I end up just like babysitting the VR now, fixing the task, fixing the reviews, that are coming in. the review comments and things like that.

So I want to be able to get the idea done of like what we should be doing and how we can verify that work is done. And then I can hand it off to Riker. They can go do the work of, you know, making sure that the reviews are done, that when it fixes code, from PR reviews, that it's still matching our overall goal of working software in some way.

And then, can just verify that. And all of me back when it needs me instead of me having to babysit it. And so with that, it's just, you know, it builds a check. It figures out what tools it needs to run, it will run them. verify that they all pass. They'll keep that evidence and show it to me in different ways. and then decide when to stop.

So if they can verify, yes, it was working, we can now fix this boat, for example, we look them together and works. So it's really just keeping me out of having to be in the minutiae of shipping, being to like final 10%, and just focusing on where unvaluable as a human, which is why we're doing work and how to end up, it's an allergies.

Okay, so do this as a mental experiment or a thought experiment, if you will, let's just kind of show up and play it, or do you feel freaking out about how we start to think as a human culture, verifying a web app. but maybe no 4 times. What are the things that you would do compare? We'll throw some easy ones up here to get started, like, represhing age, the applications all day.

Okay. see a healthy, right? One of the responses I'm getting back from the guy, like, to the Facebook, so that... Mobile hosts, or local program, persistence in some way, console logs, things like that. Network. like you said, and like reading what's actually on the page, or the contents of the page, interacting with it, right? Yeah. And the reason we're saying this is like, this is really to set up the transition from we were the human developers doing this all the time.

This was part of our corresponsibility when we were in chiseling code, if you will. And then what is the delta between doing this? And then in the early stages of LM times saying, here's 3 paragraphs of text, go execute these instructions. The delta between those 2 things is the agent's ability to verify that it actually did what you asked it to do in a real application.

and that those changes in not break. right? Otherwise, you're just getting the calculations

### 00:17:30 — Guardrails, Sandboxes & Failure Recovery

that LLMs are designed to do, because they're trying to process the text. they're trying to make you happy. If anything can't do any of this just in the terminal room, we need schools to do that. Fortunately, too older, you need to add to agents now. And we just have to tell them how to use it or tell them specifically what we're trying to support.

When you do that, you don't want it to be just a paragraph of like, hey, do this, very, always verify the change in the browser. whatever that means. That's pretty vague. Remember to reload and check, that's a little bit more specific. Check that the data crystals. Look at the console for errors, getting a little more specific, but like that's a lot. To put in there, you can certainly do that.

what a lot of skills do. That's a lot of just like saved bumps do. But if you forget anything or things change, that can leave it up to a lot of interpretation. One thing that might be better is to have a script that can proof it out in different ways. so that you can just run that over and over and it's doing more of a deterministic check across a number of things, and then you can feed that out back into the agent and it knows exactly what was wrong and how to fix it quickly.

And it just closes that loop so that it's a much faster. And the agent can just spin that, run it again, check, verify, run again, and you'll see that over and over until there's nowhere. It's also a uniform. think about it, right? We know that all not partisan. So even giving 30 is the exact same prompt, you have, you know, sensible forbarians, and you're getting it down to a single command that is backed by actual bash brands, bash calls, right?

Like that's significantly more determinative. And totally, the folks, like Learn Tan and others that are cheating 1000s of yards offensively among them, building ambitious products that were not possible to build in that time before, have mentioned that this is the 1st thing they concentrated on that actually unlocks the velocity, right? So if your specific web app, for example, does not already have the spokes, CLI that allows any agent to own flexible functionality that you care about and verifying, then you're going to have a much rougher time, and an unpaid path, if you're using prompts, you know, alone, compared to actually, again, giving each agent take away to say, yes, I actually built that transaction performance, didn't cause any errors in the application whatsoever.

So for this workshop, we made a little tool. We've been running in a couple of times, but it's called snack. You can just run in with paint in that rebo. It's not meant to be like a reusable tool, but just kind of like a template for how you can set up this, specific for the applications that you're working on, and then use that as a way to tie into the LLMs that are actually working on that application with you.

And so Snack can do a couple things. Again, manage the health of the application and bring it up, it can take it down. They could run a doctor command to see, is it actually, you know, is the database running? Does it have network connection? et cetera. that quick drive or Netflix trip that it could do. Then it has drives. You can tell it to join.

Remember, this is our midnight snack waitlist, so you can join the waitlist. It can reload the page. It can reset all of the data so it can't find it. You can have it look out things, so take a snapshot, look at the network storage, look at console logs, look at it. Momo storage, screenshot it. One of the emails, all of the above.

and then finally improve it in 2 ways. It can actually won't improve command where it's checking for deterministic output of that, and a judge, which is using a system one as well. But you can give an idea of whether we're going in the resurrection. Just to, like, fully develop this idea. When you do something like this in a refo, that you haven't already had something like this or work, the velocity games that you unlock are not, certainly for you, right?

Is for everyone else on your team that then comes along and is also able to issue significantly more VR significantly faster. The significant take a saber, right? Or more safely so that, you know, everybody on the team actually benefits. Yeah, that's like where we keep harping on this meeting, like the foundational concept, no. and if you think about it, like, that's the only big piece of, it might gave me more importantly than your software, the actual application.

It's the way that you verify it, the way that you test it. the way that you prove that it works, because that is what you can use, potentially, like a lot of people are doing in terms of your life. You can take her out, like the bun team did, convert it to rest, go typescript, convert it to go. Not necessarily with the same level of LLM health, but, they did use all ones to help with them.

And then I think Theo just last week converted it to rust instead of. When you want that, if you have all these verifiers in place, then your search term doesn't matter as much, you can sort of write it again and prove that it works. And so, these tools give your agents their eyes, or you can think about it, like, the tools that your agents use, that gives it the body.

The LLMs, the brain, and then a way that it reaches out in interacts physically, virtually on your computer is through these tools. And so things like joint is like actually having it run and do things and then it can check. you see, you know, did I did that actually succeed in some way? checkch storage. reload snapshot, et cetera. And so let's just run a couple of these, and see.

I brought up our browser. And then I'll open up another browser or another terminal. terminals and run E, snack, snapshot, and that gave us a snapshot of the page. And as Jason, that we can see, if I put Zach at Zach at Zach, and add that to the page. Hopefully we'll see some Zacks in there. So that's a way that we can verify.

We can also do screenshot. make it a little easier. If that should pop up a screenshot, huh? There's no seats, right? So that gave us the ability to, for example, not just like pass this to the LLM and how to do interpretation on it, but like proving back to us, that's the end goal, right? It proing back to the human. Being able to take screenshots, the word Vegas, put those on the forward quest.

You can do that with the GH scale. Where is the actual bottleneck? Yes, you know, spin your wheels for 3 hours to actually figure out which part was causing the burgers. Yeah. So the real key here is that there's no, it's not just code that you can look at to interpret whether this application is running correctly, but you can build tools that will help you prove to you that it's working correctly without you having to read the code at all.

because this is all we care about. Is this what the user sees? Is it correctly rendering in this browser, at this width, with dark mode, with light mode, et cetera? You can run infinite tests on that and run them over and over and over again, a loop, which, as Zach said, unlocks your OP to move faster because if you've given the agent the ability to run those checks itself as well.

So if we run this, we ran it just like this, where we ran the doctor, and then we add Ada atexample.test, and then we check the storage. It there. We run, we check the story, it's not there. We would see local storage is empty, and if we run reload and then snapshot, we would verify that it is, in fact, simple. So this is the way that the tool itself could run in a loop, could check all of these things, and yes, confirm with it before it even gets back to us.

Oh, I see that we're not actually persisting this. I forgot to do this. And the agent can just move on from that. Real quick, we wanted to stop and take a few questions if there were any. sir. Okay. What do you see, 1st of all, I'll ask you, well, do you wear a green? Okay. Yeah. Some of noises. So the question is, are we, using models to write or chase on, to then, like, help us with, you know, to make our code deterministic, to bring that back.

the answer yes I'm using that. I'm running and then I used I'll use Units around to verify different things. And then verify that the code, that is like a real interpretation of representation of what I'm expecting to get back into when I was in a model, and use that company... But then have one of those as well to kind of like have another section that we're going to do to make sure that it doesn't driven over time or anything's changed.

Any other? Frozen Goldie or Agnostical? The general process that I'm talking about? Yeah, so what I'm talking about, at least on our teams, we build a ton of applications that are internal tooling. We have some

### 00:27:17 — Hands-On Verification Architecture

customer casing applications as well. They tend to be, placed right, as they tend to be, like, one, or something. So, that works perfectly interesting. You even have evalves that are focused on the back end of your database operation. I even get as framed there as a one with a... There's definitely, yeah, works both that. And I expect that the way that we're all gonna continue, facing the software feature is gonna be, I don't know, the hardware is making sure that they're...

Yeah. We're not, like, giving out a tool and we couldn't give you a tool at this time that works generically for every single reputation that everyone in this room is working on. have to build up the tool little p that you're working on. and then give that to the models. So just make sure that they know how to run men while one.

as a, as you said, a lot of us to say like your emails, would you actually need to care about as a team or company or business are going to buy out? You know, if you're in like the interior design space versus some other place where like speed is the only few hours. I think you're gonna have like wildly different emails and there's a value to building those on you.

And there's lots of different ways to get the data to the, like, to the model in different ways, for so that it can interpret it, anything feedback. It's like a huge piece of, like, the model in the loop as to what's going on. The am team has a really great post on it. I think it's all I remember but I'll give it out there.

I think it's a little bit permanent, but yeah. But when they, in the example, they show like a canvas with a circle and a ball bouncing inside of the circle. And then, like, there's a little slit where it's like, you give it just right and you fall out of a circle, and then the game, other games are... And the whole idea of that is making things feedback.

that's what it is. where, you know, the model can't actually see the running cannets and where things are going. But if you, there's a very confusing example, if you just print out the coordinates of that ball at every point and you see a bug where, you know, once it gets to the season, a big point, it jumps to the other side of the screen.

Well, if it's moving more than one takes a lot at a time, like per loop, something is wrong potentially. And so there's a bug in there. If you can surface that to the model, then it can help you debug it where it doesn't actually have biased casino canvas and see the ball, not behaving well, like the physics. So, and also, once you do that, you can, you're also not a previous, you know, 30 different variants of software that are...

You don't see that. So that's the other thing that I think I'm on, right? And especially if it's back, you know, the models can improve, they're token to be a cheaper, potentially, that, you can imagine that they're all going to be, like, coming in on Monday and saying, like, oh, good to see 35 versions of this new feature or applications here with that.

a And so how do we actually run before create that? Well in this case, like we said, we can't really prove it, for having, like, universally. It really has to be something that's unique to your application. And so for our midnights, night and age, this is what the proof command might look like, where it's basically using a tool like playwright to check that a email was actually saved when it gets on the waitlist.

So we can check that it doesn't have any on the waitlist, any emails, then we can fill in an email on the next line, and then we can get the button and click it. The joint wait list button, and then we can expect the status element on the page has a wait listed in there. And then check the intertext of that to see if our email address is available.

And so that's one simple way to do it. Very easy if you've ever written an enjoyed test with my playwright or reacts. Any of those. you definitely fools like this. You can just give them back to the model and to your agent, and they can run them, just give them to them as a tool, and they can prove it out themselves. And you've made this reproducible bit of evidence, then you can use in this one.

next time you use it, next time that page changes and you run in the end and verify that nothing broke, it acts as a regression. and keeps everyone on the team moving. Why? One caution or professional, like a subtestful screenshot is improved. make sure that it's actually showing, you know, the state that you expect it to be in, that it actually like ran the commands to get to that state, to actually be in there because otherwise it might just be like another Y.

but your seating a screenshot on the PR and thinking 0 yeah, this is this is correct. But it might have been causing different side effects. I might have taken a different path that's not actually why it's home within the UI. So you want to make sure that it actually like runs start to finish to check my. One of the... Yeah, and so once you build these loops that are, you know, durable, reliable, repeatable uniforms, the value of what you get or whether the main benefit is that a failure starts to drive future work, right?

So if one loop, the agent fails, you're busy talking to somebody at work or you're starting another task, that agent can determine on its own. This is not quite correct. Let me go take another stab at it. Let me now run this man, verify again. okay, now we're good. If you think about what that means at scale, on a single PR or a single lane of work, if you will, the agent, you know, self-deal, self-corrects, figures it out on its own.

You're not coming back to that particular PR at the end of the day. So then being, you know, just all the way through. And if you just multiply that out, right? That's really where, again, we just say there's a foundational for speed. And how many of you write, I've been good error messages or the moment? Sarah, what's your favorite message? System air nine.

Well you should. I think the more important than ever, because when you're at your app frozen error, guess what you're interpreted and run better really well. So, if you make it so that your failure is explicit about why it failed and get as much detail as possible about how it got into that state, then, where you can just sell guilt from it.

So it's very easy, very worthwhile to do that. Yeah, and so this is a concept that, you know, maybe I can talk about, right? And it sounds like we're being, in some ways, we're trying to wrap the terminism around LLM. but we actually don't want to do that. And it's also something to the spirit what the ants team is talking about. The Asians are intelligent.

they're capable, want them to be creative actually. Because oftentimes if they have the right constraints and then oftentimes constraints can be legal freedom, right, in a way. then they will come up with creative solutions and actually solve what you said. That's why you give them the outcome. That's why, you know, Nick's project is experimenting with his outcome driven development. And so it's not about over being overly prescriptive in how we achieve things, that can actually lead to lower performance from all cases.

It's more about getting like a map. saying you must get here, you'll know you're here when this commander turns to us. You don't necessarily have to start how it gets there, though. and this is true, more and more true every single day with like the frontier multi forms. So maybe after a call 6.1, Obus 55, They're all really good at being like you can create is like the way I describe that.

But if you give them, this is where I want to get to and don't necessarily tell them the path that they need to take, they might wander and make sure that they catch more edge cases. They might figure something out or ask you a question that unlocks something, but if you're just like, you have to get here, and then here, and then here, they may not sway from you, and you want them to sway a little bit, but get to the right, right end goal.

And I get this, this is something that we won't even come around to really appreciating and the latest batch of hunter. we're truly becoming possible. So going forward, just get better. your ownicy. So when it's going, you want to get into, like, you know, the typical TVD, like red green refactor loop with your name? Because you've heard about this, you know, that every one of these AIOs, and it's no different here, but you can use that within the verification piece itself.

Verify this, reproduce it, show me, fix it, and then show me the program. And how are you gonna show me the proof? That's just as important as the fix that's gonna go in. Because that's what's gonna lead you alone and allow you to trust the model to actually do the work

### 00:35:56 — Scaling Agent Verification in CI & Production

and then when it says, hey, I'm done, you know that it's done because it's proved into you in some... So in this example, you can run snack doctor, let's just go and run that real quick. quickly highlight. And so this, this ran, and it's showing us, you know, a bunch of checks that I did. So it's checking that we have known, the chromium's installed, that our session exists.

It's actually running. and then it's successfully built. So that's like what we're running as a quickick doctor, just a bunch of different things. So then you go to the next command? join data at ex Sorry, we don't play anymore. For example, we can reference a slack weapon for if you're okay, give us the result back. Snack storage. Or all the 4070? didn't actually put the data in there.

This is the point at which, in the real world, you're aging just gotten the value of this entire system. Because at this moment, you're using realizing I am getting done, and I'm not going to drop this crime before. And if you reload it, do the same thing in return. But we have now given our out ice. We can see this. They can run these, they can, make, it can make sense and change the world of the application of the next application.

and C, or the results of that, and then be able to interpret what happened from there. . So you can try that. If we, like, apply the persistence fix to it, and add honest copy to it, then we can... That's what I' check any flight into yours code. And you probably not kick up browser and I didn't actually go. If we had or run the fix.

If we had one that fixed, it would have been together, and that's... Okay, one of the things that we're thinking about a lot lately, talking about starting to roll out more applications is like concept of receipt. you know, you can take like a ticket, I guess, to how a ticket system, because there's a certain performance the way that a human would answer to it and consider it something well.

And that you know customer wants to their service. And then what does the preserving that in some way? For example, right? Why do we want to do that? There's a ton of reasons, and we'll get into some of them, but again, if you think about, if we all, or if it seems that in some way, many, many folks are heading towards, you know, running our side, harnesses and self-evolving code cases, everything that we do today, everything that your agent does today, every run, all day long.

That is very valuable data. It's very valuable data right now, because you can feed it into, you know, pictures of money. It's incredibly valuable data in the future as tooling improves. Like, it's easier and easier to set up artists. Because then you've got data set up exactly how your system performs. that you can create, you know, very comprehensive emails for and have agents still climb on, which means loops, and see their performance, and then continue going until they get better and better and better, right?

that point they're able to pass and they using that for the previous ones. Yeah. So now, if we fix that code, it now persists, but it can also lie. So after we reload the page, if it's a weight listed, but the screenshot I might actually say is you're in, you see this confirmed. Those don't exactly match up. And so that might be, like, a failure, amazing, because they don't exactly match.

So this is kind of getting away from the static testing piece of it. Like, how do we prove that, it worked without having to be, like, very tightly coupled to the actual text on the screen. for a very contract example. and so if we just run like, you know, PD, snack, pudge. So from that, and it failed, because even though it works, and it says that we're in, Jen did not, or the model did not see that.

And it's because the confirmation text breaks the contract. It's not exactly one tool. So how would we fix that without adding a lot of time coupling to everything that we're doing? The answer is the system one models. which we'll get into here. Yeah, absolutely. So, just to introduce it for anyone that hasn't heard of it before, the concept of system one, system 2 comes from psychology, actually.

It's like a useful model to think about how they even brain works and how many things. So system one is super fast decisions. is, you know, autonomous, like someone swerved at me while driving and I just corrected without even thinking about it kind of thing, right? I was about to lose my balance and I corrected it. And then since 2 is like I need to figure out what my life.

like about it for 3 days. and so, you know, applying to the world of all levels, now we've got Jev, and then immediately after we've got cleft from Claud Flair, a few years later, at the season faster. And so there's it's a really exciting time to think about all the ways that we can combine these tools together to make the new primitives that we're gonna continue to see involving architectures.

To give kind of another way is that light right over there. I said, what color is that projecting? Quickly you were saying, yes, that's at this point, right? Just, you know, the color. But why? Now we're thinking, you know, we could go down like a physics of buy the light and make seeL? That's how we got really what we want to talk to you about today.

So I'm in this, we've got another game that we can play within. within this, it's a quick game with the snack. We have saboteur and a detective. And so, in this, the saboteur will pick a snack. It'll put a secret bug in there, randomly putting a bug in there. We don't know which, it'll just be random. And then you, the detective, funded with, with snack alone, and then prove, what's that, its name above, and it's different in fact.

So this is something that you can do if you pull down the website or pull down the refund, you can just run, PBM, snack up, after I bug random, and give it, let it run and see if you can find it. So let's try that. We'll just give it some time. to go. great. already money. Okay. So in this, it ran... It's got the outfioral.

It's running. It's not headless, so we can see it. The bug says hidden until you stop up. Yeah, right. leave this running in another terminal, where I can't give him a snack doctor. Bless you. Thank you. All right, so that ran the whole thing, and we can see, you know, sterochromes there. It's got a session. The proof here, the last receipt says fail, but the source is now, that proof is for code that no longer exists.

so it wasn't able to prove back that was a previous run, front it again. same thing. Can you even tell me what the bug is? Any this? ? Four, eight, three. I think it was running at 62174. Oh, that was right. for that one, yeah, even the cool makeupional though. so you can run through all the exercises if they don't have it and don' just go.

But, it's also a good opportunity experiment. Okay, the, the calls. They give me $5 for free when you will sign up and I think that'll have to, like, 3 years. All right. So, yeah, we ran it a couple times. I think there was some problems with time out, but I'll debug that. It's funny, I need some verification rest around my tried verification examples.

But the, you know, the outcomes that could come up are, that it names about, without the, study works, but it didn't, set it works, but it did, blame the bug that wasn't there. and then had no it was the right button or no events. Right. And this is just getting back to that point of a trying example, of course, that 13 might score, definitely, or how different criteria they're looking at.

This is superflexible. The most important thing to do is to start and create one, create an, you know, based on music. It says something to evolve it together as a team. And it gets to the point where if you're changes, your PR is automatically reflects that emails, that you can get to the point where you know it changes our safe to length, or fruiting things, or if they're doing it worse, or if they're not changing, they don't recommend.

Every time it runs, and it misses, that's a new line that can go on the map. So it can give us ideas of, like, the steps that we're getting there, why we're getting there, and kind of, like, you know, every time it fails, it's getting us one side closer, because we can fix that. So the 1st time is memory only, and it's not stored anywhere, but in a hur.

We're putting it a long email address. We've lost our confirmation. Every time we improve, so we thought that, we don't run into that again. But then the over promised one, the screenshot, or the judge running, that it, it actually did not split into the battery. Same thing with Ponsol Air. There might not be anything in the console, but it's in the receipt, or it

### 00:47:15 — Workshop Q&A & Closing Discussion

might not be getting caught before it gets to the console. Yeah, something like that. Or it could just be not. There's nothing to find everything works. and that's a real concern as well. Um... Yeah, if you run the doctor, kind of like what we were doing, it was showing you this where it was showing you the previous examples. and show the proof that no longer exists.

That's because your code might have changed quite a bit between yesterday and today. It might be different circumstances like a famous databook. for example, it might be a number of different things. So, we want to build the tools in such a way that they're flexible enough to not get caught by issues like this. This is all kind of like, going back to the basic human testings, examples.

But bringing that kind of like deterministic check to the models in a way that they can self-heal itself improve. Okay, so this again, the tie back to what we used to do as human developers, right? you could be able to see how we would watch everything. Oh, okay. That's really what we were talking about. and let me get into code. So by moving in the code, making it available and just turn it into CI, then we can give to the same path and the same experience that we would flex as, you know, developers to come from, trying to fix something lately.

And that's really what I'm on for me, being in the evolution and the ability to scale a lot of being around the code that you're delivering. And to do that in a Marcelia. Again, you know, if you, the recommendation is that you have a webhouse, and you're not already, you don't already have any custom verifiers, CLI, that's one of the highest level things you start with for your, code base, the foundational ego as well, but that shows what good looks like in your own vacation, and then also getting your agency the ability to see all aspects of the performance and, networking and traffic and rendering, et cetera.

So getting it chrome dead pools if you're in, in your, in a web app land, if you're shipping, maybe a plan for shipping, iOS, you know, or OSX stocks, then there's an alternative, projects and more coming out every day, that you're then going to attach to there. But the, the common, you know, foundation here across all of them is that you need to give your agent able to see absolutely everything that you would normally see as a developer, whoever.

Yeah, the more that you can give it, the more arms or eyes that you can give it. The more it's gonna be able to take over from the after. And then you just have, you know, the intuition of when do you use those, how to use those? Think about the way that you decide. Okay, if I had this bug came in, how would I introduce this?

Think about that and if you can break it down and this is an dependent on your application and the type of code that you're writing. you might be able to do that in a way where it can, like, think, oh, you know, for us, there's a lot of sign objects, like, is it properly setting it? Is it setting an expiration? again, like this is a playable to every you know dealry.

But it's really just all about, like, the world where it makes sense for us to want to actually look at all the times, at least evolving or at least changing rapidly. What are the foundational, like what are the same system fundamentals that we bring? It does now, so that we can only celebrate somewhere now, and they don't have any different. So yeah, during expensive policy, but the important thing is that getting that output, making sure that it's giving you detailed output about what happened, the state of it, all of that so that it can be audited by the application, by the model, and then you can run it again and fix it, run it again, and verify the post changes actually to hold, and that there's no longer any shape.

Yeah, and again, can overemphasize the value of keeping receipts. So if you have runs, you know, if it means the entire user journey, let's say it's an e-commerce app, it's like when they log in, you have to be, what happens? What does their flow? Did they see an error at all? Did they see 7 seconds of time to see your catalog, you know, come interview?

were they able to put something in their cart? Was their heart management? And so, sure, to save that all now, because every single one of those runs in our seas can be fed, 2 LLMs. You can even set up a system that's running all night long and is looking for the latest receipts being produced, and it's aggregating them and saying, well, today we saw 8 failures in the cash election.

So, obviously, you know, issue a PR at night and fix that properly. And then, oh, I have the tools I need to improve in SPR. That the issue I was trying to solve has no fix. And then the recommendations that we're seeing from folks too that are achieving like super high skill, VR shipping without errors. They're also able to, you know, add, the stuff that is for us as humans in our oversight still.

So not just screenshots of being teacher, but like a recording of I walked through the app this way. This was my flow. this is what I experienced. These were the states that I got playable. So that if I'm waking up, I'm trying to rip through, you know, 15, 14 PRs, but the 1st thing in the morning, I can 1st start watching that and make sure, okay, they're actually about to get more.

And then we, you know, started on the code. I get that something that I'm actually wanting to, like, human review. And, again, all of that, I think, is going to be immensely valuable, if you can change the, uh... And so, you know, think about what that means, though, because when we get to the point where there's the self-fault in the pool and it's just right that people are using it, there will be a specific advantage for folks that have preserved clean data sets of things that they can say, this is what we are trying to get to in this application.

to get all the way there rapidly improve it, right? If you're not sitting on a mountain of that, then you're predators are going to have some, you're going to be able to go. And this is just building up that trust. so that we can continue to improve on our app as we go. But we have these checks or everything that came before them.

So we've got, we've got, you know, so we've got... We've got whatever our application needs, and we've got a way for the model to be able to interpret and run those and improve them. in such a way that if we add new features in and we can run all of the previous ones and make sure that we didn't actually break anything. No regressions, and we could just mount and climb that evidence ladder.

Building evidence as we go, and ensure that our is working. Exactly, I think. Not really... Okay, cool. So we've got just over 5 minutes. I want to pause to see if there's an additional question. Yes, sir. I personally, I'm curious what scary you did, but I would personally listen away from, like, what my experience is, you know, up to the model that are not going to actually call it up half and leave it.

versus like having a CI and going for the these commands run those. the question is how do you run these tracks on, right? Yeah, like, you can, you can run those, you can run these regularly, you can have them be, like, RCI, for example, you can have them be, various hopes that can be, like, a, you know, all the, those, you know, for.

You could have it be like a flood code book. It depends on a bunch of people just in another... I might build like a full high extension to... PJ version back, and it's kind of like speed in... There are a number of different ways that you can do that. But the easiest way, by far, to get everyone across the board and you can see this now, just put a name on 70, how to call it that MD, in European rap, and then have it, say, like, you know, one change, buy a thing by restaurant.

So, like, every time it came significantly, but before you open up PRD, it's, like, whatever wording that you want to put in there. and then that's an easy way to get everyone across the board and they really, I have to go out of the way too. books are also around right for the whole Well, CI is a, I think, a feature of it, but it's not like being the actual tool is like the rapid development that you get.

So I get my agent the task to do and I can just quickly run. let like let the egg go. you know, basically tell them, this is where I want to end up. I want a wait list to be, I' be able to add a email to latest because it gets persistent and safe and I need. So this is how you goes into this table like whatever Yeah.
