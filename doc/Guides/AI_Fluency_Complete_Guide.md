# AI Fluency Track — Complete Guide (Assignments + Capstone)

**Track:** General AI Fluency · **Intern:** Md. Fardin Hossain
**Status as of 2026-10-13:** 11 of 26 assignments submitted (waiting for review), **15 remaining**, capstone not started.

### The ground rules (from the portal)
- Every assignment is submitted the same way: **add a public link or upload a file** on the assignment card (PDF, Google Doc link, images — any format).
- Certificate rule: the completion certificate needs **at least 5 assignments + 1 capstone from your main track**. Your main track is ML (already satisfied separately) — so the AI Fluency capstone is **optional for you**, not mandatory. But completing the track is still the best way to get the fluency skills.
- Either of the two capstone options counts.

### Suggested completion order (respects dependencies)
1. **Three Roads** (pick your stack — unblocks the build assignments)
2. **FL-04 Ship an Automation Workflow** (7h — the biggest build; FL-05 explains it later)
3. **FL-05 Agent Concepts and MCP Basics** (write the explainer about your FL-04 pipeline)
4. **PF-04 Personal Website Live** (the site everything else ships on)
5. **Make It Do Something** (one dynamic feature on the site)
6. **Open It on Your Phone** (mobile QA)
7. **Survive the Crit** (⚠️ checkpoint — must pass to proceed to Week 7)
8. **Break Your Own Site** (⚠️ checkpoint — must pass to launch)
9. **Explain It Like You Built It**
10. **FL-06 Design Your Personal Agent** (spec first)
11. **FL-07 Build the Agent** (build second — MVP + build log + 2-min video)
12. **FL-09 Documentation and Demo Video** (README + 3–5 min narrated demo)
13. **Show It / Tell the Story** (final package + retrospective + hours log)
14. **The Plan to Keep Building** (1h — easy closer)
15. **Plant Your Flag: Domain + Badge** (20h — do last, or skip the domain purchase and use a clean free subdomain; the portal confirms any free subdomain qualifies)
16. **Capstone** — pick one of the two options below.

---

## ✅ Already submitted (11) — no action needed

| # | Code | Title | Week |
|---|------|-------|------|
| 1 | FL-01 | AI Workflow Audit and Tool Setup | 1 |
| 2 | — | Draw the Path: Portfolio Sitemap + Toolkit | 1 |
| 3 | — | What Are You Proving? | 1 |
| 4 | — | Frame It as Cases: Work That Speaks for Itself | 2 |
| 5 | — | The Prompt Ladder | 2 |
| 6 | FL-02 | Prompting Fundamentals on Real Tasks v2 | 2 |
| 7 | — | Consistency, Not Talent (and Frame, Not Upstage) | 3 |
| 8 | — | Decide Once: Build Your Identity Kit | 3 |
| 9 | — | Kill your darlings: Curate Your Images | 3 |
| 10 | — | The Through-Line: Map Content & CTAs | 3 |
| 11 | — | Empty but Live: Ship a Blank Page | 4 |

All are "waiting for review" — nothing to do until feedback arrives.

---

## 📋 Remaining assignments — full how-to

### 1. Three Roads: Choose Your Stack with AI — ~2h (Week 4)
**Goal:** pick the tech stack for your site with AI's help, but decide in your own words.

**Steps:**
1. Write down 4 real constraints: (a) free-only hosting, (b) your honest skill level, (c) what the site must do — paste your Week 1 sitemap + Week 3 content map, (d) how your work must be displayed (galleries? embedded demo? code repo? long-form reading?) and whether anything must be dynamic *yet*.
2. Prompt AI for **3 stack options, simplest → most powerful**. For each, get: how you'd build it, free hosting, whether it needs a backend, and the real trade-off. (Typical answers: plain HTML/CSS on Netlify or GitHub Pages → a static site generator like Astro → a framework like Next.js.)
3. Pressure-test the front-runner with 4 questions: what breaks if I go simplest? what do I maintain if I go most powerful? can I finish in 2 weeks? does it display my kind of work properly?
4. Write a short rationale **in your own words**: chosen stack, the two rejected, and why — explicitly covering "can I maintain this?" and "does it show my work well?" Answer the backend question honestly (the right answer for most people is "not yet").

**Deliverable:** the written rationale (Google Doc or PDF), submitted as a link/file on the card.
**Rubric watch-outs:** show 3 genuine options with trade-offs (don't just obey the first answer); chosen stack must be free and matched to your real needs; rationale must be yours, not AI's.

---

### 2. FL-04 — Ship an Automation Workflow v2 — ~7h (Week 4)
**Goal:** build a no-code multi-step AI pipeline, run it 5 times, and document time saved + failure points. This is the biggest build of the track — and FL-05, FL-06, FL-07 all reference it.

**Steps:**
1. Pick one pipeline from your FL-01 audit: a **weekly industry brief**, **source-grounded study notes**, or **draft → critique → revise**.
2. **Sketch the flow first** (before building): 3+ distinct steps with clear handoffs, e.g. gather sources → synthesize → draft → review → format.
3. Build it with no-code tools — mix freely: a Claude Project with structured instructions, NotebookLM, a custom GPT, or n8n.
4. Run it on **5 real inputs** (not test data). Time yourself doing one run manually for comparison.
5. Write down where it breaks and what a human must still check — this honesty is graded.

**Deliverable:** the working workflow + a walkthrough document containing: the step diagram, every prompt/configuration used, the 5 runs with outputs, a time-saved estimate (include setup cost honestly), and known failure points.
**Rubric watch-outs:** it must run end-to-end on a brand-new input; 5 real runs documented; honest time accounting; failure points + required human review named explicitly.

---

### 3. FL-05 — Agent Concepts and MCP Basics — ~5h (Week 4)
**Goal:** learn the workflow-vs-agent distinction, connect one MCP server, and write a 600–900 word explainer.

**Steps:**
1. Read Anthropic's "Building Effective Agents". In **your own words**, write the workflow-vs-agent difference, then classify your FL-04 pipeline (it's a workflow — say why).
2. Read the MCP intro docs. Learn the 3 primitives: **tools, resources, prompts**.
3. Connect **one MCP server or connector** to Claude (any MCP client). Run **3 tasks through it that plain chat couldn't do** — e.g. reading local files, querying a live service. Screenshot each run showing actual tool calls.
4. Write a 600–900 word explainer: what an agent is, what MCP is, and what your FL-04 pipeline would need to become a real agent. Name **one concrete agent upgrade** for the pipeline.

**Deliverable:** the explainer + screenshots of the 3 MCP tasks showing tool use.
**Rubric watch-outs:** technically correct but in your own words; connector demonstrably working (outputs show tool use, not plain chat); the 3 tasks must be things chat alone couldn't do.

---

### 4. PF-04 — Personal Website Live on the FlyRank Domain — ~6h (Week 5)
**Goal:** ship your personal site on a free host over HTTPS, write a DNS walkthrough, and link it from LinkedIn/CV.

**Steps:**
1. Plan a simple site — one page is enough: who you are, what you're building, links to LinkedIn / GitHub / CV / booking, and space for future posts + capstone work.
2. Build on a free host — **Netlify recommended** (free tier, automatic HTTPS); GitHub Pages, Cloudflare Pages, or Vercel hobby tier also fine. Hand-written HTML, a static generator, or AI-assisted build all count — but you must **understand every file you deploy**.
3. Go live over HTTPS on the host's free URL and rename it to a CV-worthy name (e.g. `fardinhossain.netlify.app`). **This URL is the deliverable.**
4. Write a ½–1 page **DNS walkthrough in your own words**: what DNS does, what a CNAME record is, and what happens between typing an address and the host answering (resolver → nameserver → record → response). No custom domain purchase needed.
5. Link the live site from your LinkedIn profile and CV. (The official FlyRank graduate badge gets added later, after capstone approval.)

**Deliverable:** the live HTTPS URL (under Deliverable links on the card) + the DNS walkthrough (link or attached file).
**Rubric watch-outs:** test the URL logged out in a private window; positioning + working LinkedIn/GitHub/CV/booking links; DNS walkthrough technically correct and yours; site linked from LinkedIn and CV.

---

### 5. Make It Do Something — ~4h (Week 6)
**Goal:** wire **exactly one** dynamic feature end to end, and explain the backend in plain words.

**Steps:**
1. Choose the one dynamic feature your portfolio actually needs — a working contact form / email capture is the classic; a small live demo works too. **One, not several.**
2. Wire it end to end on a free tier with AI as your build partner. It must genuinely work — a real test submission must reach you.
3. Write a short plain-words explainer: what a backend is, what your feature does, how the data flows — **in your own words**.

**Deliverable:** the live working feature (evidence: a real test submission that reached you / the working demo) + the explainer.
**Rubric watch-outs:** exactly one feature, working live end to end; explainer correct, yours, and shows you understand the data flow.

---

### 6. Open It on Your Phone — ~4h (Week 6)
**Goal:** a mobile-first QA pass with a real fix log.

**Steps:**
1. Open the portfolio on a **real phone** (not just a resized browser). Fix: text size, spilling/blurry work images, untappable buttons, broken layout. Then check tablet + desktop widths.
2. Readability pass: comfortable text size/line spacing, color contrast, crisp work captures.
3. Click **every** link (including demo/repo links). Compress oversized images. Ask AI to audit a section: "what's broken on mobile, what's the accessibility problem, why is this slow?"
4. Keep a short **fix log**: what was broken → what changed (before/after notes, ideally phone screenshots before and after).

**Deliverable:** updated live URL + fix log.
**Rubric watch-outs:** checked on a real phone; text readable, contrast passes, work images crisp; all links work; no oversized images; fix log shows real problems found and fixed.

---

### 7. Survive the Crit — no hours listed (Week 6) ⚠️ CHECKPOINT
**Goal:** get a real design review against your Week 1 proof statement. **Must pass to proceed to Week 7.**

**Steps:**
1. Send the live portfolio + your Week 1 proof statement to a reviewer (fellow student or friend) so it's judged against its actual job.
2. Ask first: *"in 10 seconds, what do I do — and would you believe I'm good at it?"* Then collect the rest of the feedback **without defending**.
3. Sort feedback into **must-fix** (confusing, broken, hurts the one action, proof doesn't land) vs **nice-to-have** (later).
4. Fix the must-fixes; reply with what changed.

**Deliverable:** the reviewer's feedback + your must-fix/nice-to-have sort + evidence the must-fixes are live on the site.
**Rubric watch-outs:** real feedback received; reviewer could state what you do and felt the work backed it up (or the gaps are now fixed); must-fixes actually fixed; you engaged with feedback instead of defending.

---

### 8. Break Your Own Site — ~2h (Week 7) ⚠️ CHECKPOINT
**Goal:** adversarial self-testing + basic SEO. **Must pass to proceed to launch.**

**Steps:**
1. Try to break it: submit forms empty and with garbage, open the site in an untested browser/device, click everything, submit twice fast. Note what breaks.
2. Findability + speed: add basic **SEO/meta** (page title, description, social-share preview); search your own name/site; run a free speed check.
3. Triage every finding into **fix-now vs known limitation**; fix the fix-nows.
4. Submit for a hardening review (mentor or structured peer); show the "where it breaks" list and your fixes.

**Deliverable:** the honest "where it breaks" list (fixed vs known limitation) + evidence fix-nows are addressed + SEO/meta added.
**Rubric watch-outs:** real edge cases tried, not the happy path; findings triaged honestly; known limitations named, not hidden; hardening review happened and its must-fixes addressed.

---

### 9. Explain It Like You Built It — no hours listed (Week 5)
**Goal:** prove you understand one real piece of your own build.

**Steps:**
1. Pick **one real piece of your build** you found interesting or didn't fully understand — not a generic tutorial topic.
2. Get AI-tutored on it until you genuinely get it.
3. Explain it **in plain words, as if teaching a friend**.

**Deliverable:** the short plain-words explanation (link/file on the card).
**Rubric watch-outs:** a real piece of your build; explanation in your own words and actually correct; demonstrates learning, not pasted output.

---

### 10. FL-06 — Design Your Personal Agent — ~4h (Week 5)
**Goal:** write a 1–2 page agent design spec (this is the design doc for FL-07's build) and justify a build platform.

**Steps:**
1. Choose the agent's **one job** — inbox triager, research scout, study coach grounded in your notes, or weekly review assistant. Open proposals are fine if the build fits ~10 hours.
2. Write the spec (1–2 pages): job to be done; the user (you) + usage frequency; tools/data needed **with a realistic access plan for each**; draft instructions; **5 eval cases defined before building**; risks and guardrails (must-confirm vs must-never-do).
3. Choose a build platform and justify it against at least one alternative: Claude Project with connectors/skills, Claude Cowork (paid), custom GPT (paid), n8n agent workflow, or a scripted agent (free paths exist — pick one you can actually run).
4. Post the spec in the assignment's submission section.

**Deliverable:** the agent design doc.
**Rubric watch-outs:** scope achievable in ~10 build hours; every tool/data source has a realistic access plan; 5+ eval cases defined upfront; guardrails specified for risky/irreversible actions; platform justified against ≥1 alternative.

---

### 11. FL-07 — Build the Agent — ~10h (Week 5)
**Goal:** build the FL-06 agent's MVP (Checkpoint 1): narrowest core job end to end, ≥1 live tool connection, build log, raw 2-min run capture.

**Steps:**
1. Build on your FL-06 platform. Start with the **narrowest core job**; get one full end-to-end run working before adding anything.
2. Connect **≥1 real tool/data source** (MCP server/connector, files, knowledge base, external service).
3. Keep a **build log**: what broke, what changed, what was cut from the spec and why.
4. When the core job works, record **one raw, unedited ~2-minute screen capture** of a successful end-to-end run.

**Deliverable:** the working agent + build log + run capture, posted in submissions.
**Rubric watch-outs:** agent completes the core job end to end without mid-run hand-editing; ≥1 live tool/file/data connection; deviations from the FL-06 spec documented with reasons; build log shows real iteration; video unedited, full loop from request to result.

---

### 12. FL-09 — Documentation and Demo Video — ~5h (Week 8)
**Goal:** document the agent with a README and record a 3–5 min narrated live demo (no slides), uploaded as an unlisted YouTube link.

**Steps:**
1. Write the **README**: what the agent does and for whom; setup steps a stranger could follow; usage examples; a simple architecture sketch; **v2 eval results** (run your FL-06 eval cases); **limitations list**.
2. Record a **3–5 min demo video**: a live end-to-end run with voice narration explaining what the agent is doing and why. **No slide decks** — show the real thing, including one guardrail or limitation explained on camera.
3. Record with OBS Studio, Loom free tier, or any screen recorder; upload as an **unlisted YouTube link**.
4. Post both in submissions.

**Deliverable:** README + demo video link, submitted via the portal.
**Rubric watch-outs:** a stranger could reproduce setup from the README alone; eval results + limitations included; video is a live run (3–5 min) with clear narration; one design decision + one limitation explained on camera.

---

### 13. Show It / Tell the Story — ~60 min (Week 8) ⚠️ FINAL CHECKPOINT
**Goal:** capstone showcase week — documentation/demo (8.1) plus the final package, retrospective, and capstone submission (8.2). **The final review is the documented human sign-off the certificate depends on.**

**Steps:**
1. **Documentation and demo (FL-09):** post your README + demo video to the showcase thread. Include one honest line in the README naming **what was built with AI and how** (transparency diligence).
2. **Final package (FL-10):** assemble everything in one place (GitHub repo or shared folder) with an **index linking every track deliverable**.
3. Write a **500–800 word retrospective for the Week-1-you**: what you set out to do, what changed, what you'd build next, and your **3 most transferable learnings**.
4. Complete the portal **hours log**.
5. Publish the personal site on the FlyRank domain + write **one build-in-public post** telling the story (explain one real decision + one real limitation).
6. Submit for **final review** — a written sign-off or a scheduled review/demo session.

**Deliverable:** submission package + retrospective + completed hours log + live site + post URL.
**Rubric watch-outs:** every deliverable present and reachable from the index; retrospective specific, not generic; hours log complete and plausible; site live and navigable in 5 minutes; build-in-public post explains one real decision + one real limitation.

---

### 14. The Plan to Keep Building — ~1h (Week 8)
**Goal:** set up the habit that keeps the portfolio alive.

**Steps:**
1. Write a few lines on exactly **where the next case study goes** + the steps to add one (reuse the Week 2 three-beat shape: problem → what you did → what came of it).
2. Name the **next real piece of work** you intend to add; set a concrete reminder (calendar nudge, recurring note).
3. **Keep the Claude Project** — it knows your voice, stack, and identity kit, so the next case is a short conversation, not a rebuild.

**Deliverable:** the short "how to add the next case" note + the named next piece + evidence of the reminder set.
**Rubric watch-outs:** concrete "how to add" note, not vague intention; specific next piece named with a real reminder set; build context preserved.

---

### 15. Plant Your Flag: Domain + Badge — ~20h (Week 7)
**Goal:** custom domain, analytics, launch hygiene, FlyRank graduate badge in the footer.

**Steps:**
1. Point a **custom domain** at the site (a personal domain is a small cost; the portal confirms **a clean free subdomain qualifies** if budget is zero — e.g. your Netlify subdomain).
2. Add **free analytics**; confirm fully live over HTTPS on the new address.
3. **Launch hygiene:** social-share preview, favicon, page titles; open the final address on your phone once more.
4. Install the **FlyRank graduate badge** in the footer, linking to the verification page. (The badge arrives after completion certificates are issued — you may submit without it and update later. Badges: https://internship-badge.netlify.app/)

**Deliverable:** live custom-domain URL + screenshot of analytics installed + confirmation that share preview/favicon/titles are correct + badge visible in footer.
**Rubric watch-outs:** live on custom domain (or clean fallback subdomain) over HTTPS; analytics installed and working; share preview, favicon, titles correct on the real address; badge in footer linking to verification page.

---

## 🎓 Capstone — pick ONE of the two (optional for you, since ML is your main track)

### Option A — "General AI Fluency · Impact Project" (~12h, Week 6)
`/intern/assignments/fl-cap`
- **Brief:** "Master the AI stack, build a personal brand with a real website, ship a personal agent." It's a **free-choice capstone** — you choose your own project; attach a brief saying what it is about and its purpose.
- **Requirements:** (1) a few lines on exactly where your next case study goes + steps to add one (Week 2 three-beat shape), (2) name the next real piece of work + set a concrete reminder, (3) keep your Claude Project so future updates are cheap.
- **Deliverable:** the "how to add the next case" note + the named next piece + evidence of the reminder. Submit as **link or file** ("add the link or file reviewers should use for capstone review") — website link and/or a zip of files + report with screenshots are both fine.
- **Rubric:** concrete "how to add the next case" note (not vague intention); specific next piece named with a real reminder set; build context preserved.
- **After submitting:** wait for review — nothing further needed from you.

### Option B — "Send the Link: Launch, Demo & Story" (~4h, Week 8)
`/intern/assignments/CUSTOM-MQX0QS1O-B788D1AA` · tracks: General AI Fluency + Frontend AI Engineering
- Same structure as Option A: portfolio launch + demo + story. Same brief/deliverable/rubric pattern — ship the link, show the demo, tell the story.
- Resource: aifluency.flyrank.ai/week-10.html#send-the-link

**Which to pick:** Option A is the fuller impact project (12h, free choice — best showcase piece). Option B is lighter (4h) if you mainly want the certificate checkbox. Since your ML track already satisfies certification, pick A if you want the strongest portfolio artifact.

---

## ⏱️ Time budget (remaining work)

| Assignment | Hours |
|---|---|
| Three Roads | 2 |
| FL-04 Automation Workflow | 7 |
| FL-05 Agent Concepts + MCP | 5 |
| PF-04 Personal Website | 6 |
| Make It Do Something | 4 |
| Open It on Your Phone | 4 |
| Survive the Crit | — (review cycle) |
| Break Your Own Site | 2 |
| Explain It Like You Built It | — (short) |
| FL-06 Design Your Personal Agent | 4 |
| FL-07 Build the Agent | 10 |
| FL-09 Docs + Demo Video | 5 |
| Show It / Tell the Story | 1 |
| The Plan to Keep Building | 1 |
| Plant Your Flag | 20 (mostly domain/DNS waiting; skippable purchase → ~4h) |
| **Capstone (Option A / B)** | **12 / 4** |
| **Total** | **~83h (≈ 75h without domain purchase)** |

**Submission format for everything:** public link or file upload on the assignment card. When in doubt, a Google Doc link (viewable by anyone with the link) + screenshots is the fastest accepted format.

**Curriculum resources:** aifluency.flyrank.ai/week-01.html through week-10.html — each assignment lists its exact section above.
