---
title: "Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On"
speakers:
  - name: Mislav Ivanda
    affiliation: Daytona
room: "Sutton Room (NY Ballroom W)"
starts_at: "2026-10-13T15:45:00-04:00"
ends_at: "2026-10-13T16:03:00-04:00"
format: "talk"
recording: "2026-10-13_1544_give-the-agent-a-computer"
duration: "15m 27s"
source: "qwen3-asr-1.7b"
---

# Give the Model a Computer: The One Thing Every AI Agent Framework Agrees On

> Transcribed by qwen3-asr-1.7b with a schedule prompt. Possible prompt artifacts, names heard more often here than in the unprompted Voice Memos transcript (Qwen vs Voice Memos): Daytona (3 vs 1). Check them against the audio before quoting.

### 00:00:05 — Why Every Agent Framework Converges on Sandboxed Computers

And for the last year, my main task and goal there was to integrate Daytona. Basically everywhere where sandbox makes sense, because where they don't have. SaaS provider, and these are spanning from agents' frameworks, pulling agent firms. Workflow tools, development product, developer products, and stuff like that. And during this process, I noticed the pattern that was repeating all the time, and it maybe it made me stop a bit, think about some things that eventually led to this talk. So yeah, I would need your help on this slide. Does anyone have a guess which?

AI agent framework is this. He somebody has I guess LangChain, LangGraph, Google ADK. Langchain. Langchain. Okay. Let's say, let's talk about the main. Thing about this is that whatever you talk can basically be correct and dependable. Why do I say that? It's because during the integration of Daytona into these AI agent frameworks. There, I noticed that they. I can barely. Differentiate the Daytona-related code contribution part between these. So in some of these, you integrate as a tool. In others, you integrate this external plugin that you can install to make your agent do.

Some capabilities. In other ones, you extend the sandbox. Class and do some internal framework API stuff. But under the hood, all of these ways speak the three same lines, so it's. Sandbox creation, running some code or task inside the sandbox, and sandbox deletion. And this is really weird because most of these frameworks are competitors. And they barely agree on some fundamental things or concepts. What do I mean by that? So, for example. They don't even agree on what they what an agent is. For example, Langref defines an agent as a traversable.

Traversable draft. The true AI frameworks defines agents as you know world. Bunch of role-playing agents that do stuff on their own. OpenAI agents SDK. Is defining agent as a loop around the LLM model. And for example, Cloud Agent SDK ships the whole fully finished product that you just like use. Incredible localization abilities. No customization. Also, they differ in the languages they are implemented in, mostly between Python and TypeScript. And they also don't agree on who who's in charge of. Specifying what an agent does, agent behavior, for example, in Mastra or LandRat, you explicitly define your agent workflows and trajectories. While, for example, in Pro AI.

Agents do things on their own, and they decide on their own to achieve the end goal. And yeah, when companies like or companies like this. That don't agree on basically anything. Agree on something that probably isn't. Just a fashion. It's a necessity. So why they agree? Do they agree on these things? So. As I like to say, whenever you're doing something with your AI agents, that's useful. You eventually come up to the state where your agent needs to execute some kind of a code or needs to have shell access.

And the next question is where will this happen and which execution environment? So. I would say there are basically three types. Possible isolation in these environments and let's now do a brief overview around these. So number one is the most basic one. And it's probably the one you're using locally when development with your agent. So you define certain allow list of commands. You also get some approval prompts where you know Claude SQK are you sure you want to run this command? Although probably most of us just click yes and don't even read what does he say.

And you can also add some interception hooks, but the problem with this approach. Is, I would say, obvious. So, when you allow your cloud agent to run Python command. With Python dash C, he can literally. Open any sockets, modify a file system, execute code, or do. Basically everything, which you probably don't. Think about in the background and you essentially defined what. Your model should use, but you didn't define what your model can actually use, and if the model is. Compromised, you can I guess sense that you essentially open back doors for it.

To let's say, do malicious commands on your local device.

### 00:05:08 — Daytona Runtime Architecture & Isolation Primitives

Second most more advanced option is. Shifting all of this coding execution stuff inside embedded engine runtimes like. V8 or QuickJS, and this approach is better because you have certain. Network and file system isolation, but the curio with this approach. Is probably even more subtle because let's say your agent has access to certain tools, like. Query database or send email and your agent will probably generate a Python script which uses these tools. And you will execute this script inside this embedded runtime, but the problem is that.

These tools that your agent will call inside that runtime will actually run on your device outside that runtime. So basically, you're maliciously. Malicious agent can act through these tools, not directly, but through these tools, which most of people like. Probably don't think about, and as it says, you isolate the blue code at your agent. Generates, but you're not actually isolating the actual tool. So, for example, agent can use these. Email sending tool or database query tools to perform some of its malicious commands. For example, like you have delete database. How can you get into problems with this?

And the third one and recommended approach is to use a separate. Computer or VM for these purposes. And yeah, you interact with this VM via API, control its lifecycle, or do. Any kind of stuff inside it, and this VM never touches or interferes with your local. Infrastructure, network, file system, etc. And the best part of this approach, and why is it the best approach, is. So, containing this last emphasis, and then compromise that. Compromise step is not to compromise that. What do I mean by that? Is because in prior two approaches, when you're Tool calls misbehave or you, your agent misbehaves. Let's say, fight and command. You approve. That compromised step is probably.

Literally compromising your whole application and can make really bad stuff. But in this step, you can run the most. The worst tool on the planet inside the sandbox, and it can interfere with your application logic. You can just. Throw out that sandbox and spin up another one. And to back up this, that I'm not just talking, you know, some nonsense. So here's the proof. Like the direction of frameworks. The direction that AI frameworks are moving at. So in April two thousand twenty six, Pro AI removed the code interpreter tool, which essentially did.

Local code execution on your device, and they now point to dedicated sandbox services. AG2 also retired their old local coding executors and now have this new sandbox tool class that the explicitly requires from you to define the environment where you want to use this. Cloud SDK is available using sandbox, but it's specially sandbox. What do I mean by that? It's like a process level sandboxing, which you can do, for example, tools like Bubblewrap on Linux machines. OpenAI agents SDK has this sandbox agent, which has native you know support for some of the sandbox provider integrated inside.

And also for Docker, but it also allows you local code execution with you know, transparently listed flows of this approach, and it's similar to with Mustard. And you can notice that they are not. Adding sandboxes, they already had them, but they are deleting all the alternatives. And. Parallely with this shift in AI agent frameworks, direct isolation direction. Basically, there also happen a shift between how these sandboxes are actually used. So, firstly, when first agents started to evolve and got into picture, the sandboxes were mostly used as.

Short-lived machines where you're agent will spin it up on demand, run some code or task inside it, and shut it down. But then, when models became more capable. Do people realize they could literally shift hold the agent and run it inside the sandbox as an execution runtime? And give it access to file system, network calls, and basically everything. And since recently, there's also a shift where people also. I understood that if they can run thousands of these executions. Environments concurrently, they can do really interesting stuff, especially regarding reinforcement learning.

Fine-tuning, post-training benchmarks, evals. We can also spawn different sub agents while solving some problems and stuff like that. And yeah, now back to the to the question.

### 00:10:20 — Patterns from Integrating Across Agent Harnesses

So this whole shift from AI frameworks regarding execution environments and boundary. Made me also reading a common question, which me myself and I probably a lot of you are asked like which framework should I pick. And based on this whole story, I think this is essentially the wrong question. Why do I say that? That's because some of most of the. Items that you compare frameworks between are swapable, and you know can be easily done. And stuff that's not that easily swapable is normally or oftenly not.

Even considering to the picture between people were choosing, you know, developments there. So what do we mean by swappable? For example, you can. Essentially, swap between different local frameworks using the same language. You can essentially talk between frameworks. You know, if you're putting agent tasks. And it's like a refactor and developer push all the time. Second one is you can also swap between models and prompts. This can be a bit. Once again, if you're you know, fine tune to refine tune your system prompts and stuff.

To serve the model, but it requires some fine tuning and regression testing, and it's I mean completely doable. Same with missing features, so sometimes people decide on which framework to choose. Based on some feature that one brand has, another doesn't. But nowadays, yeah, you can essentially buy a missing feature or just plug it as an external plugin for certain framework. I would say this probably doesn't fully support the future calls. Durable execution that some frameworks provide. That's kind of a not that easy to replicate and replicate in the cloud because it affects the architecture and stuff, but all of the others, like high-venture, reverse tracing, memory, you can easily implement by yourself or just plug in external tool.

And you can also swap the sound provider because all of us speak the same language, so all of us. Speak, create, run some stuff inside, and delete. Although, I mean, some of us have some features and different performances and the stuff you can't. Change easily or swap later is the execution posture I was mentioning here. So that's like deciding will you run your. Exit coding stuff locally, or will you use external standards? Why you can't swap this easily? Well, the reason is that. This defines your whole system architecture, and how do you develop other parts of your system? For example.

When you're developing some kind of tools. If you're guessing that you'll use first approach, where everything runs locally. Then you write all your tools to use your host or app process environment. Using your file system without separation and stuff like that. And problem is that most of the people start with this approach as a POC phase. But unfortunately, continue all up until the production stuff. And they don't come back to it, and then when. When bad stuff happens, it's probably too late, and sometimes. By bad stuff, I mean something that can literally kill your product.

And that's why I would like to say from this talk that. You should probably consider. Picking up, there's a huge choosing the execution boundary before deciding which framework you should pick. And as I like to say, and the sentence I would maybe like for you. All of you to remember: Out of this talk is, framers our opinions and the boundary the commitment. I suggest that when you're starting to work on a product, you. You define an interface, the execution posture between an interface you control. And everything except that can be easily swappable in the future and reversed.

And once you define this interface, of course, you should use the execution architecture mentioned as. A third method, like giving your agent a proper computer. And yeah, when you do this right, the part security part regarding the execution is solved, and you can, I mean. Continue developing your product features and stuff around this. Without any concerns about the potential security vulnerabilities or stuff like that. And yeah, that's it for my side. Since I mentioned I was doing some integrations and guides, so we have these solicitors.

Plugins and packages and there's also a Turkey article shows the comparison article that's comparing different AI frameworks a bit. More in depth that we list here, yeah. This is for my second.
