---
title: "Your agent needs a skill to improve its skills"
speakers:
  - name: Ben Holmes
    affiliation: Warp
room: "Turing Room (Riverside Ballroom)"
starts_at: "2026-10-14T14:30:00-04:00"
ends_at: "2026-10-14T14:48:00-04:00"
format: "talk"
recording: "2026-10-14_1429_Warp"
duration: "19m 11s"
source: "voice-memos-transcript"
---

# Your agent needs a skill to improve its skills

### 00:00:00 — Why Agents Repeat Mistakes Across Sessions

I was always wondering what an agent form would look like. I think this is it. Okay. Well, I hope everyone's been enjoying the conference so far. I'm Ben Holmes. I'm a FedEx engineering lead at Warp, and I'm gonna be talking about building self improving agents. Agents that look through their past work and figure out how to improve their own setup. So for a bit of context, I work on warp factories, which is open flexible infrastructure to help you all build software factories of your own, and crucially ones that improve themselves as part of the stack.

I'm not going to be talking too much about software factories as a whole today, but I'm going to be talking about one crucial part of it, which is having agents introspect all of the work that they do inside of one of those systems and suggest improvements so that the agent performs better and better over time. So, I'm going to start by just presenting what you might think of when you hear the word software factory for a bit of definition setting.

It's the idea of automating the software development lifecycle. You may have seen this as an assembly line of different agents doing different things and handing off. It may have also seen it as a wheel, as you see in this case, where you start from a task list, a board, slack messages, wherever you're tracking work, and you have, an assembly line of agents go through the process of researching it or triaging, maybe working with a human to write a spec, implementing that change, and bringing computer use into the picture to take screenshots of the recording so that it's actually good for requesting it on the other side, and also maybe doing rounds of adversarial code review in the mix.

to make sure that it's something that is ready for human eyes. And on the other hand, you have agents monitored a system, and around and around we go. But the more interesting part, I would say, is all of the sort of meta engineering that goes around making that wheel run as efficiently as it can. So a few terms have been maybe floating around right now, like meta engineering, gardening, or something that we've been using, just factory engineering.

It's the idea of actually putting in engineering work to improve the system that is driving the agents themselves. And there are a lot of things that you might want to optimize inside of that system. It may be the skills that are driving the agents, maybe improving the code architecture, and doing static analysis to make sure the agents are working on the right parts of the code base.

I've been hearing about, like, sonar, cube, and other sponsors at this event that are doing things in this vein. The improvement look that we're going to be talking about is specifically around agent skills and configuration. And the loop is gonna look something like this. It's the idea that you can have agents review their past conversations, you can set up some scoring agents to score the quality of how those conversations went.

So think of this like an LM as a judge, reviewing against rubrics that you define across metrics like efficiency, or code quality, or test coverage. And then once you graded a whole lot of conversations across all the work your team is doing, you can find all the failures, figure out reasons that those ferriers are happening, and then maybe an agent wakes up on a Cron to suggest improvements, and then you can continue evaluating, seeing how the scores perform, and so on.

So I'm going to break down that wheel into the individual segments that we can talk about each of them individually. So the 1st part of that loop that I showed you is getting all of your age and conversations in one place. that the agent can actually reason about all the work that your team is doing. If you're working with, you know, local agents like blog code or Codex or Pi or any of those, those are going to be files on your system.

So, Claude, you're going to have a Claude folder where all that lives. going to have a Codex folder. And that works well enough if you want to sort of optimize your single player setup. I've actually talked to teams that set up an S3 bucket and an automation to like take everyone's dot clod folders and zip them up and put them in a shared S3 instance, just so we have everyone's conversations in one place.

It's a way of doing things. But there are other ways that you can sort of centralize this information. If you're using a software factory system, it kind of comes for free. This is the idea that agents are running inside of maybe a shared computer. So not on everyone's individual laptops, but, like, a shared computer that everyone's going to send tasks into, that might be, like, a long running compute instance on open glot, or it might be, like, isolated sandboxes that spin up for every run that you do.

If you're using warps factory setup, it would be isolated docker sandboxes for each agent, working on tasks, using other cloud runners, you'll probably end up in the same sort of system, but it's all the same idea. We want to find a way to get everyone's team, their whole team's conversations in one place, so that they're easy to introspect and figure out how to improve your setup.

And if you're doing it on one cloud runner, where all the tasks flow through, you kind of get that for free, because all the agent traces belong to a single instance. So that's something that's baked in. And inside of that, they're gonna want to make sure you have all the information. So not just the, like, transcript, talking to the agent, what did it send back where the human send back?

We also want all of the metadata around it. So that means the tool calls, the file system calls, the MCPs that it's connecting to everything that connects the agent to the outside world should also be inside of that agent trace when you start doing this analysis. And you also want the outfits to be in there. That can just be the code diffs that live inside of all of your conversations.

It can also be the actual pull request on the other side, if you like, pin the commit and look at the diff. In any case, you just want to make sure that you have three things. You got the transcript of what was said, you've got the tool calls that show what the agent did. And then you have the output, which is something that you may want to grade for quality purposes.

And once you have all of that, you can start actually scoring the quality, or rather, you can have an agent start scoring the quality. So I like doing a show of hands for this little part. How many people in here feel like their agents write too many tests? Too many of us. Okay. I expected more, but for those at home, it's about like 40% of people, which I think is a pretty big number.

On our team, it was about 100% name. It can depend on your model and it can depend on your instructions. But let's say that your team is noticing your agents are writing a lot of tests. Maybe extraneous ones, maybe have your own opinions about, do you need, and to end test coverage versus integration, coverage versus

### 00:06:38 — A Meta-Skill for Mining Past Runs & Updating Skills

unit test coverage? People are experimenting with all sorts of things there. So you might want to set up a score for that, called redundant test. that evaluates how often is the agent writing too many tests across each conversation that it has? Another thing that you may want to score is the way the agent communicates with you. So maybe another show of hands, how many people feel like their agents write too many comments?

Yeah. There's about everyone. Comments are dead. Yeah. I'm not going to call out the model name, but I have an A... You can do that. But this is also a common issue with agents, and it's not just for noise or provisions, because we all know that code review is kind of the biggest bottleneck right now. It does matter how well the age of communicates changes, both summarizing them, and also in the comments that it leaves within the code itself.

Because they can be barriers to actually get a code change reviewed quickly. So you may have another metric, like verbosity, which is what we call it, which is, is the agent overly verbose way of stopping to you or when it's writing code? Both of those are examples of kind of the same thing, which is a handle on language. So you could set up a score and that sort of defines that.

And a 3rd one, I like to bring up is just efficiency of the agent, and this speaks to the need for tool calls and MCP calls and your traces, because when you're running things a little bit, without a human in the loop, so you'll keep setting them off a longer and longer runs. Maybe they're running in a cloud sandbox. You're not looking at the conversation itself.

It becomes easier and easier to miss all of the failed tool calls that an agent does. Like, an agent, these days are very persistent and will work around whatever roadblock that they run into, and they won't tell you about it. They'll just tell you that it worked on the other side. And one common phone number, then we ran into was like, in our test harness, there were a ton of bad instructions that were out of date in the skills, but the agent worked around him and never told us because it figured it out just by trying to ping a bunch of port numbers, figure out its environment, and then eventually start doing code.

So the most that we knew is like, oh, the agent takes like 2 minutes longer than maybe we expect. But under the hood, there's actually a lot to be improved. So that's something you can evaluate as a score, to just say looking through the tool calls, is it efficiently getting to the solution or is it spinning its wheels a little bit? And I can show you what one of these scores looks like.

It's just marked down as you would probably expect. In our setup here, it'll kind of be like a specialized skilled definition where you can define what thing you're trying to score with an LM as a judge approach. So here we're evaluating efficiency in this score, saying whether the agent worked towards the result or a wasted effort on redundant steps and not necessary back and forth.

And then we set some labels that define what success and photo look like on that criteria. So, if you remember back in high school writing five paragraph essays, and the teacher gives you a rubric of, like, you wrote a good essay, if you have exactly five paragraphs, and you only use active voice instead of passive, that's sort of thing. It is still kind of helpful to put an agent through those places for things that can be pretty clearly defined.

Efficiency being one of them. So we set up one of these rubrics to have that teacher agent go through and decide, do you get good marks on efficiency, or is it kind of below the bar? And you can decide what pass and fail look like. In our case, maybe the bound is halfway through this list. So if it's a .4 or .2, that's kind of a failing grade, something went wrong in that conversation.

And above it, it is a passing grade and probably doesn't need to be evaluated. Things went mostly okay. And then down here is the actual definition of what that rubric means, and it's gonna restate some stuff that you would expect. So cost human, the information gathering phase, routine step overhead, you should keep this as succinct as possible and just build it up as you go.

This is a template that we like to give to people. But you can set it up with literally just like a couple bullet points and just your rubric and test it out yourself. It's more of a art than a science. But once you have all these scores set up, then you can start having agents actually grade the conversations. So over here, let's say we have some sable sessions that we want agents to look through.

starting with like an off service at the agent implemented in a full stack context. Let's say that we had a full agent conversation about building a full stack implementation of this, and the PR was merged, and now it's time for an agent to go great how that conversation went. Well, the agent will spin up. In our case, we're saying, one agent per conversation or one agent run per conversation run, you can set up a random sampling for, you know, just the sake of tokens, or you can run it across that brain conversation?

Roy depends. But let's say in a random sampling, it pulled out this one and then told an agent to grade across the engine of this criteria. So walking down the line, it might say, looking at the test coverage of road being a ton of unit tests for the off service, when our guidelines say that you should most prefer and fantastic. And so maybe we give it a fable because it didn't really follow the instructions we expected.

And then maybe for verbosity, it was actually pretty clear. It was using a new model selection that doesn't write code comments, GoGPT, or anyone in the room? But let's say that it didn't really write too many comments. It was very easy to understand the PR, so it gets passed. And then moving on to efficiency, let's say it was trying to do a lot of exploration in its test environment to figure out how to test this change in the first place when really it should have had some upfront instruction on that.

And that would probably be a family, right? on that score. And again, pass and fail, it says, did it fall below the line, on the rubric that we said? And then you can just go through each of your agent conversations and continue scoring them. So automatically, usually the trigger being a PR merged, kicking an agent to review that conversation across your grading criteria.

And then over time, you'll start aggregating a lot of data on how conversations go. And each of these will include like the pass and failure rates. So did it pass a fail crossing definition? And then you also have an agent describe why one of those failures or passes happened. And then this becomes context that another agent can use to decide what approve is to make.

So the way that we set it up, going back to this wheel, is the idea you, great conversations as

### 00:12:58 — Evaluating Self-Improving Agent Loops at Warp

soon as they happen. And then maybe on a chron job, every 24 hours, go through a sampling of the past 24 hours of conversations. Maybe there's been, like, 200. Filter it down to the failures. and then pass, in all of those failing reports that describe what failed and why, to a self improvement agent, and tell it, these were the 50 conversations that failed.

Here are the notes that were left on each conversation. Go ahead and find commonalities. Here's access to our skills repository and the code base if you want to make architecture changes. So in this little snippet I showed, maybe it adds a coverage pyramid because we're done to test our popping up across a lot of PRs. And I can show you a couple other examples.

Both in a skill that you can take home, and also the automated system that we have inside of warp factories. So, this is gonna be the easiest one that y'all get to try. So it's called Skill Doctor. There's something you can find at a work.dev slash school doctor or show the link in a second. But this is a skill that you can run on your single player setup, and it'll crawl through all of your agent conversations and clog, codex pire, whatever else.

And just do a one-time grading. So if you've been wondering about all the hidden gems in your conversations, because you haven't done this approach before, you can just run this across your setup and see what happens. So this was a sample I ran across from Codec sessions, building this project here, and we can see on the side that it grades in batches for a little bit of token efficiency, and it came up with some score reports across all of the metrics that we care about.

In this test environment, it has efficiency in code quality as the ones that it evaluates. And then, on the other side, the self improvement agent looks at all those scores and comes back with a report. So let's go ahead and take a look at that. I like to show the animation. We love it. But this is kind of your skill report card that shows how the agent performed across all of those rubrics that we defined.

Again, this is one shot. It's probably something that you want to do continuously on your setup rather than whenever someone remembers. But as a 1st go to just see what you can optimize right now, it's nice to get some low hanging fruit. So, in this example, it grade across these metrics and noticed that these were a little bit lower than I expected.

For Boston, it was fine. So, it went through all of the notes that were given by the scoring agents, and then suggested some changes to the skill makeup. And this one is going to mirror what I was mentioning earlier, where it noticed that the agent was usually trying to fight for port numbers on the machine that it was testing. And it didn't really understand how the environment was set up.

So this proposed a change in the end to end testing skill to have the agent get better instructions on, finding a port number first, and then going forward, instead of just banging against the wall until we got something running. Second save a little bit of efficiency in the tool calls. I also noticed that I constantly wanted to write a different chains log report with the language that was specified.

And so it rewrote my change log skill to have a more prescriptive language on how these things are written. So I don't have to do that manual back and forth every time an agent opens a PR. And these were things that I could have gone and found myself, but especially this one on port numbers, since I'm not watching the stretches super closely, it's usually just behind like a working toggle if you're using like an agent harness or it's behind a cloud.

It's nice to pick up on things like this so you don't miss them. So last thing that'll leave you with is how you can run this continuously over time. Oh, shoot. No, I lost access to my stage. Well, I can at least describe with words what that was. which is the set of sort of graphs on the scores that are written. Because one thing, I was actually explaining this to someone who uses like a memory system in their harness.

And memories are a really useful way of having agents, like introspect, maybe you've heard of like dreaming overnight and thinking about how conversations went. It's very similar to what we talked about here. But the one part that's kind of missing from that is it's very invisible, what the agent actually decided or what takeaways that it got from all the conversations. It's useful when you're using scoring to have an actual dashboard that explains how all of those conversations went.

So I kind of draw it out here, where if you have, like the efficiency over time, it's pretty easy to start aggregating data. I have not practiced this live. Let's try it. where maybe you can actually track over time how the efficiency score has been fluctuating. So the agent's constantly scoring setups and it's giving grades of like 50%, 60% on average. And you can attribute changes that you made in your agent setup to inflections in the score.

So not only are you have any age and improve themselves, you also have some proof points of like, oh, it shipped this change, and I got this result out of it. So I actually know that when I merge that skill that it suggested, something real happened on the other side. So you could say, oh, there was an inflection point here. This is when I merged the skill, and I can see that efficiency went up by a certain percentage.

By having scores in the loop with self-improvement, you can get that sort of view into things. And this is the dashboard that we have for proposing those self-improvement PRs. So in more factories, if you set up Microsoft Factory with this, instead of running it one time, the agent is continuously scoring conversations all the time. And then on a kron, an agent can look through those scores and suggest PRs to improve your setup.

So this is the inbox of things that need our team's review right now. This is actually our agent setup. So this is across all of the different agents that back our team. And we can take a look at one of them that was merged, where it noticed an issue in the triage skill, where we were missing some config to let it spawn subages.

So it was continuously like banging its head trying to figure out, how do I make subagents? And it just waste punch tool calls. Just found it and suggests you want to patch that part of your factory and take next time. That will save me some tokens. So this is one of many examples that we merged in that just make our agents a little bit more efficient and higher quality.

So with that, if you're interested in any of these ideas, you can check out work factories. It's an easy Google search. Or you can search for warp skill doctor to try out that skill I mentioned as just a way to try this out on your own setup and see if you get a little bit of benefit out of it. With that, thank you so much and enjoy the rest.
