# Awesome-Revenue-Operations-Revops-Platform

# Awesome Revenue Operations (RevOps) Platform

> A curated list of top Revenue Operations (RevOps) platforms — both SaaS/Hosted commercial solutions and open-source alternatives for unifying data, forecasting, and execution across sales, marketing, and customer success.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Clari](#clari)
  - [Gong](#gong)
  - [BoostUp.ai](#boostupai)
  - [Aviso](#aviso)
  - [LeanData](#leandata)
  - [Fullcast](#fullcast)
  - [Syncari](#syncari)
- [Open-Source Software](#-open-source-software)
  - [pipeline-diff](#pipeline-diff)
  - [b2b-revenue-forecasting](#b2b-revenue-forecasting)
  - [Revenue Ops AI Assistant](#revenue-ops-ai-assistant)
  - [zeropipeline-mcp](#zeropipeline-mcp)
  - [Horilla CRM](#horilla-crm)
  - [Odden CRM Sales](#odden-crm-sales)
  - [Eigent](#eigent)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Revenue Operations (RevOps) platforms. These are not open-source but are included as reference points for feature comparison.

### Clari
**Type:** Revenue platform with forecasting, pipeline inspection, and revenue intelligence  
Clari is the long-standing enterprise RevOps standard, bundling forecasting, pipeline management, conversation intelligence (via Copilot), and revenue analytics into a single platform. It is often the benchmark against which other RevOps tools are evaluated, with deep Salesforce integration and a broad enterprise footprint. Pricing is quote-only and typically targets mid-to-large organizations with dedicated RevOps teams.

### Gong
**Type:** Revenue intelligence with conversation analytics and forecasting  
Gong analyzes sales calls, emails, and meetings to surface deal risks, coaching opportunities, and forecast insights. It is frequently compared directly to Clari, with a strong reputation for conversation intelligence depth. Pricing is per-seat and scales with team size.

### BoostUp.ai
**Type:** AI-first revenue operations with forecasting and pipeline analytics  
BoostUp provides AI-driven forecasting, deal inspection, pipeline analytics, and revenue intelligence, positioned for mid-market to enterprise RevOps teams. It is often evaluated as a Clari alternative, with a focus on AI depth and a smaller installed base than the category leaders [citation:13].

### Aviso
**Type:** AI-first forecasting and revenue operations  
Aviso is one of the earliest AI-first RevOps platforms (founded 2012), covering AI forecasting, deal inspection, pipeline analytics, and basic AI coaching. It targets enterprise revenue ops teams wanting AI depth without Clari's bundling pressure, though its installed base and brand recognition are smaller [citation:13].

### LeanData
**Type:** Lead-to-account matching and routing  
LeanData is a core RevOps data automation tool, specializing in lead-to-account matching, routing, and orchestration. It is often a foundational layer in enterprise RevOps stacks, ensuring inbound records reach the right owners before forecasting or analytics tools process them [citation:9].

### Fullcast
**Type:** Territory and go-to-market planning  
Fullcast treats territory design, assignment rules, and coverage policies as living configuration that flows continuously into the CRM, rather than an annual planning exercise. It is scoped to territory and policy rather than full capacity planning or quota computation [citation:5].

### Syncari
**Type:** RevOps data unification and synchronization  
Syncari enforces a single source of truth at the data layer, synchronizing and governing records across CRM, marketing automation, billing, and support so the same account looks identical everywhere. The caveat is organizational: someone must own the merge rules and survivorship logic, or the platform simply automates existing disagreements [citation:5].

---

## 🟩 Open-Source Software

Self-hosted, community-driven Revenue Operations tools. The open-source ecosystem is **fragmented** across pipeline analytics, forecasting libraries, AI-assisted operator tooling, and full CRM platforms rather than direct Clari or Gong equivalents.

### pipeline-diff
**Stack:** Python / HubSpot & Salesforce connectors | **License:** Open Source (PyPI)
pipeline-diff is a CLI and dashboard tool for **pipeline change analysis**, tracking how deals move between forecast categories over time. It syncs deal snapshots from HubSpot or Salesforce, then answers questions like "which deals were pushed out this quarter" or "what changed since the last sync." It includes a demo mode that generates two years of synthetic pipeline history for an invented company, and exports reports and workspace folders designed for AI agent consumption (e.g., pointing Claude at the output folder to ask which deals slipped) [citation:11][citation:16].  
**Best for:** RevOps analysts and sales leaders wanting to understand **why pipeline changed** rather than just seeing a static forecast, with local-first operation and no dashboard login required.

### b2b-revenue-forecasting
**Stack:** Python / pandas | **License:** Open Source (PyPI)
b2b-revenue-forecasting is a Python library for **B2B revenue forecasting and quota cascading**. It supports hierarchical sales organizations, metric weighting via Pearson correlation, brand-new IC carve-outs, and **commit reconciliation** to detect and correct forecasting bias (e.g., sandbagging managers whose commits consistently understate actuals). Every output is a pandas DataFrame, making it easy to export to CSV, SQL, or a dashboard [citation:3].  
**Best for:** RevOps and finance teams wanting **programmatic, auditable quota and forecast modeling** rather than a black-box SaaS tool, particularly where custom hierarchy or bias correction is needed.

### Revenue Ops AI Assistant
**Stack:** TypeScript / Node.js / PostgreSQL / OpenAI | **License:** Open Source (GitHub)
A reference implementation of a **revenue intelligence backend** for B2B SaaS RevOps. It models accounts, contacts, opportunities, activities, campaigns, and revenue snapshots, then exposes bounded AI endpoints for **account briefs, pipeline summaries, and campaign insights**. The AI layer includes a structured fallback mode so the system remains functional without an OpenAI key, and the project explicitly states that AI must stay grounded in structured systems of record rather than improvising over loose data [citation:6].  
**Best for:** Developers and technical RevOps teams wanting a **production-minded reference architecture** for AI-assisted operator summaries, not a turnkey product.

### zeropipeline-mcp
**Stack:** Python / MCP (Model Context Protocol) | **License:** Open Source (PyPI)
zeropipeline-mcp is a **CRM that runs as an MCP server**, giving AI agents (Claude, Codex, Cursor) direct access to pipelines, deals, customers, activities, tasks, and automations via **30 built-in tools**. It positions itself as a free, open-source alternative to HubSpot, Salesforce, and Pipedrive with a native AI agent interface, zero-config auto-provisioning, and self-hostable deployment [citation:27].  
**Best for:** Teams experimenting with **AI-agent-driven pipeline management** where the primary interface is a conversational agent rather than a web dashboard, accepting that it is a newer, lighter-weight CRM foundation.

### Horilla CRM
**Stack:** Django / Python / PostgreSQL | **License:** LGPL-2.1+
Horilla CRM is a free, open-source CRM covering leads, opportunities, accounts, contacts, campaigns, and **forecasting** in a single Django application [citation:17][citation:22]. It includes role-based access control, REST API with Swagger docs, webhooks, and CSV/Excel import/export. The Docker image is actively maintained and requires PostgreSQL and Redis (for Channels and Celery) [citation:17].  
**Best for:** Organizations wanting a **full open-source CRM foundation** with built-in forecasting and a modern Django stack, accepting that RevOps-specific analytics may need to be built on top.

### Odden CRM Sales
**Stack:** PHP / Laravel | **License:** Open Source (Packagist)
Odden CRM Sales is a **revenue and deal acceleration engine** for the Odden RevOps platform, delivering multi-pipeline Kanban tracking, stage-gate enforcement, deal rotting and health scoring (0–100), CPQ quoting, outbound cadences, intelligent lead routing (RoundRobin, Weighted, Territory, SkillBased), and **weighted revenue forecasting with quota attainment** [citation:25].  
**Best for:** Laravel teams wanting a **modular, code-first RevOps engine** that can be embedded into a broader application, rather than a standalone SaaS platform.

### Eigent
**Stack:** Open-source agentic platform | **License:** Open Source (self-hostable)
Eigent is an open-source agentic cowork platform for RevOps teams, automating **CRM hygiene audits** (missing fields, duplicates, inactive opportunities), **pipeline and revenue reporting** (weekly funnel reports, QBRs), **process documentation** (SOPs, handoff guides), and **cross-team handoffs** (lead-to-sales, sales-to-CS) with automated notifications and context summaries. It integrates with Salesforce, HubSpot, and Pipedrive, and is 100% open source with self-hosting and support for local models [citation:20].  
**Best for:** RevOps teams wanting **AI agent automation for operational tasks** (data quality, reporting, handoffs) without building custom scripts, accepting that it is an agentic automation layer rather than a system of record.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Primary Focus | AI/Agent Layer | Self-Hosted | Best For |
|----------|---------|-------|---------------|----------------|-------------|----------|
| **Clari** | Proprietary | Cloud | Forecasting + pipeline | (Copilot) | ❌ | Enterprise RevOps standard |
| **Gong** | Proprietary | Cloud | Conversation intelligence | ✅ | ❌ | Call/email analysis + forecast |
| **BoostUp** | Proprietary | Cloud | AI forecasting + analytics | ✅ | ❌ | Mid-market Clari alternative |
| **LeanData** | Proprietary | Cloud | Lead matching + routing | ❌ | ❌ | RevOps data foundation |
| **Fullcast** | Proprietary | Cloud | Territory + GTM policy | ❌ | ❌ | Continuous territory planning |
| **Syncari** | Proprietary | Cloud | Data unification | ❌ | ❌ | Cross-system single truth |
| **pipeline-diff** | Open Source | Python | Pipeline change analysis | (Agent export) | ✅ | Why pipeline moved |
| **b2b-revenue-forecasting** | Open Source | Python | Quota + forecast modeling | ❌ | ✅ | Programmatic quota math |
| **Revenue Ops AI Assistant** | Open Source | TypeScript/Node | AI operator summaries | ✅ | ✅ | Reference architecture |
| **zeropipeline-mcp** | Open Source | Python/MCP | CRM via AI agent tools | ✅ Native | ✅ | Agent-first pipeline management |
| **Horilla CRM** | LGPL-2.1+ | Django/Python | Full CRM + forecasting | ❌ | ✅ | Open-source CRM foundation |
| **Odden CRM Sales** | Open Source | PHP/Laravel | Deal acceleration + CPQ | ❌ | ✅ | Modular RevOps engine |
| **Eigent** | Open Source | Agentic | CRM hygiene + reporting | ✅ | ✅ | RevOps task automation |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Revenue Operations (RevOps) tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem **splits** between **analytical/forecasting libraries** (pipeline-diff, b2b-revenue-forecasting), **AI-assisted operator tooling** (Revenue Ops AI Assistant, zeropipeline-mcp, Eigent), and **full CRM foundations with forecasting** (Horilla CRM, Odden CRM Sales). No single open-source project replicates the full breadth of Clari or Gong's conversation intelligence and enterprise forecasting, but combinations of pipeline-diff (change analysis) + b2b-revenue-forecasting (quota math) + Eigent (automation) cover meaningful subsets of the RevOps workflow. The category's blind spot — **capacity modeling** (computing how much the team can actually sell given ramp, attrition, and tenure) — remains unaddressed by both commercial and open-source tools [citation:5].

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
