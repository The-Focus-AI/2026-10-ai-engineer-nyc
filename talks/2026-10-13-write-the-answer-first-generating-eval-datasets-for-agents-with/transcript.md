---
title: "Write the Answer First: Generating Eval Datasets for Agents With No Benchmark"
speakers:
  - name: Nathanael Weill
    affiliation: Air Canada
room: "Turing Room (Riverside Ballroom)"
starts_at: "2026-10-13T11:05:00-04:00"
ends_at: "2026-10-13T11:23:00-04:00"
format: "talk"
recording: "2026-10-13_1104_Air-Canada"
duration: "19m 26s"
source: "qwen3-asr-1.7b"
---

# Write the Answer First: Generating Eval Datasets for Agents With No Benchmark

> Transcribed by qwen3-asr-1.7b with a schedule prompt. Possible prompt artifacts, names heard more often here than in the unprompted Voice Memos transcript (Qwen vs Voice Memos): Towards AI (2 vs 0), Air Canada (3 vs 0). Check them against the audio before quoting.

### 00:00:00 — Building Custom Enterprise Agents Without Benchmarks or Experts

I've been doing a lot of things since the last agent type in shipping without integration, and today I want to tell you a story. So I'm working at Air Canada. So we're going to be very much more focused on this business. I'm not analyzing. I'm not analyzing the youth company. We want integration.

So my team is in charge of delivering AI solutions. Problem when we tackle some great vision for a task that is so specific, we don't have any particular benchmark we can rely on. That's the main problem we I'm trying to address in this presentation. More importantly, it's not that we don't have a benchmark. We are better sent to build Asia, so we are in the United States, but we are not domain experts. A good domain expert sits in different business units, and they are using their own platform, and we have a limited access. So both of those things, when together, new situation where it's very hard for us to build any evaluation of any conventional.

### 00:01:29 — Telecom Q&A and the Weekly Chatbot Review Bottleneck

So before going to Air Canada, I was working for a different company. This was the company, and the task was to build Q and A system for telecommunications engineer. So I don't think you're familiar with the domain. Telecommunications are used. The main there is about ten thousand documents, a lot of vendor documents. On top of that, with the logic to know which document you should you should find in order to answer the question, so it's a bit of a complex task. And in 2024, everybody wanted to be advised, so we start with that. On meetings, it's super easy.

So the thing is, when we tackle this project is the same problem as Air Canada. We don't have access — the expert, we have limited access to the data, and we couldn't actually create the expert ourselves. Standing up, we were in competition. Two external, one internal. It's not like our solution actually worked. What means worked is actually delivering the value. Will people like this option? How should we do this? But to be honest, I don't know why was a team. So do I just want to show what I actually did, or my team actually did.

We all have the same documents, same tasks. Everything is the same, but, so for those that are familiar with Rails, the principle is to ask a question to the system. The system found the relevant documents based on, formulate an inquiry. Something that exists for a long time now. And for those that actually tried it, if you found the right page or the right documents, ninety percent of the time, you have actually the right answer. So the challenge is to find the right answer.

So we created a very complex pipeline that gets complicated over time if you education, Japan Education. Back in the time, is everybody has an amazing technique to improve the solution. We try them, it's actually improved the solution. So on paper it's all for them, for the politicians, but for us it's being hard. And more importantly, when we add complexity, we found that we break something else, so something that used. So we can either, and why we can get more easily into solving the problems, we keep constantly we keep breaking things around.

The other panel is this one. We can change an agent in a few minutes. I do. So, definitely for ranking or whatever, is it instead? But to break that, we had a crazy meeting once a week with experts. We put the giant screen is five different chatbots, ask the same question to all of them and ask the — let's get to it. I prepare this one. I prepare this one. And funny enough, they're not always agreeing. It's very hard when you when you could expand quicker in your room. That's the main risk. So our budget was we can try one solution a week, and this was not enough to go for. So the before going further, so the process was following. We ask we ask the question. They should answer. We ask the expert to read. Sometimes they don't know the answer. They look up. Takes a lot of time. Then we have the budget of one trillion.

### 00:05:31 — Inverting RAG Evaluation by Starting from the Source Page

So there is nothing new here. This is something that is well known, is we have a problem. So we start with the page, we ask an LLM to write a question about this page, which is a news task. We ask region to search for this page that has been used for generative question. We can actually use code to generate. I'm no longer opinions. No longer anything. We can automate this stuff, and that's a lot less much faster. So, for those that work in labs, there is plenty of implementation of this. This principle cannot be applied to the past.

So the impact of that is we went from one iteration week to business day, and we start to see the accuracy or the rating from the experts going up and up, and actually, removing a lot of complexity. We didn't need a lot of rules. I'm focusing on the rights, and they demand the rights, taking the right answer in the right time or is the right thing to do. And we saw the we saw the decreasing volume of customers. So I don't know why we succeeded, but I'm pretty sure the team didn't have enough. So that we're using this kind of long loop, the next step is to get much more scale and do that. I might learn from this back in twenty four is if you can't breed the agents, you can't make it better. So, let's stick to me until this day. It's been two years now.

### 00:07:23 — Supplier Contract Review and the Four-Step Agent

And I want to go back to that, where we have a different project. So in twenty six, the project is about analyzing. You can imagine there was a lot of suppliers. We did a lot of these contracts, is Excel looking at them one by one, checking each of those closes, and they've analyzed it and provide the feedback. This growth is not viable. This growth needs to be reviewed. There is a lot of work in that. It's a very long task and very costly, because if we need, we need some superior deliver right now, and we don't, includes rather giving the end to chain, and to miss the close is also very costly because at the end of the day, transaction. So it's a tricky problem.

And they came to me and to the data science team to build an agent that can actually do that for us, so can we optimize this task? Obviously, there is a lot of difference, a lot of rules, a lot of things that you do. Experts are super bullish, and imagine the price of — and there is no benchmark for that. We cannot go on the web and find documents, and find an existing benchmark. So go back to the same problem as I was in twenty four. Cycles were super slow, and we knew that we won't be there in a shape where you can go past and try and try and try. And I knew that if we if we land to a situation, we can have a better trajectory in terms of factors. That was the time for this for this project. The time is, creating the enterprise experience is a well-known and defined thing in the world, but for this specific project, there is no guy in the wall that say, hey, you should use this thing, you should use this.

So, we're trying to think how we can reapply the same mechanism from what I've done on ride to this specific project, and we have plenty of project that — so we're using the same concept of getting the answer first, and then try the agent from the back. So, bring me the speakers downstairs. It's a bit simplified, but actually the agent has four steps. We need to spot the clues in the contract. We need to find the relevant documents to support an amendment. We need to write the amendment, and then at the end, there is a conversation system that tells you should keep it on us. The first step, for example, is classifying all the sections of the contract into specific domain domains, and then found if there's a defect or there's a change to be done in this section. So we did have this trade from the right, so we know how to find the losing. So this is covered, but for the other section of the of the agent, we didn't have anything.

### 00:10:37 — Historical Contract Diffs and Rule-Driven Synthesis

So I'm going to present five different techniques that we use in this project — are we try to use in this project — that is trying to address this specific problem. My goal is not to show off, my goal is to get you inspired, in order to we applied these tools. More on challenges. So the first one is to use past decision answers. So we can use past control compare with the one that has been. The second one is to choose something you're looking for, write the contract around, or generate the contract. The third one is take a good contract that has been signed and graded. The fourth one is about things that should not change, no matter what you do, it's not that much. And the fifth one is actually the most powerful.

So immediately we jump into this approach. We asked the staff to write us the original contract, the one that has been signed. We're going to take that, do a diff like we do in the code, to get what has changed, and the agent should provide the same exact stats would be perfect. However, for many reasons, our team doesn't keep all the contract. They don't keep the original one. They just — so we could not have any of those pairs of contracts. So this thing doesn't work.

Okay. Second one, we took the rule. So that's changing a bit the topic. Instead of creating — slides are basically just a thing for slides — we start from wood. And the rule is, for example, we have the cap above one million dollars. So that's every contract that I can dash. So you know the rule, you create close without breaking this rule, and generate a contract around. And you should find the bull flag, the flag, which is breaking down. So that's simple. It doesn't require a lot of work. A lot of things can be generated. The point is, you need to know the rules. Looking up, we could actually get some of those from either the experts or the documentation they have, but cannot guarantee the coverage of everything. So we came up, we also with our own rules. So we unite again, 275. That's that we know and run, and we know the answer. But see now to the right, we just — we get the problem. We can get the problem, and we try to solve it.

### 00:13:36 — Clause Removal, Invariance Perturbations, and Blank Templates

Another one, which is very old, actually. So this kind of contract that they designed, it removes, and the agents suppose to say hey, there's something missing here. It's a very hard task. It was. Some suppliers have, on some days, different kinds of content. I mean, want to be in well contract, care of that little thinking. And we mix those with existing contracts that should not, in fact — so that's the most powerful approach we've got today. Using this approach, we can generate the contract, and at the end of the day, we found that our agents are meeting most of the food that has been removed. So that's very strong. Okay, fourth technique. You don't change. You change something that will not affect the world — well, should not change anything in the vision. For example, the name of the supplier, the address of the supplier, something that should not have any impact on the development. We can view all the flows so that all of us can publish this together, and you can build the same product manager. All of those have, I think, that.

This example shows the recent and future trends towards AI. So we stay away from elements just like.

The fifth one — the concept of our experience has evolved, and today it is now, those lines should be filled by the experts, and instead of trying to fill them, we generate an array for each of those blanks, which — some covers break some wood. Some covers doesn't. We know that. So we know what actually should be tagged as a breach or not. Again, this is a contract. We don't need to add any more words. What the good thing with this one is, our extracts are already used templates, so we can reuse them. We speak to Rand and get the evaluation back in five minutes.

### 00:16:18 — Why Deterministic Checks Beat Noisy LLM Judges

I just want to highlight one point, and we went through all of these kind of categories of revenue and developer. How much your code are very fast. As soon as we step into the room as judge can be very fancy, can be very useful. It's so hard. Like we got so much noise compared to the noise with the with the agents that we're doing. Solving this problem is almost as hard as solving the whiteboard. Finding the right end of the right harness for the end of the judge is very complex. There is some body we can do — ask, you can do fact checking, you can do something, but actually, we have so much work, and we did not find the right ones for this session. There is plenty of conversation. I won't go over all of them, but I will touch on a few of them.

### 00:17:13 — Reengineering Agents Around Evaluability

But if I were to make some hand points, so the trajectory you can — you know what you can contribute in some other. You generate a story about it. You ask me the MVP. Look at the train to see the second place right. That's where you might want to move. Doesn't matter what your agent is, if you know who to get the answer, if you know what you're looking for, and just provide an example, generate the input, and then try trying to — don't apply to everything, and sometimes we need to reengineer our solution to fit this value, even if we move away slightly from the original design of the solution. The original design we could not evaluate it. We switched to something that we can actually evaluate because of that.

One thing to highlight is that at the end of the day, you generate the test, you get a better agent, you get some good fits, so it's time to improvise if you like, and we don't use this pickup to fix major. We use this feedback to generate better tests, better plans, better ideas for new products. And what look at it? That can be done by.

There is a lot of food there, and that's my confusion slide. Great answer first. Yeah, it's been nice. When you generate those things, it's not an act of ownership towards AI for the for the solution. So I hope you like this presentation. I know that the 24-hour shift is the hardest one. If you want to quit releasing agents without evaluation and I would be happy to support you and have your company.
