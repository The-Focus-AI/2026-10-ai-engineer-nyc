---
title: "Theme 07: Governed Ontologies, Provenance, and Financial Workbenches"
theme_id: "governed-ontologies-provenance-and-financial-workbenches"
kind: theme-deep-dive
phase: archive
talks: 5
claims: 17
---

# Governed Ontologies, Provenance, and Financial Workbenches

In institutional investing and private markets, off-the-shelf web chatbots fail on stale or conflicting inputs; agents earn front-office trust only atop governed firm ontologies, validated golden sources, unified MCP connectors, and hybrid code-ML-LLM-human pipelines that write synthesis back into the vault.

Every institutional finance talk located competitive advantage in governed data infrastructure and workflow design rather than raw model selection. Bridgewater contrasted an open-web chatbot answering a Korean won query from a single three-month-old note with Vault—which aligns 100M+ documents to a bitemporal ontology, serves 1,000+ QPS agent storms via turbopuffer cluster-local native filtering, migrates researcher email habits into saved collections, and writes human-agent workbench synthesis back into the corpus so knowledge compounds. At Apollo's Redding Ridge credit platform, engineers sat daily with portfolio managers to codify golden-source precedence across 20 conflicting systems, turning multi-hour weekly loan reconciliations into one-minute automated QA reports and cutting 200–400-name CLO portfolio construction from days in Excel to minutes for the first 80–90%. Coatue modeled the hedge fund as a composite state-machine function `(external_context, internal_context) -> (stock, size, timing)`, insisting that every pixel a human sees must be API-accessible while assigning each step whichever runner—deterministic code, classical ML, LLM, or human—maximizes quality. Exa supplied the external temporal layer with 400 billion dated web snapshots built for dense exploratory agent queries, while Anthropic standardized multi-system enterprise access behind a single MCP connectivity layer.

## Bitemporal vaults and dated web snapshots over stale open-web chat

- **Aaron Linsky, Sam Green (Vault: Making Unstructured Data Work for Investing, 00:00:00)**: Bridgewater ingests over 100 million documents from 135 external sources plus internal memos and debate transcripts into Vault, enriching each document with ontology tags for countries, concepts, markets, and discussed time periods.
  > “It is carefully aligned to our internal ontology with enrichments like the countries, concepts, markets, and most importantly, time period discuss in the document.”

- **Aaron Linsky, Sam Green (Vault: Making Unstructured Data Work for Investing, 00:02:20)**: On a live Korean won query, an open-web chat agent relied on one stale three-month-old note out of 15 results, whereas connecting the same agent to Vault time-scoped the search, matched 52 candidates, and synthesized seven current sources.
  > “And so for us, this is the big lesson for building vault to kind of motivate the talk, which is that it takes great data and the right connectors to make AI powerful.”

- **Aaron Linsky, Sam Green (Vault: Making Unstructured Data Work for Investing, 00:06:23)**: Because production queries nearly always filter by date, source, or asset and agent storms exceed 100 to 1,000+ queries per second versus 100 per hour for humans, Bridgewater switched to turbopuffer's cluster-local native filtering to pair post-filtering speed with near pre-filtering recall.
  > “Their approach, which they call native filtering, looks only in the nearest clusters if it can matches, and then scores just those.”

- **Aaron Linsky, Sam Green (Vault: Making Unstructured Data Work for Investing, 00:09:34)**: Winning daily investor adoption required replicating familiar broker-email workflows inside Vault — converting distribution lists into saved searches and inbox folders into saved collections — before introducing cross-dataset queries, dynamic topic feeds, and CLI/Slack agent access.
  > “So that's exactly what we did: everything searchable, the subscriber lists became saved searches, and folders became saved collections. It's the same habits, just a new home.”

- **Aaron Linsky, Sam Green (Vault: Making Unstructured Data Work for Investing, 00:12:12)**: The proactive Investor Workbench pairs always-on topic cards and raw source evidence with deep-research agents like Pocket Analyst, automatically writing the resulting human-agent synthesis back into Vault so institutional knowledge compounds across research cycles.
  > “And when they dig deeper alongside the agent to look at the dynamic driving this question, the learnings are automatically captured — the results of their collaboration are automatically captured back in the model.”

- **Ryan Ahern (Search the Web as It Was: An Introduction to Exa Snapshot, 00:00:00)**: Unlike humans who enter brief keyword queries and stop early, AI agents issue high volumes of detailed, exploratory searches per task, requiring search infrastructure purpose-built for agentic retrieval.
  > “They tend to describe what they want to search in great detail, execute many searches, and want to understand the space more fully before they pass, and that means that they do way more searches on a post basis.”

- **Ryan Ahern (Search the Web as It Was: An Introduction to Exa Snapshot, 00:06:29)**: By archiving page states during continuous freshness crawls, Exa Snapshot exposes over 400 billion daily-indexed web snapshots for both point-in-time URL lookups and historical semantic search queries.
  > “So just recently, we released Exa Snapshot. It's 400 billion plus snapshots of the web, and you can search them by day.”

## Golden-source reconciliation and portfolio construction in private credit

- **Michael Manapat, Jack McDonald (AI in Practice: An Inside Look at Apollo's Approach, 00:00:00)**: Rowspace deploys agents to perform continuous data engineering—reconciling fragmented records across disparate enterprise systems—so portfolio managers and traders act on unified data rather than querying isolated chatbots.
  > “We essentially use agents to do the work of data engineering, right information or reconciled data from across a variety of systems to the portfolio managers, traders, and so forth can make decisions faster and more accurately.”

- **Michael Manapat, Jack McDonald (AI in Practice: An Inside Look at Apollo's Approach, 00:03:24)**: Weekly warehouse loan trade reconciliation—previously requiring two to three staff members hours of manual bank-statement checks—now runs automatically in a minute, shifting the team's role to daily QA.
  > “That report was then created and now repeatable in the span of a minute, and now all of that is automated.”

- **Michael Manapat, Jack McDonald (AI in Practice: An Inside Look at Apollo's Approach, 00:03:24)**: Combining indenture waterfall rules, compliance constraints, and real-time pricing cut 200-to-400-name mock CLO portfolio construction from two-to-three days in manual Excel to minutes for the first 80–90% of the build.
  > “that allows these PMS to kind of build something to call it eighty, ninety percent completion, and then kind of use their judgment and their thought to further refine that portfolio, that last 10 percent, to make it theirs.”

- **Michael Manapat, Jack McDonald (AI in Practice: An Inside Look at Apollo's Approach, 00:06:32)**: Because a single financial data point can appear across 20 conflicting systems with only one authoritative source, earning trading-desk trust required engineers sitting daily with PMs to encode golden-source precedence rules.
  > “Michael sits with our team on a daily basis, learning and understanding our information flow, because for one piece of data that might come from 20 different sources, and there's only one that's actually right.”

- **Michael Manapat, Jack McDonald (AI in Practice: An Inside Look at Apollo's Approach, 00:13:10)**: AI grounded in validated proprietary data creates a durable competitive advantage in private credit—rather than becoming a commodity like Excel—by giving managers real-time accuracy on available liquidity and pricing.
  > “So knowing that you have a strong process in place to go out and execute, and knowing your available liquidity, or you know where things are pricing and what the value is at any given point is crucial.”

- **Belinda Neal, Keon Shahab (Anthropic: Accelerating frontier AI in Financial Services., 00:07:57)**: Manually wiring individual agents to enterprise data systems creates a brittle integration matrix as use cases multiply, so organizations should standardize source-system access behind a single secure MCP connectivity layer.
  > “as you think about scaling up your agents into new specialized, various tasks, you'll want to have those agents work on one secure connectivity layer, which is MCP.”

## A hedge fund as a composite function across code, ML, LLMs, and humans

- **Frank Long (A Hedge Fund as a Function, 00:07:29)**: Each sub-function should be assigned whichever runner—deterministic code, classical ML regressions, LLMs, or human judgment—maximizes absolute quality for that step rather than automating with LLMs by default.
  > “There is no glory in automating things for the sake of automating things. The goal is not to take as many things and make them LLMs as possible.”

- **Frank Long (A Hedge Fund as a Function, 00:12:16)**: Composing multi-step transformations across every firm data source with 10+ hyperparameters and 20+ values per node yields an effectively infinite graph whose core challenge is technical and organizational legibility.
  > “In each of those nodes, we just talked about, at least ten hyperparameters with at least 20 different valid values for them. So the search space is basically infinite.”

- **Frank Long (A Hedge Fund as a Function, 00:01:25)**: Agent capability is wasted unless every external market feed and internal firm record—positions, liquidity and risk constraints, and decades of trade decision notes—is exposed directly via API rather than UI copy-paste.
  > “Every single thing that a human can see in pixels on the screen, an agent in your building should be able to see via API.”

