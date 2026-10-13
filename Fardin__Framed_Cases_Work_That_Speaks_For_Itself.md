# Frame It as Cases: Work That Speaks for Itself

**Track:** General AI Fluency | **Code:** FL-03 / Frame It as Cases  
**When:** Week 2 | **Phase:** Foundations | **Workload:** 3 Hours  
**Intern:** Fardin Hossain  
**Focus:** Production ML / Decision-Support Systems / Google Search Ranking Capstone  
**Target Submission Link:** [FlyRank AI Fluency Week 2: Frame It as Cases](https://aifluency.flyrank.ai/week-02.html#frame-it-as-cases)

---

## 🎙️ The Voice Card (Standing Claude Project Instruction)

> **“Direct, rigorous, plain, unhyped, zero buzzwords.”**

### Standing Voice Directive Added to Claude Project:
*Sound like a production machine learning practitioner reporting from the terminal. Explain what broke, what was discarded, and how validation was kept honest. Never use marketing cliches like “spearheaded”, “cutting-edge”, “innovative”, or “results-driven”. If a baseline failed or a split leaked, state it plainly and explain the fix.*

---

## ⚖️ The Before / After Editing Contrast

### Generic AI Output (Before - Buzzword Heavy):
> *“Leveraged cutting-edge machine learning and advanced data science pipelines to seamlessly optimize search discoverability, empowering stakeholders to drive unprecedented organic growth with intelligent decision-making.”*

### My Edited Version (After - Direct, Grounded & Authentic):
> *“Queried 78.8M Google Search impressions in DuckDB to flag declining URLs. Standard random splits gave a fake 99% accuracy because client domains leaked between train and test. I replaced them with 5-fold GroupKFold by domain, trained LightGBM on cold-start queries, and delivered 2.4x Top-K refresh lift with zero leakage.”*

---

## 1. Anchor Case Study: Cold-Start Search Triage Engine

* **Sitemap Location:** `/work/flyrank-search-triage`
* **Role:** Tabular ML & Validation Engineer

### Beat 1: The Problem
Search marketing teams monitor hundreds of client domains and tens of thousands of URLs. When search impressions drop, editors don't know whether a page suffered from natural query seasonality or an actual ranking decay worth rewriting. Teams drown in raw CSV exports from Google Search Console, making triage arbitrary, reactive, and slow. To automate this with machine learning, the model cannot simply memorize existing client domains; it must generalize reliably on the very first day a brand-new, unseen client domain connects its data.

### Beat 2: What I Did (and What I Decided)
I built an end-to-end data pipeline using DuckDB to ingest and aggregate 78.8 million row-level Google Search telemetry records without running out of memory. Rather than applying standard random train/test splits—which allowed URLs from the same domain to appear in both sets and artificially inflated accuracy to 99%—I made the critical engineering decision to enforce 5-fold GroupKFold validation strictly grouped by client domain. This simulated true zero-shot cold-start conditions. I engineered 28-day impression slope, position volatility, and CTR gap features, then benchmarked Logistic Regression, Random Forest, and LightGBM specifically optimized for PR-AUC under severe class imbalance.

### Beat 3: What Came of It
Under honest grouped evaluation, LightGBM achieved 0.814 PR-AUC (surpassing the baseline's 0.682) and delivered a 2.4x lift in Top-K refresh candidates on unseen client websites. I packaged the model into a decision-support engine that attaches plain-English triage flags (e.g., `HIGH_IMPRESSION_LOW_CTR`, `STEEP_POSITION_DROP`) to ranked URLs. SEO teams can now filter directly to high-recovery opportunities in seconds rather than spending hours sifting through spreadsheets.

---

## 2. Supporting Systems: Leak-Free Pipeline & IEEE Research Paper

* **Sitemap Location:** `/systems`
* **Role:** Systems & Research Lead

### Beat 1: The Problem
Most machine learning projects live as messy, non-reproducible Jupyter notebooks with hardcoded file paths, hidden out-of-order execution state, and undocumented assumptions. Technical leads and research reviewers cannot easily verify whether reported metrics are real or products of subtle target leakage and cherry-picked seeds.

### Beat 2: What I Did (and What I Decided)
I refactored the experimental notebooks into a clean production monorepo with typed Python modules, deterministic seeds, and automated unit verification. I authored a formal 6-page IEEE-format research paper documenting the data distribution, cold-start distribution shifts, and baseline trade-offs. To guarantee zero temporal leakage, I strictly isolated pre-refresh observation windows from post-refresh evaluation periods.

### Beat 3: What Came of It
A verifiable repository that executes end-to-end via a single terminal command and reproduces all paper figures and tables deterministically. Any engineering lead can clone the repo, run the test suite, and verify the model's cold-start performance without manual configuration.

---

## 3. Bio & Contact/CTA Copy

### Short Bio (Landing Hero & About Card)
> *“I am a Machine Learning Engineer focused on tabular ranking systems and production decision-support engines. I spend most of my time in DuckDB and LightGBM working with messy real-world telemetry, designing leak-free evaluation splits, and turning high-dimensional model scores into clear, verifiable business actions.”*

### Contact & CTA Copy (Driving The One Action)
> *“If your team builds ranking systems or deals with noisy distribution shifts on real data, let’s talk. Email me at `fardin.hosn@gmail.com` with 'ML Technical Interview' in the subject line to schedule a 20-minute architectural walkthrough. I’ll show you the code, the failure cases, and how the model holds up.”*

---

## 4. The AI Extraction Interview (Raw Decision Log)

Claude was used to interrogate my technical decisions and extract the unpolished engineering realities:

* **AI Interviewer (Q1):** *“What was the single messiest failure you ran into when you first trained your model?”*  
  * **My Honest Answer:** “My first random-split baseline hit 99% ROC-AUC. I knew immediately it was bogus. The dataset had multiple search queries for the same client website across different dates. The model wasn't learning rank dynamics—it was just memorizing which domains usually rank in position 1. It would have collapsed the moment a new client joined.”
* **AI Interviewer (Q2):** *“What did you decide to do about it, and what did that decision cost you?”*  
  * **My Honest Answer:** “I forced 5-fold GroupKFold strictly by client domain. My metrics instantly plunged from 0.99 to 0.74 ROC-AUC. It hurt my pride for five minutes, but it reflected the true cold-start generalization performance on unseen domains. That's the baseline I chose to defend in the IEEE paper.”
* **AI Interviewer (Q3):** *“Why didn't you just use deep learning or an LLM to rank the pages?”*  
  * **My Honest Answer:** “Because tabular search telemetry with 78.8 million rows across 28-day aggregation windows doesn't benefit from an LLM. It needs sub-second tree-based inference, explicit feature slopes, and calibrated probability thresholds that explain why a URL is flagged. LightGBM ran in seconds and gave 0.814 PR-AUC.”
* **AI Interviewer (Q4):** *“Now tell me what the hiring manager gets out of reading this.”*  
  * **My Honest Answer:** “They see that I don't hide bad numbers, I know how data leakage ruins production models, and I can engineer a real decision-support pipeline that human operators can trust.”

---

## 5. Pass / Revise Self-Audit Matrix

| Pass / Revise Criterion | Verification Status | Evidence in this Deliverable |
| :--- | :---: | :--- |
| **1. A framed case exists for each piece the sitemap calls for, not a bare screenshot or title.** | **PASS** | Full cases framed for both pieces called for in the sitemap: the Search Triage Engine (`/work/flyrank-search-triage`) and the Supporting Systems/Paper (`/systems`). |
| **2. Each case has the three beats and could only describe their project.** | **PASS** | Every case strictly follows: 1) Problem, 2) What I Did & Decided (GroupKFold, 78.8M rows, DuckDB), and 3) What Came of It (0.814 PR-AUC, 2.4x lift). Uniquely describes this repo. |
| **3. It sounds like a specific person, the before/after shows the difference from generic AI copy.** | **PASS** | Guided by the 6-word voice card (*“Direct, rigorous, plain, unhyped, zero buzzwords”*). Includes explicit before/after contrast showcasing human-edited clarity over generic AI jargon. |
| **4. It speaks to the one audience and points at the one action; tight, no 'results-driven' filler.** | **PASS** | Tailored to an Engineering Manager / Applied AI Lead and drives directly to the one action: emailing `fardin.hosn@gmail.com` for a 20-minute technical interview. |
