# The Plan to Keep Building: Portfolio Habit Plan
## Case Study Expansion Protocol, Next Named Project & Context Preservation

**Track:** General AI Fluency | **Week:** 8 Continuous Building Habit | **Workload:** ~1 Hour  
**Intern:** Md. Fardin Hossain  
**Submission Portal URL:** [https://aifluency.flyrank.ai/week-08.html#the-plan](https://aifluency.flyrank.ai/week-08.html#the-plan)  
**Core Principle:** Low-Friction Compounding Engineering Habits Over Heroic Sprints  

---

### The Habit Philosophy

> *“A portfolio that is difficult to update becomes a graveyard within six months. By enforcing the 3-beat case study template (Problem $\rightarrow$ What I Did $\rightarrow$ What Came of It), preserving our Claude Project context file with all design tokens, and naming the exact next project with a calendar cadence, adding a new case study becomes a 20-minute editorial conversation rather than an intimidating full-stack rebuild.”*

---

### 1. Protocol: Where the Next Case Goes & How to Add It

- **Placement on Site:** In `index.html`, under a dedicated `<section id="featured-cases">` placed immediately below the through-line claim and systems architecture card. Each case is rendered as a clean, high-contrast card linking to deep technical notes.
- **The 3-Beat Execution Shape (Reused from Week 2):**

| The Three Beats | Structural Mandate & Word Budget | Engineering Evidence Grounding |
| :--- | :--- | :--- |
| **Beat 1: The Problem**<br>*(60–80 words)* | Name the real commercial or architectural friction. Avoid generic academic preambles; focus on why standard approaches break. | *e.g., Cold-start queries have zero click signals; standard collaborative filtering returns empty candidates, causing 35% search abandonment.* |
| **Beat 2: What I Did**<br>*(100–140 words)* | Detail the engineering intervention with exact tools, loss functions, or pipelines. Emphasize data hygiene and trade-offs. | *e.g., Engineered a Two-Tower ONNX vector retrieval pipeline in DuckDB using HNSW indexing, generating dense query-document embeddings in <15ms.* |
| **Beat 3: What Came of It**<br>*(60–80 words)* | Report empirical metrics, latency deltas, and business outcomes honestly. Include trade-offs or known boundaries. | *e.g., Lifted cold-query recall@20 from 41% to 68%; achieved 14ms p95 latency on CPU; deployed across 12,000 daily catalog queries.* |

---

### 2. The Next Named Project & Scheduled Reminder

#### 2.1 Specific Next Piece Named
> **“Case Study 2: Low-Latency Two-Tower Vector Retrieval with DuckDB VSS for Sub-50ms Cold-Start Query Candidate Generation”**  
> **Scope:** Ingesting 500k product catalog embeddings into DuckDB's Vector Similarity Search (`vss`) extension, benchmarking cosine distance vs dot-product latency on commodity CPU instances, and evaluating candidate recall.

#### 2.2 Concrete Scheduled Reminder Set
- **Calendar Platform:** Google Calendar (Recurring Bi-Weekly Event)
- **Schedule Cadence:** Every second Monday at 10:00 AM (Next trigger: Monday, Oct 26, 2026)
- **Notification Title:** `🔔 Portfolio Habit: Audit Recent Code & Draft Next 3-Beat Case Study`
- **Action Checklist Attached to Event:**
  1. Pull latest Git commits from `FlyRankAI-ML-Internship-Task`.
  2. Capture 1 terminal latency screenshot of DuckDB execution.
  3. Open Claude Project with preserved context to generate 3-beat draft.
  4. Paste into `index.html` and push to Vercel edge.

---

### 3. Preserving the Claude Project Context

To ensure future additions require zero setup overhead, the Claude Project retains our permanent **Engineering Context Document** (`.claude/project_context.md`) with:

| Context Dimension | Preserved Parameter & Rule |
| :--- | :--- |
| **Design Tokens & Palette** | Background: `#FAFAFA` \| Text: `#09090B` \| Accent: `#0284C7` \| Borders: `#E4E4E7`. Fonts: Geist (Headings/Body), JetBrains Mono (Code). |
| **Voice & Tone Guidelines** | Direct, empirical, code-first, and zero fluff. Never use exaggerated marketing buzzwords (*"groundbreaking"*, *"game-changing"*). |
| **The 3-Beat Template** | Enforce strict Problem $\rightarrow$ What I Did $\rightarrow$ What Came of It structure with mandatory before/after metrics. |

---

### 4. Pass / Revise Self-Audit Matrix

| Pass / Revise Criterion | Status | Detailed Verification & Evidence |
| :--- | :---: | :--- |
| **Concrete 'how to add' note, not vague intention.** | **PASS** | Defines exact HTML placement in `index.html` and specifies 3-beat word budgets and structure. |
| **Specific next piece named with a real reminder set.** | **PASS** | Names *"Two-Tower Vector Retrieval with DuckDB VSS"* and documents bi-weekly recurring Google Calendar reminder. |
| **Build context preserved in Claude Project.** | **PASS** | Preserves typography, color hex codes, brand voice rules, and 3-beat prompt templates in project context. |
