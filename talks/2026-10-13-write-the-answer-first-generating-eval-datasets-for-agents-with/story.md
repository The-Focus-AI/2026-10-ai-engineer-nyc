---
title: "Write the Answer First: Generating Eval Datasets for Agents With No Benchmark"
speakers: "Nathanael Weill (Air Canada)"
duration: "19:26"
source: transcript.md
video: "https://www.youtube.com/watch?v=c_SPW__jF9w"
themes: [bootstrapping-domain-evals-without-public-benchmarks]
kind: talk-story
status: draft
---

# Start from the right answer. Most of what else they tried didn't work.

Nathanael Weill framed his talk as a recovery meeting: 720 days of shipping agents with evals, after a long stretch of shipping them without. His method fits in one line. Decide the right answer first, generate the input that should lead to it, and let code check the result. Most of the talk is the list of things that failed before and after he found it.

The recording of this talk transcribed badly, so much of the detail here comes from his slides, taken from the official video. Where the story relies on a slide rather than his words, it says so.

## The problem: no benchmark, and the experts are somewhere else

Weill's team builds AI for Air Canada's business units. The tasks are specific enough that there is no public benchmark to lean on (00:00:00). The second half of the problem is worse. His team is not the domain expert; the experts sit in other units, work in their own systems, and have little time to give (00:00:00). His slide puts the question behind every one of their agents this way: how do you test an agent when you are not the expert, and the experts have no time?

**Key points**

- The tasks are too specific for any existing benchmark.
- The people who could grade the answers are not on the team.
- Without one or the other, there is no conventional way to evaluate.

> “we don't have any particular benchmark we can rely on”
> — 00:00:00

**Visual:** slide `experience/720-days.jpg`, `experience/no-benchmarks.jpg` (the "Agent Builders Anonymous" opener; "Air Canada has lots of agents and no benchmarks")

## What didn't work in 2024: more parts, and a weekly expert

He had met the problem before, at a telecom company in 2024: a question-answering system for engineers over about ten thousand standards and vendor documents (00:00:00). Four teams got the same documents and the same task. His slide says three of them didn't work, and that he still doesn't know why; he only knows what his own team did.

What his team did at first also failed. They kept adding to the retrieval pipeline, one technique a week. The slide lists them: better parsing, a re-ranker, a query rewriter, a chunker, HyPE, extra reasoning steps. Each looked good on paper, and each fix broke something that used to work (00:00:00). The slide's quality line stays flat for eight weeks.

The only way to know whether a change helped was a weekly meeting with the experts. They put five chatbots on a big screen, asked each the same question, and had the experts say which answer was better. The experts did not always agree, and sometimes had to go and look the answer up (00:00:00). That set the pace: one try a week.

**Key points**

- Three of four teams on the same task failed.
- Adding retrieval techniques weekly moved nothing and broke things.
- Expert review allowed one experiment a week, and the experts disagreed.

> “So our budget was we can try one solution a week”
> — 00:01:29

**Visual:** slide `experience/telecom-2024.jpg`, `experience/four-teams.jpg`, `experience/quality-flat.jpg`, `experience/one-try-a-week.jpg` (the 2024 task; four teams; the flat line with eight added parts; one review slot a week)

## What worked: pick the page, then write the question

The fix reverses the order. Start with a page of the documents. Ask an LLM to write a question that page answers. Give the agent the question and check, in code, whether it retrieves that page (00:00:00). Nobody's opinion is involved, so the whole thing can be automated. He notes this is a known technique, not his invention (00:00:00).

They went from one iteration a week to one a business day by his account on stage (00:00:00); the slide says dozens of tries a day. Every change got a score, kept if the score rose and dropped if it fell. The experts' ratings went up, and the pipeline got simpler, because much of the added complexity turned out not to be needed (00:05:31).

His slide answers the four-teams question with what he calls an axiom: the other three had no test set, and if you can't tell whether a change helped, you can't make the agent better.

**Key points**

- Choose the answer first; generate the question from it.
- The check becomes code, so it runs in seconds without an expert.
- A score on every change also let them remove complexity.

> “we went from one iteration week to business day”
> — 00:05:31

**Visual:** slide `experience/answer-first.jpg`, `experience/every-day.jpg`, `experience/axiom.jpg` (before and now; one try a week to dozens a day; the axiom)

## The fix that didn't carry over

In 2026 at Air Canada the task was different: review supplier contracts clause by clause and say which need changing. It is slow, expensive work, and a missed clause is costly too (00:05:31). There was again no benchmark and the experts were again busy (00:05:31).

The agent has four steps: spot the clause with a problem, find the documents that support a change, write the amendment, and decide whether to flag it (00:05:31). The 2024 test only covers one of them. They already knew how to test finding, from the earlier project (00:05:31). The slide is blunt about the rest: the search test says nothing about spotting, writing or deciding, and re-applying it kept them on the flat line.

So the idea had to be reapplied step by step: get the answer first, then test the agent from the back (00:05:31).

**Key points**

- A contract-review agent spots, finds, writes and decides.
- The page-retrieval test covers only "find".
- Each job needs its own way of knowing the answer in advance.

> “so we're using the same concept of getting the answer first”
> — 00:07:23

**Visual:** slide `experience/contracts-2026.jpg`, `experience/rag-again.jpg`, `experience/four-jobs.jpg` (the contract workflow; the flat line again; spot, find, write, decide)

## Five ways to get an answer, and what each one found

He presents five techniques and is explicit that the aim is to give the audience ideas, not to show off (00:05:31). What each found comes from the slides.

**1. Use past decisions as the answers.** Take a contract as received and as signed, diff them, and expect the agent to propose the same changes. It failed for a mundane reason: the team does not keep the original versions (00:05:31). The slide: "we asked for these pairs. None arrived."

**2. Choose the answer, then write the contract.** Start from a rule, such as a liability cap of at least $1 million, write a clause that breaks it, and generate a contract around that clause (00:10:37). They could not get full coverage of the rules from experts or documentation, so they wrote some of their own (00:10:37). The slide: 43 rules became 275 answers, known before any test ran.

**3. Take a good contract and break it.** Delete a clause from a signed contract, mix the broken copies with clean ones, and see whether the agent notices what is missing (00:10:37). He calls this a very hard task for the agent. The slide: deleted sections were noticed 1 time in 3.

**4. Check how the answer moves.** When there is no right answer, change something that should not matter, such as the supplier's name or address, and check that the output does not change (00:10:37). The slide: the same contract, run 5 times, changed 1 in 3 judgments.

**5. Turn one example into many.** The experts already work from templates with blanks. Fill each blank with a range of values, some that break a rule and some that don't, and the expected flags are known (00:10:37). He says an evaluation comes back in five minutes (00:10:37).

Which of these he considers the strongest is not clear from the recording: he says it of the fifth when he lists them, and of the third when he describes it.

**Key points**

- One technique produced nothing because the data did not exist.
- Two of them work as tests and expose a weak agent: missed deletions, unstable judgments.
- All five end in a check that code can run.

> “so we could not have any of those pairs of contracts. So this thing doesn't work.”
> — 00:10:37

**Visual:** slide `experience/five-ways.jpg`, `experience/way-1-past-decisions.jpg`, `experience/way-2-choose-the-answer.jpg`, `experience/way-3-break-a-contract.jpg`, `experience/way-4-how-the-answer-moves.jpg`, `experience/way-5-one-into-many.jpg` (the overview, then one slide per technique with "what we found")

## Keep the check in code, and treat generated tests as a start

Everything above is checked by code, and that is deliberate. As soon as they brought in an LLM as judge, the noise from the judge was larger than the differences between the agents they were comparing, and finding the right setup for the judge was nearly as hard as the original problem (00:10:37). The slide orders the checks cheapest first, exact match, then code, then an AI judge, then a human, and says no AI judge was needed for any of the five. Its headline number: feedback that took four weeks from a beta now takes five minutes from a scripted run.

The pattern is not specific to contracts. For any agent: know what answer you are looking for, generate the input, run it (00:10:37). His slide gives two more cases, tool-call trajectories and text-to-SQL. It does not fit everything, and sometimes they changed the design of the solution so that it could be evaluated (00:10:37).

Generated tests are where you begin. Real feedback then goes into writing better tests (00:10:37). The closing slide says a person still checks every change, and sets homework: pick one agent, write ten answers before you write the tests, and run them tomorrow.

**Key points**

- An LLM judge added more noise than signal; code checks did not.
- Sometimes the solution was redesigned so it could be tested.
- Generated tests start the loop; real feedback improves the tests.

> “The original design we could not evaluate it. We switched to something that we can actually evaluate because of that.”
> — 00:17:13

**Visual:** slide `experience/five-minutes.jpg`, `experience/beyond-contracts.jpg`, `experience/feedback-loop.jpg`, `experience/write-the-answer-first.jpg`, `experience/24-hour-chip.jpg` (four weeks to five minutes; the pattern for other agents; the feedback loop; the two takeaways; the homework)
