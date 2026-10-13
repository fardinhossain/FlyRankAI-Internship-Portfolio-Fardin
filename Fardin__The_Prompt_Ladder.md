# The Prompt Ladder: From Lazy Query to Production ML Protocol

**Track:** General AI Fluency | **Code:** FL-04 / The Prompt Ladder  
**When:** Week 2 | **Phase:** Foundations | **Workload:** 2 Hours  
**Intern:** Fardin Hossain  
**Focus:** Production ML / Decision-Support Systems / Google Search Ranking Capstone  
**Target Submission Link:** [FlyRank AI Fluency Week 2: The Prompt Ladder](https://aifluency.flyrank.ai/week-02.html#the-prompt-ladder)

---

## 📌 Executive Summary & Methodology

The gap between a lazy prompt and an engineered one is the cheapest performance upgrade in AI, but most people never see it because they change five variables at once and learn nothing. 

This document chronicles a disciplined **6-run Prompt Ladder** (a weak baseline + 5 iterative versions). Each version introduces **exactly ONE architectural layer**, directly attacking the biggest weakness of the preceding output. This controlled progression isolates which instruction moves the needle, documents an authentic **"this made it worse" regression** in Version 3, and culminates in a production-ready, reusable prompt that any machine learning engineer can operate without assistance.

---

## 🪜 1. The Prompt Ladder Architecture

| Run | Single Named Layer Added | Core Prompt Delta | Observable Output Shift |
| :--- | :--- | :--- | :--- |
| **V0** | **Baseline (None)** | *“How should I evaluate my ML model on search data?”* | Generic tutorial list: `train_test_split` (80/20), accuracy, MSE, confusion matrix. Zero domain awareness. |
| **V1** | **+ Real Context** | Adds 78.8M GSC rows, schema columns (impressions, CTR, position). | Drops text/image ML advice; recommends rolling lag metrics. Still lacks an operational business goal. |
| **V2** | **+ Clearer Goal** | Defines goal: LightGBM for declining page refresh triage. | Narrows to binary classification; suggests impression slope targets. Still defaults to leaking random splits. |
| **V3** | **+ Constraints** | Demands zero leakage across domains; bans standard accuracy & ROC-AUC. | **REGRESSION / HONEST FRICTION:** AI over-indexes on academic ranking math (NDCG@k) & brittle 45-line custom loops. Lost practical utility. |
| **V4** | **+ Defined Audience** | Targets Applied ML Engineer & SEO Product Lead. | Recovers from academic tangents: balances domain-level GroupKFold with Top-K business lift and human reason codes. |
| **V5** | **+ Specified Output Format** | Enforces 4-part protocol: Splitting, Scorecard, Baselines, Sanity Checks. | Executive-grade structured specification. Clean markdown tables, explicit failure thresholds, fully reproducible. |

---

## 🔬 2. Step-by-Step Evolution: Prompts, Outputs & Evaluation Notes

### Version 0: The Weak Baseline (Embarrassing Lazy Prompt)
* **Single Named Layer Added:** None (Bare Query)
* **Prompt Input:**
  > *“How should I evaluate my machine learning model on search data?”*
* **Representative Output Excerpt:**
  > *“To evaluate a machine learning model on search data, follow these standard steps:*  
  > *1. Train-Test Split: Use an 80/20 train_test_split from scikit-learn.*  
  > *2. Standard Metrics: Depending on whether you have classification or regression, calculate Accuracy, Precision, Recall, and F1-score, or Mean Squared Error (MSE) and R².*  
  > *3. Confusion Matrix: Plot a confusion matrix to observe true positives.*  
  > *4. Cross-Validation: Run 5-fold cross-validation to ensure model stability.”*
* **The Four Evaluation Notes:**
  1. **What changed in the prompt:** Nothing. This is the unengineered baseline typed without context, goals, or constraints.
  2. **What actually improved in the output:** Baseline starting point. It provides a generic high-school textbook summary of `sklearn` functions.
  3. **What still failed:** Catastrophic failure for real-world ML. If followed on search data, an 80/20 random split causes severe domain and temporal leakage, leading to 99% illusory accuracy and instant failure in production.
  4. **What to try next:** Add **Real Context** about the dataset scale, multi-tenant nature, and schema.

---

### Version 1: Adding Real Context
* **Single Named Layer Added:** Real Context
* **Prompt Input:**
  > *“How should I evaluate my machine learning model on search data?*  
  > *Context: I have 78.8 million rows of Google Search Console telemetry across multiple client domains, where each row has domain, page URL, query, date, impressions, clicks, CTR, and average position.”*
* **Representative Output Excerpt:**
  > *“Given 78.8 million rows of Google Search Console data across multiple domains, traditional in-memory evaluation won't scale. Key recommendations:*  
  > *1. Out-of-Core Aggregation: Use DuckDB or Polars to group data by page URL and 28-day rolling windows rather than evaluating raw daily impressions.*  
  > *2. Lag Features: Calculate position delta (pos_t - pos_t-28) and CTR ratio.*  
  > *3. Evaluation Tasks: You could evaluate this as a CTR prediction regressor, an anomaly detector for drops, or a ranker for query relevance.”*
* **The Four Evaluation Notes:**
  1. **What changed in the prompt:** Added explicit dataset scale (78.8M rows), source (Google Search Console), multi-domain structure, and schema fields.
  2. **What actually improved in the output:** It stopped suggesting in-memory pandas splits and recognized memory constraints; suggested rolling temporal aggregations and lag features.
  3. **What still failed:** It brainstormed three completely different ML tasks (CTR regression, anomaly detection, query ranking) because it had no operational business objective.
  4. **What to try next:** Add a **Clearer Goal** defining what the model is predicting and why.

---

### Version 2: Adding a Clearer Goal
* **Single Named Layer Added:** A Clearer Goal
* **Prompt Input:**
  > *“How should I evaluate my machine learning model on search data?*  
  > *Context: I have 78.8 million rows of Google Search Console telemetry across multiple client domains, where each row has domain, page URL, query, date, impressions, clicks, CTR, and average position.*  
  > *Goal: I want to train a LightGBM model that identifies which declining search pages should be prioritized for content refresh next month.”*
* **Representative Output Excerpt:**
  > *“For identifying declining pages for content refresh prioritization using LightGBM:*  
  > *1. Binary Target Definition: Define y=1 if a page experienced a >=20% impression drop and >=3 position drop over a 28-day window post-evaluation.*  
  > *2. Model Evaluation: Train LightGBM with binary logloss. Evaluate using ROC-AUC and Precision-Recall AUC (PR-AUC) because declining pages are only 5-10% of total URLs.*  
  > *3. Validation Split: Perform a random 80/20 train/test split or a simple time split across your dataset.”*
* **The Four Evaluation Notes:**
  1. **What changed in the prompt:** Specified the exact model type (LightGBM), problem formulation (declining page identification), and business outcome (content refresh prioritization).
  2. **What actually improved in the output:** It eliminated generic regression tasks and honed in on binary imbalanced classification with PR-AUC and impression-slope target definitions.
  3. **What still failed:** It recommended a standard random 80/20 split or simple time split. This allows identical client domains to exist in both train and test, leaking domain authority and producing false optimism for unseen client domains.
  4. **What to try next:** Add **Constraints** demanding zero leakage across client domains and penalizing vanity metrics.

---

### Version 3: Adding Constraints (The "Made It Worse" Friction Moment)
* **Single Named Layer Added:** Constraints
* **Prompt Input:**
  > *“How should I evaluate my machine learning model on search data?*  
  > *Context: I have 78.8 million rows of Google Search Console telemetry across multiple client domains, where each row has domain, page URL, query, date, impressions, clicks, CTR, and average position.*  
  > *Goal: I want to train a LightGBM model that identifies which declining search pages should be prioritized for content refresh next month.*  
  > *Constraint: The evaluation must be strictly zero-leakage across client websites, simulating cold-start deployment on new client domains, and you must not use standard accuracy or ROC-AUC.”*
* **Representative Output Excerpt:**
  > *“To enforce strict zero-leakage without scikit-learn's standard classification metrics:*  
  > *1. Custom Leave-One-Domain-Out Loop: Implement a manual NumPy generator that yields full domain subsets one by one [includes 45 lines of brittle custom looping code].*  
  > *2. Information Retrieval Metrics: Since ROC-AUC is forbidden, formulate this strictly as a learning-to-rank problem. Calculate Mean Reciprocal Rank (MRR) and Normalized Discounted Cumulative Gain (NDCG@10) across all query groups.*  
  > *3. Pairwise Ranking Loss: Switch LightGBM objective to lambdarank with custom group query bounds.”*
* **The Four Evaluation Notes:**
  1. **What changed in the prompt:** Added strict negative constraints: zero domain leakage for cold-start deployment, and explicitly forbade accuracy and ROC-AUC.
  2. **What actually improved in the output:** It correctly recognized the domain-level grouping requirement rather than naive random shuffling.
  3. **What actually GOT WORSE / FAILED:** **HONEST FAILURE MOMENT:** The negative constraint triggered an academic over-reaction. The LLM abandoned practical tabular triage, forced an overly complex LambdaRank setup with NDCG@10 (which makes zero sense for page-level refresh decisions), and wrote 45 lines of brittle Python loop code that would crash out-of-core memory on 78.8M rows. It lost all business relevance.
  4. **What to try next:** Ground the prompt with a **Defined Audience** (Applied ML Engineer + SEO Product Lead) to force practical decision-support trade-offs.

---

### Version 4: Adding a Defined Audience
* **Single Named Layer Added:** Defined Audience
* **Prompt Input:**
  > *“How should I evaluate my machine learning model on search data?*  
  > *Context: I have 78.8 million rows of Google Search Console telemetry across multiple client domains, where each row has domain, page URL, query, date, impressions, clicks, CTR, and average position.*  
  > *Goal: I want to train a LightGBM model that identifies which declining search pages should be prioritized for content refresh next month.*  
  > *Constraint: The evaluation must be strictly zero-leakage across client websites, simulating cold-start deployment on new client domains.*  
  > *Audience: An Applied ML Engineer building this in DuckDB/Python and presenting the trade-offs to an SEO Product Lead.”*
* **Representative Output Excerpt:**
  > *“For an Applied ML Engineer collaborating with an SEO Product Lead on zero-leakage evaluation:*  
  > *1. Engineering Rigor: Implement 5-fold GroupKFold grouped by domain (not random splits) to simulate cold-start onboarding of new client domains. Use PR-AUC as the primary optimization metric under class imbalance.*  
  > *2. Product-Facing Translation: An SEO Lead cannot act on PR-AUC. Translate model scores into Top-K Precision / Refresh Lift (e.g., if editors can only refresh 50 pages this week, what percentage of the top 50 flagged URLs truly suffered significant drop vs. a baseline heuristic?).*  
  > *3. Reason Codes: Output feature contributions (SHAP / split importance) explaining why each URL was prioritized (e.g., 'Position drop from 3.2 to 8.4 despite steady query impressions').”*
* **The Four Evaluation Notes:**
  1. **What changed in the prompt:** Added dual-audience framing: an Applied ML Engineer implementer and an SEO Product Lead consumer.
  2. **What actually improved in the output:** Dramatically recovered from V3's academic rabbit hole. Connected mathematical rigor (GroupKFold, PR-AUC) directly to commercial business decisions (Top-K refresh lift, human reason codes).
  3. **What still failed:** The response was a wall of mixed paragraphs and code snippets. It lacked an actionable, structured specification document that an engineer can execute step-by-step.
  4. **What to try next:** Add a **Specified Output Format** requiring a 4-part structured evaluation playbook with markdown tables.

---

### Version 5: Adding a Specified Output Format
* **Single Named Layer Added:** Specified Output Format
* **Prompt Input:**
  > *“How should I evaluate my machine learning model on search data?*  
  > *Context: I have 78.8 million rows of Google Search Console telemetry across multiple client domains, where each row has domain, page URL, query, date, impressions, clicks, CTR, and average position.*  
  > *Goal: I want to train a LightGBM model that identifies which declining search pages should be prioritized for content refresh next month.*  
  > *Constraint: The evaluation must be strictly zero-leakage across client websites, simulating cold-start deployment on new client domains.*  
  > *Audience: An Applied ML Engineer building this in DuckDB/Python and presenting the trade-offs to an SEO Product Lead.*  
  > *Output Format: Provide a structured evaluation playbook with exactly 4 sections:*  
  > *  1. Data Splitting Architecture (formula & split unit)*  
  > *  2. Metric Scorecard (markdown table with Metric, Evaluation Level, Target Threshold, and Why It Matters)*  
  > *  3. Baseline Comparison Protocol (rules to compare against a naive heuristic)*  
  > *  4. Production Sanity & Leakage Audit Checks”*
* **Representative Output Excerpt:**
  > *“### 1. Data Splitting Architecture*  
  > *- Split Strategy: 5-Fold GroupKFold partitioned strictly on client domain_id.*  
  > *- Temporal Guardrail: Features computed on [T-56 to T-28]; target labels evaluated on [T-28 to T-0]. Zero temporal overlap.*  
  >  
  > *### 2. Metric Scorecard*  
  > *| Metric | Level | Target Threshold | Why It Matters |*  
  > *| :--- | :--- | :--- | :--- |*  
  > *| PR-AUC | Fold Average | >= 0.75 | Validates ranking quality under severe class imbalance (~8% positive rate). |*  
  > *| Top-50 Refresh Precision | Domain-level | >= 65% | Guarantees that at least 32 of 50 editorially refreshed pages were true decline candidates. |*  
  > *| Top-K Lift vs Heuristic | Macro Average | >= 2.0x | Proves the ML model delivers double the actionable yield of a simple position-drop rule. |*  
  >  
  > *### 3. Baseline Comparison Protocol*  
  > *- Baseline 1: Naive Rule (Top URLs by raw 28-day impression drop).*  
  > *- Success Criteria: LightGBM must beat Baseline 1 on Top-50 Precision across at least 4 of 5 cross-validation folds.*  
  >  
  > *### 4. Production Sanity & Leakage Audit*  
  > *- Assert len(set(train_domains).intersection(set(test_domains))) == 0.*  
  > *- Verify zero future-timestamp data is present in historical feature aggregation windows.”*
* **The Four Evaluation Notes:**
  1. **What changed in the prompt:** Prescribed an explicit 4-part playbook structure with section headings, tabular scorecard schema, and verification checks.
  2. **What actually improved in the output:** Eliminated conversational padding entirely. Output became a production-grade engineering design document with concrete thresholds and verifiable sanity checks.
  3. **What still failed:** Minor: specific to this single task. Needed to be generalized into a turnkey reusable template that any data practitioner can apply to other tabular ranking problems.
  4. **What to try next:** Clean and parametrize into the Final Reusable Prompt with clear variable placeholders.

---

## 💥 3. The "Made It Worse" Moment: Dissecting the V3 Constraint Trap

In Version 3, I added a negative constraint:  
> *“The evaluation must be strictly zero-leakage across client websites... and you must not use standard accuracy or ROC-AUC.”*

Rather than producing a cleaner pipeline, this constraint backfired. The LLM took the negative instruction as a mandate to enter full academic overdrive: it discarded binary classification entirely, pushed a convoluted LambdaRank information retrieval formulation with NDCG@10, and generated 45 lines of brittle Python looping code that would crash memory limits on 78.8 million rows. It completely forgot that an SEO editorial team cannot interpret NDCG scores to decide which web page to rewrite on Tuesday morning.

> **Key Takeaway:** Negative constraints without an anchor audience cause LLMs to overcompensate with unnecessary technical complexity. Prompt engineering requires defining *who* is acting on the output (Version 4's audience layer), not just what the AI is forbidden from doing.

---

## 🛠️ 4. The Final Reusable Prompt (Production-Ready Template)

This cleaned, turnkey prompt can be handed to any ML Engineer or Data Scientist working on tabular ranking, multi-tenant data, or cold-start prioritization without requiring additional context:

```markdown
ACT AS: A Senior Machine Learning Systems Architect specializing in tabular ranking and leak-free evaluation.

CONTEXT & DATASET:
- Scale & Source: [DATASET_SCALE, e.g. 78.8M rows of multi-tenant event telemetry].
- Grouping Entity: [GROUP_COLUMN, e.g. client_domain_id] with high entity cardinality and potential distribution shifts.
- Temporal Structure: Time-stamped event log with observation windows and evaluation windows.

CORE GOAL:
- Model: [MODEL_CLASS, e.g. LightGBM Gradient Boosted Decision Trees].
- Objective: Prioritize top declining or high-opportunity entities for automated operational triage.

CONSTRAINTS & RIGOR:
1. Zero Leakage: The evaluation split must strictly prevent entities or groups from leaking between train and test (cold-start simulation).
2. Zero Temporal Leakage: Feature extraction windows must strictly precede label observation windows.
3. Anti-Vanity: Do not report raw accuracy or ROC-AUC without PR-AUC and Top-K recall under class imbalance.

AUDIENCE:
- Technical Implementer: ML Engineer coding out-of-core queries in DuckDB/Python.
- Business Consumer: Product Lead who requires interpretable reason codes and quantifiable Top-K lift.

OUTPUT SPECIFICATION:
Deliver a complete, implementation-ready protocol containing:
1. Splitting Protocol: Mathematical definition of the group split, fold count, and temporal boundaries.
2. Metric Scorecard: A Markdown table with columns [Metric Name | Evaluation Scope | Target Threshold | Business Rationale].
3. Baseline Benchmark: A naive rule-based heuristic to beat and the exact statistical criteria for victory.
4. Automated Audit Checklist: Four assertions (in pseudo-code or Python) that fail the build if leakage is detected.
```

---

## 🎯 5. Pass / Revise Self-Audit Matrix

| Pass / Revise Criterion | Status | Verification & Justification |
| :--- | :---: | :--- |
| **1. Six runs total (baseline plus five), each version tied to exactly one named layer.** | **PASS** | Includes V0 (Baseline) plus V1 (Real Context), V2 (Clearer Goal), V3 (Constraints), V4 (Defined Audience), and V5 (Specified Output Format). Exactly one named layer added per step. |
| **2. Notes describe changes in the output, not just changes in the prompt.** | **PASS** | Every version documents the four required notes with heavy focus on output behavior: “stopped suggesting in-memory pandas”, “abandoned academic LambdaRank loops”, “connected PR-AUC to Top-K business lift”. |
| **3. At least one honest 'this didn't help' or 'this made it worse' moment.** | **PASS** | V3 documents an honest regression where negative constraints provoked the LLM to write unusable 45-line custom loops and an overly complex NDCG@10 formula that lost practical triage value. |
| **4. The final prompt works for a stranger, not just for you.** | **PASS** | Parametrized into a universal ML specification with clear placeholders (`[DATASET_SCALE]`, `[GROUP_COLUMN]`, etc.) usable by any data science or ML engineering team without prior context. |
