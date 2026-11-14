---
title: "Frontier Models for Acting in Space and Time"
speakers:
  - name: Pim de Witte
    affiliation: General Intuition
room: "Simons Room (Metropolitan East)"
starts_at: "2026-10-13T16:48:00-04:00"
ends_at: "2026-10-13T17:06:00-04:00"
format: "keynote"
recording: "2026-10-13_1645_general-intuition"
duration: "19m 36s"
source: "qwen3-asr-1.7b"
---

# Frontier Models for Acting in Space and Time

> The recording opens mid-sentence.

> Transcribed by qwen3-asr-1.7b with a schedule prompt. Possible prompt artifacts, names heard more often here than in the unprompted Voice Memos transcript (Qwen vs Voice Memos): Tenex (1 vs 0), General Intuition (2 vs 1). Check them against the audio before quoting.

### 00:00:09 — Observing While Acting: Why LLMs Struggle in Space and Time

Para ver o que estão fazendo mais do que nossas ideias. Microsoft Build Conference. Hello.

I want you to zoom out for a second and think about if somebody were to tell you today that we would take all the information on the internet, and then we would train a model on it, and we would use that in order to solve scientific problems that were not on the internet, a lot of people would tell you that's crazy, and what we're doing has a lot of parallels to that story.

And so, if you think about how intelligence works, imagine for a second that you're in the movie Frozen and you're Olaf, the snowman. If Olaf was an L M, and there's a scene which is one of my favorites, which is where he rolls down a mountain, and there's a little stone that pops up, and all of spreads out, temporarily becomes a disassembled snowman, and then becomes an assembled snowman. Olaf knows how to do that because Olaf can observe as he is acting. Olaf can, unlike LLMs, which auto-regressively predict tokens, constantly, part of that behavior is that it's constantly observing as it is acting.

And so, this is the big difference between, you know when you see LMs try to solve robotics problems, or when you look at native architectures that we're working on, it's very easy to think of LLMs and the demos you see on Twitter as the thing that will solve everything. There's fundamental limitations that we see where purpose-built models are much better fits now. Today I'm going to talk a little bit about what the other side of that coin looks like.

### 00:02:33 — From Medal's Game Clips to Shared Controller Action Spaces

And so, for us, it all started with metal. We built the largest video game recorder in the world, and we think of that as the internet. So people use metals, record themselves playing tens of thousands of different video games, and if you think about it, as a human, we can tell operator robots with the exact same brain that we played a video game, and in fact, in many cases, we also can use the same controller.

So what this means is that the action space for video games, often because of game controllers, and the action space for operations or the real world many cases are the same. And so every single robot built below certain degrees of freedom shifts with the game controller. Majority of the supply chains already work this way.

And so we thought, what if you just take all of the action data that we get through the video recorder, which associates the inputs and the actions with the actual friends. We label the actions so we understand semantic meaning of every action, and we use it to give it to a vision-based model, and so what you see here on the left is just an intuitive way of how the model works. So you give the model a set of keys to choose from. Potentially, a Bayes model. It gives frames as the input, so you can give it a text prompt as well, and you set up your API, and you say somebody waves at you, wave back. In the input space, the model understands that you have a greed action available. It will output the action associated with that — one way of intuiting understanding how this works.

### 00:04:12 — Turn-Based Coding Models vs. Continuous Pixel-to-Action Streams

So I've obviously simplified here because it's predicting the next token, not the next word, but you're welcome to hear. Alex took large scale internet data, then trained it with Truic Connects text token, and now uses for writing software, and these are all workloads that are really, really well fit for futures that are not simultaneously unfolding as you are predicting, right?

Code is a turn-based. You can say something, the model will do something. You can say something again, the model will do something again. And you can use them for lots of valuable work, but at the end of the day, because it's turn-based, it's very difficult for it to generalize to environments, especially that include space and time, and so our models, the way that they work is they're are continuously receiving frames or receiving batches of essentially information from the camera, the robot, to the screen, and it predicts everything as if it were just a video game, so you can think of the way that Intuitive focused on just nailing coding, so yeah, they were never frontier in just base text generation. They always focused on being the best at generating code. And then what the debate that they made is that more people would start bringing more problems into coaching space.

If you think of general intuition, our bet is that you can, as humans, we are generally pixels to action converters plus sensors, which in many cases you can convert into pixels as well, and you can output actions at the same time. Those actions are, in this case, your keyboard and mouse, or a game controller. So the applet opens with a model are essentially equivalent to that of enhance computer use model with more actions in the output space to internalize it. So you send frames and you get actions.

### 00:06:01 — Human Controllers vs. End-to-End Motor Torque & Medal's Scale

This works again because every single thing that you see here can control all of these different embodiments, right? So as humans, we do not know how to predict motor torque, we do not we do not know what value to set the machine. There's this beautiful device that has been made for many years, which actually does that work for us, so we can control them.

Most robotics companies today are trying to solve the problem at the end-to-end level, trying to predict exact poses or exact values in the motor, instead of just looking and picking up the thing that every robotics company has built to generalize our very limited abilities to have physics understanding and predict exact values and sulfur, and so our approach is let's just use that, and so Medal at the moment sees about a billion videos uploaded per year. This year, we're on track for three billion, which lead to over a trillion and a half actions taken per month. So just for comparison, to think about the best — the total amount of data that Frontier Labs uses today to train robotics models, we collect in at the moment half a day.

And so the type of bet, and again, think of the fact that humans can use the exact same controllers and their eyes to play video games that they can't tell a brain robot — it is the same thing. We just bet on scaling pixel space the same way that anthropic scaled coding space, and betting that people will just as we scale data compute into pixelspace, that people will bring more problems into pixelspace.

### 00:07:53 — World Models, Native Human Modality, and High-APM Action Density

And so, what happens? All of a sudden, you get an incredibly general agent that can go and solve problems on computers in the real world, and in addition, similarly, Tenex focused on doing coding environments, we focus on world models, which most of you know as for the mirror-based world models, then generate additional environments for these models to learn in.

One way of internalizing a big advantage of this approach against LMs is, if you're enough — if you're an MLM company and you have to bet on the ability to generate environments for your models to learn, you have you have two problems. One, you actually need to spend to compute to simulate environments, and the more realistic you try to simulate, the more expensive that gets. And so, imagine you have you want to learn a new thing. You want to learn that new thing in the exact input space of the human, right? So you, if we are learning from pixels, we're learning by looking around. If I'm trying to communicate something, I want my robot partner to observe that exact same thing, and so what I don't want is for data to go through an LM for a digital twin to have to be created, for them all to have to get deployed, for it to be a bunch of verified checks, whatever or not, things are equivalent, and then for the robot to learn much later, right? And so one way of thinking about it is when you can learn in the native modality of the human, you can all of a sudden start solving a lot more problems a lot faster — which you'll see when these models come out is there significantly faster than any L M at doing these things.

We, because games are so action dense, so what you see right is one thing that's interesting is use software to model breaking multiple actions at the same time. We're able to take that action density from gamers and convert them into really complex robotics work. So, for example, if you are operating a drone and you need to make lots of little adjustments, you really, really, really want to start with games. You don't want to start with tell operations because the human moves take a lot less actions. It has a lot less information, so you want a model that can predict really high APM. And so, the APM of the dataset puts a lot of these problems all of a sudden in reach, so that it can do a lot of these actions simultaneously, and as I mentioned, the model doesn't just understand the key it's predicting, and also understand the semantic meaning associated with that key it's predicting, which is really important for things like interpretability.

### 00:10:31 — Real-Time Capabilities, Orchestrator Integration, and Accessibility

So we will be releasing the models this year. We are very happy. I think the correct word would be that we're stunned by the fact of what these models can do. It is — this is a live stream, so I unfortunately couldn't share the release videos without breaking the surprise, but if you're in New York, we are also in New York, and so we have started doing a few demos of the models. If you can know somebody in the team, reach out, and we can start showing you some of the some of the capabilities live.

That we have essentially one model which can play video games to highest level and control over 1000 robots using the exact same primitives. So pixels in, actions out, completely real time, and we'll be rolling out early access two use models over the next few months. We already have some customers that are on them, but it's still private, so you're not hearing too much about it, but if you scan the QR code, you'll be able to get the models because we go by who's signed up on the waitlist at which times, so this is a great — this is a great moment to get in touch. As I mentioned, we are in New York. I think what you'll find is similar to how Jav and a lot of these decision-making models have kind of opened people's eyes on what you can do when you have a new architectural primitive. People are ready to kind of do away with the unpredictability of an LLM and put something in that is more reliable and faster, and you just want to how it's going to react, as opposed to having to work around it.

If that resonates, these models are exactly what you're looking for, and all of a sudden you can start exploring the environments that you generate with LLMs. All of a sudden, one of the use cases that I'm really excited about is, well, these models, they can take actions as if a human was on the interface, and so if you're doing UX work, and you're trying to understand: Is this an intuitive interface? So this is a very interesting way of solving the problem.

So all these problems that LMs can't solve because they can't actually explore like a human, you can use these problems to start — you start using these models for, so, the way that we're going to be released is, we still expect you to use an orchestrator model, so you may use something like Gemini or Astro in order to do long-term planning and everything, and you'll be able to plug these into your workloads. And we're actually the models are so general, it is genuinely going to, I think, feel like the early LLM days, when you have a new toy and you just want to figure out what it does and all the things you can use it for.

My reaction was like that when I when I first started using the checkpoints, and I think I think you'll have the same reaction, and I think a lot of you will, just like LMs, if you're a bit early and you start understanding these primitives, I think you'll understand that you can even build lots of businesses on top of this, right? You know, think about, for instance, a science lab, right? If you all of a sudden, if you can reliably orchestrate robots in space and time, and they can take text instructions and do things, all of a sudden — I — this is a recursive problem, right? Robotics is interesting because one of the big problems with solving robotics is making them robust, and so there are all these businesses that because it's so bottlenecked by intelligence, are going to emerge just from solving this one simple problem, which is pixels to actions. And I think if you're early on getting your hands on these, it will have a similar effect on getting your hands on early LLMs.

I am most excited — also, one of the things that we're working on, which is interesting, is if you have any friends or family who are in some way, need accessibility help for using their computer because these models can use computers like a human, all of a sudden, for instance, if you're if you're if you only can use one arm, all of a sudden, the model can allow you to play video games because you can you can use you can just control the mouse, and the model is predicting the actions for your keyboard. And because the model also understands which actions you're predicting, because that's the input, right? It's observing as it's acting, it will actually just not predict the things that you're doing, and it will just predict keys, and so it has all these downstream effects of things that you can build on top that — I'm an engineer.

If you're interested in building in this space, this is going to be the most interesting toy that comes out this year, I, I'm fairly certain, and I also think a lot of the initial uses will sit in simulation. So if you are into generating environments with Astera or with Gemini's, perfect. Now all of a sudden you can have something that can explore it, and you don't have to do it yourself, and it's perfect timing because of all the environmental sustainability stuff going into these models.

### 00:15:34 — General Intuition Team Structure, Hiring, and Upcoming Hackathons

Okay, so really quickly before I wrap up, I want to talk about the team. So we are based in New York City — I — the medal team and the general intuition team is here in New York City, so if you're here, you should reach out to us and you can both show your models, especially if you want to join the team. I think we'll prioritize even higher, but I we really are looking for people who a want to understand these models as much as we do, so people are really good at generating novel environments. Typically, if you have some sort of research background, but I don't have a research background, so that's okay. If you know, if you if you come from an engineering background and you're very happy to learn, this is this is fine too, and ideally, what we want is somebody who has experience shipping end-to-end AI products, but it doesn't have to be on the research side. So we just want to kind of higher people understand the entire thing.

Let's see. We have three teams: so one is world modeling, the other is the policy — so the agent, and the other one is working on essentially the data generation and the environment generation. So these are the main teams for an engineer. Best ones are joining us probably the environment generation team, and then you sort of grow into getting access to their ones.

Yeah, we — I'm very excited for November. I really hope that you'll be on the lookout. As I mentioned, it will be either late November or early December, as we're currently planning. One more thing, we are going to organize three hackathons. So the first is going to be in New York City. It will be mid-December. And we will send out — if you sign up for the partner waitlist, we'll send out some emails that everybody can get access. We hope to see everybody at thekephons. I think it will be really the first time to get your hands on them the way that we're playing with them internally now. And there will be one in New York City and one in London. So if you're in either of those cities or with a travel to either of those cities, those would be good. Thanks to the team.

### 00:17:42 — Q&A: Explicit Action Labels vs. JEPA Inferred Actions

Yeah, let's see. I have time for one or two questions, and then I think we can wrap. So much.

How is it different from Japa?

Yeah, how's different from Grepa? So Jeffa is doesn't train on the action labels, so they bet on inferred action labels for the most part, which I think, like one of the way of thinking about it is Jeppa, I think, in the limit is the more correct approach, but it's a lot less practical in the short term because you need to bet on the separate scaling law and the action inference itself, and we really like Jetbase concept. We think it's a you know we use some of the things in the models. And, but at the end of the day, it's an approach, but not a product, and I think we'll, you know, borrow concepts both ways. Thank you.

One way of thinking about it is because we have so much action data, let's say you're flying a plane and you're moving the rudder in the back. There's no way of being able to tell that from the video frames. It's very difficult, so our mode of having the action data really transfers better to action sequences than it does to world models and to generate the pixels. And that's why we just went all in on training these general foundation models for action predictions, and we use all sorts of techniques to do world models, you know, our own. We really like other companies building on this wall.

Great. One more that I got about. Think. Okay. All right. Thank you, everyone.
