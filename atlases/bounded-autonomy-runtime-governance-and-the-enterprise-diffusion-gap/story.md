---
title: "Theme 04: Bounded Autonomy, Runtime Governance, and the Enterprise Diffusion Gap"
theme_id: "bounded-autonomy-runtime-governance-and-the-enterprise-diffusion-gap"
kind: theme-deep-dive
phase: archive
talks: 8
claims: 24
---

# Bounded Autonomy, Runtime Governance, and the Enterprise Diffusion Gap

Outside software engineering, enterprise agents remain near 5% production adoption not for lack of raw model intelligence, but because non-deterministic workers require institutional trust infrastructure—automatic registries, build-time policy DAGs, risk-tiered entitlements, and opinionated workflows—between reckless autonomy and paralyzing lockdown.

Tenex quantified the conference's starkest macro reality: across roughly 100 large enterprises, general-purpose LLM access sits near 90% and coding agents near 50%, yet autonomous agents in non-engineering business workflows sit around 5%. Anthropic, Apollo, GEICO, Basis, and Apify all traced that diffusion gap to governance, process, and trust friction rather than model IQ—with Apify showing that even after eighteen months of agent payment standards, 30-day volume sits near $1M on x402 and $1,500 on MPP because static API keys, untrusted endpoints requiring marketplace middlemen, and deferred-settlement double-spend risks dominate the funnel. The architectural remedy across regulated firms was bounded autonomy: Two Sigma replaces months-long manual review queues and rubber-stamp approval fatigue with automatic framework registration, risk-scored scrutiny, registry-compiled runtime entitlements, and conservative classifiers that escalate only ambiguous calls; Coinbase separates build-time normative policy ('the original institutional system prompt') from mutating runtime state inside compliance DAGs; Basis encodes opinionated, auditable tax and accounting workflows rather than 'Move 37' creativity; and Anthropic scopes financial agents with least-privilege identities and deterministic hooks gated on advisor or SME sign-off. Qualifying this optimism, Daytona showed that host-level policy allowlists collapse if an interpreter command is permitted, while GEICO's one-day war rooms proved outer-loop enterprise inertia can be broken when decision-makers sit inside the loop.

## Why non-coding enterprise agents sit at 5%: process, trust, and payment friction

- **Mitchell Troyanovsky (Process Supervision for Agents That Do Long-Horizon Work, 00:17:21)**: Enterprise diffusion depends on predictable, repeatable execution calibrated to blast radius rather than 'Move 37' creative novelty, because organizations scale output through standardized workflows their teams can audit and trust.
  > “Nobody wants their agent to move thirty-seven their tax return. They want it done reliably at scale in a way that they can trust, and in a way that their people know how to work with.”

- **Mitchell Troyanovsky (Process Supervision for Agents That Do Long-Horizon Work, 00:03:42)**: General-purpose coding-style agent products fail to raise enterprise-wide productivity because pushing prompt, memory, and workflow management onto end users creates both a user competency gap and an unstandardized process gap.
  > “The first problem is that there is a competency gap, because agents, as you think of them as you think of them today, they outsource the complexity to the user.”

- **Mitchell Troyanovsky (Process Supervision for Agents That Do Long-Horizon Work, 00:06:10)**: Open-ended agents produce inconsistent outputs unless builders encode explicit domain opinions—such as checking primary tax sources or visually inspecting generated slides—while explicitly trading off accuracy against latency.
  > “Not because the process it did was bad, but because the process it did was not opinionated.”

- **Michael Manapat, Jack McDonald (AI in Practice: An Inside Look at Apollo's Approach, 00:11:07)**: Institutional banking and asset management remain early on the AI adoption curve because off-the-shelf research summarization delivers low value compared to automating complex middle- and back-office data workflows.
  > “In finance broadly, especially in call it the asset management, investment banking, the bank institution institutional world, I still think it's very early.”

- **Jan Curn (Agents can pay. So why don’t they?, 00:17:02)**: Variable pay-per-use compute jobs cannot use naive deferred-settlement 'up-to' payment schemes because buyers can double-spend wallet funds before on-chain settlement, forcing providers toward upfront overcharge-and-refund workarounds or on-chain escrow with batch settlement.
  > “even though like it allowed you to charge random costs, there was not nothing preventing the buyer, the agent, to spend those money wise, you know, because the transaction was only like settled on blockchain later.”

- **Jan Curn (Agents can pay. So why don’t they?, 00:04:45)**: Despite more than a dozen competing agentic payment protocols launching over eighteen months, actual 30-day on-chain settlement volume is negligible at roughly $1 million on Coinbase's x402 and $1,500 on Stripe's MPP.
  > “in the last 30 days, on this road too, there was just only like one million dollars. Nobody. And on MPP, only like one point five thousand dollars. I mean, it's basically nothing.”

- **Jan Curn (Agents can pay. So why don’t they?, 00:07:35)**: Agentic payment protocols lose today not to card rails directly, but to pre-provisioned SaaS accounts and static API keys billed to a developer's credit card, which are far simpler when tool needs are known upfront.
  > “Like authentication are competing with Visa. It's they are competing with API keys because it's just the more convenient way.”

- **Jan Curn (Agents can pay. So why don’t they?, 00:13:19)**: Because autonomous agents cannot verify whether an arbitrary external endpoint will deliver promised results or honor pricing, paid tool discovery relies on curated connector directories and marketplaces acting as trust intermediaries.
  > “same for ChatGPT, they have apps, and Apify is in marketplace as well, so basically there is just a middleman that tells you, okay, this is the service you can trust to know, and you're going to get results.”

- **Alex Lieberman (Welcome Back - Featured Keynotes, 00:02:29)**: Enterprise diffusion drops by 30 percentage points between provisioning an LLM (90%) and formally training employees to apply those AI surfaces in daily workflows (~60%).
  > “Under that is people actually getting trained in how to use the technology, how to actually use these surfaces in their work — that's like sixty percent.”

- **Alex Lieberman (Welcome Back - Featured Keynotes, 00:02:29)**: Autonomous agents running in non-engineering business functions sit at roughly 5% enterprise adoption, defining a 12-to-36-month diffusion frontier alongside open-source versus fine-tuned model selection and scaling AI engineer hiring.
  > “the final one where we are truly still day one is agents actually working in non-engineering workloads in an organization, that is around five percent right now.”

- **Alex Lieberman (Welcome Back - Featured Keynotes, 00:02:29)**: Roughly 50% of surveyed large enterprises have deployed coding agents inside software engineering and product workflows, making software delivery the leading production agent beachhead.
  > “Next up is coding agents, agents that are actually used within engineering and product workflows — that's around 50% of all the enterprises we've been in”

- **Alex Lieberman (Welcome Back - Featured Keynotes, 00:02:29)**: Across roughly a hundred large enterprises Tenex advises in financial services, healthcare, and industrials, foundational employee access to a general-purpose LLM has reached about 90% penetration.
  > “So ninety percent of the enterprises we work with have rolled out general-purpose LLM.”

## Automatic registries, risk-tiered entitlements, and five-layer foundations

- **Belinda Neal, Keon Shahab (Anthropic: Accelerating frontier AI in Financial Services., 00:09:35)**: Production financial agents enforce operational safety through least-privilege role identities, deterministic hook guardrails, and sandboxed write boundaries where agents can only propose booking amendments that a human SME must approve before execution.
  > “Once they approve, then that amendment will be made, and the change will be applied. Guardrails, deterministic guardrails, called hooks around your agent, so that it's never overreaching beyond what you'd like it to do within its confines.”

- **Belinda Neal, Keon Shahab (Anthropic: Accelerating frontier AI in Financial Services., 00:01:32)**: Model intelligence is no longer the primary constraint in financial services, shifting the strategic bottleneck from proving individual agent capabilities to building reusable infrastructure that scales deployments from one-by-one builds to many.
  > “And our opportunity here is scale — is not the model, our opportunity here is scale, is building the foundation for agents that can go one to many.”

- **Belinda Neal, Keon Shahab (Anthropic: Accelerating frontier AI in Financial Services., 00:15:33)**: Anthropic applied this shared-foundation pattern at the industry level for wealth management by combining twenty-five pre-built custody, CRM, and portfolio connectors with eight open-source workflow skills gated on mandatory advisor approval.
  > “We built a plugin that is available on GitHub that builds eight skills and workflows that an advisor can take out of the box, use today, and implement tomorrow. Layer four approval, the advisor proves everything that comes out of Claude.”

- **John Feminella (Balancing Acceleration and Safety for AI Agents, 00:07:48)**: Instead of blocking teams behind an onerous pre-registration gate that drives experimentation into ungoverned shadow IT, approved agent frameworks automatically record each agent's owner, product, declared tools, and endpoints in a central registry.
  > “It just happens when you use one of the firms approved agent building frameworks. It's automatically registered. All that information is recorded there for you, and if you want to do a manual registration, you can certainly do that.”

- **John Feminella (Balancing Acceleration and Safety for AI Agents, 00:10:00)**: Applying uniform manual review to every agent stalls low-risk experiments and drowns reviewers in trivial requests, so governance queues must be risk-scored based on each purpose-built agent's declared tools and target systems.
  > “Again, that feels safe, but now we've got a trivial summarizer waiting two months for the same sign-offs as an agent-based captioning production system.”

- **John Feminella (Balancing Acceleration and Safety for AI Agents, 00:11:58)**: Managed agent runtimes avoid blunt firm-wide allowlists by querying the agent registry at initialization time and compiling each agent's declared tool, host, and resource entitlements into enforceable runtime boundaries.
  > “when agents run in our managed environments, they look at the registry we talked about before to look up what policies apply to it at initialization time, and that policy gets translated into enforceable statements.”

- **John Feminella (Balancing Acceleration and Safety for AI Agents, 00:16:32)**: Asking humans to approve every agent action induces rubber-stamp review fatigue, so production runtimes should handle clear rules via deterministic fast paths and filter routine calls with independent conservative classifiers, escalating only genuinely ambiguous actions.
  > “when explicit rules apply, we want deterministic fast paths. When explicit rules don't apply and there's some ambiguity, you want a classifier to do that work instead.”

## Build-time policy DAGs and breaking outer-loop inertia

- **Ford Prior (Inside the Fable War Room, 00:00:00)**: Although coding agents have collapsed inner-loop coding time and offloaded routine patch work, major enterprise architecture changes remain bottlenecked by the outer loop of cross-functional alignment, risk governance, and decision-making.
  > “So while we've seen this interloop speed up to use Jean Kim's concept, we find ourselves seemingly stuck within the bounds of this outer, which is to say, everything that happens other than the current moment.”

- **Evan Kormos (Trusting Agents in Policy-Driven Workflows, 00:02:29)**: In enterprise governance, agents act as a cross-cutting operational model spanning people, process, and technology simultaneously—collaborating with human staff, executing workflow steps directly, and operating within explicit process boundaries.
  > “So I see them as an operational model cutting across all three. They work with people, execute parts of the process themselves, and they use and are made up of technology.”

- **Evan Kormos (Trusting Agents in Policy-Driven Workflows, 00:00:18)**: Regulated systems must architecturally separate build-time policy definition from the run-time production system, which mutates continuously through product changes while remaining bound by policy constraints.
  > “Everything is expected to still be roughly bound by policy, but ultimately, we separate this from the run state and the build state.”

- **Evan Kormos (Trusting Agents in Policy-Driven Workflows, 00:00:18)**: Written enterprise and risk-compliance policy—expressed through normative must, may, and should rules—functions as the organization's foundational system prompt governing how operational decisions are made.
  > “Think of policy as the original institutional intent, or the original system prompt.”

