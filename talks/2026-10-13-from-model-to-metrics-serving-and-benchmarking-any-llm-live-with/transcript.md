---
title: "From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod"
speakers:
  - name: Chris Vela
    affiliation: Runpod
room: "McCarthy Room (Riverside Suite)"
starts_at: "2026-10-13T15:20:00-04:00"
ends_at: "2026-10-13T15:38:00-04:00"
format: "talk"
recording: "2026-10-13_1520_bench-marking-llms"
duration: "17m 29s"
source: "voice-memos-transcript"
---

# From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod

### 00:00:00 — Why Live LLM Serving & Benchmarking Is Hard

French working VLMs, kind of like the struggle that people have, especially like a new mom comes out. just some like learnings that we've had internally I've run by in like Christmas. So Tim, I'm going to be showing you, essentially like a dashboard, but Phil and Todd will, like, be OM. It's using our like pods, actually. So speaking over a little more context, sort of like what run podcast is renew about, we make it really, really easy for you to run GPs.

Starting from like RND to like more surface production workflows. A lot of times when I see the customers, but there will be a lot of, like, someone wants, you know, the latest model, they don't know how to, like, spin it up. Or they want to start going into production and they don't know the knobs to, like, touch, but they're just using whatever, like, the base can be big.

And I'm guessing a lot of you probably seem like be able to own recipes before. You know, it's a good start, especially in like, but like, especially in this world, we're always moving fast. So how do you get to more production level style code? And at the same time, not just like buy me, or like how you actually have data, how do you show, you know, your manager, like your staff and chair, that, hey, this is actually better.

This is actually working correctly. So, Really, what I'm trying to say is like, I've seen a lot, everyone's just guessing. Like, you know, you're, a lot of times I see people are using the wrong VLM version, they might, they're probably not using like the nightly version. They have the wrong size for the contacts window. It really depends like I took always of step back.

It's like, what are you trying to achieve with your LML? Are you, is it gonna be a coding agent? Is it more kind of like you're just, you know, doing summaries? It's like very, very basic tasks. That's usually the 1st question I'd be asking before. you know, getting commun, having million long contactsext. Like that's not always necessary. And at the same time, it's like, how many users are going to be using this?

A lot of times people are like building, everyone's trying to get always get like the smallest amount of GQ for the cheapest price. But if you're going to be going to more comparing users, you start thinking about, like, how am I going to be utilizing the caving cash? So all this is, there's all these little like optimization knobs that you need to like figure out before you go into production.

And a lot of times we're trying to put fast. So, Yeah, like I said, like Run Pod, like we like have very much like, you know, we make it very easy. It's like a BF. It's doctorized. You can bring your own image. but at the end of the day, like, like who here is used to like deal a lot of people work.

Okay, it's like, okay, you know, like, when you're looking for, like, it's like, 2 K three, like, if you use like a version of, like, you know, 0.27, I'm not gonna be working, like, we're moving so fast. the code is not getting as fast. Like, you need to have the right version. And a lot of times that turn a new kind of like a CIC process that, especially if people who don't understand what's happening, just start struggling.

They start seeing errzona like why is it not working? And, you know, the layers move in it are not, they haven't been written or they're all together. And at the same time, that's actually kind of a problem. It's like, communicate 3 comes out, you know, the next day, I would not put that on production just yet. You're gonna be seeing a lot of probably hallucinations.

It's just not ready in that state, I would say. So what I proposed, so I created this thing called, it's called Benchpot. It's gonna be a template. It hasn't come out yet. So it's essentially built on top of, like, BLM. It's a whole metric system. You can benchmark very easy and a lot of you are familiar with like VLMing and benchmark already.

But this kind of, symbolizes everything. like you can be able to see everything, be able to change the thing very quickly. That's like a very important thing that I notice is that, especially with people who use like our pods, is you set up a config, but then you have to restart the image. You have to wait for cold starts to happen. It's all this loading and you're not moving as fast.

You're waiting like 30 minutes, like for Kimmy K3 to like download the weights, loading the GPU, it's kind of waste of time. I mean, if you have an agent, you know, you really don't care, but, that is a pain point, especially when we're trying to move fast. And at the same time, it's like, cool thing about Renbod is you can find these machines.

So if you have that question, it's like, I want to run King Gapery on a B 300, we have B 300s, and you can start going from like, not just like being a body, you can actually start testing it. And seeing if, you know, there's truth to all these metrics. So, yeah, so like, like I said, like French pod is more like, it's, it's built like a, a dog image of, BLM open ABI.

We're going to be having every version already. We just have a little like payload bit like pretty much craze this whole nasty MPI application. You can do the breed agents. The cool thing is you can serve, you can pretty much specify which models you want to have. We have a whole watchdog too, sort of like self heels too. So, if you're actually starting to go to

### 00:05:16 — Serving Open Models with vLLM on Runpod

4 production levels, you can actually, you don't have to worry about it. I'll show you, like, this past Sunday, Kimmy went down on our incident and it, self field. And, you know, we have we have right now like 4 nodes running it. So none of like our internal users saw any problem. It was like production ready. getting have to like think about it too much.

And at the end of the day, yeah, like it's, it makes it much more simple process to have the production for the workflows. So, I'm guessing why people, I'm going to be showing Kim and K3 because we've been using that a lot. I'm guessing a lot of people here are very familiar with chemicadry. So again, 11000000 contacts. one thing that's interesting on one B 300 can get to the $1 million got to use half of it.

But one thing I've noticed, especially where I came, like, we're uniting a lot for pretty, agents. that is very much, enough to do a long task. It's utilizing KB Cash very well too. So in terms of speed of like time to 1st second. it is very, very. like in the demo there used to like running model. So, this is like our dashboard.

have a lot of metrics. Yeah, I think it looks like a lot, but, essentially, you know, we're always thinking about like UP, like, you know, have a lot of like computer metrics, you know, and what Cooter version are, which is very, very important. You know, if you're running Kimmy, who doesn't work on a 128, who works on 13.0. and really, it's what we have is like the we can we can look at benchmarking, look at all our data, we can like playground with it.

So, like, before you even put it into your, like, cooking agent or just hitting the open AI response, you can start testing real quick, they could be working. And just a lot of, like, once you guys see positive of, like, you know, however my goal starts happening. how are am I metress? through animal traffic? So I'm gonna show you guys a demo, so...

So really, like, I'm sure you real quick, like, the run line itself. So, this will, so we don't have the tumbled out yet. Like I said, it'll be up by the end of the month. But really all we have is just like a doctor image and be able to put that in right there. But it's correctly. But, yeah, so right now, there's not major hutters, but I have one running right now.

That's the fun thing about working in this industry. you know, a supply can be dependent. But yeah, in the sense of that, like, you know, we make it really easy. You can put storage volume. you deploy it, you know, we have a part two, it's like you can deploy when you're available. So, you know, if we're seeing the screen like this, maybe we'll deploy whenever it gets started.

So that's like literally the process. You click that button, bench pod, right, starts up, and I can show you, like, right here. bit. I'll show you guys here. So like this is like this is our actual like Kenny running apparently. So the cool thing is, like, you know, you start like it has a whole air scan, so you have actual data to know, like, what is happening.

Cool thing is we have live metrics too. things are right. All of this is also like backed up on like storage data, so like it's all backed up no matter what. It's all nice, fast API call, so you're aging can easily just call those data. Yeah, you should just serve everything. Like, you don't even have to use the UI. I think I'm a fake reponter of like, as we graduate as, it's like, I still want to have like some awareness of what's happening and having this gives me a good, like, the, like, beetles eye view of, like, what is happening with my, kid, K3 instance.

Yeah, like you can see there, like, I was gonna show you, like, this past weekend we had Baylor with the GPU. we were able to fix it, but, being able to just do a full-star time for like 9 minutes on, hey, through is pretty, pretty good. And the cool thing here is that you have to serve certain experiments, and essentially, like, apply them to restart roleplay.

you can, it's clearly just like a contingy animal file from like the OLM. And so like, for this like little demo, what I tested was we were just changing the max number of match tokens that were sent through. And I kind of wanted to show you guys like, you know, what if what kind of like speedups would happen with this, I'll go right here.

So I read this before because we're not gonna spend like 20 minutes just looking at benchmarks. So these benchmarks are running like comparency, so they're running, you know, starting with like this one comparing user and an 864, 182. And the cool thing is, like, we can be at, we can actually compare multiple runs against each other. You can kind of see, like, even just increasing the match, the number of match tokens, doesn't really change that much to the time for a second.

but the interesting thing that I did notice of increasing that is like the inner token latency actually decreases quite a bit when you increase that, batch shogans, which means it's like the request itself, especially running like a long, like job, essentially. it's actually much faster finishing the job than, like, that, like, you find on deal around recipe. The cool thing is, like, you can add the certain agent and just start going crazy with it, and you can start getting those answers much, much quicker, have the data, and move

### 00:11:15 — Throughput, Latency & Cost Metrics in Practice

from this, if you have it like on pod, you can start moving to, you know, a whole tanker cluster. You can move to surface too. so you're gonna be like scaling up and down. that this is a perfect way of like actually getting data. And just to give you, like, a context on our service, a lot of people will do the same thing.

They just hope whatever the base can pay is. and then are struggling as like they're waiting for workers to start up. this actually gets you the real data. You're now ready to go to production, makes it really, really simple. And just gives, it's, I don't know, like I would say, it's basing everything in facts. And, I can like show you guys right here.

like this is actually like kid rightding. So I was just like, what is, punch punk? Stop it, sorry. But this is the little Jimmy instance running through it. yeah, and, you know, it is pretty, pretty quick. Like, I would say like there's like probably like 50 users right now on our internal one and we, most of us are getting off clod and just using this.

And we have other instances who are like geolam, deep sea, .3.8. But, yeah, like, I think in the future we're looking to more at, like, smart routers, like how do we host all this without being reliant on someone else? Yeah, so let me go back to our... Some, like, an important data that we were just talking about if anyone wants to screenshot that, but, like I said, like, you can you can specify the experiment yourself too.

So if you were like, I might have like 500 people using this all the time, like, I wanna, like, see how well this is gonna be. But at the end of the day, like I said, is how do we go from R&D to production? And I think this is where like bench pod will make it a lot more easier for people to use, So, like, at the end of it, like, what I want you guys to, like, know is, like, you know, pick a pod, kids, look at GP machine.

You have your model, compared from bigs. Don't just start with like the meal and recipe. The meal and recipe is proven, but it's not production, right? And then test, have your agent tested? And then whatever, you know, based on what you needed, this IPL, you need PDF, TPO team, like metric, like optimize on that, and then ship that. sort of a scale out, and now you can like, now you have a working LLM model that can be used internally, can be used for customers.

Yeah, it's it just makes it very, very simple. But yeah, one thing I would say, especially with like Kimmy that I've noticed is, It's not always necessary for a team. Like, a big thing that I think, like, most people don't think about is that, you can use a small model. Yeah, it's different. Right now. Like, okay, that's, like, on our on our platform, like, that's gonna cost you 40K a month, essentially.

And it might go up, it might go down a little, but, you know, it's a very powerful machine. And I think when you're thinking about like how you're gonna be, serving stuff if you want to be doing this internally over yourself, it's like, what makes sense the best. And just because the frontier model really doesn't make sense. Like I said, like, like I've run a DC on a 4 H miners, and it was a really good job.

Jimmy is more for like long tasks that I'm trying to solve something like very, very detailed. but like I said, the other thing is like making sure you're like tooling too is like on there. That's the big thing, context, like I'm not going to be going through too much about like contacts, like release and all that. But the ability to have all that, and like AI governance is the next step that we are going to be going with run time, but it's just something that can always be thinking about, especially if you're going to be cell phones, hosting your, your LM models.

But yeah, is there any questions? And we'll also be able to. serious. Yeah, I mean, I'm late then, if you want to talk more on the initially, supporting everything off, like, every week. So, I always have some, like, gotchos that have been like through, through the time I've been doing all this work. And, yeah, also scan the cart, QR code. So you can get, to get some credits and, test out what I'm on.

like I said, the template will be out like at the end of the month. So you can go play around with it. Yeah, any questions? Let's see. Yes, you have one over here. Oh, yeah, sorry. a little... Oh, yes. Do you guys have the ability to do disaggregated serving? Oh, yes, yes. Okay, yes. Yeah, that is. So, like, I would actually use like a custard for that.

but yes, that is very possible. you can also run like a ray cluster, professing certain multiple models. a lot of like m right now. but I that's also another thing as you scale on, but like, you know how you are using like L cash. Like, I mean, right now, like, I would say, our tests internally, like, the fastest cash is opportunity in itself, but once you start serving to, you know, know those on users, that's where I think, I mean, desire is serving and also, like, you're cashing, like, that's something to the point.

Anything else? Well, it's a pleasure. Yeah, seeing has a move. I think you guys want to talk I love talking about Fritola and anything that has to do with
