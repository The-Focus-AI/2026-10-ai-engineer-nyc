---
title: "Trusting Agents in Policy-Driven Workflows"
speakers:
  - name: Evan Kormos
    affiliation: Coinbase
room: "Simons Room (Metropolitan East)"
starts_at: "2026-10-14T09:36:00-04:00"
ends_at: "2026-10-14T09:54:00-04:00"
format: "keynote"
recording: "2026-10-14_0932_Coinbase"
duration: "4m 35s"
source: "qwen3-asr-1.7b"
---

# Trusting Agents in Policy-Driven Workflows

> Transcribed by qwen3-asr-1.7b with a schedule prompt. Possible prompt artifacts, names heard more often here than in the unprompted Voice Memos transcript (Qwen vs Voice Memos): Evan Kormos (1 vs 0), Coinbase (1 vs 0). Check them against the audio before quoting.

### 00:00:18 — Policy as Institutional Intent vs. the Running System

Hi, my name is Evan Kormos. I've been delivering, designing, building software for 20 years, the last 15 in enterprise financial services. I am a player coach at Coinbase, and we're here today to talk about trusting agents and policy-driven workflows.

So let's start with policy, and it's pretty boring. I'm gonna go over here to my notes. So our starting point centers around policy, and this sets the rules for how work gets done within the organization, and including especially risk compliance. Think of policy as the original institutional intent, or the original system prompt. So ideally, we have this written down, it's a little bit boring, so stick with me, using language like must, may, and should. And again, these help define the rules and decisions about how the system operates.

In the organization, separate from policy, we have the actual running system. So the first thing we're going to do is separate these two, these two, both the build stage and the run stage, at two different moments in time. So typically, we're either defining or changing our policy, but the system is constantly running and it's constantly moving and changing. So we can then sort of imagine a compilation of a that — Oops! Sorry, let's skip ahead. It's constantly changing. So, it's evolving quickly with these product-driven changes. Everything is expected to still be roughly bound by policy, but ultimately, we separate this from the run state and the build state.

### 00:02:29 — Agents Across People, Process, and Technology

The inside the system, what does it look like? We have a familiar model, if we have any enterprise folks in the room here, people processing technology, but we're really the agents. So I see them as an operational model cutting across all three. They work with people, execute parts of the process themselves, and they use and are made up of technology. So for our talk today, we're going to be focusing here where agents need process, what work we give them, what boundaries we set, and how we build trust in their outputs.

### 00:03:19 — Mapping Gated Workflows and Parallel Reviews as DAGs

So let's dive into your workflow, and it's high level when it seems basic, but if you haven't, there are good reasons to map this out. So maybe a change has to be approved before it goes live, or a customer goes through, has to go through verification before their account is opened. We expect work to flow in a specific and gated direction.

So I believe it makes, agents make it worth revisiting what we do in parallel. Previously, some work used to cost too much or be too complex to coordinate in this way. Now we can run independent reviews alongside each other, bring results together, but keep the required checks in place. So this is a directed acyclic graph, or a DAG, is a way to represent this workflow or process: the steps, the dependencies for a flow that moves forward without looking back on itself. Apache Airflow, if you're familiar, is an example of open source software that.
