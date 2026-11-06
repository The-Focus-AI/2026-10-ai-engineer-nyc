---
title: "Inside the Fable War Room"
speakers:
  - name: Ford Prior
    affiliation: GEICO
room: "Sutton Room (NY Ballroom W)"
starts_at: "2026-10-13T11:55:00-04:00"
ends_at: "2026-10-13T12:13:00-04:00"
format: "talk"
recording: "2026-10-13_1155_Fable-War-Room"
duration: "19m 13s"
source: "voice-memos-transcript"
---

# Inside the Fable War Room

### 00:00:00 — SDLC Velocity vs. Incident Operations at GEICO

Past? couple years. Feels like all we've been talking about is that increase the velocity of our SDLC. You all know what I'm talking about. Specifically this big fat built chunk in the middle. Okay? We've been doing a lot of our coding, you know, intellectual work. And sure enough, at least where I work, that step is basically been obliterated, right? And we reclaim a bless your time.

Thank you. But I think, and I'm no profit in imagining some future where Asians are doing the work and humans are there in the middle. or as executive was signing off each stage. But I work at Geico and we're not a tech company. We're a risk management company. And risk management is faked into everything that we do, usually the way we develop into the software.

So while we've seen this interlude speed up to use Gene Kim's concept, we find ourselves seemingly stuck within the bounds of this outer loop, which is to say everything happens other than the code. And we find ourselves wondering what life might be like outside of these walls in a world where the outer loop keeps pace with the inner lid. So this is a story of how we broke free, as it were.

And my intention with this talk is the power of you guys to do the same. Now, when Geico manages America's fleet of automobiles or risk their end, and something happens on the road, like an accident, we incur what we call lost. Which is typically reported by one of our policyholders, and it becomes a claim, it claims technology, is where the policy comes to life, and gives the customer back on the road as quickly as possible, with minimal destruction, which we call a resolution.

And I'm Ford Pryor. I am a senior staff, engineer, and tech evangelist embedded in acclaimed tech group at GEICO. And I think I'm the only type of band with Bertra Hathway, but basically what that means is within our 300 engineer group, we have like 32 pizza teams, as we used to call them, with a tech lead counterpart for each. This is kind of our free each.

And my job is to find and implement best practices in our SDLC. I run a claims, innovation lab, and I share stories like this one to attract the best engineers in the world to our problem space, which we find very patient, not to mention, important part of the American economy. So a little bit more context in how we develop software, as many organizations do, we can see over our work in terms of semantic versioning.

And about 6 months ago, we looked at our backlogs and found that our engineers, after they finished their latest patch, or chased down the latest minor upgrade, had only 25% on a good day or less other bandwidth to dedicate towards the major changes that keep us competitive instead they have the competition. That's like V one to V 2 to be. So he began strategically investing in Geico managed AI agents.

on a variety of harnesses using a variety of models to offload that work. all the way from spec to deployment for our patches and minor work. But the goal of redirecting or rerouting that work so that our engineers can stay are brilliant engineers, can stay focused on the stuff that matters and that they find most joyful, which is to do the major work.

Which again, as I mentioned, is key to our competitive edge. Okay, says current state. But as we look at this major work, we find ourselves rate limited by our ability to collaborate in rooms full of the right individuals, summoned at the right time, to make the right decisions at every interval in whatever life would need to happen in order to get the major work product.

And not only are we missing the ability to collaborate, but we're also missing this intelligence, this ability to weave together all the variables relevant to the problem space, as we learn it, and deepen our understanding of it, including the fact checking, the code crunching, basically everything that needs to happen, just serve up the insights as quickly as the decisions come up. And that's what ultimately gives us the confidence to bring those major changes to market.

Okay? So it's collaboration and intelligence. We're missing both of those at the major change scale. So install for this, we create a multiplayer AI native war room, and it consists of a roster of key decision makers and subject matter experts relevant to the topic. A driver to wield these expensive AI tools and an AI native productivity suite, which includes our comms channels for all the chatter, an interactive design studio.

I can't mention the vendor name. You don't take a lot of guesss. to, for all of our collaborative elements, and then obviously we have our code depositories. And all of these are wired into a powerful combination of workflows, 80 skills, MCPs, enterprise MCPs, and these ancient fleets to do the heavy lifting, back checking, synthesis, et cetera. So my question was, how might we accelerate the delivery of agent cullible APIs for legacy core capabilities?

And for context, our legacy claims, it's like 1000000s of lines. So, and the deep context that we're trying to build here, gets built once and they can be reused. That's just some additional context. But my bet was that with a $1000 in hand of AI tokens. And one day, we can map out one domain end to end, including like graph representations of the business apology, all the complex code, and our legacy systems, and everything in between.

And you can have the agency, find and propose one serious change, which, in our case, we scope down to an aging called the API and tour a legacy. claim systems. and have the whole thing deployed to our skills, age, platform, and running a demo to my boss at 4 PM. So I put the pressure on myself. But we ran this experiment 3 different times across 3 different code of modernization missions.

And this little taxonomy here, upload, transform, reimagine is from the endropic code modernization plug-in, which I'll touch on in a minute. But the story is that we 1st we looked at our rentals domain, which is a relatively similar one, that is all the type behind you guys, your rental cars, when your primary car gets in an accident. And we implemented a newer version of the same type, which is, again, the definition of uplift,

### 00:06:43 — Inside the Fable War Room: Multi-Agent Incident Response

and we extended an existing API. And in this case, it was an interesting story because the agent used some interesting process to find and distill data, to figure out that we can connect a couple dots and save ourselves 8.5000 calls per month by giving the customer up to date rental information. So that was the 1st experiment that we ran. And then the 2nd one was transformation of our damages domain.

And damages is like, arguably our most complex. no, sorry, damages isn't you. Damage domain is how we put dollar signs on a reported loss. And so for this case, we build a set of new agent called Wave Guys to unlock a larger book floor that needed damages data. And then last thing we reimagined our salvage donation, which is arguably the most complex of the three, it's basically everything that happens when your car's totaled.

And in this case, we produce a fully embedded migration plan, but take by specs and design lockups, ratified, and this is the most poor part, brain lit by product and tech at every level. Okay, so there's like a fully vetted project plan that's ready to be implemented, which is like, as you guys know, it's like, that's like a milestone onto itself, getting everybody on the same page.

including the top with. And honestly, like, in this case, it understood the domains really well. And the story of the salvage work was that it found a product. I can't talk about more, but it was... So anyways, you may be curious about kind of what, like, a little bit more detail in how this all worked. Really, like we had our friends at Anthropic, who provided a bunch of stuff, and then we had our boss to provide a lot of stuff.

So on the left here, we have... The harness, the model, this thing called Fleet Kit, which I'll explain just a moment. And this plug-in that did code modernization tasks. That's on the left, brought by the vendor. Okay, we can replace any of that, by the way, with another vendor, another model, another framework, et cetera. And on the right was the stuff that we can replace.

This is everything that go. We need to punish. We had context in our knowledge face, the police software standards, and all of this past decision, archaeology, we had to do, list of tools that the Asian can access on my machine, and instructions for the agents, and how to use it. We had the methods in doing these out of order here. We had methods, which is essentially like all of our skills and all of the kind of quirky, domain specific, highly optimized way that we develop software, probably different from what you guys do.

And then lasting judgment, which is like, who can decide what and at what gate, right? So both from the subject matter expert point of view and from the decision maker leadership point of view. and, we grouped them into 2 reposts. I'll explain why. But that allows us to allows us to have the agents add to it and correct it, and also human students.

But that AI, and this is kind of one of the interesting parts, is expensive, right? To run its scale. And so we need a fleet manager, like a PhD level fleet manager. And this was a bit of a collaboration with anthropic and it isn't open source yet, but I can share how it works today in hopes that you guys can construct your own version because it's not rocket science.

So FleetKit is this type structured collection of rules, protocols, instructions, while we're in Markdown. Optimized for the quad harmon, specifically fable, and designed around the poor task of architecture transformation. And you guys can kind of guess, like, this type of thing doesn't really work with some of the previous iterations of models. I think, like, notice straight and beyond. I would guess is like something that could handle this type of like steering.

Because it's like one level above the actual system prompting, right? This is like rules that it has to follow. The agent has to follow. and pretty simple, takes a goal, breaks it down, dispatches leaders to do all the research, and decide about the approach. It puts everything into this like human the loop cube. You could use get up issues, for example, something that the humans can comment on and improve or that other agents can add more context to.

And then whenever the thing looks type from a verbal standpoint, it dispatches a pill, it just do the rest. And in this case, we use beans on the trip, they'll have about means, but these kind of helps HSC check everything. within our own easy space. And ultimately, the goal is to produce what we call a material change, which is like a change request to our systems or code change.

And the ultimate, like, idea with this, though, is that, like, developing software, just, like, buying a canvas, and more like working a factory. Okay, I need to go faster. So ultimately, on the left here, you see these 3 repositories. They contain everything that's going to be used. So, right, including the fainted force. By the way, all these slides are available on the blog post that I'll link at the very end and tell the lights, use information.

But I just want to let y'all know that if you want to look at the, the visualizations that I'm showing here, they're on a blog post that was released today and I linked 13th. So, all this boots up, gets pulled into a blog, plot code session with a plug-in, gets invoked, and you give it a mission, it's an adopter, create slack channel, or in our platform.

And then that's that mission channel is where everyone communicates. All the war re members, the people are relevant to the decisions, and the project are invited. And every time the agent reaches a milestone, as it follows, it's 9 step process. It creates one of 2 artifacts. And by the way, on the right there, where it says war room, that's where it, like, it can paint individual people based on the roster.

So, for example, it's missing some product details. It'll figure out who owns that from proper perspective. mention that name of a person. But other than that, it creates portraits that are like actually really well done. HTML, using clawed artifacts, who can fill them out. They're automatically safe. And that's still for

### 00:12:34 — Production Results & Cultural Takeaways

the gaps. It also creates design documents, including like these like complex visualization of architecture that Didney says before, that teams were delighted to get because they kept them afterwards. that we can then edit, and then AG can then reread, or edited, like, design document, or draw IO, or figma, and then all that, it's that, all that can slur back up into the defects on the session.

OK. and if you had stumbled into a war room in Richmond, Virginia, where I'm from, on the summer, you would have seen the Peter up a block code screen, with a bunch of people humming around it or one of these 2 screens here. On the left is like a product worksheet that we had to fill out, and then on the right, it's like one of our diagramming tools.

And so the big gist with this and that thing that was so delightful for me is that people were really high quality artifacts. So there wasn't like ever a question of like, why is the agent asking me dumb questions? I was like, wow, that's actually a great question that we've never thought about, identifying an edge case either in the business or with technology.

And then the design artifacts, like I said, the teams could keep them afterwards and oftentimes they were mapping stuff that just no one had taken the time to do. I was going, no, not every engineer loves clean diagrams. Okay, I'm sleeping stuff here, but we're gonna continue after that, like, 3 minutes. These weren't tools. First way, assembly, basically those 2 types of agents, the code dives that we call them, where it did lots of code crunching and graphing of our legacy.

Legacy domain specific languages. that happened in the cloud, and then we had local agents running that had access to all of my laptop, my all their MCPs on my laptop, many of which were not in production yet in an enterprise specific, highly optimized for our problem space. and then can surface really viable data, including like chunked versions of the code bases that were being dived.

So, there's a bindings file that I gave the agent to basically describe what's on my machine, how it works, and how to map it to the fleet tip. work. And you can see the built-ins, the TV servers, the really quick code modernization plug-in. This is at the heart of the whole thing. And what's inside of it, I think you guys will find someone interesting.

And I would encourage you to look into it after the fact, after this presentation, to get more information. I'm like, I keep moving here. Ultimately, the driver's laptop, my laptop was the runtime. Okay? So I had to run 9 steps that are that are, sort of at the mooning step. So A steps after that. And what I went to taking this super busy slide is that on the left here, those were all steps forked from the code, not plug-in.

So we adapted it to our knees, as I were encouraging them to do. And on the right, those orange colored elements are worksheets that were created. So that was gonna require human approval. And so as we did this like modernization journey, you can see that there's a lot of human input in the beginning, less on the end, and all the core of it was this code modernization plug-in.

And I have just an interesting detail, and this is something that the code moderation plugging does, is it does, like, a deterministic analysis of, like, did the previous step create the artifacts that you put in a file? So some interesting lessons. Obviously, I've burned a lot of burn a lot tokens. And, one, just as a little takeaway, do not like Claude, running fables set of crimes to check on work.

because you'll, it'll launch a claw, a label session each time and burn your budget immediately. But, some other interesting unique ways we have were relevant prompt cashing, which was way higher than I thought it would be. And then since would be salvation behavior. But one of the interesting things was, like after we deal the context building and have these agents dispatched to like write our complex legacy code, we ran benchmarks against like using our existing code recently written as the golden data and found out that Fable, or Sonnet 55 wrote it just as good as if not better than Fable.

So, model selection for the win. And then looking forward, I think, you know, enhanced skating enforcement is going to be the biggest one that we have. In my mind at least, we also have some interesting updates to make for the decision models, within our harness, and within the model selection framework. And then, our light, our context was just like marked down files, y'all.

we didn't really have an complex way to wrap things out. Like, we weren't using anything fancy with a, like, like grapify or, obsidian. I mean, any of these, I mean, honestly, if that's by me afterwards, I'd love your input on this, but like a more optimized way to do search and look at all that context that we're using to inform this war room.

Oh, and then lastly, audio is a data source. Like, I want to turn a recorder on and have these conversations we have, like automatically transcribe. But I had, like, instead, said, I'm furiously write down all the notes that were happening during these meetings. And so that was kind of like a distracting thing that I'm sure I lost a bunch of it. So less lossy way to incorporate the inputs from the order.

And then lastly, how can we deploy this thing across the organization? Y'all find some group in your organization that doesn't know how to make decisions, deploy this, drive it, control the cost, make it yours. And at GEICO, we're like trying to figure out how as these agents are health climbing and figuring out better ways to do things, where can we put humans in the loop?

And right? How can we, like, put our best, brightest engineers who are receiving genius, divine intervention, as it were, and have them pick the next hill as they exist climb the 1st one. All right, and that is it. We broke free of our outloop. Now it's your turn. And that's the blog. You guys can take a picture of. All right, thanks for your time.

Well... Why are... Yeah, someone...
