# FL-06: Design Your Personal Agent
## Engineering Specification: Search Telemetry Research Scout (ST-Scout)

**Track:** General AI Fluency | **Code:** FL-06 | **Week:** 5 | **Workload:** ~4 Hours  
**Intern:** Md. Fardin Hossain  
**Submission Portal URL:** [https://aifluency.flyrank.ai/week-05.html#fl-06](https://aifluency.flyrank.ai/week-05.html#fl-06)  
**Target Build Window:** ~10 Hours (Execution in Assignment FL-07)  

---

### The Agent's One Job to Be Done

> *“The Search Telemetry Research Scout (ST-Scout) autonomously queries out-of-core DuckDB telemetry logs to discover high-volume search queries suffering from anomalous CTR suppression, dynamically inspects live competitor SERP architectures via web search, synthesizes a prioritized remediation action brief, and stages the artifact directly into the local repository—executing a closed-loop reasoning cycle without manual human intervention.”*

---

### 1. User Profile & Tool Connection Architecture

- **Primary User:** Md. Fardin Hossain (Machine Learning & Search Systems Engineer).
- **Usage Frequency:** Executed weekly or upon ingestion of new Search Console monthly batch telemetry exports.
- **Scope Boundaries:** Strictly bounded to ~10 build hours for FL-07 by leveraging modular Python tools.

| Tool / Connector | Underlying Mechanism | Realistic Access Plan | Role in Agent Loop |
| :--- | :--- | :--- | :--- |
| **1. Telemetry Query Tool**<br>`(query_telemetry_db)` | Python `duckdb` connector querying local parquet telemetry directory. | Reads existing `d:/My All Project/.../parquet` tables using SQL aggregates. 100% free, 0ms network latency. | **Perception:** Discovers queries where $\text{CTR} < 0.5 \times \text{baseline}$ and $\text{impressions} > 2,000$. |
| **2. SERP Competitor Inspector**<br>`(inspect_serp_competitors)` | HTTP request / Web search tool pulling live Google/Bing snippets. | Free SERP API endpoint or Tavily/DuckDuckGo instant search client with zero-credit quotas. | **Observation:** Gathers current top 3 competitor title tags and meta descriptions in real time. |
| **3. Action Brief File Stager**<br>`(stage_action_brief)` | Local OS filesystem write tool (Python file/docx writer). | Direct write access to project `General AI Fluency/` directory within current workspace. | **Action:** Writes validated Markdown and Word action briefs for human sign-off. |

---

### 2. Five Eval Test Cases (Pre-Registered Before Build)

| Eval Case # & Scenario | Input Stimulus | Expected Deterministic Output |
| :--- | :--- | :--- |
| **Eval 1: Severe CTR Anomaly** | Impressions: 12,000 \| Clicks: 95 \| CTR: 0.79% \| Position: 4.1 | Diagnoses *"Intent Mismatch"*; generates Title $\le 60\text{ch}$; proposes specific code snippet insertion; projects +450 clicks/mo. |
| **Eval 2: Recency Decay** | Impressions: 8,000 \| 90-day position drop from 3.2 to 8.4 | Diagnoses *"Competitive Recency Decay"*; recommends updating technical benchmarks and publishing comparison table. |
| **Eval 3: High Bounce Deficit** | CTR: 6.8% (Pos 2.1) \| Bounce Rate: 86% | Diagnoses *"UX Content Burial"*; recommends placing TL;DR formula at top of page and adding scikit-learn example. |
| **Eval 4: Ambiguous Intent Query** | Query: `'search algorithms'` (broad multi-intent) | Flags query as *"Informational Broad Cluster"*; refuses single title fix; recommends sub-topic intent landing hub. |
| **Eval 5: Corrupt / Zero Telemetry** | Impressions: 0 \| Clicks: 0 \| Position: 99.0 | Triggers defensive error catch; outputs *"Telemetry Ingestion Insufficient for Inference"*; refuses to fabricate metrics. |

---

### 3. Risk Guardrails & Build Platform Justification

#### 3.1 Guardrails & Permission Policies
- **Must-Confirm Actions (Human-in-the-Loop):**
  - Committing or pushing git commits to the remote `main` branch.
  - Dispatching automated email notifications or external webhooks.
  - Modifying production web server routing configurations.
- **Must-Never-Do Actions (Hard Architectural Locks):**
  - **NEVER** overwrite raw Parquet telemetry data on disk.
  - **NEVER** generate SEO title recommendations exceeding 60 characters.
  - **NEVER** fabricate synthetic impressions or hallucinate click performance data.

#### 3.2 Platform Selection & Trade-Off Justification
- **Chosen Platform:** Scripted Python Agent with LLM Tool Calling (Local DuckDB + File/Web APIs).
- **Alternative Rejected:** OpenAI Custom GPT or Claude Cowork (Paid).
- **Engineering Rationale:** Cloud-hosted Custom GPTs run in a walled-garden sandbox without direct access to local out-of-core DuckDB parquet tables on disk. A local scripted Python agent executes queries over 78.8M rows in milliseconds, costs $0.00, runs natively in the workspace environment, and allows strict programmatic guardrail enforcement.

---

### 4. Pass / Revise Self-Audit Matrix

| Pass / Revise Criterion | Status | Detailed Verification & Evidence |
| :--- | :---: | :--- |
| **Scope achievable in ~10 build hours.** | **PASS** | Modular architecture leverages existing DuckDB pipeline and local file writer tools, strictly bounded to core triage loop. |
| **Every tool/data source has a realistic access plan.** | **PASS** | Direct local DuckDB access, free SERP inspector, and local OS filesystem access—all fully functional without paid API blockers. |
| **5+ eval test cases defined upfront before building.** | **PASS** | Pre-registers 5 concrete cases: severe CTR anomaly, recency decay, bounce rate deficit, ambiguous intent, and corrupt telemetry. |
| **Guardrails specified for risky/irreversible actions.** | **PASS** | Explicitly enumerates Must-Confirm policies (git pushes, email dispatch) and Must-Never-Do rules (never overwrite raw data, $\le 60\text{ch}$ titles). |
| **Platform justified against $\ge 1$ alternative.** | **PASS** | Thoroughly justifies Python Scripted Agent over cloud Custom GPT based on local disk DuckDB access, zero cost, and execution control. |
