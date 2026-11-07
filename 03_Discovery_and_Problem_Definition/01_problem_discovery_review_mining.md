# PM-01 — Urban Company
## 08 — Problem Discovery

**Stage:** SCOPING → RESEARCH → SYNTHESIS  
**Purpose:** Record, refine, and eventually validate (or invalidate) the problem hypotheses for this project.  
**Last updated:** 2026-09-18 (Post-Task 4 Assumptions & Hypotheses Alignment)  

> **Critical Rule:** This file tracks hypotheses. They are NOT findings. They are NOT conclusions. They are testable propositions. Every hypothesis is labelled with its current empirical status based strictly on evidence logged in [`05_evidence_matrix.md`](data/evidence_matrix.md).

---

## Section 1: The Investigation Area (Not the Problem Statement)

**Approved investigation area:** Trust and repeat booking in Urban Company's two-sided marketplace.

**Post-Review Mining Scope Calibration (Human Review Decision):**  
The initial scoping used "Trust and repeat booking" as a starting lens. However, review mining across 179 audited reviews revealed that customer dissatisfaction is heavily concentrated in pricing surcharges ($37.3\%$ of negative reviews, `E004`), cancellations ($37.3\%$ of negative reviews, `E005`), and automated support deflection ($21.6\%$ of negative reviews, `E011`), while explicit rebooking UX complaints represent only $5.9\%$ ($n=3$) of negative reviews (`E009`).

Per human review decision, the Phase 2 research scope is broadened to investigate four candidate friction tracks in parallel, without prematurely declaring any single problem as final:
* **Track A: Trust & Repeat-Booking Friction** (relationship continuity vs. algorithm liquidity; UX barriers to familiar professionals)
* **Track B: Post-Service Failure and Recovery** (AI chatbot deflection loops, absence of telephone escalation, unresolved warranty/damage claims)
* **Track C: Pricing Transparency & Fee Stacking** (checkout platform fees, weekend surge, unexpected on-site technician add-ons)
* **Track D: Cancellation & Fulfillment Reliability** (on-demand Insta Help supply fragility, partner no-shows, asymmetric cancellation fines)

> **Note on Phase 2 Scope:** These four parallel tracks represent a **broadened Phase 2 investigation scope**, NOT a validated or pre-selected problem shortlist. Final problem selection remains strictly deferred until multi-source triangulation (hands-on product walkthrough, financial/take-rate teardown, and secondary industry research) is completed in Phase 2.

The purpose of Phase 2 is to determine which problem area is best supported after multi-source triangulation.

---

## Section 2: Hypotheses & Current Evidence Status

---

### H1 — Repeat-booking UX creates friction

**Hypothesis Statement:** A meaningful subset of customers wants to rebook the same professional they have previously used, but the current Urban Company experience creates friction in discovering, selecting, and completing that rebooking.

* **Current Status:** `PARTIALLY SUPPORTED AT SYMPTOM LEVEL; UX MECHANISM UNVALIDATED`
* **Confidence:** Medium-Low (Dual confidence: High for observed customer symptom existence; Low for UX mechanism causality)
* **Why this is plausible:** Home services are deeply personal and relationship-sensitive. When a customer identifies a skilled, trustworthy cleaner, electrician, or salon professional, rebooking that specific partner significantly lowers uncertainty, anxiety, and the overhead of re-explaining domestic preferences. If the platform interface makes re-selection difficult or reassigns personnel, friction is introduced.
* **What this hypothesis concerns:** Customer side (desire for continuity) and Platform UX layer (information architecture, booking flow, partner re-selection mechanisms).
* **What evidence would support it:** High customer demand for repeat partner booking accompanied by verified UX obstacles (e.g., hidden rebooking buttons, absence of partner-specific order history CTAs, forced multi-step workarounds).
* **What would weaken/contradict it:** Prominent, frictionless rebooking CTAs in the app interface, or empirical findings that customers are indifferent to partner identity so long as delivery is fast.
* **Affected segment (if true):** Repeat customers; high-touch domestic service categories (women's salon, deep cleaning, recurring appliance maintenance).
* **Supporting Evidence (`05_evidence_matrix.md`):**
  * `E009`: $n=3$ explicit repeat booking friction cases in negative reviews: package failures upon rebooking (`R0073`), repeated platform cancellations on rebooking (`R0101`), and booking loops (`R0176`).
  * `E018`: $n=7/179$ reviews ($50.0\%$ of the rebooking/consistency cohort, $n=7/14$) explicitly demand familiar professionals and express sharp frustration when the platform reassigns unfamiliar technicians without consent (`R0179` — *"in some time they will change the person with out our knowledge once Booking is down they should take priority"*).
  * `E019`: $n=7/179$ reviews ($14.6\%$ of 4-star reviews, $n=7/48$) demonstrate customers decoupling partner praise from platform complaints, confirming strong loyalty to individual workers over the platform.
* **Contradicting / Challenging Evidence:**
  * `E009`: Explicit rebooking complaints represent only $3.4\%$ ($n=6/179$) of the total review sample and $5.9\%$ ($n=3/51$) of negative reviews. This low volume challenges the premise that rebooking UX friction is the primary or dominant driver of customer dissatisfaction compared to pricing transparency ($25.7\%$, `E004`) or cancellation failures ($14.5\%$, `E005`).
  * Fungible supply acceptance: `R0013` books across multiple categories without expressing worker-specific preference.
* **Current Interpretation:**
  * *Observed Symptom (Supported):* A subset of customers actively desires to rebook or retain preferred professionals and experiences acute frustration when the platform fails to facilitate continuity.
  * *Causal Mechanism (Unvalidated):* Customer review data captures behavioral frustration and outcomes, but cannot establish that the root cause is the discoverability or usability of the rebooking UX.
* **Remaining Unknowns:**
  * Does the live Urban Company app feature a "Book Again" or "Rebook Partner" CTA?
  * Where does rebooking reside in the information architecture (Home tab, Account tab, Order History, or post-service screen)?
  * Is rebooking friction caused by UI obscurity, partner scheduling unavailability, or algorithmic suppression?
* **What Phase 2 Research Can Resolve:**
  * Hands-on product walkthrough (Task 6) systematically testing the live app booking flow, past order screens, and rebooking entry points across categories.

---

### H2 — Service quality inconsistency reduces repeat booking behavior

**Hypothesis Statement:** Inconsistent service quality across different professionals in the same category is a primary driver of customer reluctance to rebook through the platform (as opposed to seeking a trusted professional directly).

* **Current Status:** `DIRECTIONALLY SUPPORTED (Premise & Salience Supported; Retention Impact Indirect)`
* **Confidence:** Dual-Confidence Framework: High for phenomenon existence and acute defect severity (`E016`, `E010`); Medium for sample prevalence and retention causality.
* **Why this is plausible:** If a customer has an outstanding experience with Professional A but later receives a substandard or damaging service from Professional B, trust in the platform's standardization promise collapses, reducing willingness to risk future bookings through the platform.
* **What this hypothesis concerns:** Customer side (experience of variance) and Platform layer (quality assurance, skill benchmarking, vetting).
* **What evidence would support it:** Consistent customer reports linking service degradation across visits to explicit decisions to abandon the platform or seek direct offline arrangements.
* **What would weaken/contradict it:** High service consistency across partners, or evidence that customers absorb occasional quality variance without churning while defecting over pricing or customer support failures.
* **Affected segment (if true):** Repeat customers who have experienced two or more bookings; technical and physical service categories (appliance repair, deep cleaning).
* **Supporting Evidence (`05_evidence_matrix.md`):**
  * `E003`: Quality is a dominant evaluative theme, appearing in $28.5\%$ ($n=51/179$) of all reviews, heavily concentrated in Cleaning ($93.8\%$, $n=15/16$) and Appliance Repair ($61.0\%$, $n=25/41$).
  * `E007`: Professional conduct and partner demeanor are cited in $30.2\%$ ($n=54/179$) of reviews, representing the primary positive determinant of ratings (overwhelmingly positive, $n=41/93$ in positive reviews), while `E017` confirms partner courtesy represents the primary loyalty anchor in 5-star reviews ($n=15/15$ in core cohort). Source-level counter-evidence reviews (`R0099`, `R0161`) illustrate the negative behavioral tail where delayed arrival or unprofessional conduct undermines trust.
  * `E010`: Variance across professionals and quality degradation over time appear in $n=4$ reviews (within the $n=6/179$ consistency theme: `R0074` — *"the 4 star rating is for the professionals and not for UC"*, `R0117`, `R0147`, `R0179`).
  * `E011`: Automated support deflection walls prevent remediation when quality failures occur ($n=11/51$ negative reviews).
  * `E016`: $n=6/179$ reviews ($11.8\%$ of quality reviews, $n=6/51$) document severe secondary appliance breakdowns post-servicing (`R0079`, `R0111`, `R0118`, `R0127`, `R0160`, `R0166`), documenting catastrophic quality defect modes in the sample.
* **Contradicting / Counter-Evidence:**
  * High satisfaction with technical execution: `E003` shows positive workmanship praised in $33.3\%$ ($n=31/93$) of all positive reviews ($60.8\%$ of quality reviews, $n=31/51$); `E016` source-level counter-evidence documents first-time repair accuracy and flawless execution (`R0001`, `R0014`, `R0016`, `R0024`, `R0048`); and reviews report flawless repeated service with zero quality variation (`R0017`, `R0033`) and standardized partner training (`R0040`).
* **Current Interpretation (Human Review Decision 1):**
  * *Established:* Review data conclusively establishes that service quality and partner demeanor are highly salient evaluative criteria ($28.5\%$ and $30.2\%$), that quality variance occurs across visits (`E010`), and that severe physical failures happen (`E016`).
  * *Not Established:* Review data **cannot** establish platform-wide repeat-booking causality or aggregate churn impact without cohort retention telemetry. Per Human Decision 1, H2 is maintained as directionally supported at the broad platform level and is not narrowed to technical verticals yet.
* **Remaining Unknowns:**
  * What percentage of customers who experience a quality defect actually churn versus rebooking under a warranty claim or switching categories?
  * What is the platform-wide baseline defect rate across all categories?
* **What Phase 2 Research Can Resolve:**
  * Secondary industry retention benchmarks (Task 8) regarding marketplace quality elasticity; operational analysis of Urban Company's 30-day service guarantee and revisit workflows.

---

### H3 — Professional continuity is constrained by platform allocation rules, creating a supply-side root cause

**Hypothesis Statement:** Even if customers want to book the same professional, and even if the professional wants to serve the same customer, the platform's matching and allocation system may prevent or discourage continuity — because the platform optimizes for liquidity and utilization across its professional pool rather than for individual customer-professional relationships.

* **Current Status:** `UNVALIDATED`
  * *Customer-Perceived Symptoms:* `SUPPORTED / CONSISTENT WITH H3`
  * *Causal Mechanism:* `UNVALIDATED`
* **Confidence:** Medium-Low (Dual confidence: High for observed customer symptoms in `E012`, `E013`, `E018`; Low for internal algorithmic dispatch mechanism)
* **Why this is plausible:** On-demand marketplaces face an inherent architectural trade-off: maximizing liquidity and fleet utilization requires treating service partners as interchangeable, fungible supply units. Allowing customers to lock in specific partners introduces scheduling rigidity, lowers fleet utilization, and complicates geographic clustering.
* **What this hypothesis concerns:** Platform allocation engine, dispatch algorithms, and supply-side capacity management.
* **What evidence would support it:** Platform dispatch documentation, partner allocation policies, or algorithmic rules confirming that partner re-selection is deprioritized, restricted, or actively suppressed in favor of instant dispatch.
* **What would weaken/contradict it:** Platform features that explicitly route repeat requests to previous partners whenever available, or high partner schedule autonomy.
* **Affected segment (if true):** Repeat customers seeking partner continuity; service partners seeking steady, familiar client rosters.
* **Supporting Evidence — Customer-Facing Symptoms (`05_evidence_matrix.md`):**
  * `E005`: High cancellation prevalence ($14.5\%$ overall, $37.3\%$ of negative reviews) reflecting supply allocation fragility.
  * `E012`: $n=5$ asymmetric cancellation penalties imposed on customers even when platform delivery or dispatch fails.
  * `E013`: $n=11$ Insta Help reviews documenting severe partner no-shows and supply fragility ($42.3\%$ of sampled reviews in vertical mentioned cancellation/no-show, $n=11/26$).
  * `E018`: $n=7$ repeat customers reporting that the platform arbitrarily reassigns unfamiliar personnel without consent or notice (`R0179`).
* **Contradicting / Challenging Evidence:**
  * Zero direct evidence that Urban Company's algorithm intentionally blocks repeat matching when a partner is available.
* **Insta Help Vertical-Specific Boundary (Human Review Decision 4):**
  * `E013` confirms that $42.3\%$ ($n=11/26$) of sampled reviews in the Insta Help vertical mentioned partner cancellations or no-shows. Per Human Decision 4, this is classified as **strong evidence of a vertical-specific operational problem** in on-demand daily chores (where short lead times break partner availability). It is **NOT** classified as proof of platform-wide marketplace allocation failure.
* **Current Interpretation:**
  * *Customer Symptoms:* Observed customer friction (cancellations, no-shows, forced partner substitution) is consistent with allocation constraints.
  * *Causal Mechanism:* Unvalidated. Customer reviews observe external outcomes, not Urban Company's proprietary dispatch engine.
* **Remaining Unknowns:**
  * How does Urban Company's dispatch engine handle repeat requests?
  * Does the algorithm prioritize proximity, partner tier, utilization balancing, or customer preference?
  * Are partner continuity constraints technical, economic, or operational?
* **What Phase 2 Research Can Resolve:**
  * Professional-side operational research (Task 8), analysis of published partner SLAs and dispatch models, and business model / take-rate teardown (Task 7).

---

### H4 — Two-Stage Trust Model: Pre-Booking Platform Trust vs. Post-Booking Domestic/Service-Execution Trust

**Hypothesis Statement (Reformulated per Human Review Decision 5):** Trust in Urban Company's home-services journey has at least two potentially distinct stages: pre-booking platform trust and post-booking domestic/service-execution trust. Review evidence suggests that trust can also fail after booking, but public reviews cannot determine the relative size or conversion impact of pre-booking versus post-booking trust barriers.

* **Current Status:** `REFORMULATED / PARTIALLY SUPPORTED`
* **Confidence:** Medium (Dual confidence: High for post-booking domestic breach existence `E008`, `E015`; Unassessed for pre-booking conversion drop-off)
* **The Two Stages Defined:**
  1. *Stage 1 — Pre-Booking Platform Trust:* Customer hesitation regarding platform credibility, partner background verification, identity screening, and transparent upfront pricing before committing to the transaction.
  2. *Stage 2 — Post-Booking Domestic / Service-Execution Trust:* Customer vulnerability, personal safety, property integrity, and physical boundary maintenance once an external service professional crosses into the private living space ("domestic sanctuary").
* **Why this is plausible (Two-Stage Trust Model):** Unlike ride-hailing or e-commerce where interactions occur in public spaces or at the doorstep, home services require admitting unknown individuals into private residences. Initial hesitation focuses on platform legitimacy and fraud risk; once booked, vulnerability shifts to physical security, privacy, property protection, and recourse when things go wrong.
* **What this hypothesis concerns:** Customer domestic psychology, platform vetting/safety features, in-home operational protocols.
* **What evidence would support it:** High top-of-funnel drop-off due to vetting/safety anxiety (Stage 1) combined with acute domestic boundary and property integrity failures inside the home (Stage 2).
* **What would weaken/contradict it:** If customer trust concerns were entirely confined to pre-booking payment security, or if customers expressed total indifference to domestic privacy and boundary protocols.
* **Affected segment (if true):** Prospective first-time bookers (Stage 1); solo dwellers, women, families, and customers booking in-home personal care or long-duration repairs (Stage 2).
* **Supporting Evidence (`05_evidence_matrix.md`):**
  * `E008`: $n=8/51$ negative reviews (representing 8 of the 14 trust-themed reviews in the sample) detail acute in-home safety, property damage, and boundary breaches.
  * `E015`: $n=4$ acute privacy and domestic boundary violations inside the home: unannounced personal washroom use (`R0143`), video recording into private domestic quarters (`R0109`), and socio-religious domestic friction (`R0179`).
  * `E016`: $n=6$ severe secondary appliance damage and hazardous installation failures (`R0079`, `R0111`, `R0118`, `R0127`, `R0160`, `R0166`).
* **Counter-Evidence / Positive Domestic Trust:**
  * Reviews praising partner background verification and feeling completely secure welcoming professionals into the home (`R0036`, `R0052`, `R0056`).
* **Current Interpretation (Human Review Decision 5):**
  * *Supported:* Post-booking domestic trust failures exist, are intensely felt, and trigger catastrophic customer sentiment; review evidence supports the existence of acute in-home boundary and domestic property breaches.
  * *Not Established:* The relative magnitude or conversion impact of pre-booking versus post-booking trust barriers cannot be determined from public reviews.
  * *Critical Methodological Boundary:* App store reviews represent transacting customers who already overcame initial pre-booking friction. They **cannot** measure pre-booking hesitation among prospective users who visited the app and abandoned before booking. Therefore, pre-booking platform trust is **not** disproven, but remains unassessed in review data.
* **Remaining Unknowns:**
  * What is the drop-off rate of new users at the onboarding/search stage due to lack of trust or safety disclosures?
  * How does the severity of post-booking domestic breaches affect lifetime customer retention compared to routine quality defects?
* **What Phase 2 Research Can Resolve:**
  * Hands-on product walkthrough (Task 6) evaluating in-app trust architecture (safety badges, partner profile depth, SOS features, background check disclosures); secondary industry funnel benchmarks (Task 8).

---

### H5 — Improving customer-professional continuity creates meaningful supply-side tensions

**Hypothesis Statement:** A product mechanism that enables customers to lock in a preferred professional may improve customer retention but create negative consequences for the supply side: disadvantaging professionals who are not selected repeatedly, reducing platform scheduling flexibility, and potentially allowing professionals to develop off-platform relationships (disintermediating Urban Company).

* **Current Status:** `UNVALIDATED`
* **Confidence:** Low (Zero direct visibility in customer review mining)
* **Why this is plausible:** Two-sided marketplaces face classic disintermediation and supply-allocation risks. If customers develop strong direct relationships with specific professionals, both parties have economic incentives to transact off-platform to avoid platform fees (Urban Company take-rates) and customer surcharges. Furthermore, preferential routing creates a "superstar effect," concentrating high-value bookings among senior partners while leaving newer partners with low utilization.
* **What this hypothesis concerns:** Supply-side economics (partner earnings distribution, fleet utilization), disintermediation risk, platform commission defensibility.
* **What evidence would support it:** Partner community grievances regarding lead starvation, evidence of off-platform private arrangements, platform anti-disintermediation enforcement actions.
* **What would weaken/contradict it:** Evidence that partner retention and total platform revenue increase under continuity models without increasing disintermediation.
* **Affected segment (if true):** Supply side (service professionals, gig workers); platform marketplace operations and unit economics.
* **Supporting Evidence (`05_evidence_matrix.md`):**
  * No direct supply-side data exists in customer review mining.
  * While customer reviews report friction around arbitrary partner reassignment (`E018`, `R0179`), this represents customer-perceived friction only. Similarly, while `E014` captures customer-facing post-booking cost inflation, neither can be used to validate partner-side incentives, earnings distribution, or structural supply-side tensions.
* **Contradicting Evidence:** None in customer review data.
* **Current Interpretation:** Customer reviews provide zero visibility into supply-side economics or partner sentiment. Reassignment complaints from customers cannot be used to infer partner-side preferences or marketplace disintermediation dynamics.
* **Remaining Unknowns:**
  * Do Urban Company service professionals want repeat customer relationships, or do they prefer algorithmic dispatch?
  * What is the true incidence of off-platform disintermediation, and how does Urban Company police it?
  * How would preferred-partner booking impact overall fleet utilization and partner churn?
* **What Phase 2 Research Can Resolve:**
  * Secondary research into gig-economy labor dynamics, partner union disputes, and platform take-rates (Task 8); business model and partner commission teardown (Task 7).

---

## Section 3: Hypothesis Validity Criteria

Before any hypothesis can move to fully "VALIDATED" status:
* Evidence must be multi-source (review mining + product walkthrough + operational/financial data).
* Causal mechanisms must be distinguished from descriptive co-occurrence.
* Contradicting evidence must be explicitly reconciled.
* Supply-side and platform-economic feasibility must be established.

---

## Section 4: What Would Invalidate the Entire Investigation Area

If multi-source Phase 2 research establishes that:
1. Rebooking friction and partner continuity are non-issues for customers, AND
2. The core barrier to platform retention is entirely centered on post-service dispute failures, cancellation cascades, or fee-stacking resentment...

...then the investigation will formally pivot, and a strategic decision will be logged in `07_decision_log.md` redirecting the problem definition to the best-supported problem track.

---

## Section 5: Hypothesis Summary Table (Part C)

| Hypothesis | Current Status | Evidence Strength | What Is Supported | What Remains Unvalidated |
|:---:|---|:---:|---|---|
| **H1** | `PARTIALLY SUPPORTED AT SYMPTOM LEVEL; UX MECHANISM UNVALIDATED` | Medium-Low | Customer desire to rebook preferred professionals; frustration when platform arbitrarily reassigns unfamiliar personnel (`E009`, `E018`, `E019`) | Whether the mobile app UX is the causal barrier to rebooking; UI hierarchy and CTA discoverability |
| **H2** | `DIRECTIONALLY SUPPORTED (Premise & Salience Supported; Retention Impact Indirect)` | Dual-Confidence: High (defects) / Medium (prevalence) | High customer salience of quality ($28.5\%$, `E003`) and partner demeanor ($30.2\%$, `E007`); acute collateral damage failure modes (`E010`, `E016`) | Platform-wide repeat-booking causality; macro retention reduction; aggregate churn rate attributable to quality variance |
| **H3** | `UNVALIDATED` (Customer symptoms: `SUPPORTED / CONSISTENT WITH H3`; Causal mechanism: `UNVALIDATED`) | Medium-Low (Symptoms High, Mechanism Low) | Customer-facing symptoms of dispatch instability: cancellations ($14.5\%$, `E005`), no-shows, sudden partner reassignment (`E012`, `E013`, `E018`) | Internal dispatch algorithms; platform liquidity vs relationship optimization rules; platform-wide allocation policies (Insta Help is vertical-specific) |
| **H4** | `REFORMULATED / PARTIALLY SUPPORTED` | Medium (Post-booking High, Pre-booking Unassessed) | Post-booking domestic sanctuary breaches, property damage, and boundary violations inside the home (`E008`, `E015`, `E016`) | Relative magnitude or conversion impact of pre-booking platform trust vs post-booking domestic trust (pre-booking is unassessed, not disproven) |
| **H5** | `UNVALIDATED` | Low (Zero direct review data) | Nothing direct; customer anecdotes report reassignment friction (`E018`) and pricing disputes (`E014`) | Supply-side partner economics; earnings inequality/superstar effects; platform disintermediation rates; partner scheduling autonomy |

---

## Section 6: Phase 2 Research Required (Part D)

| Open Question | Hypothesis | Research Needed | Permitted Phase 2 Stream / Task |
|---|:---:|---|---|
| Is rebooking UX actually hard to discover or use in the live app? | **H1** | Hands-on walkthrough of live booking flows, order history screens, and rebooking entry points across categories | Task 6 — Hands-on Product Walkthrough |
| Does service quality inconsistency causally drive customer churn platform-wide? | **H2** | External triangulation and secondary industry retention benchmarks across on-demand home service marketplaces | Task 8 — Secondary Industry Research & Benchmarking |
| Are platform allocation rules structurally causing partner reassignment and fulfillment failure? | **H3** | Professional-side evidence, partner dispatch SLAs, operational teardown, and public marketplace architecture analysis | Task 7 — Take-Rate Teardown / Task 8 — Secondary Research |
| How important is pre-booking platform trust relative to post-booking domestic sanctuary trust? | **H4** | Audit of trust cues, safety disclosures, and onboarding flows in live app; secondary funnel drop-off benchmarks | Task 6 — Product Walkthrough / Task 8 — Secondary Research |
| Do continuity mechanisms create supply-side tensions, earnings concentration, or disintermediation? | **H5** | Secondary research into gig-economy labor dynamics, partner union disputes, and take-rate/commission structures | Task 7 — Take-Rate Teardown / Task 8 — Secondary Research (Partner-Side) |

---

*Stage: SCOPING → RESEARCH → SYNTHESIS — Hypotheses aligned with Task 2 Evidence Matrix, Task 4 calibration rules, and Human Review Decisions.*  
*Last updated: 2026-09-18*
