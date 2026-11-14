---
title: "Your job is now \"agent manager\""
speakers: "Ryan Carson (Untangle)"
duration: "11:09"
source: transcript.md
video: "https://www.youtube.com/watch?v=BTtyguoPvBU"
themes: [deterministic-verification-loops-over-line-by-line-review, self-improving-fleets-and-the-agent-manager]
kind: talk-story
status: draft
---

# Stop running local dev. Manage a fleet of agents instead.

Ryan Carson builds Untangle, an AI product for divorce, using a hierarchy of cloud agent sessions: manager agents, up to twenty parallel builders per ticket board, automated review and child QA loops, and a merge manager. Humans stay out of local editors, verify pull requests by watching mandatory feature videos on a laptop, and hire engineers strictly from screen recordings of them operating agents.

The in-room audio transcript begins mid-talk and cuts off early before the close, while the official video slides cover the full fifteen-minute presentation. Details from the opening setup and late-talk slides are attributed explicitly to the slides, while all blockquotes are verbatim from the room transcript.

## An org chart where the manager agent never writes code

Carson's opening org-chart slide places a human at the top with two responsibilities: setting weekly priorities and talking to customers. Directly below sits a Manager agent labeled "never writes code," linked to the human by audio chat where the operator asks what needs attention and receives a single question plus a recommendation. Work moves strictly through Linear ("no ticket, no work") into up to twenty concurrent Builder agents, one per ticket, with a later slide build showing the manager agent checking in every ten minutes.

Where the room audio picks up, Carson describes how those builder sessions police their own output before escalating to a person (00:00:07). Every builder invokes a built-in reviewer agent in a loop capped at three passes; only if significant bugs remain after three attempts does the builder escalate to the manager agent, which escalates to Carson only when stuck (00:00:07).

Alongside the review loop, an Untangle engineer named Dale added a separate child process under each builder dedicated to QA (00:00:07). Because cloud agent runs are cheap, Carson urges teams to spin up as many verification processes per feature as they want, watching out for the one real constraint downstream: slowing down the merge queue by over-packing pull requests (00:00:07).

**Key points**

- On Untangle's org-chart slide, humans set weekly priorities and talk to customers while a Manager agent turns decisions into Linear tickets for up to twenty parallel builders.
- Builder sessions loop with a reviewer agent up to three times before escalating unresolved bugs to the manager agent.
- Each builder spawns a child QA process, trading cheap compute for higher pre-merge confidence.

> “We typically stick to a three-review max, where we allow the builders to loop about three times with reviews.”
> — 00:00:07

**Visual:** slide `experience/human-audio-chat-manager.jpg` (Untangle's org chart: a human talking over audio chat to a non-coding manager agent above Linear tickets and twenty parallel builders)

## Every pull request ships with a feature video, and a human has to watch it

Carson's verification slide draws a four-step bottom row under the builder loop: write code with a failing test first, pass the QA agent's proof check, record a video of the working feature, and wait for a human to type "Ship it." In production, Untangle relies on Devin's built-in Test capability so every builder session writes test cases and captures a video of the feature running and passing tests (00:01:40).

Watching that recording is the one human-in-the-loop gate Carson refuses to shortcut (00:01:40). When his manager session notifies him that a pull request video is ready, he reads a brief summary of what the PR is meant to change and inspects the video to confirm both behavior and visual polish (00:01:40).

Trying to clear that gate from a phone does not hold up. Right before walking onstage, Carson's manager session sent over a PR video while he was on his phone; squinting at the small screen, he realized he could not verify the details properly and forced himself to wait until he was back on his laptop (00:01:40). After hundreds of iterations on the workflow, attentive laptop video review remains the product owner's irreducible bottleneck (00:01:40).

**Key points**

- Every builder generates test cases and records a walkthrough video showing the user-facing feature passing them.
- Human product owners review behavior and UI polish through the video summary and recording rather than line-by-line local testing.
- Phone-screen spot checks miss subtle regressions; laptop inspection is the final gate before typing "Ship it."

> “Every builder records a video of the feature being used and passing tests.”
> — 00:01:40

**Visual:** diagram "Builder verification gate from failing test and child QA through three-pass review, recorded feature video, and laptop sign-off"

## Local dev cannot run a communicating fleet or a merge manager

Carson tells engineers still writing code in local development environments to stop immediately (00:03:38). Running local dev, he argues, holds back both the individual engineer and the whole company because a single laptop checkout cannot run or coordinate parallel fleets of cloud sessions (00:03:38).

To show how the model scales across an engineering org, his team slide depicts a ring of ten humans paired with ten manager agents, all messaging one another across named Devin sessions (00:03:38). When Carson inspects the transcripts, the sessions exchange direct operational updates rather than filler chatter, echoing advice he cites from an OpenAI talk earlier at the conference: define clear roles and unhobble the model (00:03:38).

Even communicating sessions collide when dozens of pull requests land at once, especially around sequential shared state like database migration numbers (00:03:38). Untangle dedicates a separate Merge Manager agent session — shown on his slide feeding five PRs into a GitHub merge queue and onto `main` in order — to sequence ready work and eliminate migration collisions (00:03:38).

**Key points**

- Local development workflows bottleneck teams because they cannot host fleets of concurrent, inter-messaging agent sessions.
- Named cloud sessions message one another directly to coordinate dependencies across ten human-manager pairs.
- A dedicated Merge Manager session sequences ready PRs into the GitHub merge queue so database migration numbers do not collide.

> “I don't care whatever it is, but if you're running local dev, you are screwing up. You're holding yourself back. You're holding your team back. You're holding everything back, because you can't do this.”
> — 00:03:38

**Visual:** slide `experience/same-ring-coordinate-center.jpg` (ten humans and ten manager agents coordinating into a Merge Manager agent and an ordered GitHub merge queue)

## Resumes and interviews are noise; 45-minute agent recordings are signal

Rebuilding engineering around agent fleets led Carson to scrap conventional hiring (00:06:23). Untangle runs no resume pre-screens and no introductory video chats, on the grounds that live conversations bias interviewers toward a candidate's personality, speaking style, or hobbies while revealing nothing about how well they operate agents (00:06:23).

Instead, every applicant starts at the same uncompensated gate shown on Carson's "How we hire" slide: submit an unguided, 45-minute whole-screen video of yourself using agents to ship a new feature pull request on an application you already maintain (00:06:23).

Untangle feeds every submitted video and transcript into a ranking agent tasked with watching the full session and stack-ranking the candidates (00:06:23). The first time Carson ran the ranker, he disagreed with its number-one pick and distrusted the output — only to realize afterward that his own bias had misled him and the model's ranking was right, even when strong operators worked silently without thinking out loud (00:06:23).

**Key points**

- Pre-screens and introductory calls introduce interpersonal bias without measuring agent-operating skill.
- Applicants apply by submitting an unguided 45-minute full-screen video shipping a real feature PR with agents.
- A ranking agent evaluates every video and transcript to stack-rank candidates more objectively than gut instinct.

> “You'll like their hobbies. You'll like the way they talk to you. You'll think they're interesting, and it's all noise. None of it is real, right? All that matters is can they operate an agent?”
> — 00:06:23

**Visual:** slide `experience/single-card-candidates-person.jpg` (the entry card of Untangle's hiring funnel: a 45-minute whole-screen recording of candidates shipping a feature with agents)

## Sixteen-hour paid codebase trials replace the interview loop

From the ranking agent's stack rank, Untangle invites the top five candidates into a paid trial at a fixed fee for up to sixteen hours (00:08:39). Each candidate signs an NDA, gets a seat in Untangle's agent setup, and records their entire screen across all sixteen hours while driving a real pull request toward production in Untangle's codebase (00:08:39).

Untangle feeds those sixteen-hour recordings into its evaluation agent and reviews the footage to pick a finalist (00:08:39). In his most recent hiring cycle, Carson watched all sixteen hours of trial video himself and concluded that recorded agent operation gave him a far truer read on engineers than traditional loops across the hundreds of people he has hired in past companies (00:08:39).

On his completed hiring slide, a single red bracket spans Candidates, the Ranking agent, and the Top 5 trial with a crossed-out phone icon labeled "no interview calls" — nobody speaks on the phone until a finalist has already shipped inside the repo (00:08:39). Carson wraps up three minutes ahead of schedule with an invitation to follow his work at Untangle in family law before the room audio cuts off (00:08:39).

**Key points**

- Top-five candidates complete a fixed-fee, 16-hour screen-recorded trial shipping a real PR in Untangle's codebase under NDA.
- AI and human review of the 16-hour trial footage selects the finalist before a single phone call takes place.
- Recorded work on real tickets replaces multi-round interviews with direct proof of how an operator manages agents.

> “Then we basically pick the top five, and we invite them to a paid project. So we pay a fixed fee for sixteen hours at a time.”
> — 00:08:39

**Visual:** slide `experience/same-pipeline-pick-1.jpg` (the full hiring pipeline from 45-minute videos and ranking agent to paid 16-hour trials and finalist selection, bracketed by "no interview calls")
