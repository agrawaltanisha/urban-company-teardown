# PM-01 — Urban Company
## 07 — Decision Log

**Stage:** SCOPING → (maintained through all stages)
**Purpose:** Record every significant project decision: options considered, trade-offs, rationale, and what would change the decision.
**Last updated:** 2026-09-16

> **Rule:** Per AGENTS.md, every significant decision must be logged here. Record the reasoning path, not just the final answer. Revisit past decisions when new evidence emerges.

---

## Decision Entry Format

| Field | Content |
|-------|---------|
| Decision ID | D001, D002... |
| Decision | What was decided |
| Stage | When this decision was made |
| Options considered | What alternatives were available |
| Evidence used | What information informed the decision |
| Rationale | Why this option was chosen |
| Trade-offs | What was given up by making this choice |
| What would change this decision | What new evidence or situation would cause a reversal |
| Status | Active / Superseded / Retired |

---

## Decisions at Initialization

---

### D001 — Approved investigation area: Trust and repeat booking

**Decision:** Accept "trust and repeat booking" as the initial investigation area for PM-01.

**Stage:** SCOPING

**Options considered:**
1. Trust and repeat booking (selected)
2. Professional quality control and vetting
3. Pricing transparency and value perception
4. Onboarding and first-time booking experience
5. Post-service resolution and complaints handling

**Evidence used:**
- Approved portfolio architecture (`apm-portfolio-architecture.md`) which explicitly selected this area
- Architecture document's rationale: "abundant public evidence; genuinely two-sided dynamics; repeat bookings drop when customers get a bad or inconsistent professional"
- Public domain knowledge that home services are inherently trust-sensitive

**Rationale:**
This was an architect-level decision made before project initialization. The portfolio architecture document justified it on three grounds: evidence availability, strategic richness (two-sided dynamics), and PM skill demonstration value (marketplace trade-offs). This decision is accepted as the starting point but does not commit to "trust and repeat booking" as the validated problem — only as the area to investigate.

**Trade-offs:**
- By starting here, we are not starting with price transparency, onboarding, or post-service recovery — these may turn out to be bigger problems
- The investigation may discover that trust/repeat booking is a secondary concern, which would require redirection

**What would change this decision:**
- Research showing that trust/repeat booking receives minimal mention in user feedback, while another area (e.g., cancellation behavior, pricing surprises) dominates
- Evidence that the problem is exclusively supply-side and not addressable through product UX

**Status:** Superseded by D004 (Historical context preserved: original scoping area redirected to Pricing Transparency / Cancellation Fairness with initial focus on post-booking price predictability)

---

### D002 — Project type: Teardown + UX Redesign + PRD (three downstream artifacts)

**Decision:** PM-01 will produce three artifacts: Product Teardown, UX Redesign, and PRD. These are all downstream from Stage 1–4.

**Stage:** SCOPING

**Options considered:**
1. Teardown only (simpler, lower investment)
2. Teardown + PRD (skip UX)
3. Teardown + UX Redesign + PRD (selected — per portfolio architecture)

**Evidence used:**
- Portfolio architecture document (`apm-portfolio-architecture.md`) which specified all three artifacts for Project 1

**Rationale:**
The portfolio architecture deliberately designed Project 1 to cover the most PM skills in one project. Producing all three artifacts demonstrates the full spectrum from problem discovery through UX thinking to engineering-facing requirements. This was a deliberate portfolio strategy decision.

**Trade-offs:**
- Significantly more work than a single artifact
- All three artifacts depend on the quality of the problem discovery stage — a weak problem definition will cascade into weak UX and PRD

**What would change this decision:**
- If problem discovery reveals the problem is not suited for a UX redesign (e.g., it's primarily a back-end/algorithm problem)
- If time constraints require scoping down

**Status:** Active

---

### D003 — Evidence policy: No fabricated data at any stage

**Decision:** This project will not use any fabricated user interviews, invented metrics, or constructed quotes. All evidence must be real and cited.

**Stage:** SCOPING

**Options considered:**
1. Use fabricated/representative examples clearly labelled as synthetic (partially acceptable per EVIDENCE_POLICY.md)
2. Only use real, citable evidence — and explicitly label gaps where evidence is unavailable (selected)

**Evidence used:**
- AGENTS.md No-Fabrication Policy (mandatory and non-negotiable)
- EVIDENCE_POLICY.md
- Portfolio architecture document's rationale: "hiring managers will probe until the story breaks"

**Rationale:**
The workspace system explicitly prohibits fabrication. Beyond policy, the strategic rationale is interview credibility — any fabricated claim that is exposed under questioning destroys the project's value. Genuine evidence gaps, honestly acknowledged, are more defensible than plausible-sounding fictions.

**Trade-offs:**
- Evidence constraints may mean some questions cannot be answered
- The analysis may be less "complete-sounding" but will be more defensible

**What would change this decision:**
- Nothing. This is a non-negotiable policy.

**Status:** Active — permanent

---

---

## D004 — Decision Brief (Pre-Gate 2 Options Evaluation)

**Status:** EVALUATED & DECIDED (Final decision formally recorded in D004 below)  
**Decision Question:** What should the next investigation phase primarily focus on, given the evidence collected so far?  
**Stage:** Gate 1 → Gate 2 Transition (Phase 1 Closure)  

> **Governance Notice:** Per PM portfolio governance and the non-negotiable workflow rules, this Decision Brief evaluated five potential strategic directions using strictly audited evidence from Tasks 1–4. The human project owner has made the final strategic choice D004 recorded below.

---

### Option 1: Continue Trust and Repeat Booking — NOT SELECTED

* **Status:** NOT SELECTED by Human Decision D004
* **Reason for Non-Selection:** The evidence shows a genuine continuity signal (`E018`, `E019`), but observed prevalence is small ($3.4\%$ overall, $n=6/179$; $5.9\%$ negative, $n=3/51$) and the actual UX discoverability mechanism (`A003`) remains unvalidated.
* **Core Strategic Focus:** Investigates whether customers experience friction in discovering, selecting, and retaining preferred service professionals, and tests whether relationship continuity affects repeat booking behavior.
* **A. Supporting Evidence:**
  * `E008`: Trust and security themes appear in $7.8\%$ ($n=14/179$) overall and $15.7\%$ ($n=8/51$) of negative reviews, highlighting acute in-home vulnerability.
  * `E009`: Repeat booking and continuity appear in $3.4\%$ ($n=6/179$) of reviews, capturing package failures on rebooking (`R0073`), repeated platform cancellations on rebooking (`R0101`), and booking loops (`R0176`).
  * `E018`: $n=7/179$ reviews ($50.0\%$ of rebooking cohort, $n=7/14$) explicitly articulate a preference for familiar professionals and voice frustration when unfamiliar personnel are reassigned (`R0179`).
  * `E019`: $n=7/179$ reviews ($14.6\%$ of 4-star reviews, $n=7/48$) show customers explicitly bifurcating evaluation, praising the individual worker while criticizing platform policies or docking ratings (`R0074`, `R0092`, `R0093`).
* **B. Contradictory Evidence:**
  * Low relative complaint volume: Explicit rebooking friction appears in only $3.4\%$ ($n=6/179$) of all reviews and $5.9\%$ ($n=3/51$) of negative reviews (`E009`).
  * Dissatisfaction is heavily dominated by operational failure modes: Pricing transparency ($25.7\%$, `E004`), cancellation cascades ($14.5\%$, `E005`), and automated support deflection ($21.6\%$ of negative reviews, `E011`).
  * Fungible supply acceptance: Reviewers like `R0013` book across multiple categories without expressing worker-specific preference as long as execution standards are met.
* **C. Evidence IDs:** `E008`, `E009`, `E018`, `E019`; counter-evidence `E004`, `E005`, `E006`, `E011`.
* **D. Relevant Review IDs:** Repeat-booking friction: `R0073`, `R0074`, `R0101`, `R0176`, `R0179`; Positive counter-context: `R0017`, `R0033`, `R0059` (customers reporting multi-year satisfaction across regular bookings); Fungible supply counter-evidence: `R0013`.
* **E. Sample Sizes / Denominators:** $n=6/179$ ($3.4\%$) rebooking theme; $n=7/179$ ($3.9\%$ of total sample, $50.0\%$ of $n=14$ cohort) rebooking preference (`E018`); $n=7/48$ ($14.6\%$) in 4-star cohort (`E019`).
* **F. What Is Established:** A distinct subset of customers actively seeks relationship continuity with familiar technicians and experiences friction when the platform reassigns workers.
* **G. What Remains Hypothetical:** That the mobile app UI/UX is the causal bottleneck preventing repeat booking, and that repeat-booking friction causes platform-level churn.
* **H. Missing Evidence:** Hands-on app walkthrough data; rebooking discoverability telemetry; platform repeat booking rates; category-level continuity demand.
* **I. What Phase 2 Research Would Test:** Task 6 hands-on walkthrough of live app rebooking flows, order history screens, and "Book Again" entry points; Task 8 marketplace retention benchmarks.
* **J. Risks of Prematurely Pursuing Direction:** Building a solution for a narrow edge case while ignoring the primary volume drivers of customer dissatisfaction (pricing surprises and support failures).

---

### Option 2: Pivot to Post-Service Support and Recovery — NOT SELECTED

* **Status:** NOT SELECTED by Human Decision D004
* **Reason for Non-Selection:** Support/recovery evidence is meaningful ($21.6\%$ negative reviews, `E011`), but it may be downstream of upstream operational failures (pricing errors, cancellations, or repair damages) and requires additional root-cause clarification.
* **Core Strategic Focus:** Investigates whether post-service dispute resolution failures and automated AI chatbot deflection loops prevent timely escalation and negatively influence repeat customer trust.
* **A. Supporting Evidence:**
  * `E011`: Automated support deflection and lack of telephone escalation appear in $6.1\%$ ($n=11/179$) of all reviews and $21.6\%$ ($n=11/51$) of negative reviews.
  * `E006`: App/UX friction accounts for $31.4\%$ ($n=16/51$) of negative reviews, heavily dominated by repetitive AI chatbot loops (e.g., `R0071`, `R0108`, `R0117`, `R0158`) and missing telephone helpline access (e.g., `R0059`, `R0118`, `R0170`).
  * `E016`: Severe secondary appliance breakdown and collateral damage ($n=6/179$, $11.8\%$ of quality reviews, $n=6/51$) where customers are denied warranty claims or trapped in unhelpful chatbot trees (`R0079`, `R0111`, `R0118`, `R0127`, `R0160`, `R0166`).
* **B. Contradictory Evidence:**
  * Fast, responsive resolution praise exists in the sample: `R0048` praises rapid technician dispatch and remote audit; `R0028` notes swift customer service.
  * Support complaints are inherently reactive: users contact support only after an operational breakdown (pricing error, cancellation, defective repair) has already occurred. Support deflection amplifies dissatisfaction but is not the originating operational failure.
* **C. Evidence IDs:** `E006`, `E011`, `E016`; counter-evidence `R0028`, `R0048`.
* **D. Relevant Review IDs:** Support loop / helpline friction: `R0059`, `R0071`, `R0108`, `R0117`, `R0118`, `R0158`, `R0170`; Secondary damage disputes: `R0079`, `R0111`, `R0127`, `R0160`, `R0166`; Positive resolution counter-evidence: `R0028`, `R0048`.
* **E. Sample Sizes / Denominators:** $n=11/51$ ($21.6\%$) of negative reviews (`E011`); $n=16/51$ ($31.4\%$) of negative reviews citing UX/support friction (`E006`); $n=6/51$ ($11.8\%$) of quality reviews citing severe damage (`E016`).
* **F. What Is Established:** Urban Company's automated AI support bot creates acute customer frustration and blocks escalation when physical service damage or financial disputes occur.
* **G. What Remains Hypothetical:** Whether solving support deflection alone restores customer retention if the underlying physical service defects or cancellation failures continue.
* **H. Missing Evidence:** Internal customer support metrics (ticket volume, first-contact resolution rates, chatbot containment rates, refund payout ratios); warranty claim volume.
* **I. What Phase 2 Research Would Test:** Task 6 audit of in-app Help Center and escalation architecture; Task 8 industry benchmarks on post-service recovery impact on LTV.
* **J. Risks of Prematurely Pursuing Direction:** May address symptoms rather than the root causes of service failures; requires substantial operational and human agent cost modeling.

---

### Option 3: Pivot to Insta Help Reliability — NOT SELECTED

* **Status:** NOT SELECTED by Human Decision D004
* **Reason for Non-Selection:** The vertical-specific operational breakdown is severe and mechanistically clear ($42.3\%$ cancellation mention in vertical, `E013`), but the project's evidence cannot establish platform-wide business scale ($14.5\%$ of sample).
* **Core Strategic Focus:** Investigates whether severe supply fragility, cancellations, and partner no-shows in on-demand daily chores (Insta Help) degrade user trust in that vertical. (Note: Insta Help presents a severe vertical-specific operational breakdown in the sampled reviews, but is not ranked against other Urban Company categories).
* **A. Supporting Evidence:**
  * `E005`: Cancellations appear in $14.5\%$ ($n=26/179$) of all reviews and $37.3\%$ ($n=19/51$) of negative reviews, with $42.3\%$ ($n=11/26$) concentrated in Insta Help.
  * `E013`: $n=11/26$ ($42.3\%$) of sampled Insta Help reviews document severe partner no-shows, repeated cancellations, and helper refusals upon arrival (`R0108`, `R0126`, `R0176`).
  * `E012`: Customers report asymmetric ₹50 cancellation penalties even when platform delivery or dispatch fails (`R0145`).
* **B. Contradictory Evidence:**
  * Vertical-specific boundary: Insta Help represents only $14.5\%$ ($n=26/179$) of the total review sample.
  * Cancellations are non-existent or rare in scheduled complex verticals (e.g., Home Cleaning $n=0/16$ cancellations in sample).
  * Positive Insta Help reviews exist (`R0076`, `R0152`), showing successful maid dispatch and clean execution.
* **C. Evidence IDs:** `E005`, `E012`, `E013`; counter-evidence `R0076`, `R0152`.
* **D. Relevant Review IDs:** `R0108`, `R0126`, `R0134`, `R0145`, `R0176`, `R0179`; counter: `R0076`, `R0152`.
* **E. Sample Sizes / Denominators:** $n=11/26$ ($42.3\%$) of sampled Insta Help reviews mention cancellations/no-shows (`E013`); represents $11/26$ ($42.3\%$) of all sample cancellation mentions.
* **F. What Is Established:** On-demand daily domestic chores suffer severe operational matching fragility under short lead times in the sampled reviews, leading to acute customer dissatisfaction.
* **G. What Remains Hypothetical:** Whether Insta Help reliability failures are associated with reduced activity in core scheduled verticals (Salon, Appliance Repair). (Note: scheduled verticals have their own documented friction points, such as cancellation mentions in Appliance Repair, and cannot be presumed to be unaffected).
* **H. Missing Evidence:** Insta Help GMV share; platform-wide fulfillment and cancellation rates across verticals; partner supply density in on-demand chores.
* **I. What Phase 2 Research Would Test:** Task 6 audit of Insta Help booking and cancellation UX; Task 7 unit economics of low-ticket on-demand services; Task 8 on-demand dispatch models.
* **J. Risks of Prematurely Pursuing Direction:** Narrowing the entire project to a single experimental vertical that may represent a small fraction of Urban Company's enterprise revenue.

---

### Option 4: Pivot to Pricing Transparency / Cancellation Fairness — SELECTED

* **Status:** SELECTED by Human Decision D004 (Initial focus narrowed to Post-Booking Price Predictability and Transparency)
* **Reason for Selection:** Higher observed prevalence, concrete post-booking pricing mechanisms, clear customer-facing friction, and a directly observable product surface. The investigation will initially emphasize price predictability/transparency rather than assuming that pricing level or monetization policy itself is the problem.
* **Core Strategic Focus:** Investigates whether post-booking monetization friction, fee stacking (platform fees, weekend surge), and asymmetric cancellation fines prompt user dissatisfaction or defection.
* **A. Supporting Evidence:**
  * `E004`: Pricing transparency and unexpected surcharges appear in $25.7\%$ ($n=46/179$ pricing-themed reviews in the full sample) and $37.3\%$ ($n=19/51$ negative reviews mentioning pricing) — note that $25.7\%$ uses the full sample denominator of 179, while $37.3\%$ uses the negative review cohort denominator of 51.
  * `E014`: $n=13/46$ pricing reviews ($28.3\%$ of pricing cohort) document post-booking price inflation: automated weekend surge (₹150–₹200), platform convenience fees (₹166), and technician add-on demands (`R0058`, `R0090`, `R0092`).
  * `E012`: $n=5$ explicit complaints regarding asymmetric ₹50 cancellation penalties imposed on customers even when platform technicians arrive late or fail to show up (`R0058`, `R0092`, `R0145`).
* **B. Contradictory Evidence:**
  * Strong positive pricing sentiment: multiple 5-star reviews specifically praise transparent pricing, competitive rates, and fair billing with zero unexpected add-ons (`R0001`, `R0008`, `R0033`, `R0035`).
  * Platform fees and surge pricing may represent monetization mechanisms; their contribution to take-rate, margin, and revenue is unverified in this project.
* **C. Evidence IDs:** `E004`, `E012`, `E014`; counter-evidence `R0001`, `R0008`, `R0033`, `R0035`.
* **D. Relevant Review IDs:** `R0058`, `R0070`, `R0090`, `R0092`, `R0113`, `R0145`, `R0163`; counter: `R0001`, `R0008`, `R0033`, `R0035`.
* **E. Sample Sizes / Denominators:** Full sample base: $n=46/179$ ($25.7\%$); Negative review cohort base: $n=19/51$ ($37.3\%$); Fee stacking subset within pricing cohort: $n=13/46$ ($28.3\%$ in `E014`); Asymmetric cancellation penalty mentions: $n=5$ in `E012`.
* **F. What Is Established:** Checkout fee stacking and unexpected add-ons generate acute feeling of "bait-and-switch" and prompt stated switching threats to local mechanics (`PAT-10`).
* **G. What Remains Hypothetical:** The price elasticity of demand across categories, and whether fee transparency would decrease total platform revenue despite improving customer satisfaction.
* **H. Missing Evidence:** Urban Company take-rate schedules; fee elasticity curves; contribution of convenience fees to EBITDA; partner fee-sharing percentages.
* **I. What Phase 2 Research Would Test:** Task 7 financial teardown of take-rates, platform fees, and surge algorithms; Task 8 secondary pricing benchmarking against competitors.
* **J. Risks of Prematurely Pursuing Direction:** Proposing fee changes without verifying fee revenue contribution, marketplace take-rate impact, or customer price sensitivity, which risks focusing on pricing mechanics without resolving underlying service delivery issues.

---

### Option 5: Synthesize to Post-Booking Reliability Problem — NOT SELECTED

* **Status:** NOT SELECTED by Human Decision D004
* **Reason for Non-Selection:** The synthesis is currently too broad and lacks evidence of a common causal mechanism across quality, pricing, cancellation, and support.
* **Core Strategic Focus:** Investigates the synthesis hypothesis that repeat platform usage may be discouraged by cumulative post-booking friction across quality, pricing, cancellation, and support in trust-sensitive categories.
* **A. Supporting Evidence:**
  * Co-occurrence of top failure modes in negative reviews: pricing surcharges ($37.3\%$ negative, `E004`), cancellations ($37.3\%$ negative, `E005`), support deflection ($21.6\%$ negative, `E011`), and quality defects ($28.5\%$, `E003`).
  * `H4 Two-Stage Trust Model`: Post-booking domestic sanctuary trust failures occur inside the customer's private home (`E008`, `E015`, `E016`).
  * `E019`: Customers decouple partner loyalty from platform dissatisfaction ($n=7/48$ 4-star reviews), demonstrating that trust in the human worker survives while platform reliability collapses.
* **B. Contradictory Evidence:**
  * Multi-faceted scope: combining post-booking failures across quality, pricing, and support increases analytical complexity compared to a focused single-variable problem.
  * Different verticals have distinct failure mechanisms (Appliance Repair suffers collateral damage `E016`, while Insta Help suffers cancellation cascades `E013`).
* **C. Evidence IDs:** `E003`, `E004`, `E005`, `E008`, `E011`, `E015`, `E016`, `E018`, `E019`.
* **D. Relevant Review IDs:** `R0074`, `R0079`, `R0092`, `R0108`, `R0109`, `R0111`, `R0117`, `R0143`, `R0160`, `R0179`.
* **E. Sample Sizes / Denominators:** Bridges the high-prevalence negative themes across the full $n=51$ negative review cohort and $n=48$ 4-star review cohort.
* **F. What Is Established:** The review evidence establishes several co-occurring failure modes across pricing, cancellations, support, and quality in the sample, but does not demonstrate a common causal mechanism.
* **G. What Remains Hypothetical:** This option investigates whether cumulative post-booking friction across multiple touchpoints degrades platform-level trust and repeat booking. The evidence establishes several co-occurring failure modes but does not demonstrate a common causal mechanism. It remains unproven whether these co-occurring failures share a single root cause, cumulatively harm retention, or can be addressed through a unified product/UX intervention.
* **H. Missing Evidence:** Multi-booking cohort retention curves; relative churn attribution across failure types; service guarantee revisit data.
* **I. What Phase 2 Research Would Test:** Cross-functional triangulation across Task 6 (walkthrough of post-service & dispute flows), Task 7 (take-rate & fee structure), and Task 8 (marketplace quality guarantees).
* **J. Risks of Prematurely Pursuing Direction:** Risk of creating an overly broad or unfocused problem statement that attempts to solve all operational defects at once.

---

## D004 — Core Problem Direction Decision

### Decision
**Option 4 — Pricing Transparency / Cancellation Fairness**

### Narrowed Investigation Focus
**Post-booking price predictability and transparency.**

**Working Investigation Frame:**
> *"Investigate whether customers lose confidence when post-booking prices or cancellation consequences differ materially from what they reasonably expected at booking."*

*(Important: This is an active working investigation direction, NOT yet a final validated problem statement and NOT yet a solution).*

### Decision Owner
**HUMAN — project owner.**

### Stage
Gate 1 → Gate 2 Transition (Phase 1 Closure / Entry into Phase 2 Research)

### Evidence Basis
The decision is grounded directly in the audited review-mining evidence:
1. **High Negative Review Prevalence (`E004`):** Pricing transparency and unexpected surcharges represent one of the two co-dominant complaint themes in the audited review sample:
   - Present in $25.7\%$ of the full sample ($n=46/179$ reviews).
   - Present in $37.3\%$ of negative reviews ($n=19/51$ negative reviews).
2. **Specific Post-Booking Pricing Mechanisms (`E014`):** Within the pricing-themed cohort, $28.3\%$ ($n=13/46$ reviews) cite concrete post-booking mechanisms rather than general complaints:
   - Automated post-booking fee stacking (platform convenience fees, e.g., ₹166 in `R0070`).
   - Surcharges added after slot selection (weekend/peak surge fees of ₹150–₹200, e.g., `R0058`, `R0090`, `R0092`).
   - On-site technician add-on demands and unexpected parts billing (`R0113`, `R0163`).
3. **Asymmetric Cancellation Penalties (`E012`):** $n=5$ reviews (`R0058`, `R0092`, `R0145`) document customers being penalized with ₹50 cancellation fines even when platform technicians arrive late or fail to show up, compounding perceived financial unfairness.
4. **Stated Comparison & Defection Friction (`PAT-10`):** $n=4$ reviews (`R0058`, `R0070`, `R0092`, `R0163`) articulate customer friction comparing Urban Company's stacked pricing against local offline alternatives (e.g., local mechanics), explicitly stating intentions to switch or avoid rebooking. *(Note: While PAT-10 captures stated defection threats, it does NOT establish verified aggregate customer defection or platform-level churn).*
5. **Positive Pricing Counter-Evidence:** Multiple 5-star reviews specifically praise transparent rates, fair billing, and absence of unexpected add-ons:
   - `R0001` (Salon: transparent pricing and professional service).
   - `R0008` (Appliance: clear upfront quotation without extra charges).
   - `R0033` (Multi-year customer: consistent fair pricing).
   - `R0035` (Cleaning: upfront estimate matched final invoice).  
   *Implication:* This counter-evidence demonstrates that the customer problem is not that "Urban Company pricing is bad" or that baseline rates are too high, but that pricing predictability and expectations break down post-booking under specific conditions.

### Evidence Boundary
The review-mining data and qualitative evidence do **NOT** establish:
- Aggregate platform churn or user retention curves.
- Price elasticity of demand across service categories.
- Urban Company take-rates or fee schedules.
- Gross margin or EBITDA contribution of convenience/platform fees.
- Percentage of platform revenue derived from surge or convenience fees.
- Partner fee-sharing economics or split of add-on services.  
These remain unobserved internal operational and economic variables and are explicitly recorded as research gaps to be investigated during Phase 2 (Tasks 6–8) and Phase 3 (Opportunity Analysis).

### Why This Direction Was Selected
1. **Substantial Observed Prevalence:** Unlike rebooking UX friction ($3.4\%$ overall, $5.9\%$ negative), pricing friction is co-dominant across negative reviews ($37.3\%$).
2. **Observable and Controllable Product Surface:** Narrowing toward *post-booking price predictability and transparency* gives the project an observable, product-addressable interaction surface (booking disclosure, checkout breakdown, post-booking confirmation, add-on approval flows) without making unsupported claims that the underlying commercial pricing model or monetization strategy is flawed.
3. **Clear Customer-Facing Mechanism:** Post-booking fee stacking (`E014`) and asymmetric penalties (`E012`) present an identifiable breakdown in customer trust where expectations set at booking differ from the reality at payment.
4. **Strict Demarcation Between Problem and Solution:** Selecting this direction does **NOT** mean deciding to "reduce prices," "eliminate fees," "waive cancellation penalties," or build a specific UI widget. It establishes a disciplined working investigation frame to discover *how and why* expectations diverge before evaluating any product solutions.

### Why Other Options Were Not Selected
- **Option 1 (Trust and Repeat Booking) — NOT SELECTED:** The evidence shows a genuine continuity signal (`E018`, `E019`), but observed complaint prevalence in reviews is small ($3.4\%$ overall, $n=6/179$; $5.9\%$ negative, $n=3/51$), and the hypothesized UX discoverability mechanism (`A003`) remains completely unvalidated.
- **Option 2 (Post-Service Support & Recovery) — NOT SELECTED:** While support deflection (`E011`, $21.6\%$ of negative reviews) and chatbot friction (`E006`) are substantial, support complaints are inherently reactive to upstream operational defects (pricing errors, cancellations, or damages). Pursuing support in isolation risks focusing on downstream symptom mitigation without resolving the initiating triggers, and requires internal support ticket data not yet available.
- **Option 3 (Insta Help Reliability) — NOT SELECTED:** Although the supply fragility and cancellation breakdown in on-demand chores is acute ($42.3\%$ cancellation mention within vertical, `E013`), Insta Help represents an experimental or vertical-specific segment ($14.5\%$ of sample) and the current evidence cannot establish platform-wide business scale or GMV significance.
- **Option 5 (Post-Booking Reliability Synthesis) — NOT SELECTED:** Synthesizing quality defects, cancellations, pricing surcharges, and support deflection into a single overarching hypothesis is conceptually appealing, but currently too broad. The available evidence does not establish a shared causal mechanism across disparate service verticals, risking an unwieldy and unfocused investigation.

### Scope Boundary (What This Decision Is and Is NOT)
- **What it IS:** A disciplined working investigation frame: *"Investigate whether customers lose confidence when post-booking prices or cancellation consequences differ materially from what they reasonably expected at booking."*
- **What it is NOT:**
  - It is NOT a validated final customer problem statement.
  - It is NOT a decision that "Urban Company is deceiving customers" or that "fees are excessive."
  - It is NOT a claim that pricing causes verified churn or retention decline.
  - It is NOT a solution commitment (no PRD, no UX wireframes, no fee waivers, no price locks, no cancellation redesigns).
  - The project remains strictly in discovery / research completion.

### Reversal Conditions
D004 will be formally re-evaluated and reconsidered if future evidence demonstrates any of the following:
1. **Product Walkthrough Triangulation (Task 6):** First-hand inspection of the live Urban Company mobile app reveals that fee breakdowns, surge pricing, and cancellation policies are already clearly, predictably, and prominently disclosed throughout the booking flow.
2. **Category-Specific Isolation:** External research or industry benchmarking indicates that pricing surprises are confined strictly to one narrow niche category (e.g., legacy water purifier repairs) rather than representing a broader platform dynamics issue.
3. **Dominance of Cancellation Mechanics:** Deeper investigation reveals that cancellation fairness / partner fulfillment failure is the true causal driver of customer defection, with pricing complaints merely serving as an incidental secondary reaction.
4. **Fulfillment Root Cause:** Operational evidence demonstrates that customer dissatisfaction stems overwhelmingly from service fulfillment quality and partner skill variance rather than pricing disclosure.
5. **Primary Research Contradiction:** Primary user research or independent customer interviews directly contradict the review-mining interpretation and show that pricing predictability is not a meaningful factor in platform trust or repeat booking decisions.

*(Note: No arbitrary numerical thresholds or fabricated quantitative targets are assumed).*

### Status
**Active** — Decided by HUMAN (Project Owner). Governs Phase 2 research.

---

## D005 — Problem Definition Selection: Post-Diagnostic Price Uncertainty

### Decision
**Candidate 2 Selected — Post-Diagnostic Price Uncertainty**

### Canonical Problem Statement
> **"For customers booking diagnosis-dependent home services, the final cost can become uncertain after booking because the exact scope of work is determined only after on-site inspection, while the diagnostic/visitation cost and subsequent repair quote affect the customer's ability to confidently decide whether to proceed."**

### Decision Owner
**HUMAN — project owner.**

### Final Problem Direction
**Post-Diagnostic Price Uncertainty**

### Stage
Phase 3: Analysis & Synthesis (Task 9 — Problem Definition)

### Options Considered
1. **Candidate 1: Booking-Stage Price Transparency / Payment Amount Mismatch** — Focuses exclusively on checkout/payment gateway price inflation (`E022`).
2. **Candidate 2: Post-Diagnostic Price Uncertainty (SELECTED)** — Focuses on the quoting inflection point for diagnosis-dependent services where scope is discovered on-site.
3. **Candidate 3: Asymmetric Cancellation Penalties** — Focuses on cancellation fees within the 24-hour window (`E012`, `E046a`).
4. **Candidate 4: Broad Post-Booking Price & Cancellation Predictability (Synthesis)** — Aggregates Candidates 1, 2, and 3 under an omnibus predictability umbrella.

### Evidence Basis
* **Primary Evidence Chain:**
  - `E014`: Post-booking price inflation and add-on complaints in reviews ($28.3\%$ of pricing cohort, $n=13/46$).
  - `E024`: In-app quote verification policy requiring partners to generate in-app quotes for additional work.
  - `E025`: Extra-charge policy guidance establishing on-site discovery of spare parts as recognized platform workflow.
  - `E026`: Gas-refill quoting and customer approval workflow requiring explicit in-app confirmation before execution.
  - `E040`: Granular rate-card pricing architecture for spare parts and diagnostic steps.
  - `E041`: Visitation and diagnostic fee mechanism charged if customer declines repair post-inspection.
  - `E042`: High-value consultation and staged quote approval structure.
* **Supporting Context (With Strict Methodological Separation):**
  - `E004`: Pricing-theme prevalence across reviews ($25.7\%$ overall, $37.3\%$ negative).
  - `E022`: Separate booking-stage amount discrepancy (₹99 mismatch at payment).  
    *Important Rule:* `E022` must remain a separate phenomenon and must **NOT** be used as direct evidence of post-diagnostic pricing.

### Problem Boundary
* **IN SCOPE:**
  - Diagnosis-dependent home services
  - On-site inspection
  - Diagnostic / visitation fees
  - Post-diagnostic repair quotations
  - Additional work discovered after booking
  - Customer accept/reject decision after diagnosis
  - Price predictability across this journey
  - Clarity of quote / approval mechanisms
* **OUT OF SCOPE:**
  - General Urban Company pricing complaints
  - All cancellation problems
  - General service quality
  - General customer support
  - General platform trust
  - Rebooking
  - The ₹99 booking/payment amount discrepancy as the primary problem
  - Retention/churn as an established outcome
  - Any claim that fees are intentionally hidden
  - Any claim of customer "lock-in"

### What Remains Explicitly Unproven
1. Frequency of post-diagnostic quote escalation.
2. Frequency of customers rejecting quotes.
3. Magnitude of price increases after diagnosis.
4. Whether customers perceive the diagnostic fee as unfair.
5. Whether this problem materially reduces conversion.
6. Whether this problem materially reduces repeat booking or retention.
7. Whether the dominant issue is UX, policy, or unavoidable service-scope uncertainty.
8. Whether this problem is equally important across all diagnosis-dependent categories.

### Rationale
Candidate 2 captures an authentic operational tension inherent to on-demand physical services: the transition from digital fixed-price expectation to physical on-site diagnostic reality. It targets an addressable product and workflow surface (quoting, approval, parts transparency, visitation fee dynamics) without diffusing focus into macro cancellation policies or speculative platform churn claims. It cleanly isolates checkout UI bugs (`E022`) from genuine post-booking scope uncertainty.

### Trade-offs
- Deliberately leaves cancellation friction and general fee stacking out of primary scope.
- Requires designing within physical operational constraints (technicians must physically open appliances to know what is broken).

### Reversal Conditions
- Quantitative data demonstrating that post-diagnostic quote escalation occurs in $<2\%$ of diagnosis-dependent bookings.
- Operational evidence indicating customer quote rejection rate is negligible and creates zero friction or offline disintermediation.
- Platform evidence showing that cancellation penalties or partner no-shows represent overwhelmingly greater customer friction.

### Status
**Active** — Decided by HUMAN (Project Owner). Governs Task 10 (Behavioral User Segmentation) and downstream product definition.

---

## D006 — Primary Segment Selection: First-Time Diagnosis-Dependent Bookers

### Decision
* **Primary Target Segment:** **Segment 1 — First-Time Diagnosis-Dependent Bookers**
* **Secondary Business-Risk Segment:** **Segment 3 — Price-Sensitive Quote Evaluators**

### Decision Owner
**HUMAN — project owner.**

### Stage
Phase 3: Analysis & Synthesis (Task 10 — Behavioral User Segmentation)

### Human Decision Rationale
> *"I selected first-time diagnosis-dependent customers because post-diagnostic price uncertainty occurs at the earliest stage of their relationship with Urban Company and can disrupt their mental model of how diagnosis, visitation fees, repair scope, and final pricing work. Solving the problem upstream has the potential to strengthen initial trust and establish more predictable expectations for future usage. However, the project does NOT currently have evidence proving that this problem causes churn, retention loss, or conversion loss, so those remain hypotheses."*

### Secondary Status Rationale (Segment 3)
> *"This segment sits directly at the quote accept/reject boundary and has the clearest observed connection to price comparison, substitution, and potential offline defection. However, quote rejection frequency and the magnitude of associated business impact remain unmeasured."*

### Options Considered
1. **Segment 1: First-Time Diagnosis-Dependent Bookers (SELECTED AS PRIMARY):** Focuses on expectation setting, early trust formation, and mental-model clarity at the booking-to-inspection threshold.
2. **Segment 2: Experienced / Repeat Diagnosis-Dependent Customers:** Focuses on rate-card adherence (`E040`) and high-LTV customer retention.
3. **Segment 3: Price-Sensitive Quote Evaluators (SELECTED AS SECONDARY BUSINESS-RISK):** Focuses on the accept/reject threshold, price comparison, and offline disintermediation leakage (`PAT-10`).
4. **Segment 4: Urgent / Time-Pressured Repair Customers:** Focuses on emergency domestic breakdowns and accept-under-duress dynamics.
5. **Segment 5: Post-Surprise Recovery Customers:** Focuses on downstream disputes, chatbot deflection (`E011`), and resolution failures.

### Evidence Basis
* **Primary Evidence Chain:** `E014` (post-booking add-on complaints), `E024` (quote verification FAQ), `E025` (extra-charge FAQ), `E026` (variable quoting approval policy), `E040` (granular rate cards), `E041` (visitation fee policy), `PAT-10` (substitution with offline mechanics).
* **Supporting Context:** `E004` (pricing theme prevalence).
* **Explicit Evidence Boundaries:**
  - The ₹99 checkout difference (`E022`) remains strictly isolated as a separate pre-payment phenomenon.
  - The project does **NOT** claim or assume that post-diagnostic pricing uncertainty has been proven to cause churn, retention loss, or conversion loss as established facts.

### Trade-offs
- Deliberately centers initial product requirements and teardown on onboarding, expectation setting, and early-journey quoting clarity rather than downstream dispute containment (Segment 5).
- Acknowledges that solving for first-time bookers does not automatically eliminate price elasticity pressures or external competition from offline mechanics (Segment 3).

### Reversal Conditions
- Telemetry demonstrating that first-time user quote acceptance and satisfaction are exceptionally high, with pricing friction concentrated almost exclusively among repeat multi-year bookers.
- Evidence that offline disintermediation among price-sensitive evaluators (Segment 3) represents the single dominant driver of unit-economic leakage.

### Status
**Active** — Decided by HUMAN (Project Owner). Governs Task 11 (Opportunity Analysis) and downstream product definition.

---

## D007 — Final Opportunity Selection: O4 — Accept/Reject Decision Support & Sunk-Cost Clarification

### Decision
* **Selected Primary Opportunity:** **O4 — Accept/Reject Decision Support & Sunk-Cost Clarification**
* **Complementary Opportunity Note:** **O1 (Pre-Diagnostic Price Expectation & Cost Education)** remains a strong complementary candidate that may inform eventual solution architecture, but O4 is the primary anchor selected at D007.
* **Excluded from MVP:** **O6 (Post-Quote Dispute Escalation & Price Verification Support)** remains outside the MVP and is deferred for later validation. It is distinct from "real-time escrow" (which is a separate, rejected concept).

### Decision Owner
**HUMAN — project owner.**

### Stage
Phase 3: Analysis & Synthesis (Task 12 — Opportunity Prioritization)

### Human Decision Rationale
> *"O4 most directly addresses the central decision moment in the locked problem: the customer's transition from an initial booking expectation to a post-diagnostic decision about whether to proceed with the proposed repair. It serves the primary first-time diagnosis-dependent segment while also addressing the secondary price-sensitive evaluator segment. Compared with upstream expectation-setting alone, O4 intervenes at the point where uncertainty becomes actionable; compared with downstream dispute escalation, it attempts to improve the decision before the interaction becomes a recovery case. The decision is based on problem fit, segment alignment, controllability, and marketplace considerations—not on an established claim of churn reduction or retention lift.*  
*O1 remains a strong complementary opportunity and may become part of the eventual solution, but it is not the primary opportunity selected at D007."*

### Options Considered
1. **O1: Pre-Diagnostic Price Expectation & Cost Education:** Focuses on upstream mental-model setting before technician arrival; held as a strong complementary opportunity.
2. **O2: Structured On-Site Quote Transparency & Itemization:** Line-item digital bill of materials on-site; high partner field compliance friction.
3. **O3: Quote Verification & Rate-Card Confidence:** Rate-card verification and warranty backing; primary value for Segment 3 price benchmarking.
4. **O4: Accept/Reject Decision Support & Sunk-Cost Clarification (SELECTED AS PRIMARY):** Intervenes at the actionable decision threshold where social duress, visitation fees, and churn intersect.
5. **O5: Diagnostic-Fee Reinvestment & Alternative Resolution Paths:** Converts diagnostic fees into platform credit; severe unit-economic margin erosion.
6. **O6: Post-Quote Dispute Escalation & Price Verification Support:** Reactive human dispute channel; heavy support operating expenses conflicting with EBITDA targets (`E039`).


### Evidence Basis
* **Primary Evidence Chain:** `E041` (mandatory visitation fee mechanism on decline), `E026` (AC gas customer approval precedent), `E014` (feeling overcharged or trapped on-site), `PAT-10` (substitution with offline mechanics when pressured), `E024` (quote verification policy).
* **Supporting Context:** `E004` (pricing friction prevalence), `E040` (granular rate cards).
* **Explicit Evidence Boundaries:**
  - Decision is grounded in problem fit, segment alignment, controllability, and marketplace feasibility—**not** on an established claim of churn reduction or retention lift.
  - The ₹99 checkout difference (`E022`) remains isolated as a booking-stage phenomenon.

### Trade-offs
- Intervenes at the in-home moment of decision rather than preventing all surprise upstream (O1), accepting that technicians will still uncover variable scope.
- Must balance customer decision freedom with partner job conversion so technicians do not feel the platform is encouraging customer decline over repair completion.

### Reversal Conditions
- Evidence that in-home decision support cannot be effectively delivered digitally while the technician is physically present.
- Platform data demonstrating that upstream price expectation setting (O1) alone eliminates >80% of on-site quote friction without harming top-of-funnel checkout conversion.

### Status
**Active** — Decided by HUMAN (Project Owner). Governs Task 13 (Product Strategy) and downstream PRD / UX redesign.

---

## Decision Summary Table

| ID | Decision | Stage | Status |
|----|---------|-------|--------|
| D001 | Approved investigation area: trust and repeat booking | SCOPING | Superseded by D004 (Historical context preserved) |
| D002 | Three downstream artifacts: Teardown, UX Redesign, PRD | SCOPING | Active |
| D003 | No fabricated data at any stage | SCOPING | Active — permanent |
| D004 | Core problem direction: Option 4 — Pricing Transparency / Cancellation Fairness (Working focus: post-booking price predictability & transparency) | Gate 1 → Gate 2 (Phase 1 Closure) | Active (Decided by HUMAN) |
| D005 | Canonical problem statement selection: Candidate 2 — Post-Diagnostic Price Uncertainty | Phase 3 (Synthesis / Task 9) | Active (Decided by HUMAN) |
| D006 | Primary behavioral segment selection: Segment 1 (Primary) & Segment 3 (Secondary) | Phase 3 (Analysis / Task 10) | Active (Decided by HUMAN) |
| D007 | Final opportunity selection: O4 — Accept/Reject Decision Support & Sunk-Cost Clarification | Phase 3 (Synthesis / Task 12) | **Active (Decided by HUMAN)** |

---

*New decisions must be logged here as they arise throughout the project.*  
*Last updated: 2026-09-18 (D007 Formalized by Human Decision)*






