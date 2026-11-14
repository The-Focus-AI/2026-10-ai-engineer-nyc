---
title: "Can Any Model Write Like Me? Building a Benchmark for Creative Writing"
speakers: "Louis-François Bouchard (Towards AI)"
duration: "18:49"
source: transcript.md
video: "https://www.youtube.com/watch?v=_dTF3NpPzGo"
themes: [bootstrapping-domain-evals-without-public-benchmarks, token-economics-right-sizing-and-open-foundations]
kind: talk-story
status: draft
---

# To find a model that writes like you, write down what "like you" means

Louis-François Bouchard writes for a living and was tired of fixing what models produce for him. So he built a benchmark, ToneBench, around one question: can a model write a script he could read out loud as his own? Answering it took about 8,000 words of instructions per task, five drafts from every model, and four AI judges that each turned out to favour their own maker.

The recording never catches the word "slop" (it comes out as "love" or "stuff") or the benchmark's name. Those, and most of the figures here, are from his slides.

## Slop is six things, and the worst is having no voice

Bouchard starts by defining what he wants to stop. Models keep improving and slop does not go away, so more training alone is not the fix (00:00:00). His slide lists six parts. Overused words that people rarely write and models write constantly. Being too general: "most teams", "most projects", nothing specific, which he admits to doing himself on LinkedIn. Saying nothing in pleasant words. Repeating itself. Hallucinating. And the wrong tone (00:00:00).

He calls the last one the worst. Generated text has no tone, or everyone's tone at once, and does not sound like the person it is supposed to be from (00:00:00). That sets the target: measure sloppy writing as a whole, not count slop words (00:00:00).

**Key points**

- Slop is overused words, generality, emptiness, repetition, hallucination and wrong tone.
- Better models have not made it go away.
- The goal is to measure sloppy writing, not just flag words.

> “it usually has the wrong tone, or at least it has no tone and like everyone's tone at the same time”
> — 00:00:00

**Visual:** slide `experience/slop-made-of.jpg`, `experience/word-cloud.jpg` (the six parts of slop; the cloud of overused phrases)

## The test: could I read this out loud without cringing?

He has a practical reason to care. Towards AI is a small team that produces a great deal of teaching material, uses AI to do it, and spends a lot of time fixing the results (00:00:00). The same team builds evaluation pipelines for clients (00:00:00).

The benchmark is openly subjective. It measures whether a model can write like him, defined as a script he could read aloud without cringing at words he would never use (00:00:00). Each model gets a brief and research and is asked for a complete video script that he could have written. He says that, of course, it never quite manages it (00:05:34).

The prompt is long. His slide breaks it down: a voice guide of 2,626 words, a storytelling guide of 3,243, a contract of hard requirements, the brief and the research. The output is one script of about 2,000 words. There are ten such tasks, built from his own scripts and chosen to differ in kind, length and voice. Some were never published, as a check on whether models have seen them (00:05:34).

**Key points**

- The standard is personal: would he say this out loud as himself?
- Each model gets roughly 8,000 words of guidance for a 2,000-word script.
- Ten tasks from his own scripts, some unpublished to catch contamination.

> “Obviously, that doesn't happen.”
> — 00:05:34

**Visual:** slide `experience/writer-sees.jpg`, `experience/tonebench.jpg`, `experience/ten-scripts.jpg`, `experience/whole-system.jpg` (what the writer model sees and writes; the ToneBench title; the ten scripts; the whole pipeline)

## One draft tells you nothing

Every model writes each script five times. The reason is variation within a single model, which he recommends checking in any evaluation, and especially for creative tasks (00:05:34). Some models produce one draft in five that is as good as the best model's, and four that are not (00:05:34).

His slide shows three cases on the same script. The top model's five drafts sit within a point of each other. A second model splits into two clusters and ranks fifth on its best drafts and 67th on its worst. A third is scattered. The weaker the model, the wider the spread (00:05:34). Five drafts was the compromise between seeing this and what it costs to run (00:05:34).

**Key points**

- The same model on the same prompt can land far apart.
- A single good draft can hide an unreliable model.
- Weaker models vary more.

> “the worse the model is, the widest the variance”
> — 00:05:34

**Visual:** slide `experience/five-drafts.jpg` (five drafts of the same script from three models, with each model's rank on its best and worst drafts)

## Nine metrics, four judges, and every judge has a favourite lab

Quality is scored on nine metrics. He groups them as tone, storytelling craft, following instructions on length and format, accuracy against the research, and slop (00:05:34). On the slide, tone and voice carries the most weight at 19% and slop itself only 5%.

Each judge receives about 14,000 words: around a thousand words of instructions and examples per metric, his own script as the reference, and the research. Judges do not see which model wrote the draft, and length is scored by code (00:05:34). For tone, the judge first places the draft in one of six bands and then gives a score within it. He found that worked better than a direct percentage, a yes or no, or categories alone (00:05:34). Each score comes back with a justification and a quoted example (00:05:34).

With over a hundred models, five drafts and ten tasks, there are thousands of scripts, so the judging has to be automated (00:05:34). The problem is that judges have preferences, and some prefer their own family of models, not just themselves (00:08:55). His slide measures it. One lab's judge adds 2.3 points to its own lab's drafts and takes 2.8 off its main rival's; the rival's judge adds 3.9 to its own and takes 2.1 off the first. His advice is to judge with models from different families (00:08:55). His team has also compared a thousand pairs of excerpts by hand (00:08:55).

**Key points**

- Tone weighs most; the slop score is a small part.
- Band first, then score, with long descriptions of each band.
- AI judges favour their own lab, so use several from different families.

> “Some models prefer themselves”
> — 00:08:55

**Visual:** slide `experience/favorite-lab.jpg`, `experience/nine-metrics.jpg`, `experience/judge-sees.jpg`, `experience/tone-example.jpg`, `experience/judges-send-back.jpg` (each judge's bias by lab; the nine metrics and their weights; what a judge sees; the tone rubric; a judge's reply)

## What it cost

The first cost was people: about 500 hours to prepare the scripts, define the rubrics, find examples and work out how to quantify quality (00:08:55). Then four months of his own iteration on the metrics and their weights, and thousands of dollars in model usage (00:08:55).

The running cost is what makes changes expensive. Altering one thing in the rubric means every draft has to be judged again, which he puts at more than two thousand dollars (00:08:55); the slide says $2,350. Changing a line in the writer's prompt means regenerating everything as well. His advice to anyone building something similar is to make those changes carefully (00:08:55).

**Key points**

- About 500 hours of setup and four months of iteration.
- One rubric change costs over $2,000 to re-judge.
- A prompt change costs more, because every draft is regenerated.

> “it would cost us more than two thousand dollars.”
> — 00:13:56

**Visual:** slide `experience/cost.jpg` (about 500 hours, four months, $2,350 to re-judge, $3,750 to regenerate and re-judge)

## What it taught him about writing with AI

His main conclusion is not about which model writes the best single draft. Pick the one that gets you where you want to be with the least irritation, because none of them will be perfect soon (00:08:55). At scale that is a cheap open model, which he says is about fifty times cheaper than the top-ranked one. For the top model, the highest thinking setting costs two and a half times more than the one below it for the same result (00:08:55).

The rest is practice. Make the prompt long and detailed, with every example of what to do and what not to do, including whole pieces of your own writing (00:08:55). Have a second model review the draft against the same instructions and give feedback, once and no more than three times, or it loops back into slop (00:08:55). For volume, generate several drafts with a cheap model and have a stronger one pick and merge the best parts, which he expects to cost less than one draft from the best model (00:08:55). And a person still reviews the result (00:08:55).

He ends on a limit. The benchmark measures his voice. It is one data point and does not show that the top model is the best one. He suggests people build their own (00:08:55).

**Key points**

- Choose the model that needs the fewest edits, not the most impressive one.
- Long prompts, negative examples, one review pass, cheap drafts merged by a strong model.
- It measures one person's voice; build your own for yours.

> “You just want to find a model that will be the least annoying to you”
> — 00:13:56

**Visual:** slide `experience/tips.jpg`, `experience/one-data-point.jpg` (six tips for writing with AI; "One data point, not the truth")
