# FL-09: Agent Documentation & Demo Video
## Comprehensive README, v2 Eval Benchmark & Live Narration Guide

**Track:** General AI Fluency | **Code:** FL-09 | **Week:** 8 | **Workload:** ~5 Hours  
**Intern:** Md. Fardin Hossain  
**Submission Portal URL:** [https://aifluency.flyrank.ai/week-08.html#fl-09](https://aifluency.flyrank.ai/week-08.html#fl-09)  
**Agent Repository:** [https://github.com/fardinhossain/FlyRankAI-ML-Internship-Task](https://github.com/fardinhossain/FlyRankAI-ML-Internship-Task)  

---

### Executive Overview

> **Documentation & Demo Video Specifications:**  
> This deliverable provides stranger-reproducible documentation for the Search Telemetry Research Scout (ST-Scout) agent. It includes a complete technical README, exact zero-dependency setup instructions, an architecture schema, empirical results for the 5 pre-registered FL-06 eval test cases (100% pass rate), a catalog of known limitations, and a structured storyboard for the 3–5 minute unedited live demonstration video.

---

### 1. The Complete Technical README (Reproducible Setup)

#### 1.1 What ST-Scout Does and For Whom
The **Search Telemetry Research Scout (ST-Scout)** is an autonomous AI agent engineered for Machine Learning Engineers and Technical SEO Systems Leads. In large-scale enterprise websites, millions of search impressions occur across long-tail queries. ST-Scout continuously scans DuckDB telemetry tables, flags statistically suppressed CTR anomalies (>2.0 standard deviations below benchmark), inspects live competitor SERP architectures, applies rigorous guardrails, and stages structured Markdown action briefs for editorial and ML teams.

#### 1.2 Zero-Friction Quickstart Setup (Stranger-Reproducible)

```bash
# Step 1: Clone the repository and enter the project root
git clone https://github.com/fardinhossain/FlyRankAI-ML-Internship-Task.git
cd FlyRankAI-ML-Internship-Task

# Step 2: Create and activate a Python virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Step 3: Install verified dependencies
pip install duckdb pandas

# Step 4: Execute the autonomous agent
python "General AI Fluency/st_scout_agent.py"
```

**Expected Outcome:** The agent executes in <2 seconds, outputs perception and reasoning traces to stdout, and writes validated action brief files into `General AI Fluency/Action_Brief__*.md`.

#### 1.3 Architecture Schema: Perception $\rightarrow$ Reasoning $\rightarrow$ Guardrails $\rightarrow$ Action

```
+-------------------------------------------------------------------------+
| 1. PERCEPTION: DuckDB SQL Scanner (Filter: impressions >= 2000, CTR delta)|
+-----------------------------------+-------------------------------------+
                                    | Anomaly Dict Array
                                    v
+-------------------------------------------------------------------------+
| 2. TOOL CALL: inspect_serp_competitors(query)                           |
| Fetches live SERP competitor titles & content snippets                  |
+-----------------------------------+-------------------------------------+
                                    | Competitor Snippets
                                    v
+-------------------------------------------------------------------------+
| 3. REASONING & SYNTHESIS: Diagnostic root-cause, uplift calculation      |
+-----------------------------------+-------------------------------------+
                                    | Draft Brief
                                    v
+-------------------------------------------------------------------------+
| 4. HARD GUARDRAIL HOOK: len(title) <= 60 chars (Auto-trimming clamp)    |
+-----------------------------------+-------------------------------------+
                                    | Validated Brief
                                    v
+-------------------------------------------------------------------------+
| 5. ACTION: stage_action_brief(output_path) -> Local Disk Write          |
+-------------------------------------------------------------------------+
```

---

### 2. Empirical v2 Eval Results (Verification of 5 FL-06 Cases)

| Eval Case # & Title | Input Stimulus | Observed Agent Output | Result |
| :--- | :--- | :--- | :---: |
| **Eval 1: Severe CTR Anomaly** | Impressions: 14.2k \| CTR: 0.8% \| Pos: 4.2 | Diagnosed *'Intent Mismatch'*; generated title trimmed to $\le 60\text{ch}$; projected +525 clicks/mo. | **PASS** |
| **Eval 2: Recency Decay** | Impressions: 8.4k \| Pos: 7.1 (Dropped from 3.8) | Diagnosed *'Competitive Recency Decay'*; recommended modern 2026 Two-Tower bandit benchmark update. | **PASS** |
| **Eval 3: High Bounce Deficit** | CTR: 6.2% \| Pos: 2.3 \| Bounce: 84% | Diagnosed *'UX Content Burial'*; recommended TL;DR formula callout at top of page. | **PASS** |
| **Eval 4: Broad Query Cluster** | Query: `'search algorithms'` (broad) | Classified query as broad cluster; refused single-URL title fix; recommended intent pillar hub. | **PASS** |
| **Eval 5: Corrupt Telemetry** | Impressions: 0 \| Clicks: 0 \| Pos: 99.0 | Defensive catch triggered; logged *'Insufficient Telemetry'*; refused to fabricate metrics. | **PASS** |

---

### 3. Limitations List & 3–5 Minute Narrated Demo Script

#### 3.1 Catalog of Known Limitations
1. **Local Table Dependency:** Currently operates on local DuckDB in-memory or Parquet files; does not yet maintain a direct live OAuth sync to the Google Search Console API.
2. **Competitor SERP Heuristic:** The competitor inspector currently queries desktop SERP representations, which may miss mobile-only search features or carousel packs.
3. **Decoupled Git Push:** To guarantee safety, the agent stages files locally on disk rather than automatically committing to GitHub `main`.

#### 3.2 Narrated Demo Video Storyboard (Duration: ~3.5 min, No Slides, Live Screen)
- **Minute 0:00–0:45 (Context & Mission):** Introduce Fardin Hossain, ML Engineer. Show the terminal and project directory. Explain ST-Scout's one job: turning raw search console telemetry anomalies into verified engineering action briefs.
- **Minute 0:45–1:45 (Live Terminal Execution):** Run `python General AI Fluency/st_scout_agent.py` on camera. Point to stdout traces showing DuckDB SQL perception, anomaly detection, and the live tool call to inspect competitor SERPs.
- **Minute 1:45–2:30 (Design Decision on Camera):** Explain why we built programmatic guardrails to clamp titles at 60 characters, and why we decoupled automatic git push to maintain a mandatory human-in-the-loop sign-off.
- **Minute 2:30–3:15 (Artifact Inspection):** Open the newly generated Markdown action brief in VS Code. Walk through the empirical CTR delta, competitor title analysis, and concrete code insertion diff.
- **Minute 3:15–3:30 (Wrap-up & Limitations):** Explain Limitation #1 (local DuckDB parquet reliance vs live OAuth) and conclude.

---

### 4. Pass / Revise Self-Audit Matrix

| Pass / Revise Criterion | Status | Detailed Verification & Evidence |
| :--- | :---: | :--- |
| **Stranger could reproduce setup from README alone.** | **PASS** | Provides step-by-step shell commands covering clone, venv setup, pip install, and execution with expected outputs. |
| **v2 Eval results and limitations explicitly documented.** | **PASS** | Documents 100% pass across 5 FL-06 eval cases; catalogs 3 concrete system limitations transparently. |
| **Video storyboard structured for 3–5 min live demonstration.** | **PASS** | Complete chronological script mapped from 0:00 to 3:30, zero slide decks, focusing on real code and artifacts. |
| **One design decision and one limitation explained on camera.** | **PASS** | Explicitly covers the 60-character title guardrail decision and the local DuckDB parquet constraint. |
