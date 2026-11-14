---
title: "Can Any Model Write Like Me? Building a Benchmark for Creative Writing"
speakers:
  - name: Louis-François Bouchard
    affiliation: Towards AI
room: "Turing Room (Riverside Ballroom)"
starts_at: "2026-10-13T10:40:00-04:00"
ends_at: "2026-10-13T10:58:00-04:00"
format: "talk"
recording: "2026-10-13_1039_Writing-Slop"
duration: "18m 49s"
source: "qwen3-asr-1.7b"
---

# Can Any Model Write Like Me? Building a Benchmark for Creative Writing

> Transcribed by qwen3-asr-1.7b with a schedule prompt. Possible prompt artifacts, names heard more often here than in the unprompted Voice Memos transcript (Qwen vs Voice Memos): Towards AI (2 vs 0). Check them against the audio before quoting.

### 00:00:00 — Defining AI Slop & Introducing ToneBench

And more importantly, I want to trying to help fixing what Kerfatin termed as the stuck Achilles, that he thought would start in twenty six and I think we've seen that on social media. So, to try to fix this, and to stub it up, the first thing to define it.

So first, what is love? There are tons of different definitions from the various persons that build, but what I think we can all agree is that it really sucks to read something that feels generated, and it usually looks like this with the words that you know of, the Dell and the generative and other things like these. And the main problem is that even as models get better with Stable Diffusion, Point One, and all the better models, love doesn't seem to go away. It just keeps on scaling, so we need something different than just training the models more, it seems.

And I do want to try to, at this point, define what stuff is, so that we can understand why it's there. And so, to me, stuff is made of six main things. First, there are tons of overused words by language models that we don't really use, like "del," that we reading the well. Second is usually too general. It's always talking about most things, most projects, it doesn't share nothing specific, and I'm myself guilty of doing that on LinkedIn as well, which I guess it's the LinkedIn meta, so it's is normal there, and worse, sloppy text usually says nothing. It's just like nice words put together that we don't even know, and even wars end up, it says nothing, but it also repeats itself enough.

So it repeats nothing, and it's too general, and even worse, it hallucinates, as we know, models hallucinate. So the stuff text also would not be totally trusted. Endlessly, the worst to me is that it usually has the wrong tone, or at least it has no tone and like everyone's tone at the same time, so it just doesn't really talk back to you. It doesn't share stuff that you would share. So my goal here today, and with this project that I've been working on, is to first measure this sloppy writing — not just love words. I don't want to rebuild the two bench love score. It's just, it's really about measuring how — so in order to do that, we are well today right now, releasing a new benchmark that we called Phone Bench, which the whole goal of the benchmark is to measure if the new models or models are good at creative writing, which illustrates the fine as well.

So here's the plan for today. The plan is to justify do we even need another benchmark. Then how it works, what we measure, what — how we built it, and I want to share like the cost of building it, our decisions, what we learned already from for writing with AI from the benchmark, and share some more stuff about this.

### 00:03:21 — Why Educational Content Needs a Creative Writing Benchmark

So with that, let's delve in. So the first, first thing: Do we even need another benchmark again? And just looking at LinkedIn and X replies, my replies on X, I think we do. It's like people are spamming more and more generated content, so at least have them be decently good, and more precisely, I also really need it.

We are a small team at Towards AI, my company, and we have one side of the company that is focused on education. We build tons of educational content, mostly for AI engineering. And as a small team, obviously we use AI as well for that, and it's been extremely annoying to redo this stuff constantly and try to fix it. We, I published hundreds of videos. We published thousands of articles. We released a book. We are working on a second one for AI engineering, and so we really need to have the best models possible that will help us write better and not be full of stuff.

And another nice addition to that is that I've been sharing this benchmark on Ace for quite some time, as I've been building it, and it got really nice engagement, and people seem to confirm that we did need some sort of more creative writing benchmarks like this one.

And lastly, to prove that I think we are the right team to work on this benchmark, we, well, I've been building everything — AI models since my master's and then PhD, and now at Towards AI, we do build evaluation pipelines for our clients. We have 15 AI engineers with us, and we have creative writers, editors, onboards. So we already have that for our content, but I think, well, I wanted to leverage that to build a bed farm and help the community. So what did we build exactly? Hopefully, I will try to share as much as possible, and I'm happy to chat if we can help even build our own, or if I can just share some of our learnings.

### 00:05:34 — Benchmark Architecture: Prompts, Scripts & Draft Variance

So what we built is super subjective. It's a weak measure if a model can write like me. And how I define that is that is just that if I can read it out loud like right now without cringing because of the words that I wouldn't do myself.

So the process is very simple. The process benchmark — the benchmark process is very simple. We have the prompt, that is the brief and the resource that we send to a model, and hopefully it will generate entirely a video script that I could have written. Obviously, that doesn't happen. It resurfaces. But that's the whole goal, and we made sure that final script, again, our rubrics and just our whole evaluation process.

And the prompt that we send to every model in the benchmark is much more in depth than that. It looks more like this, where we have a lot of details on how I talk, how I write, all tons of examples of my previous content videos. We have a lot of information on storytelling in general, active sentences, and just how to write well, and we have directions on what to generate and what to do for this current task, which in the end, the model would generate one script, and this is just one of them. In the current benchmark, we have ten different scripts that we worked really hard to make as good as possible, and we built rubrics for them to help, as we will see, LLM judges rate these generations. So we have ten different scripts. Some of them are published. Some are not. We don't see which ones are the benchmarks, so that we check for contamination as well.

And then, what do we do with these ten scripts? We take all the models out there, and we try to measure their generation. What that means is that, for every single model, we will do ten times this process, generate the article from the prompt. In fact, we generated five of them. I will very soon share away. Then we have four different A.I. Judges — an item I recently added as a test. Not sure if I will keep that, but yeah, I added it just to see if it worked well. And then we calculate in the end a final score for the lead-up.

I will go through all of these steps from left to right. So first, why do we generate the five scripts? Is to check for intra-model variability, which are I suggest if you are building your own evaluations, because, especially, I guess, on the creative task, sometimes, as we see here with Graph 4.7, some of the generations are outliers where it's as we see from the benchmark, it's just as good as Opus 5.5, but on just one generation out of five, so we want to measure for that. And the worse the model is, the widest the variance. So we have some learnings about that I'll share at the end as well. But yeah, it's we found that five drafts seems to be the good middle ground in terms of cost for us to execute and to measure this disparity.

### 00:08:55 — Scoring Rubrics, LLM Judge Bias & Human Ratings

So what do we measure exactly, and how do you even quantify writing quality? That's been the challenge, and we worked on it for quite some time. Right now, in all of the main parking, there are way more details on the back part as well, but what we measure is nine different metrics that we detail, that we really develop, but I can condense them in five main aspects. First, we measure the tone. Does it sound like me? Which means that can the model adapt to a specific. Second, we measure just pure — is it good writing? Does it have like good hooks, good emotion, emotional transition, and all the aspects that we're looking in a in a good story.

Then we must refer to those instructions. Then follow the length, the expected length, the format is better. Did it put the right images and right things in the right place? Fourth, we measure for research accuracy. So, we have a research brief along with each, and we just measure if it's hallucinated or used the research correctly, and lastly we measure for stuff using Incubants, but also our own measurements.

And what this looks, in terms of what the judges see, is more like that: we have around a thousand words of examples and instructions and directions around each of the metrics that we have, along with the script analyzed, my own script as some sort of guidance, and the reading the research. So all in all, it's a fourteen thousand pound that we send to every judge, to then get the feedback today. The next and — so the judge just analyzes the writing quality. It doesn't focus on length and doesn't know which model is writing. We just do that after with code itself.

On one metric, by tone and voice, which is our main metric, it looks a bit like this, where we have a lot of detailed descriptions of what is my tone and what to expect and how to analyze this. Then, the judge will categorize between six categories first, and after having found the category, it will give a rating. We found that this is the best way to measure for this more qualitative task. From just binary that we usually suggest to use, or directly categories, or directly percentage, we found that this actually works really well.

And it has tons of examples of what each score means in terms of for I think for each of the tasks, and what the judge sent back is something like this. It has the nine different metrics scored, with a justification for the score and an example of like, I wrote this part because of this example in particular. But the main thing is that all of this is automated, obviously, because we, with one hundred twenty models, we generate five drafts each for ten tasks, it quickly goes to the thousands of scripts to review. So we cannot really review this ourselves. And the problem with AI judges is that they have references. Some models prefer themselves, all of those for themselves, and particularly open AI.

And what I found quite funny when studying this is that it seems like Anthropic and OpenAI are really in a in a war here, where they seem to have plus training on painting each other. But all this to say that you really want to check for when you when you use LLM judges like using GPT for — if you want to know which model is best for your task, be careful and use different model family just to — because we see here that OpenAI really has a strong reference on its own family of models, not just one model, but all open AI models.

And so the fix also for that we listened to a few comments that I got on X, using human for a creative task, which would be ideal, but quite impractical. We still try to do that in a scalable way, where right now we compare manually me and two of my emails, one thousand AD pairs of the generated scripts, not the full scripts, but like a good chunk that is comparable between two scripts, two generations, and hopefully we'll do more. And I want to publicize this also for — to get help from the community in the future, but that's not right now.

### 00:13:56 — Benchmark Costs, Model Rankings & Price Tradeoffs

So what did it cost us, and what's the work behind us? For me, for us, it was a kickoff cost in terms of hours of around 500 hours to build the transcripts, define all the rubrics, find the examples, try to quantify quality, which is very difficult. And then I just iterated myself with four different 28 subscription for four months to build a benchmark and all the other things, and experiment, and change the matrix, the ratio, and all these things. And so we just spent thousands of dollars there.

And if you want to do this, a similar type of benchmark, you need to know that it costs quite a lot right now. If I just change one thing in the rubric, so how the judge rate generations, it would cost us more than two thousand dollars. And if I just change one line in an input prompt, it can control when it generates these things in the front, so you want to do this very carefully. Now, what can we get out of this benchmark, all the tone bins? You can get tons of things on the website itself. There's like a lot of details, but importantly, I want to share that what I've learned from the past four months is that you don't want to pick — or for creative writing, is that we don't want to pick the model that will generate the one-shot, amazing pose. You just want to find a model that will be the least annoying to you to get to where you want to be, so like there won't be any perfection anytime soon, I think.

And what that means right now on the benchmark, it means at scale, GLM five point three flash is extremely good, extremely cheap. It's 50 times cheaper than the best one, which is Opus 5.5 extra high, which is two point five times cheaper than Max Thinking, but with same results. So you don't want to use Max for writing, usually.

### 00:16:06 — Practical Workflow: Long Prompts & Multi-Draft Merging

And otherwise, for the best how to write with models that we got out of this is to first have an extremely long and detailed prompt. It cannot be long enough, and the more, the better. You want to have every example you can think of what to do and how to do it. Same thing for negative examples of things you don't like, and that doesn't sound right, the words you don't want, everything. You can share every if you write newsletters or whatever you can share it in full and it will just be better as well.

And what we've seen that really helps is to use a high thinking just, just one time, one to three times. Otherwise, it will loop into stuff. So just one review of another model with the same instructions directions that will give feedback to the writer. It really like I don't have the quantitative metrics on that, but it helps a lot.

And for a company, if you work with APIs and want to do this, have the best results at scale possible, what I suggest is to generate several drafts — ten drafts of one specific thing with a cheaper model like GLM or Flash, and then have a smarter high thinking job like Office, or whatever you want, pick and merge the best parts of each of these drafts, which I think will still land way less expensive than just one generation by Office 5.5, and I think will lead to better results from everything.

And lastly, you want a human review. You cannot really go around that. But all of these benchmark measures, obviously, my voice, so it's super subjective, but I and it's just one data point. We don't want to put too much — doesn't mean open source five is the best model. So, but ideally, it's a strong signal to find which model is good at writing and which is less sloppy.

I suggest you to build your own evaluation pipelines. If you want, we can help. You can chat or reach out. And regarding the benchmark, it's live. We just like right now publish this and release this, so there are tons of graphs, tons of insights, tons of comparisons, and details on the implementation methodology. Just check it out, and hopefully, it's useful.
