---
title: "AI in Practice: An Inside Look at Apollo's Approach"
speakers: "Michael Manapat (Rowspace), Jack McDonald (Apollo Global Management)"
duration: "18:48"
source: transcript.md
video: "https://www.youtube.com/watch?v=BOWYujhIQuo"
themes: [bounded-autonomy-runtime-governance-and-the-enterprise-diffusion-gap, governed-ontologies-provenance-and-financial-workbenches]
kind: talk-story
status: draft
---

# In private credit, AI earns trust only after you reconcile twenty conflicting versions of one number

Jack McDonald helps run Redding Ridge Asset Management, Apollo's structured credit and collateralized loan obligation (CLO) business overseeing roughly $50 billion. Speaking alongside Rowspace co-founder Michael Manapat, he walked through how agents moved from research toys to daily front-office infrastructure: compressing multi-day Excel portfolio builds and manual bank-statement reconciliations into minutes by encoding which internal system actually holds the truth.

## Fifty billion dollars in active credit, trapped in private documents

Manapat opened with the gap his team at Rowspace sees across financial firms: plenty of institutions experiment with AI, far fewer trust it inside mission-critical operations (00:00:00, 00:01:19). Rather than building another chat interface, Rowspace uses agents to do continuous data engineering, reconciling records across scattered internal systems so portfolio managers and traders can act on clean numbers (00:00:00).

McDonald explained why structured credit makes that data problem acute. Operating as an independent subsidiary captive to Apollo, Redding Ridge manages roughly $50 billion across structured credit and thousand-name broadly syndicated loan pools, taking in thousands of data points every day (00:00:00, 00:01:19). Unlike public equities or public bond markets, private and structured credit terms do not sit in a single standardized public feed; they live fragmented across deal agreements and internal files while the desk trades in a fast-moving market (00:01:19).

**Key points**

- Redding Ridge manages roughly $50 billion across CLOs and thousand-name syndicated loan pools.
- Structured credit terms and calculations sit scattered across private deal documents rather than uniform public feeds.
- Agents create value on the desk by doing the data engineering that unifies those records before a trade happens.

> “It's very fragmented in various documents, so we've looked to companies like Rowspace to partner with to come in and actually sit with our teams, work with us, and understand the actual calculations and information that we're looking to, and what's actually the golden source of truth”
> — 00:01:19

**Visual:** slide `experience/same-black-zip-neck.jpg` (Jack McDonald on the Simons Room stage describing data fragmentation across Redding Ridge's CLO business)

## Mock CLO portfolios in minutes instead of three days of manual Excel

When Manapat asked for concrete fire drills that used to consume a week of staff time, McDonald started with CLO portfolio construction (00:03:24). Every CLO vehicle is governed by strict legal tests and cash-flow waterfall rules buried inside lengthy indenture agreements. To construct a mock portfolio of 200 to 400 individual corporate credit names, a portfolio manager historically read through those legal agreements and built bespoke Excel models by hand, a process that took two to three days per build (00:03:24).

By pulling indenture rules, document libraries, trade and compliance constraints, and live loan pricing into one reconciled view, Redding Ridge cut that build time to minutes (00:03:24). The software does not replace the portfolio manager's credit call; it carries the mechanical assembly to 80 or 90 percent completion so the manager can spend their time shaping the final 10 percent around risk judgment (00:03:24).

**Key points**

- A single mock CLO portfolio spans 200 to 400 credit names bound by legal indenture tests and cash-flow waterfalls.
- Assembling a compliant mock portfolio previously took a portfolio manager two to three days in manual spreadsheets.
- Automated data assembly reaches 80 to 90 percent completion in minutes, reserving human judgment for the final allocation choices.

> “Today, we're able to kind of get the latest and greatest information that's real time, create a portfolio that would take somebody days to now do it in the matter of minutes, and then that allows these PMS to kind of build something to call it eighty, ninety percent completion, and then kind of use their judgment and their thought to further refine that portfolio, that last 10 percent, to make it theirs.”
> — 00:03:24

**Visual:** slide `experience/black-zip-neck-presenter.jpg` (Jack McDonald walking through automated CLO mock portfolio construction)

## Automated warehouse trade reconciliation and the twenty-source problem

McDonald's second example came from loan warehouse operations, where Redding Ridge uses bank financing lines to buy loans in the market ahead of securitization (00:03:24). Every week, two or three team members spent hours logging directly into bank portals to check settlement statements, matching buys and sells by hand, and writing an email recap for senior management (00:03:24). Dropping that reporting workflow into Rowspace turned a multi-hour weekly reconciliation into an automated job that runs in a minute, shifting the staff's role to a quick daily quality check (00:03:24).

That operational reliability answered Manapat's next question: why not just hand raw files to an off-the-shelf frontier chatbot like Claude or ChatGPT (00:06:32)? General models work fine for background research on an unfamiliar company, McDonald said, because they draw on public knowledge rather than proprietary positions (00:06:32). Trading and portfolio decisions require owning and validating internal data first. Inside a credit shop, a single metric can appear across 20 different places, including the trade order management system, performance accounting, Bloomberg, and pricing indices, with only one source holding the authoritative figure for a given calculation (00:06:32). Earning desk trust meant Rowspace engineers sitting beside portfolio managers and finance staff every day to codify which source overrides the others (00:06:32).

**Key points**

- Weekly loan warehouse trade reconciliation dropped from hours of manual bank-statement checks by two to three staffers to a one-minute automated run with daily QA.
- Off-the-shelf chatbots help with general company research but lack governed access to proprietary positions and settlement records.
- When one data point appears across 20 systems, engineers must sit with the desk to encode explicit golden-source override rules.

> “Michael sits with our team on a daily basis, learning and understanding our information flow, because for one piece of data that might come from 20 different sources, and there's only one that's actually right.”
> — 00:06:32

**Visual:** slide `experience/black-zip-neck-presenter-04.jpg` (Jack McDonald explaining how golden-source override rules earn trading-desk confidence)

## Platforms over point tools in an industry still near the starting line

Stepping back to firm-wide strategy, Manapat noted that Apollo committed early to rebuilding around a shared AI data platform rather than buying disconnected point solutions, back when coding tools were still mostly doing tab completion (00:09:07). McDonald credited a flat, nimble operating culture across Apollo that treats new tooling as a way to clear manual bottlenecks so staff can focus on higher-judgment work (00:09:07).

Even so, when Manapat compared finance against software engineering, legal work, and customer support, McDonald placed institutional banking and asset management near the beginning of the adoption curve (00:11:07). Large financial institutions carry sprawling middle- and back-office plumbing where nothing is simple (00:11:07). Using models to summarize public research or draft basic company primers is easy to deploy, he argued, yet delivers modest value compared with automating the routine operational machinery that consumes internal capacity (00:11:07).

**Key points**

- Apollo favored a unified data platform over isolated point tools from the start of its AI push.
- Institutional asset management and banking remain early in adoption because of deep middle- and back-office complexity.
- Summarizing external research offers far less leverage than automating recurring internal operational workflows.

> “In finance broadly, especially in call it the asset management, investment banking, the bank institution institutional world, I still think it's very early.”
> — 00:11:07

**Visual:** slide `experience/black-zip-neck-presenter-05.jpg` (Jack McDonald assessing where institutional finance sits on the AI adoption curve)

## Why governed data turns AI into an edge rather than the next Excel

Manapat pressed on a strategic question for asset managers: does AI end up like Excel, cutting operating costs across the board without giving any single firm a lasting edge, or does it create durable competitive separation (00:13:10)?

McDonald argued it creates real separation if tied to proprietary process and live data (00:13:10). In actively traded and private credit markets alike, execution depends on knowing exact available liquidity, live market pricing, and relative value before competitors move (00:13:10). While public markets already run on fast data feeds, private credit is still building that connective tissue across the broader Apollo platform. Acting on misaligned internal figures risks misinformed trades whose consequences ripple straight through the enterprise to end investors (00:13:10).

**Key points**

- Productivity tools become commodities like Excel only when every firm applies them to the same generic tasks.
- Real-time clarity on available liquidity, live pricing, and credit value creates an execution edge in private and structured markets.
- Preventing misaligned internal numbers protects both trading decisions and downstream investor reporting.

> “So knowing that you have a strong process in place to go out and execute, and knowing your available liquidity, or you know where things are pricing and what the value is at any given point is crucial.”
> — 00:13:10

**Visual:** slide `experience/two-presenters-standing-wide.jpg` (Michael Manapat and Jack McDonald in conversation on the Simons Room stage)

## Four hundred global investors and no substitute for sitting with the desk

Looking ahead over the next several months, McDonald named two priorities. The first is ironclad confidence in every number leaving the firm to its base of more than 400 global investors, without staff burning hours checking figures by hand (00:15:10). The second is shifting how front- and middle-office teams view technology: instead of treating tooling as a secondary afterthought while grinding through daily routines, freeing capacity lets staff question why an inherited workflow exists and how it should be redesigned as the business scales (00:15:10).

Asked what engineers entering financial AI underestimate most, McDonald warned against assuming strange-looking institutional processes are mistakes (00:15:10). Regulatory, legal, or accounting constraints usually explain why a workflow looks unusual from the outside. Getting ahead of Redding Ridge's roadmap took Rowspace engineers sitting physically alongside portfolio managers and operations staff nearly every day until those nuances were part of the system (00:15:10).

**Key points**

- Outbound reporting to more than 400 global investors leaves zero tolerance for unverified numbers.
- Automating routine checks frees staff to question and redesign legacy workflows rather than merely keeping up with volume.
- Unusual financial workflows usually reflect real structural constraints, requiring engineers to sit daily with front-office teams.

> “typically, things might look a little bit novel or strange and out of place, but it's probably actually there for a reason or structured in a specific way.”
> — 00:15:10

**Visual:** slide `experience/olive-jacket-presenter-close.jpg`, `experience/black-zip-neck-presenter-08.jpg` (Michael Manapat asking about near-term priorities; Jack McDonald closing on embedding engineers with the desk)
