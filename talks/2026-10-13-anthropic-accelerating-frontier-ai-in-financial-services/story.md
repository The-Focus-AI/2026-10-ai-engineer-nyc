---
title: "Anthropic: Accelerating frontier AI in Financial Services."
speakers: "Belinda Neal (Anthropic), Keon Shahab (Anthropic)"
duration: "18:46"
source: transcript.md
themes: [bounded-autonomy-runtime-governance-and-the-enterprise-diffusion-gap, self-improving-fleets-and-the-agent-manager, governed-ontologies-provenance-and-financial-workbenches]
kind: talk-story
status: draft
---

# The model is no longer the bottleneck in finance. Hand-built agents are.

Belinda Neal and Keon Shahab from Anthropic argued that frontier model capability, cost efficiency, and prompt-injection defense have outrun how fast financial institutions deploy them. Moving from one-off pilots to firm-wide production takes a reusable five-layer foundation built once and shared across business and engineering teams.

## Frontier models outpace enterprise adoption

Belinda Neal, who spent nineteen years at Goldman Sachs before leading Financial Services at Anthropic, opened alongside applied AI architect Keon Shahab by splitting the industry's opportunity into three parts: applying frontier intelligence for alpha, scaling agents inside the firm, and compounding shared foundations across an industry vertical (00:00:11).

Model capability, Neal argued, is now ahead of organizational diffusion, doubling roughly every four months (00:01:32). Autonomous task horizons stretched from minutes in 2023 to more than sixteen hours, `Opus 5.5` lowered cost per task by 40 percent compared with Opus 5, and Anthropic's newest frontier release held successful prompt-injection attacks to 1 percent versus 9 to 53 percent across peer frontier models (00:01:32). Citing the latest Evident AI report, she noted that banks already sit 26 percent ahead on AI maturity scores, pointing to a $120 million auto-loan fraud reduction at one bank and research report drafts cut from 45 minutes to 15 (00:01:32). Yet after moving from 2023 chatbots to 2024 knowledge pilots to production agents today, most engineering rooms still wire each agent one by one (00:01:32).

**Key points**

- Autonomous run length (16+ hours), 40% lower task cost in `Opus 5.5`, and 1% prompt-injection success mean the model is no longer the limiting factor.
- Banks already report concrete returns, including $120M in prevented auto-loan fraud and 3x faster research drafting.
- Building agents one by one by hand caps how far those gains spread across an institution.

> “And our opportunity here is scale — is not the model, our opportunity here is scale, is building the foundation for agents that can go one to many.”
> — 00:01:32

**Visual:** slide `experience/taking-frontier-to-industry.jpg` (room-photographed slide: applying intelligence, scaling agents, and compounding impact)

## Five layers built once, instead of wiring every agent by hand

Shahab traced three phases across financial firms: proofs of concept last year, hand-crafted production agents this year, and fleet-level scale next year (00:06:12). Manually wiring five agents to five internal systems already leaves a team maintaining twenty-five point-to-point integrations (00:07:57). Standardizing system access behind a single secure Model Context Protocol (MCP) layer replaces that integration matrix with reusable plumbing (00:07:57).

Above the base model, Anthropic's architecture slide organizes the reusable stack into five numbered layers split across two questions (00:06:12). **What it can do** covers Layer 1 (`Connectors` to reach internal systems and data) and Layer 2 (`Skills` to encode business rules and workflows) (00:06:12, 00:07:57). **What lets you trust it** covers Layer 3 (`Identity and permissions` defining who the agent acts as), Layer 4 (`Sandbox and approval` governing who signs off before action), and Layer 5 (`Traces and evals` proving the agent still works as models or rules change) (00:06:12).

**Key points**

- Hand-wiring five agents to five systems creates twenty-five bespoke integrations; MCP collapses them into one connectivity layer.
- Layers 1 and 2 (`Connectors` and `Skills`) turn a general model into a domain-capable specialist.
- Layers 3, 4, and 5 (`Identity`, `Sandbox and approval`, and `Traces and evals`) supply the governance regulated firms require.

> “as you think about scaling up your agents into new specialized, various tasks, you'll want to have those agents work on one secure connectivity layer, which is MCP.”
> — 00:07:57

**Visual:** slide `experience/five-layers-agent-foundation.jpg` (room-photographed slide: the five-layer agent foundation above the model)

## Plain-text SME skills and scoped identity on a trade break

To show how the layers work together in production, Shahab walked through a trade-break investigation agent tasked with reconciling two mismatched records of the same trade (00:07:57). Rather than hard-coding investigation rules inside software releases, operations subject-matter experts write the step-by-step business rules in plain-text skills that engineering versions, reviews, and updates like living code (00:07:57).

At Layer 3, the platform assigns the agent its own explicit identity as `trade break investigator` under an `ops analyst` permission role (00:09:35). That role grants read access to order data and market data, intentionally denies queries to the CRM database so the agent cannot overreach into unrelated client records, and withholds direct write privileges on booking records so the agent can only draft proposed amendments (00:09:35).

**Key points**

- Domain procedures live in plain-text skills authored with subject-matter experts and versioned like code.
- Each agent runs under a named role identity (`ops analyst`) rather than broad service credentials.
- Least-privilege boundaries deny CRM reads and block direct booking writes at the infrastructure layer.

> “this is the business context that an SME provides, and we think about skills as living, breathing, versioned code, essentially, even though they're just plain text. They're meant to be dynamic. They're meant to be updated frequently.”
> — 00:07:57

**Visual:** diagram "Trade-break investigator permissions: MCP read access to order and market data, denied CRM, and write-blocked booking proposals"

## Approval hooks and the tight loop between business and engineering

Layer 4 governs execution boundaries (00:09:35). Wrapped in deterministic guardrails called hooks inside a sandboxed workflow, the trade-break agent investigates the discrepancy and proposes a booking amendment, then pauses until a human SME reviews and signs off before any record is modified (00:09:35). Layer 5 closes the reliability loop: SMEs help curate baseline test suites so every model upgrade or skill revision is benchmarked for regressions before deployment (00:09:35).

Once built, the same five-layer foundation serves four access points across the firm: coworker interfaces for business staff, coding environments for engineers, and custom internal UIs powered by managed agents or the Agent SDK (00:12:25). In practice, Shahab noted, that shared stack pulls business and engineering into a continuous operating loop: operations specialists work directly with the live agent, flag corrections, and propose adjustments that engineering tests against the eval baseline and ships back as updated skills (00:12:25).

**Key points**

- Deterministic hooks hold proposed booking amendments in a sandbox until a human specialist approves execution.
- SME-defined eval baselines test whether model upgrades or skill edits improve accuracy or cause regressions.
- Business users propose corrections directly from live usage, and engineering promotes validated changes into versioned skills.

> “Once they approve, then that amendment will be made, and the change will be applied. Guardrails, deterministic guardrails, called hooks around your agent, so that it's never overreaching beyond what you'd like it to do within its confines.”
> — 00:09:35

**Visual:** diagram "Sandboxed approval hooks and the continuous SME-to-engineering skill and eval loop"

## Building once for an industry: Claude for Financial Advisors

Neal returned to show how the same five-layer blueprint compounds when built once across an entire sector rather than inside a single firm (00:15:33). Financial advisors spend roughly 20 percent of their working hours directly with clients while administrative prep and follow-up consume the rest (00:15:33).

Launched in September, Anthropic's wealth offering assembles Layer 1 connectors across twenty-five custody, portfolio-planning, market-data, and CRM platforms, including Schwab and Salesforce, so advisory firms integrate once rather than rebuilding identical pipes (00:15:33). On top of those connectors, Anthropic published an open-source GitHub plugin containing eight Layer 2 workflow skills that teams can customize, such as pulling a full family plan across systems into a single pre-meeting brief or turning meeting notes into structured CRM updates and follow-ups (00:15:33). Layer 4 holds throughout: nothing is saved to a system of record or sent to a client until the advisor approves it (00:15:33).

**Key points**

- Advisors spend only about 20% of their time with clients; shared connectors and workflow skills target the remaining 80%.
- Twenty-five pre-built custody, planning, data, and CRM connectors remove duplicated integration work across wealth firms.
- Eight open-source GitHub skills handle multi-system briefs and CRM follow-ups while keeping mandatory advisor approval on every output.

> “We built a plugin that is available on GitHub that builds eight skills and workflows that an advisor can take out of the box, use today, and implement tomorrow. Layer four approval, the advisor proves everything that comes out of Claude.”
> — 00:15:33

**Visual:** diagram "Shared wealth-management stack: 25 custody and CRM connectors, 8 open-source advisor skills, and mandatory advisor sign-off"
