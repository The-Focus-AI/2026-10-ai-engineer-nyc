---
title: "Vault: Making Unstructured Data Work for Investing"
speakers:
  - name: Aaron Linsky
    affiliation: Bridgewater
  - name: Sam Green
    affiliation: Bridgewater
room: "Simons Room (Metropolitan East)"
starts_at: "2026-10-13T09:00:00-04:00"
ends_at: "2026-10-13T09:18:00-04:00"
format: "keynote"
recording: "2026-10-13_0904_Blackwater"
duration: "14m 58s"
source: "voice-memos-transcript"
---

# Vault: Making Unstructured Data Work for Investing

### 00:00:00 — From Structured Time Series to Unstructured Data at Bridgewater

All these phases of evolution, we've had a constant philosophy in mind, which is that we want to be constantly looking at how a world is changing and what's going on in the world. Noticing what dynamics are not yet encoded in our understanding and use that learning to improve and compound the future. For most of Bridgewalk's history, that meant building and overseeing time series models on structured data.

And that structured data needed to be carefully built so that it could be safe for use in our research process. And aligned to our internal ontology and world model so that we could get great leverage out of using the data that we can come. With the emersions of language models, we have that huge new opportunity to engage with a much wider world of data.

you know, news and research, transcripts, policy documents, and all of the internal conversation that was previously just in the ether. So the internal memos and meeting transcripts and debate happening inside department. We quickly realized that all of that data needed the exact same treatment to be fit for purpose. We needed to be carefully cleaned, governed, and made ready for use in both point and time, research questions today, and also our systematics study over time.

And when we looked out at the landscape of data vendors and data platform providers, there was nothing that brought us with all of the control that we needed to build and maintain our good advantage. And so we built the vault, which is our propository of external and internal and structure data. And the platform that indexes, organizes, and makes all of it ready for use by our human investors and agents.

Today, the vault has more than $100 million documents in it, with 1000s more added every day, minute by minute, from 135 external sources, and again, growing all the time, as well as all of the data from inside of Bridgewater. And crucially, all that data is not just dumped on our investor's desk. It is carefully aligned to our internal oncology with enrichments like the countries, concepts, markets, and most importantly, time period, discussed in the document.

To bring this to, I start with that a quick motivating example. So what I did here is I asked a fairly basic representative investment question to an enterprise chat plan. I asked, how is AI infrastructure investment impacting the Korean War and 2 market participants expect us to continue? And as you're all, I'm sure familiar with, the agent goes to the web and looks for resources they can draw on because I've explicitly asked it to go find other people's perspectives on the question.

And you can see it zooms in and it finds 15 relevant looking resources to draw on. before it gives a bad answer. And when I zoomed in on the answer, it gave back, a couple of things deducted me. The 1st is that even though it found 15 around good looking sources, it only picked one or 2 to answer to answer my question.

And the 2nd is down at the end of its response, where the agent itself acknowledges that it hasn't answered my question. It didn't find enough documents on the open web to establish a market consensus and meet the meet the parameters that I lay down. When I double look even further, the problem got even worse. One of the notes that it primarily drew on, to answer my question, was published way back in July of 2026, even though I asked this question and captured this answer just at the end of last week in early October.

In the age of AI and investing for 3 months is a massive amount of time. It's not even close to good enough to draw this resource, dance my question. When I ask this exact same query attached to the vault, something totally different happens. The 1st is that the connection to the ball tells to prompt the agent that it should look for a specific period of time when answering my question, so it zooms in on October 1st to October raise.

It finds a much wider array of resources. 52 candidate documents that are involving into the query over this specific period of time, because of the loss, much more significant corpus of content that's relevant to asking questions. And when it ultimately answers my question, it draws on seven, instead of only one or two. It gives me back a rich answer that the agent is more confident is going to address my question.

And so, for us, this is the big lesson for really involved to kind of motivate the talk today, which is that it takes great data and the right connectors to make PHDs impactful. And I'm gonna talk hand over to Aaron now to talk

### 00:04:56 — Inside Vault: Architecture for Investment Research

about some of the body engineering takeaways from political. Thanks, man. So, hi, I'm Erin. I run product engineering in Bridgewater. I'm gonna take us through a few of our learnings for building the vault over the past few years. I'm gonna start with one that might seem obvious, but I still think it's worth saying, which is, search is hard. But it gets even harder if we're designing for two different consumers.

And in this case, we're sorry for human nature, because I go over the difference here, starting with us. So, human feed precision and a high signal to noise ratio, because we can only read so much. Even a fast reader manages about 300 words a minute, personally, I mean, much slower. Agents are a different kind of reader. They're far less sensitive to precision.

If the data is there, they'll find it. And basically, anything you hand do them will get attended to. They scale super quickly, and they come and they consume about a 100 times faster, 40,000 words per man. And so we need to build valve for both of these. Well, we're thinking about the dimensions that matter, there are these 5 on the board, recall, precision, filtering, entitlements, and scale.

Some of them matter to people, so a matter of word agents, many to vote. I'm gonna go deep on three of these, precision for people, scale for agents, and then feel pretty cool. So, precision. Once we filled the vault, which was a heroic effort by our data and legal teams, recall was no longer a pressing issue. However, the number one complaint was fault searches back.

As a five gunner, it's painful to hear that, but my response was, let's match market. And that's what we did. We collected questions and found the best documents by hand, including ones at hotel full of warrant. You know, in total, it was about 200 examples and it took us less than a week. It was not fun or very glamorous, but it was very helpful.

And after we were having a very clear search wasn't that, the key metric we were looking at is precision at 10, which is of the top 10 results. How many are the right documents? And we were hitting about 15%. So the people were right, it was bad. But now we had a way to measure all of the improvements. And here on board are five of them, and by the time we got done with agenda search, we were up in the 995% recall time or preceding that time.

All right, so that was precision. Now on a filter. Like anyone, we want the most relevant documents. But when we looked at the production traces what we were seeing, is that almost always there was some condition, either at a certain date or from a certain source or about a specific asset. And all of that requires advanced filtering. And that's where we ran into our first major performance issue.

We're gonna quickly go through this a little bit technical here. There's classically two ways to build, background data. Post-filtering will use that factor index first, and then filter the top results by metadata. It's fast, but recall could be pretty low because the globally relevant results might not match your filters. On the other side, we have prefiltering, where we'll filter 1st and then calculate distances for every one of those matches.

The advantage there is that the recall is very good, but it can be very slow. And we need something in between. So that's what led us to try and then ultimately switch to turbo buffer. Their approach, which they call native filtering, looks only in the nearest clusters. I became matches and then sports just those. Well, you end up getting is something that's fast, like post-multering, but with close to the same recall as pre-filtering.

And lastly, I'm gonna talk about scale. Human scale for us, you're pretty pedestrian. 100 queries an hour, we have 300 users. They're gonna search, you know, every so often. It takes a user, it's been excreted out, so that they're receiving. Agent, on the other hand, are fewer as magnitude beyond that. Easily, 100 plus queries a second, and agents forms can hit thousands easily.

And they obviously will read, as I said earlier, will read dots in seconds. So we needed something I could scale as well. And again, turbo buffer handled that easily too. So we were covering all 5 dimensions. I didn't talk about the title, but I'll be talking about that later today. But we covered it all. It unlocked new workflows. But it didn't change how our researchers worked.

They still weren't coming involved every morning. And that's my second class, and I want to share here is no matter how amazing the tools are,

### 00:09:55 — Grounding, Evaluation & Iterative Deployment

we can't just drop them on our investor's desks and expect them to be used. We need to migrate theiral habits into I. And so we looked at what they were already doing. Many of them were living an email. The research came straight from the rovers. It subscribed lists, dead rules that filtered everything in the folders. It worked. It was familiar, and they knew that they weren't missing any night.

So, we had to build all of these features in the fall. So that's exactly it. Everything surgical, the subscriber lists became surges, and folders became, say, collections. It's the same habits, just a new home. And once we had that in there, we could open up new habits. So we can ask, they can ask questions across all the data, same show. They can follow dynamic fees by topic, and they can hand those collections over to their agents to take another action.

And that's when we clearly have power marketing. And once we had that fit, the users wanted it everywhere, so we put in a chat, we made a phone app, so they slackened their ID, and, of course, we availed all that to the agents as well. and put in a CRI because game influence, yeah. Okay, so the main topic here is, okay, so what is this name?

The second's gonna talk about what we're building right now, but 1st and foremost, it's helping us to move around that research circle faster. With our pocket analyst, which is our first AI analyst, you can do hunt, it can do ours. You can do powers of research in just a few minutes for a few dollars, and that's lying on the ball. And then we're expanding that now with the researcher, which is an next generation.

It's the same idea, stretched across days or weeks. We're also able to train custom models to more intelligently recent over the false data and use those together with other foundation models to feed systematic decision making processes. The forecaster is our 1st one, which produces AI generating macro relevant predictions. And then we also have built investment signals for them all, turning on structure data, structure, traditional tractors.

Now, and it's a sand to take us through false latest capability. So, like I alluded to it, we have to talk. The real prize is when you can take agents from a reactive resource that can be ready to answer, a human's question, and instead make them proactive participants, helping to steer your highlight professionals towards the most important areas for their attention. And the way that we're solving that problem is in an experience we're calling the investor or workbench, where the agent is always on tracking what's important to that investor and presenting them with the areas that are most in the of their attention.

It looks like an experience like this that relies on fault, where a topic is proposed and several pieces of information are for them to the investor, to decide whether they should be deeper or they ignore that time entirely. You can see here the car that investor sees in order to decide whether to dig it deeper into the same AI impact on currencies question that we looked at earlier and taught.

And the investor receives everything they need. And a genetic summary, if they want a quick scan across the agent's fundings, they also get the exact evidence that the agent was drawing on, so that they can assess for themselves what was leading to this recommendation. And if they choose to dig deeper, they have a direct connection to the research output from the analytical tools that Aaron's just describing.

And when they dig deeper alongside the agent to look at the dynamics driving this question, the learnings are automatically captured. The results of their collaboration are automatically captured back in the world. And so this process is the key lesson. The fault enables compounding. Because it provides the right evidence, the right internal, and external information at the fingertips of our investors and agents.

And it automatically captures the synthesis that they generate and puts it back to the forecast for the next term. And that makes us go around so little faster, I know. And so, when we think back to our, the question, would you DM with? What it takes to make nature work is the right context and the right understanding of what's going on in your world.

And so our question for you is, does your AI know around the world and doesn't remember what your farm is learning about it? Because we are teaching Osteo. And if these sounding, it's not like an exciting challenge. Excuse me. Is anyone ? . Thank you very much. Coming up next, we're delighted to welcome two speakers from Anthropic. Please put your
