# PM-01 — Urban Company
## 03 — Research Plan

**Stage:** SCOPING → RESEARCH
**Purpose:** Define what must be learned, from where, and in what sequence before analysis can begin.
**Last updated:** 2026-09-16

> **Rule:** Do not begin conducting research until this plan is reviewed. Do not answer the research questions here. This file defines the questions and the method.

---

## 1. Research Objective

Surface sufficient evidence to determine:

> Is there a meaningful, evidence-supported user/problem opportunity within Urban Company's trust and repeat-booking experience?

If yes → understand its causes and affected segments
If no → identify what the real problem area might be instead
If unclear → identify what additional evidence would resolve the ambiguity

---

## 2. Research Questions — Organized by Priority

### PRIORITY 1 — What do we need to know first?
(These questions must be answered before hypotheses can be refined)

**RQ-01:** What do customers most commonly complain about on the Urban Company platform, across public review channels?

**RQ-02:** Does trust or service quality consistency appear as a recurring theme in public customer complaints, or is it minor compared to other issues (e.g., pricing, availability, cancellations)?

**RQ-03:** Do customers explicitly mention wanting to rebook the same professional? Is this expressed as a desire, a frustration, or a solved need?

**RQ-04:** What do customers praise about the Urban Company experience? (Establishing where the product works, so we don't redesign a working area.)

**RQ-05:** Which service categories appear most frequently in negative feedback? (Cleaning? AC service? Beauty? Appliance repair?) Does the trust problem apply uniformly or is it category-specific?

---

### PRIORITY 2 — Deeper user understanding
(These questions follow once Priority 1 is answered)

**RQ-06:** Are there identifiable customer segments with meaningfully different experiences? (e.g., first-time bookers vs. repeat users; metro vs. non-metro; high-ticket vs. low-ticket services)

**RQ-07:** What are the behavioral consequences of a bad experience? (Does the customer rebook on Urban Company with a different professional? Stop using the platform entirely? Go back to the unorganized market?)

**RQ-08:** Is there evidence of customers actively trying to work around the platform to maintain a preferred professional relationship (e.g., paying the professional directly, contacting them off-platform)?

**RQ-09:** How significant does the trust/repeat-booking problem appear relative to other customer complaints (pricing, app bugs, cancellation behavior by professionals, late arrivals)?

---

### PRIORITY 3 — Supply-side signals
(Professional experience — harder to find, but critical)

**RQ-10:** Is there publicly accessible evidence of professional-side experience with the platform? (Reddit, Glassdoor, LinkedIn, news articles about gig worker conditions)

**RQ-11:** Do professionals have an incentive to return to the same customers, or does the platform structure work against continuity?

**RQ-12:** Do professionals express concerns about rating mechanisms, job allocation, or customer behavior?

---

### PRIORITY 4 — Competitive and comparative context
(Only after the core user problem is characterized)

**RQ-13:** What do Urban Company's direct or indirect competitors (e.g., Housejoy, BookMyShow Home Services, TaskUs, informal market) do differently in terms of trust and professional continuity?

**RQ-14:** Are there analogous international platforms (e.g., Handy, TaskRabbit, Amazon Home Services) whose approaches to professional continuity are publicly documented?

**RQ-15:** What does the academic or industry literature say about trust in gig economy platforms? (Not required for problem discovery, but useful for solution design later.)

---

## 3. What "Good Evidence" Looks Like

For this problem to be worth developing:

**Signals that SUPPORT the investigation area:**
- Multiple independent users expressing frustration with service inconsistency or inability to rebook specific professionals
- Evidence of behavioral consequences (leaving platform, going direct with professionals)
- Evidence that the problem affects a meaningful segment (not one or two outliers)
- Pattern that repeats across review platforms and forums (triangulation)

**Signals that WOULD WEAKEN or REDIRECT the investigation:**
- Reviews dominated by other issues (pricing, availability, technical bugs) with trust/rebooking as a minor theme
- Evidence that the rebooking feature already works well and users are satisfied
- Evidence that the real problem is pre-booking (trust before a first booking, not repeat booking)
- Evidence that the problem is category-specific and not broad enough for a platform-level feature

---

## 4. Source Plan

| Research Question | Source Type | Specific Source | Priority |
|------------------|-------------|----------------|----------|
| RQ-01 to RQ-05 | Tier C: Community | Google Play Store reviews (Urban Company app) | Highest |
| RQ-01 to RQ-05 | Tier C: Community | Apple App Store reviews (if accessible) | High |
| RQ-01 to RQ-09 | Tier C: Community | Reddit — r/india, r/bangalore, r/mumbai, r/delhi | High |
| RQ-06 to RQ-09 | Tier C: Community | Twitter/X search for Urban Company complaints and praise | Medium |
| RQ-01 to RQ-05 | Tier A: Official | Urban Company website — product features, feature descriptions | High |
| RQ-01 | Tier A: Official | Urban Company Help Centre / Support documentation | Medium |
| RQ-10 to RQ-12 | Tier C: Community | Glassdoor (professional reviews, where available) | Medium |
| RQ-10 to RQ-12 | Tier B: Journalism | News articles about Urban Company professional conditions | Medium |
| RQ-13 to RQ-14 | Tier B/C | Competitor websites, app store reviews of competitors | Lower |
| RQ-15 | Tier A/B: Academic | Published research on trust in gig economy platforms | Lower |

---

## 5. Research Method — Stage 2 Execution Protocol

Follow this sequence:

**Step 1: Product walkthrough**
Before reading any reviews, manually explore the Urban Company product:
- Download/open the app
- Walk through a simulated booking flow
- Identify where trust signals exist (ratings shown, professional photos, badges)
- Identify where repeat booking is or is not surfaced
- Document observations in `02_product_context.md` (update that file)

**Step 2: Review mining — Google Play Store**
- Read a defined sample of reviews (target: 80–100 recent reviews + top-rated reviews + lowest-rated reviews)
- Tag each review with: topic categories, sentiment, service category mentioned, specific friction mentioned
- Record as observations, not conclusions
- Log evidence in `05_evidence_matrix.md`

**Step 3: Reddit research**
- Search for Urban Company on r/india, r/bangalore, r/mumbai, r/delhi, r/hyderabad
- Read threads mentioning Urban Company experience
- Separate posts about pricing, cancellations, quality, trust, rebooking
- Log evidence in `05_evidence_matrix.md`

**Step 4: Professional-side research**
- Search Glassdoor for "Urban Company" reviews from professionals
- Search news sources for coverage of professional working conditions
- Note: this evidence will be sparse — document the absence as a gap

**Step 5: Pattern identification**
- After raw evidence collection is complete, identify recurring themes
- Do NOT identify themes while collecting — finish collection first, then categorize
- Separate: observations → patterns → interpretations

**Step 6: Gap identification**
- Identify what the research could NOT establish
- Identify what would require primary research (interviews) to resolve

---

## 6. What NOT to Do During Research

- Do NOT form a hypothesis before reviewing evidence, then cherry-pick evidence to support it
- Do NOT treat one strong negative review as evidence of a widespread pattern
- Do NOT treat absence of evidence as evidence of absence
- Do NOT interview "Urban Company users" who are actually people you invent
- Do NOT draw competitor conclusions before characterizing the core problem

---

## 7. Research Output Expected

After completing Stage 2, produce:

1. **Source Log** (`04_source_log.md`) — all sources with full metadata
2. **Evidence Matrix** (`05_evidence_matrix.md`) — all evidence entries with labels and classification
3. **Updated Problem Discovery** (`08_problem_discovery.md`) — revised hypotheses based on evidence
4. **Updated Assumption Log** (`06_assumption_log.md`) — which assumptions were confirmed, weakened, or contradicted

---

## 8. Research Time Budget (Approximate)

| Activity | Estimated time |
|----------|---------------|
| Product walkthrough | 30–60 minutes |
| Play Store review mining (80–100 reviews) | 2–3 hours |
| Reddit research | 1–2 hours |
| Professional-side research | 1 hour |
| Evidence tagging and logging | 1–2 hours |
| Pattern identification | 1 hour |
| **Total estimate** | **~8–10 hours** |

---

*Stage: SCOPING — Research plan initialized. Research execution: Stage 2.*
*Last updated: 2026-09-16*
