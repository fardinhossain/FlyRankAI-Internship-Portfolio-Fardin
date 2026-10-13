# Draw the Path: Portfolio Sitemap + Toolkit (Week 1 Setup)

**Track:** General AI Fluency | **Code:** FL-02 / Draw the Path | **Phase:** Setup | **Workload:** 3 Hours  
**Intern:** Fardin Hossain  
**Focus:** Production ML / Decision-Support Systems / Google Search Ranking Capstone  
**Target Submission Link:** [FlyRank AI Fluency Week 1](https://aifluency.flyrank.ai/week-01.html#draw-the-path)

---

## Executive Summary & Alignment Card

| Element | Specification |
| :--- | :--- |
| **The One Claim (Proof Statement)** | *"I build and deploy production-grade machine learning models on messy real-world data (78.8M+ search impressions) and evaluate them with rigorous, leak-free grouped validation."* |
| **The One Person (Target Audience)** | Senior Engineering Manager / Lead Applied AI Researcher hiring for an ML Engineer or Decision-Support Systems role at an applied AI scale-up. |
| **The One Action (Desired Conversion)** | Send an email to `fardin.hosn@gmail.com` requesting a 20-minute technical interview or deep-dive walkthrough. |
| **The One-Line Why** | A standard CV lists libraries and claims proficiency; this portfolio proves end-to-end data pipelines, cold-start generalization across unseen client domains, and trade-off defense under uncertainty. |

---

## 1. Portfolio Sitemap Architecture

```
                  ┌───────────────────────────────────────────────┐
                  │                 ENTRY POINT                   │
                  │             Page 1: Landing (/)               │
                  │   - Hero Proof Statement                      │
                  │   - Live Quantitative Impact Metrics          │
                  │   - Featured Anchor Case Study Teaser         │
                  └───────────────────────┬───────────────────────┘
                                          │
                           [Deep Dive into Evidence]
                                          ▼
                  ┌───────────────────────────────────────────────┐
                  │               THE CORE PROOF                  │
                  │   Page 2: Search Ranking Triage Engine        │
                  │           (/work/flyrank-search-triage)       │
                  │   - 30-Second Executive Summary Card          │
                  │   - Problem: Cold-Start Prioritization        │
                  │   - Data Architecture: 78.8M rows in DuckDB   │
                  │   - Leakage Prevention: Domain-Grouped Splits │
                  │   - Model Comparison: LightGBM vs Baselines   │
                  │   - Interactive Ranking Prioritizer           │
                  └───────────────────────┬───────────────────────┘
                                          │
                     [Need Technical Depth / Reproducibility?]
                                          ▼
                  ┌───────────────────────────────────────────────┐
                  │            ENGINEERING CAPABILITIES           │
                  │     Page 3: Supporting Systems (/systems)     │
                  │   - Architecture Breakdown & Benchmarks       │
                  │   - 6-Page IEEE Style Research Paper Link     │
                  │   - GitHub Monorepo Code Verification         │
                  └───────────────────────┬───────────────────────┘
                                          │
                               [Ready to Connect?]
                                          ▼
                  ┌───────────────────────────────────────────────┐
                  │              CONVERSION / ONE ACTION          │
                  │            Page 4: Contact (/contact)         │
                  │   - Direct Mailto: fardin.hosn@gmail.com      │
                  │   - 1-Click Resume PDF Download               │
                  │   - GitHub & LinkedIn Profile Links           │
                  └───────────────────────────────────────────────┘

       [SCRAPPED / REVISED OUT]:
       ❌ Page 5: Generic Blog (/blog) - Removed after Claude Project Pressure Test!
          (Avoids superficial tutorials and keeps focus on industrial proof).
```

### Visual Sitemap Diagram
The high-resolution sitemap sketch diagram is saved locally at:  
`./sitemap_sketch.png`

---

## 2. Page-by-Page Audit: Earning Its Place Against the One Action

| Page Route | Purpose | Key Content & Artifacts | Why It Earns Its Place |
| :--- | :--- | :--- | :--- |
| **Page 1: Landing (`/`)** | Hook within 5 seconds | • Clear Hero: ML Engineer specializing in ranking systems and tabular modeling.<br>• Proof Statement banner.<br>• 3 Core Metric Badges: 78.8M rows analyzed, 8,986 unseen domain queries evaluated, zero data leakage.<br>• Direct CTA button: *"Explore the Search Triage Engine"*. | Eliminates fluff. Proves immediately that this candidate works on real-scale industrial ML problems, filtering out non-technical recruiters and engaging engineering leads. |
| **Page 2: The Core Proof (`/work/flyrank-search-triage`)** | Convince the technical interviewer | • 30-second TL;DR card for time-constrained leads.<br>• Business & Decision-Support context.<br>• GroupKFold & cold-start evaluation methodology.<br>• ROC-AUC, PR-AUC, and Top-K Refresh Lift charts.<br>• Live Streamlit/DuckDB interactive demo. | The heart of the portfolio. Proves data hygiene, statistical rigor, and ability to translate model scores into commercial business actions. |
| **Page 3: Systems & Reproducibility (`/systems`)** | Deep verification | • IEEE format technical research paper viewer.<br>• System architecture flow (DuckDB $\to$ Feature Store $\to$ LightGBM Ranker $\to$ JSON Action Engine).<br>• Reproducibility instructions & clean code monorepo link. | Satisfies the staff engineer or principal researcher who inspects code quality, type hints, test suites, and experimental design. |
| **Page 4: Contact (`/contact`)** | Drive the One Action | • Direct email CTA: *"Let's talk about ranking systems and ML engineering"* (`fardin.hosn@gmail.com`).<br>• One-click PDF resume download.<br>• Clean links to GitHub and LinkedIn. | Zero friction to conversion. No cumbersome multi-field contact forms that get lost in spam filters. |

---

## 3. Toolkit Setup Verification

The four free frontier AI tools have been provisioned and verified:

| Tool | Status | Primary Use Case in 8-Week Portfolio Workflow |
| :--- | :--- | :--- |
| **Claude (Anthropic)** | Active (Project Configured) | Primary architectural tutor, narrative pressure-tester, paper review assistant, and code auditor. |
| **ChatGPT (OpenAI)** | Active | Rapid code generation, Bash/PowerShell scripting, unit test coverage generation, and alternative copy ideation. |
| **Gemini (Google DeepMind)** | Active | Long-context analysis (ingesting large documentation repositories, GSC technical documentation, and IEEE paper drafts). |
| **Perplexity AI** | Active | Grounded literature search, state-of-the-art ranking paper citations, and live SEO industry trend verification. |

---

## 4. Claude Project Configuration

### Project Name
`Portfolio Build: ML & Decision-Support Systems`

### Project Scope & Follow-through
Active tutor for Weeks 1 through 8 of the FlyRank AI Fluency & Machine Learning tracks.

### Genuine Custom Instructions (Configured in Project)

```markdown
# Role & Identity
You are my senior technical advisor, mentor, and rigorous reviewer for my 8-week portfolio build.
My focus is Applied Machine Learning, Decision-Support Systems, and Search Discoverability.

# My Proof Statement (The One Claim)
"I build and deploy production-grade machine learning models on messy real-world data 
(78.8M+ search impressions) and evaluate them with rigorous, leak-free grouped validation."

# My Target Audience (The One Person)
A Senior Engineering Manager or Lead Applied AI Researcher hiring for an ML Engineer or 
Decision-Support Systems role at a high-growth tech company or AI scale-up.

# The Desired Conversion (The One Action)
Contact me via email (fardin.hosn@gmail.com) to schedule a 20-minute technical interview 
or deep-dive walkthrough.

# Your Coaching Rules & Behavioral Guardrails
1. Brutal Objectivity: Never give polite flattery. If a section looks junior, generic, or unconvincing, call it out directly and explain why a hiring manager would bounce.
2. The "Show, Don't Tell" Standard: Enforce concrete metrics (row counts, latency, AUC lift, memory footprints) over hand-wavy claims like "passionate learner" or "skilled in Python".
3. Ruthless Elimination of Fluff: Constantly ask: "Does this page or section directly serve the one action?" If not, recommend deleting it.
4. Technical Integrity: Reject data leakage, unvalidated metric improvements, and trivial toy datasets (Iris, Titanic). Hold everything to production ML standards.
5. Socratic Tutoring: Before rewriting content for me, ask diagnostic questions to clarify my technical trade-offs and decision rationale.
```

---

## 5. Pressure-Test Prompt & Output Record

### The Exact Prompt Run
```text
I am designing my portfolio sitemap to prove my claim:
"I build and deploy production-grade machine learning models on messy real-world data (78.8M+ search impressions) and evaluate them with rigorous, leak-free grouped validation."

My target audience is a Senior Engineering Manager or Applied AI Lead.
My one action is having them email me to book a 20-minute technical interview.

Here is my initial proposed sitemap:
1. Landing (/) - Hero claim, bio summary, skills pills, links to work.
2. Case Study: FlyRank Search Triage Engine (/work/flyrank-search-triage) - 78.8M dataset, grouped validation, DuckDB, LightGBM, interactive table.
3. Supporting Systems (/systems) - Monorepo architecture, 6-page research paper PDF, reproducibility benchmarks.
4. Technical Blog (/blog) - 3 short tutorial posts on DuckDB tips, LightGBM tuning, and GSC data quirks.
5. About Me (/about) - Background, university education, hobbies, journey into ML.
6. Contact (/contact) - Contact form with dropdowns and resume link.

Pressure-test this sitemap:
1. Which pages are actively hurting my credibility or distracting from the one action?
2. How does a busy engineering manager navigate this under a 90-second time limit?
3. What is one specific structural change I must make immediately?
```

### Claude Project Tutor Output (Saved Transcript)

> **Claude Project Tutor Response:**
> 
> Let's analyze your sitemap from the perspective of an engineering manager who has 90 seconds between meetings to decide if you get an interview.
> 
> ### 1. Friction & Distraction Audit:
> * **Kill `/blog` immediately:** Three short tutorial posts like "DuckDB tips" or "How to tune LightGBM" scream junior developer. An engineering lead evaluating you for a machine learning role on 78.8M rows does not care about introductory tutorials—they care about your specific architectural trade-offs. A sparse or beginner blog dilutes the authority established by your capstone project.
> * **Eliminate the standalone `/about` page:** Engineering managers rarely click "About Me" on first review. Everything they need to know about your technical maturity belongs in the context of the work: your engineering philosophy, how you handled missing data, and how you prevented domain leakage. Move a 3-sentence professional bio to the landing hero and your resume.
> * **Simplify `/contact`:** Ditch the multi-field contact form. Forms feel corporate and create friction. Use a direct, hyperlinked email button with a pre-filled subject line alongside your PDF resume link.
> 
> ### 2. The 90-Second Navigation Reality:
> * **Seconds 0–15:** The manager lands on `/`. If they see generic "skills pills" (Python, Scikit-Learn, Pandas), they tune out. If they see: *"78.8M search rows processed with DuckDB; 0 domain leakage via GroupKFold"*, they are hooked.
> * **Seconds 15–60:** They click `/work/flyrank-search-triage`. They will NOT read a wall of text. They scan for:
>   1. The business problem (cold-start content opportunity ranking).
>   2. The architecture diagram.
>   3. The validation rigor (why standard K-Fold would have leaked and produced false optimism).
>   4. The quantitative result (Top-K recall/lift).
> * **Seconds 60–90:** They want to verify you actually wrote clean code. They glance at `/systems` or jump directly to your GitHub repo and IEEE paper link, then look for your email.
> 
> ### 3. The One Critical Change to Make Immediately:
> **Collapse the sitemap from 6 pages to 4 pages, and add a "30-Second Executive Summary Card" at the top of the Case Study page.**
> 
> Delete `/blog` and `/about`. Your new sitemap should be strictly:
> 1. `Landing (/)` (Hooks with proof statement + metric highlights)
> 2. `Case Study: Search Triage Engine (/work/flyrank-search-triage)` (The core undeniable proof)
> 3. `Supporting Systems (/systems)` (Paper, monorepo, reproducibility proofs)
> 4. `Contact (/contact)` (Zero-friction conversion to interview)
> 
> Every page now directly earns its place by answering one question: *Can this person build production ML systems that I can trust on day one?*

---

## 6. Iteration Reflection: Concrete Changes Made

Based on the pressure-test output from the Claude Project Tutor, the following 3 concrete improvements were made to the portfolio plan:

1. **Scrapped `/blog` Entirely:**  
   Eliminated the planned blog section. Writing introductory tutorials on basic libraries conveys a junior mindset. The focus is 100% on industrial-scale tabular modeling and decision-support triage.
2. **Merged `/about` into Landing & Case Study:**  
   Removed the separate About page. The professional background and engineering philosophy are now woven directly into the hero section and case study context.
3. **Introduced the "30-Second Executive Summary Card":**  
   Added a structured TL;DR component to the top of the Case Study page containing: Problem $\to$ Dataset Scale $\to$ Validation Strategy $\to$ Key Metric $\to$ Action Engine Output. This accommodates the 90-second scanning habits of busy hiring leads.

---

## 7. Pass / Revise Self-Audit Matrix

| Pass / Revise Criterion | Verification Status | Evidence in this Deliverable |
| :--- | :---: | :--- |
| **1. The sitemap is small and every page earns its place against the claim and the one action.** | **PASS** | Reduced to exactly 4 essential pages (`/`, `/work/flyrank-search-triage`, `/systems`, `/contact`). No extra fluff or orphaned pages. |
| **2. Claude Project configured with genuine custom instructions (proof statement pasted in), not defaults.** | **PASS** | Custom instructions explicitly include the 78.8M-row proof statement, target persona, one action, and 5 brutal review guardrails. |
| **3. The first prompt pressure-tested the map, and you noted at least one thing you’ll change.** | **PASS** | Pressure-tested against an engineering lead's 90-second scan; discarded `/blog` and `/about`, and added the 30-second summary card. |
| **4. Deliverables stored locally in `General AI Fluency/` (no git push).** | **PASS** | High-res diagram `sitemap_sketch.png`, formatted `.docx`, and `.md` companions saved cleanly in `General AI Fluency/`. |
