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
source: "qwen3-asr-1.7b"
---

# From Model to Metrics: Serving and Benchmarking Any LLM Live with vLLM and Runpod

> Transcribed by qwen3-asr-1.7b with a schedule prompt. Possible prompt artifacts, names heard more often here than in the unprompted Voice Memos transcript (Qwen vs Voice Memos): Kepler (1 vs 0), Optiver (1 vs 0), Runpod (3 vs 0). Check them against the audio before quoting.

### 00:00:00 — Why Live LLM Serving & Benchmarking Is Hard

Benchmarking VLMs, kind of like the struggle that. Especially like a new model comes out, just some like learnings that we've had internally. I've run by and like first version. So today I'm going to be showing you. Essentially, like a dashboard that builds on top of like DLN. It's using our like pods. Actually, so to give you a little more context of like what RunPod does is we're in the cloud. We make it really easy for you. To rent GPUs, starting from like R and D to like more serverless.

Production workflows. A lot of times, what I see with customers, especially with VLMs, like someone wants. You know the latest model. They don't know how to explain it up, or they want to start going into production. They don't know the knobs. To like touch, they're just using whatever, like the base config, and I'm guessing a lot of you probably seen like VLM. Before, you know, it's a good start, especially but like especially in this. World, we're always moving fast. So how do you get to more of a production level?

Stop code and at the same time, not just like buy data. It's more like how do you actually have data? How do you show? You know your manager or like your staff engineer that hey this is actually better this is actually working correctly. So. Really, what I'm trying to say is like. I've seen a lot. Everyone's just guessing, like you know. A lot of times, I see people are using the wrong v11 version. They might they're probably not using the nightly version. They have the wrong size for the contacts window.

It really depends. Like, like I take always a step back. It's like. What are you trying to achieve with your LLM? Are you is it going to be a coding agent? Is it More kind of like you're just you know doing summaries like very basic tasks. That's usually the first question. We asked before you, you know, getting K3 having a million long contexts like. That's not always necessary, and at the same time, it's like how many users are going to be using this. A lot of times, people are like everyone's trying to always.

Get like the smallest amount of GPU for the cheapest price. But if you're going to be going to more concurrent users, you need to start thinking about like how Am I going to be utilizing the KV cache? So. All this is there's all these little like optimization knobs that you need to like figure out. Before you get into production, and a lot of times we're trying to move fast, so. Yeah, like I said, like Runpod, like we like have very much like you know we make it very easy.

It's like a VR. It's dockerized. You can bring your own image, but at the end of the day, like. Like who here has used like Meta a lot before? Okay, so. You know, like when you're looking for like, like especially like K3, like. You use like a version of like you know zero point twenty seven. It's not gonna be working like. Like we're moving so fast, the code is not getting as fast. Like you need to have the right version, and a lot of times that turns into kind of like a CICD process that.

Especially people who don't understand what's happening, just start struggling. They start seeing errors and they're like, why is it not working? And you know, the layers that are not they haven't been written or they're. A Jakovcevic; Just yet, you're going to be seeing a lot of probably hallucinations. It's just not ready in that state, I would say. So, what I proposed. So I created this thing called it's called Benchbase. This could be a template. It hasn't come out yet, so it's essentially built on top of like.

VLM, it's a whole metric system. You can benchmark very easy, and a lot of you who are. Familiar with like BLM, you can benchmark already, but this kind of simplifies everything, so you can be able to see everything, be able to change the very quickly, that's like a very important thing that I. I notice is that especially with people who use like our pods is. You set up a config, but then you have to restart the image. You have to wait for cold starts to happen.

It's all this loading, and you're not moving as fast. You're waiting like 30 minutes. Like for Kimi K3 to like download the weights, loading the GPU. It's kind of wasted time. I mean, if you have an agent, you know, you really don't care, but that is a pain point, especially when we're trying to move fast, and at the same time, it's like. Cool thing about Runpod is you can find these machines. So. If you have that question, it's like I want to run Kepler on a P300.

We have millions, and you can start going from like not just like reading about it; you can actually start testing it and seeing if you know those truths. All these metrics. So yeah. So like I said, like Benchpod is. More like it's built like a Docker image of a VLM OpenAPI. We're going to be having every version already. We just have a little like. Like payload that like pretty much creates this whole fast API application. You can use it for your agents. The cool thing is, you can serve. You can pretty much specify which models you want to have, we have a whole watchdog too, so like self heals too, so.

### 00:05:15 — Serving Open Models with vLLM on Runpod

If you are actually starting to go to more production levels. You can actually. You don't have to worry about it. I'll show you. Like this past Sunday, Kimmy went down on our instance, and it. Cell field, and you know we have we have right now like four nodes running it. So none of like our internal users sawing. It was a production-ready. Didn't have to like think about it too much, and at the end of the day, yeah, like it's it makes it much more simple process.

To have production workloads. Workflows. So, I'm guessing a lot of people. I'm going to be showing Kevin K3 because we've been using that a lot. I'm guessing a lot of people here are very familiar with Kimi G3. So you know, one million contacts. One thing that's interesting on one billion kind of. Can't get to the one million. Got to use half of it. But one thing I've noticed, especially where Team like we're using a lot of our trading agents. That is very much enough to do a long task.

It's utilizing KV cache very well too. So in terms of speed of like time to first second. It is very rare. Like in the demo, I'll show you like my teammates running this model. So, this is like our dashboard. Has a lot of metrics. It looks like a lot, but essentially, you know, we're always thinking about like GPU, like you know, have a lot of like GPU metrics. You know what could be emerging on, which is very important. You know if you're running Kimmy. It doesn't work on a twelve eight. CUDA works on thirteen point zero, and really is.

What we have is like the bench. We can we can look at benchmarking, look at all our data. We can like play around with it. So like, before you even put it in here, like. Coding agent, or just getting the OpenAI response, you can start testing real quick if this is working. And just a lot of like more CI/CD process of like you know how are my cold starts happening. So I'm going to show you guys a demo. So. So really, like I'm going to show you real quick, like the website itself.

So this one. So we don't have this template out yet. Like. Like I said, it will be up by the end of the month. But Really, all we have is just like a Docker image, and be able to put that in right there. Let us correctly, but yeah. So right now, there's not major headers, but that's the fun thing about working in this industry. You know, supply can be. Dependent, but yeah, in the sense of that, like you know, we make it really easy. You can put storage volume. You deploy it.

You know, we have a part too. It's like you deploy when you're available. So, you know, if we're seeing the screen like this, you will deploy. Whenever it started, so. That's like literally the process. You click that button, Benchpod like starts up, and I can show you. Like right here. Okay. I'll show you guys here. So, like, this is like. This is our actual like kidney running, apparently. So cool thing is like. You know, you start like it has a whole error scan. So you have actual data to know like what is happening. Cool thing is we have live metrics too. So things are running.

All this is also like backed up and like stored data, so like it's all. Backed up, no matter what. It's all based fast API calls, so your agent. Easily just call all those things. You can actually just serve everything. Like you don't even have to use the UI. I think I'm a big proponent of like as we get data, it's like I still want to have like some awareness of what's happening. And having this gives me a good like eagle's eye view of like what is happening with my computer.

K three instance. Yeah. Like you can see here, like I was gonna show you, like this past weekend we had a failure with the GPU. We were able to fix it, but being able to just do a cold start time of like nine minutes. Category is pretty good. And essentially, like apply them. It'll restart real quick. It's clearly just like a config YAML file from like the LLM. And so, like for this like little demo, what I tested was we were just changing the max number of batch tokens that were sent through, and I kind of wanted to show you guys like.

You know what? What kind of like speedups would happen? With us, I'll go right here. So I read these before because we're not gonna spend like twenty minutes just looking at benchmarks. So these benchmarks are running like concurrently. So they're running. You know, starting with like this one comparison user and then. Eight sixty four hundred eighty two, and the cool thing is like we can be at we can actually compare multiple runs against each other. You can kind of see, like, even just increasing the match the number of match tokens, doesn't really change.

That much, the, timer for a second. But an interesting thing that I did notice of increasing that is like the inter-token latency. Actually decreases quite a bit when you increase that. Batch tokens, which means it's like the request itself, especially running like a long. Like jobs, actually, it's actually much faster finishing these jobs than like. The cool thing is, like. You can add this to an agent, and just start going. And you can start getting those answers much faster.

### 00:11:12 — Throughput, Latency & Cost Metrics in Practice

Like, have the data and move from this. If you have it like on Pod, you can. Start moving to you know multi-node cluster. You can move to serverless too. So you're going to be like scaling up and down. That this. Is a perfect way of like actually getting data, and just to give you like a context on our serverless. Serviceless. A lot of people will do the same thing. They just put whatever the base config is. And then are struggling as like they're waiting for workers to.

Startup. This actually gets you the real data. You're now ready to go to production. Makes it really simple and just gives it's like I always say it's basing everything in fact. And I can like show you guys right here. Like this is. Actually, like Kimmy Rani, so I was just like, what is a bunch of Stop it! Sorry. But that this is little commands just running through it. Yeah, you know it is pretty quick. Like I would say like there's like probably like. 50 users right now on our internal one, and we most of us are getting off.

I'm just using this, and we have other instances. We like GLM, DeepSeek, Run 3.8, but yeah, like I think in the future we're looking to more at like. Smart routers, like how do we host all this without being reliant on someone else? Yeah. So let me go back to our. A Jakovcevic; Some like an important data. We were just talking about if anyone was a screenshot that. But like I said, like you can you can specify the experiment. Yourself too. So if you're like, I'm gonna have like 500 people using this all the time. Like I want to like see how well.

This is going to be, but at the end of the day, like I said, is. How do we go from R and D to production? And I think this is where like Benchpod will. Make it a lot more easier for people to use. So, like at the end of the day. Like what I want you guys to like know is like, you know. Pick a pod. Look at a GPU machine. You have your model. Compare and base. Don't just start with like the meal and recipe. The meal and recipe is proven.

But it's not production ready. And then test. Have your agent test it. And then whatever you. You know, based on what you need, this ITL, you need TDF, TPO team, like metric, like optimize on that. And then should that go to service scale out and how you might. Now you have a working LLM model. That can be used internally. Can be used for customers. Yeah, it's it just makes it very simple. But yeah. One thing I would say, especially with like Kimmy, that I've noticed is it's not always necessary.

Like, like a big thing that I think like. Most people don't think about is that you can use a small Yeah, right now like that's like on our on our platform like that's getting. Essentially, it might go up, might go down a little, but you know, it's a very powerful machine. And I think when you're thinking about like how you're gonna be. Serving stuff if you want to be doing this internally or for yourself, what makes sense the best? And just because it's the frontier model, it doesn't make sense. Like I said, like.

Guy runs deepseek on a 48200s and does a really good job. Kimmy's More for like long tasks that I'm trying to solve something like very detailed. But like I said, the other thing is like making sure you're like tooling tools like on there. That's a big thing. Contexts like I'm not going to be going through too much about like contexts. Like with these and all that, but the ability to have all that. And like AI governance is the next step that we are going to be going in the front line, but just something to always be thinking about, especially if you're going to be.

Hosting your LLM models, but yeah, is there any questions? And we'll also be downstairs. But yeah, add me on LinkedIn if you want to talk. More. I'm always exploring everything new every week, so always have some like gotchas that I Through the time I've been doing all this work. And yeah, also scan the QR code so you can get some credits. A Jakovcevic; So you can go play around with it. Yeah, any questions? Yes. Yes. Yes. You have one over here. Oh yeah. Sorry. Oh yes, do you guys have the ability to do disaggregated serving?

Ah yes, we yes, yes, yeah. So like I would actually use like a for that, but yes, that is very possible. You can also run like a Ray cluster, cluster serving. But that's also another thing as you scale up, of like you know how you are using like. Llama cache. Yeah, like I mean, right now, like I would say. Our tests internally, like the fastest cache is Optiver itself. But once you start serving to you know, millions of users. That's where I think. I mean, desired serving, and also like your caching mechanism is important.

Anything else? Oh well. It's a pleasure. Yeah, see me at the at the booth. If you guys want to talk more, we love talking about for Tel and anything that it has to do with.
