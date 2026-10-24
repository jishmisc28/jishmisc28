## 

## Hi there 👋, I'm Abhranshu  

- Currently: Building @ [Autonmis](https://autonmis.com) AI-native governed data platform for Ops & Business.  
- Previously: AVP Data & ML @ Paytm · Head of Data @ Junglee Games, Lido, Simplilearn
- Built multi petabyte scale data processing platforms at Paytm & Junglee Games 
- Focus: Data platforms, Agents, distributed compute systems, governance, AI execution layers

### Selected Work
- Open source: [hearth](https://github.com/jishmisc28/hearth) — prompt-cache stability for agent loops. `pip install hearth-ai`
- Open source: [synthetic-enterprise-lab](https://github.com/jishmisc28/synthetic-enterprise-lab) — a runnable lender whose books disagree
- Open source: [first-impressions-ai](https://github.com/jishmisc28/first-impressions-ai) — a signed-in product walk that checks the numbers, with evidence
- System design: https://www.linkedin.com/in/abhranshu-bagchi/recent-activity/articles/
- Case studies: https://autonmis.com/blogs
- Articles: https://medium.com/@abhranshubagchi

### Current Focus
Designing AI-native governed execution systems on enterprise data, and open-sourcing the pieces that have to be true before an agent touches that data.
- **hearth** — in-process wrap around the existing LLM client. Holds the prompt-cache prefix stable across turns, attributes the break, and records read / write / uncached usage. `observe` is byte-identical. `safe` changes serialisation only. `optimize` moves volatile fields out of the prefix and compacts history when the remaining turns pay for the rewrite.
- **synthetic-enterprise-lab** — runnable multi-system estate (loan book, collections, general ledger, ERP, events, object store) with planted disagreements and fault injection (`make break` / `make heal`).
- **first-impressions-ai** — signed-in walk of a B2B or data-heavy product. Checks cross-screen sums, a KPI that does not match its API, and dead controls, then writes an evidence report. Local. No live billing.


## What I've shipped

**@Autonmis** 
Full-stack AI-native data platform built largely solo. Microservice led multi-tenant org architecture with RLS and 7-year audit logging. Governed access & metric lifecycle (defined → draft → published) enforced across dashboards, alerts, and executive briefs. LangGraph session graphs + BullMQ  worker pools + OpenRouter model routing with fallback chain. On-premises EKS/EC2 deployment with VPC isolation for regulated 
customers. Early deployment on customer data in diverse verticals.

**@hearth** (`hearth-ai`)
Python library that wraps the Anthropic, OpenAI, or Gemini client in-process and keeps the prompt cache warm across an agent loop. Volatile timestamps, shifting tool order, and non-deterministic JSON were breaking the prefix on every turn. `observe` passes the request through byte-for-byte and writes the break to a local ledger. `safe` restores tool order and cache breakpoints without changing message text. `optimize` moves those volatile fields to the tail, stubs tool outputs over 2,000 tokens, and compacts history only past the break-even. Adapters for LangGraph, Pydantic AI, and the OpenAI Agents SDK. Measured overhead 0.66 ms p50 at 50k tokens of context. `pip install hearth-ai`.

**@synthetic-enterprise-lab**
A local company you boot with Docker, whose systems disagree on purpose, for testing data agents, analytics, and reconciliation. First domain is Aarohan, a synthetic lender. Separate processes for the loan book, collections, general ledger, a gold vault, an ERP API, a pull-based event feed, a webhook sink, and partner files on MinIO. Loan `AF-LN-I01-PL`: UPI `UPI-I01-8891` succeeded for 6052.14, the loan book never applied it, the ledger posted it the next day with an empty loan reference. `make verify` checks that truth sheet. `make break` can slow the loan book, withhold payment events, stop MinIO, or return HTTP 500 from the ERP. `make heal` restores them. One domain. Not a warehouse and not an agent framework.

**@first-impressions-ai**
A local first user for B2B and data-heavy products. Signs in with a test account, walks the app, and writes an HTML report with evidence for faults you can check: a headline that the rows do not add up to, a card that disagrees with its API, a dead control, a badge that over-counts the table. Northstar, the sandbox finance app, headlines $1,240,500 while the region rows fail to sum. Three repeats found the same seven defects. The clean build found none. `pnpm fia diff` marks a later run fixed, new, regressed, or unchanged. The test password is scanned out of the report. `pnpm fia demo` runs the sandbox. No public URL, and the plan switch does not charge a card.

**@Paytm — Data & ML Platform:** 
Ledger reconciliation and financial reporting across ₹250Cr+/month in flows. MLOps for AML in Payments. Payout engine for 100K field agents — rules engine, scoring 
system, device servicing workflows. Governance and observability layer across 1,000+ production pipelines.

**@Junglee Games — Data Eng & ML Systems:** 
Real-time gameplay ecosystem at 1B+ daily events. Sub-second leaderboard updates for 10M concurrent players. Financial-grade 
transaction processing for 50M+ monthly transactions. Data org built 0 → 22 engineers.

---

## What I’m building

Most of my work is in private repositories.

This repository captures:
- system design decisions
- architecture patterns
- lessons from building production data systems

---

## Consulting and fractional availability

I take on a small number of engagements where the problem is hard and the context fits.

**Architecture sprint** — 2–4+ week embedded engagement. 
Current-state audit, architecture decision document, implementation roadmap. For teams at the inflection point between scrappy and engineered.

**Platform deployment** — Full Autonmis deployment on your infrastructure, configured for your data and governance requirements. For lean teams that need the system working, not just designed.

**Fractional data leadership** — Ongoing technical anchor for data decisions: architecture reviews, hiring, roadmap. 
For companies between "no data leader" and "ready to hire full-time."

Book a call: https://cal.com/abhranshu-b/exploratory


