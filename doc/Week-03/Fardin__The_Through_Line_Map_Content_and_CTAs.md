# The Through-Line: Map Content & CTAs

**Track:** General AI Fluency | **Code:** FL-03A / The Through-Line: Map Content & CTAs  
**When:** Week 3 | **Phase:** Foundations | **Workload:** 2 Hours  
**Intern:** Fardin Hossain  
**Focus:** Production ML / Decision-Support Systems / Google Search Ranking Capstone  
**Target Submission Link:** [FlyRank AI Fluency Week 3: The Through-Line](https://aifluency.flyrank.ai/week-03.html#the-through-line)

---

## 🎯 The Winning One-Line Claim (The Through-Line)

> **“I build leak-free ranking models that help business teams prioritize content on cold-start search domains.”**

* **Length:** Exactly 16 words.
* **Why it wins:** Avoids generic resume fluff (*“passionate about AI”*), names the primary technical skill (*leak-free ranking models*), and states the business outcome on uncurated data (*prioritizing content on cold-start search domains*). It forms the structural through-line connecting every page, case study, and call to action.

---

## 🔬 1. Claim Generation & Sharpening: The 10 AI Options Audit

I tested 10 candidate claims using AI as a sparring partner to distill the most truthful, punchy, and non-generic sentence:

| # | Candidate One-Line Claim | Critique & Selection Verdict |
| :-: | :--- | :--- |
| **1** | *I am an AI engineer who builds machine learning solutions to help modern companies grow.* | **REJECTED:** Completely invisible. Pure generic resume fluff; proves zero skills. |
| **2** | *I build machine learning, data engineering, and frontend web applications for search discoverability.* | **REJECTED:** Hiding behind “and”. Claims three disciplines without anchoring mastery. |
| **3** | *I research gradient-boosted decision trees and group-partitioned cross-validation on search click logs.* | **REJECTED:** Purely academic. Ignores the commercial product outcome and business value. |
| **4** | *I help content creators rank higher on Google Search using advanced predictive AI analytics.* | **REJECTED:** Sounds like an SEO agency pitch rather than an ML systems engineering portfolio. |
| **5** | *I train LightGBM models on large-scale tabular telemetry to optimize search engine clicks.* | **REJECTED:** Too narrow on clicks; ignores cold-start distribution shifts across client domains. |
| **6** | **I build leak-free ranking models that help business teams prioritize content on cold-start search domains.** | **WINNER (SELECTED):** Names the primary discipline (leak-free ranking) and the hard business problem (cold-start triage). |
| **7** | *I turn 78.8 million messy search impressions into automated editorial refresh decisions.* | **STRONG RUNNER-UP:** Good scale hook, but “ranking models” in #6 better defines the engineering role. |
| **8** | *I design reproducible tabular ML pipelines that prevent temporal and cross-domain data leakage.* | **REJECTED:** Sounds like a data QA tester; lacks search discoverability context. |
| **9** | *I develop decision-support ranking algorithms with interpretable reason codes for enterprise SEO.* | **REJECTED:** A bit corporate; “cold-start search domains” in #6 is technically more compelling. |
| **10** | *I help scale-ups build production ML systems that don't fail when deployed on new clients.* | **REJECTED:** Too conversational; does not name ranking systems or tabular models explicitly. |

---

## 🗺️ 2. The Content Map: Pages → Ordered Sections → Cases → CTAs

| Page & Route | Sections in Sequential Order | Case Placement & Evidence | Named Call to Action (CTA) |
| :--- | :--- | :--- | :--- |
| **Page 1: Landing (`/`)** | 1. Hero Claim & Value Prop<br>2. 3 Impact Metrics (78.8M rows, 0 leakage, LightGBM)<br>3. Anchor Case Teaser<br>4. Engineering Discipline Card<br>5. Direct Conversion Footer | **Lead Case Teaser:** The FlyRank Search Triage Engine. Hook visitor with cold-start challenge. | **Primary Button:**<br>*“Explore the Search Triage Engine”* (routes to Page 2)<br><br>**Secondary:**<br>*“Schedule 20-Min Interview”* |
| **Page 2: Core Proof (`/work/search-triage`)** | 1. 30-Sec Executive Summary<br>2. Problem: Cold-Start Client Decay<br>3. Data Architecture (DuckDB)<br>4. Leakage Elimination (GroupKFold)<br>5. LightGBM Benchmarks (0.814 PR-AUC)<br>6. Decision Triage & Reason Codes<br>7. Conversion Invitation Card | **THE PRIMARY ANCHOR CASE:**<br>Full end-to-end evidence. Proves data hygiene, statistical rigor, and business triage lift. | **Mid-Page & Bottom:**<br>*“Schedule 20-Min Technical Walkthrough”* (direct mailto)<br><br>**Secondary:**<br>*“Inspect Monorepo on GitHub”* |
| **Page 3: Systems (`/systems`)** | 1. Pipeline Topology Diagram<br>2. 6-Page IEEE Paper Viewer<br>3. Deterministic Seed Suite<br>4. Benchmark Script CLI Logs<br>5. Systems Conversion Footer | **SUPPORTING SYSTEMS CASE:**<br>Proof of clean code, test suites, Docker reproducibility, and academic documentation. | **Primary Button:**<br>*“Inspect Verified Monorepo”*<br><br>**Secondary:**<br>*“Discuss Engineering with Fardin”* |
| **Page 4: Contact (`/contact`)** | 1. Direct Invitation Statement<br>2. Pre-filled Mailto Button<br>3. 1-Click Resume PDF Download<br>4. Monorepo & LinkedIn Badges<br>5. Availability Guarantee (<24h) | **CONVERSION TERMINAL:**<br>Zero friction. Direct gateway to scheduling the technical interview. | **Single Dominant CTA:**<br>*“Email fardin.hosn@gmail.com to Schedule 20-Min Chat”* |

---

## 🪜 3. The Call-to-Action Laddering Architecture

```
[Page 1: Landing] ─── CTA: "Explore Search Triage Engine" ───► [Page 2: Core Proof]
                                                                        │
                                   CTA: "Schedule 20-Min Walkthrough" ──┤
                                                                        ▼
[Page 3: Systems] ─── CTA: "Discuss System Architecture" ────► [Page 4: Contact & Conversion]
                                                                        │
                                                                        ▼
                                                         THE SINGLE FINAL ACTION:
                                                    "Email fardin.hosn@gmail.com to
                                                    Schedule a 20-Minute Technical Interview"
```

* **Laddering Rule Enforced:** Every secondary action feeds forward. There are zero dead-ends and zero distracting side paths (no newsletters, no social rabbit holes). Every link deepens belief or triggers the 20-minute interview.

---

## 📋 4. The Honest "Still Need to Gather" Audit (Unblocking Build Week)

| Asset Required | Source / Location in Repo | Current Status | Action Plan / Next Step |
| :--- | :--- | :---: | :--- |
| **DuckDB CLI Terminal Log** | `./real_capture_duckdb_terminal.png` | **READY** | Cropped, verified 300 DPI image showing 78.8M rows in 4.18s. |
| **Cost-Value Decision Matrix** | `./real_capture_cost_value_matrix.png` | **READY** | Exported directly from `paper/figures/cost_value_matrix.png`. |
| **6-Page IEEE Research Paper** | `paper/main.pdf` | **READY** | Full IEEE paper written, compiled via LaTeX, and verified in repo. |
| **Demo Walkthrough Outline** | `work/demo_outline_and_shareable_cuts.md` | **READY** | 5-minute presentation script and two shareable cuts drafted. |
| **Professional Headshot Photo** | Bio Card on Landing / Contact | **GATHERING** | Crop a high-res, natural daylight 1:1 portrait before Week 5 deploy. |

---

## 🎯 5. Pass / Revise Self-Audit Matrix

| Criterion | Status | Detailed Verification & Evidence |
| :--- | :---: | :--- |
| **1. A single, memorable claim, not a paragraph.** | **PASS** | Single 16-word claim: *“I build leak-free ranking models that help business teams prioritize content on cold-start search domains.”* Filtered from 10 options. |
| **2. Every page has ordered sections and a named call to action; the strongest work leads.** | **PASS** | All 4 pages contain explicit section sequences. The primary capstone case study (Search Triage Prioritizer) leads on Page 2 and is teased prominently on Landing. |
| **3. The calls to action ladder up to the one action from Chapter 1.** | **PASS** | Every CTA links sequentially to the single ultimate goal: emailing `fardin.hosn@gmail.com` to schedule a 20-minute technical interview. |
| **4. The gather-list is honest, so the build week isn't blocked.** | **PASS** | Audits all 5 core assets; confirms that data terminal captures, plots, paper PDF, and demo outline are already completed, unblocking development. |
