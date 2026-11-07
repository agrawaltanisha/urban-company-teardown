# PM-01 — Urban Company
## 06 — Assumption Log

**Stage:** SCOPING → RESEARCH → SYNTHESIS (Maintained across all stages)  
**Purpose:** Explicitly record every assumption the project currently relies on, along with its confidence level and the evidence required to validate or invalidate it.  
**Last updated:** 2026-09-18 (Post-Task 4 Assumptions Alignment)  

> **Rule:** Assumptions must be logged the moment they are made. They must never be allowed to silently harden into facts. When evidence confirms or contradicts an assumption, update this log immediately.

---

## Assumption Status Codes

| Code | Meaning |
|------|---------|
| `UNVALIDATED` | Assumption made, no evidence yet |
| `PARTIALLY SUPPORTED` | Some evidence supports it, but not conclusive |
| `SUPPORTED` | Substantial evidence now backs this assumption |
| `WEAKENED` | Evidence has reduced confidence in this assumption |
| `CONTRADICTED` | Evidence suggests this assumption is likely wrong |
| `RETIRED` | No longer relevant to project direction |

---

## Assumptions & Current Empirical Status

---

### A001 — Trust and repeat-booking is a meaningful problem area

**Assumption:** The trust and repeat-booking experience on Urban Company is a genuine source of user frustration for a meaningful segment of customers.

* **Why it matters:** If this assumption is wrong — if trust and rebooking are already working well — the entire investigation area is misplaced and the project must be redirected.
* **Current Status:** `PARTIALLY SUPPORTED`
* **Current Confidence:** Medium
* **Calibrated Meaning (Human Review Decision):** This assumption now means that trust and repeat-booking is a **meaningful investigation area**, NOT that it is established as the primary or dominant platform-level customer problem.
* **Evidence Now Supporting the Assumption:**
  * `E008`: Trust and security themes appear in $7.8\%$ ($n=14/179$) of the total sample and $15.7\%$ ($n=8/51$) of negative reviews, highlighting acute in-home vulnerability, property integrity, and domestic boundary concerns.
  * `E009`: Repeat booking and continuity themes appear in $3.4\%$ ($n=6/179$) of reviews, capturing recurring package booking failures (`R0073`), repeated platform cancellations on rebooking (`R0101`), and booking loops (`R0176`).
  * `E018`: $n=7/179$ reviews ($50.0\%$ of the rebooking/consistency cohort, $n=7/14$) explicitly demand familiar professionals and express frustration when the platform arbitrarily reassigns unfamiliar technicians (`R0179`).
  * `E019`: $n=7/179$ reviews ($14.6\%$ of 4-star reviews, $n=7/48$) show customers explicitly decoupling individual partner excellence from platform defects, indicating that relationship-specific trust exists within this cohort.
* **Evidence Weakening the Assumption:**
  * Explicit rebooking friction is relatively limited in the sampled reviews ($3.4\%$ overall, $n=6/179$; $5.9\%$ of negative reviews, $n=3/51$, `E009`).
  * Dissatisfaction is materially dominated by competing operational friction points: Pricing transparency and unexpected surcharges appear in $25.7\%$ ($n=46/179$) of all reviews and $37.3\%$ ($n=19/51$) of negative reviews (`E004`), Cancellation/no-show failures appear in $14.5\%$ ($n=26/179$) of all reviews and $37.3\%$ ($n=19/51$) of negative reviews (`E005`), automated AI chatbot deflection blocks dispute escalation in $21.6\%$ ($n=11/51$) of negative reviews (`E011`), and general App/UX friction accounts for $31.4\%$ ($n=16/51$) of negative reviews (`E006`).
* **What Remains Unknown:**
  * True population-wide prevalence of repeat booking intent across active Urban Company users.
  * Whether trust/rebooking friction causes higher platform churn than pricing surcharges or cancellation cascades.
  * Overall marketplace retention elasticity relative to partner continuity.
* **What Phase 2 Research is Required:**
  * Hands-on product walkthrough (Task 6) to test the rebooking UI and determine if discoverability or workflow design creates artificial friction.
  * Financial and take-rate teardown (Task 7) to assess whether pricing surcharges and platform fees interact with rebooking behavior.
  * Secondary industry research (Task 8) benchmarking multi-category marketplace churn drivers.
  * Parallel investigation of four candidate tracks (Trust/Rebooking, Post-Service Recovery, Pricing/Surge, Cancellation/Fulfillment) without prematurely selecting any single problem.

---

### A002 — Customers value consistency with the same professional

**Assumption:** A meaningful proportion of customers prefer to book the same professional repeatedly rather than accepting a new professional each time.

* **Why it matters:** If customers are largely indifferent to which professional arrives (so long as quality is acceptable), the "repeat booking" angle is less important and the problem statement should shift to "service quality consistency" instead.
* **Current Status:** `PARTIALLY SUPPORTED`
* **Current Confidence:** Medium
* **Calibrated Meaning:** A subset of sampled reviewers explicitly values continuity with a known professional. This does NOT establish that customers broadly prefer the same professional across all service categories.
* **Evidence Now Supporting the Assumption:**
  * `E018`: $n=7/179$ reviews ($50.0\%$ of the rebooking/consistency cohort, $n=7/14$) explicitly articulate a preference for retaining familiar professionals and express acute frustration when the platform reassigns unfamiliar personnel without consent (`R0179` — *"in some time they will change the person with out our knowledge once Booking is down they should take priority"*).
  * `E010`: $n=6/179$ reviews in the consistency theme document customers valuing technician familiarity with home layouts, appliance history, or personal grooming preferences (with $n=4$ noting degradation or partner variance over time).
  * `E019`: $n=7/179$ reviews ($14.6\%$ of 4-star reviews, $n=7/48$) show customers explicitly bifurcating evaluations by praising individual technicians while docking platform ratings or criticizing corporate policies/fees (e.g., `R0074`, `R0092`, `R0093`), illustrating relationship-specific interpersonal loyalty.
* **Evidence Weakening the Assumption:**
  * Small absolute sample volume ($n=7$, $n=6$).
  * Certain reviewers display fungible supply acceptance: `R0013` books across multiple categories without expressing worker-specific preference as long as execution standards are met.
  * Low-involvement or standardized tasks (e.g., standard drain unclogging, basic home cleaning) may exhibit indifference to worker identity compared to high-touch, intimate categories (women's salon, deep cleaning).
* **What Remains Unknown:**
  * Category-by-category variance in partner continuity preference (e.g., beauty/wellness vs home repair vs appliance installation).
  * Proportion of Urban Company's total active user base that actively desires partner continuity versus fast turnaround/instant allocation.
  * Customer willingness to wait or pay a premium for a familiar professional.
* **What Phase 2 Research is Required:**
  * Product walkthrough (Task 6) to determine whether category-specific flows treat partner selection differently.
  * Secondary marketplace benchmarks (Task 8) on user retention in relationship-driven versus commodity on-demand services.

---

### A003 — The platform does not currently make repeat booking easy to discover and act on

**Assumption:** Even if Urban Company has a technical mechanism for rebooking the same professional, the UX either buries it or does not make it the default path.

* **Why it matters:** If the feature is already prominent and well-designed, the UX opportunity disappears and the project must find a different angle.
* **Current Status:** `UNVALIDATED` (Task 8 primary research omitted; no direct validation available)
* **Current Confidence:** Low
* **Calibrated Meaning:** Review evidence documents customer rebooking frustration, but cannot establish that the root cause is the UX discoverability of the rebooking mechanism. Behavioral friction must not be conflated with UX design failure.
* **Evidence Now Supporting the Assumption:**
  * No direct empirical UX evidence in customer review mining.
  * Anecdotal behavioral friction exists in `E009` ($n=3$: package rebooking glitches in `R0073`, repeated platform cancellations on rebooking in `R0101`, booking loops in `R0176`) and `E018` (`R0179`), but these reflect operational or algorithmic outcomes, not UX visibility.
* **Evidence Weakening the Assumption:**
  * No direct UX audit or interface inspection has been conducted yet; customer reviews do not describe UI hierarchy, navigation architecture, or CTA placement.
* **What Remains Unknown:**
  * Whether the current Urban Company mobile app includes a dedicated "Book Again" or "Rebook Professional" CTA on the home screen, order history screen, or post-service screen.
  * Where the rebooking option is placed in the information architecture and whether it is restricted by category, city, or partner availability.
  * Whether customer drop-off is driven by UI obscurity, partner scheduling unavailability, or algorithm suppression.
* **What Phase 2 Research is Required:**
  * Hands-on product walkthrough (Task 6) systematically mapping the live app UI, booking flows, past booking screens, rebooking prompts, and partner selection paths.

---

### A004 — Inconsistent service quality is a meaningful driver of customer dissatisfaction

**Assumption:** Customers experience quality variation across professionals in the same service category, and this variation is a source of frustration.

* **Why it matters:** If quality is actually quite consistent across professionals (because training and vetting work well), then "inconsistency" is not the root cause. The problem might be elsewhere.
* **Current Status:** `PARTIALLY SUPPORTED`
* **Current Confidence:** Medium
* **Calibrated Meaning:** Quality variation and service failures are materially present in the review sample and are plausibly relevant to dissatisfaction. However, review data cannot prove that quality inconsistency causes platform-wide churn.
* **Evidence Now Supporting the Assumption:**
  * `E003`: Quality is a dominant theme, appearing in $28.5\%$ ($n=51/179$) of all reviews, heavily clustered in Cleaning ($93.8\%$, $n=15/16$) and Appliance Repair ($61.0\%$, $n=25/41$).
  * `E007`: Professional conduct is cited in $30.2\%$ ($n=54/179$) of reviews, representing the primary positive determinant of ratings (overwhelmingly positive, $n=41/93$ in positive reviews), while `E017` confirms partner courtesy represents the primary loyalty anchor in 5-star reviews ($n=15/15$ in core cohort). Source-level counter-evidence reviews (`R0099`, `R0161`) illustrate the negative behavioral tail where delayed arrival or unprofessional conduct undermines trust.
  * `E010`: Variance across professionals and quality degradation over time appear in $n=4$ reviews (within the $n=6/179$ consistency theme: `R0074` — *"the 4 star rating is for the professionals and not for UC"*, `R0117`, `R0147`, `R0179`).
  * `E016`: $n=6/179$ reviews ($11.8\%$ of quality-themed reviews, $n=6/51$) report severe secondary appliance breakdowns and collateral physical damage post-servicing (`R0079`, `R0111`, `R0118`, `R0127`, `R0160`, `R0166`).
* **Evidence Weakening the Assumption:**
  * Substantial counter-evidence of consistent quality: `E003` shows positive workmanship praised in $33.3\%$ ($n=31/93$) of all positive reviews ($60.8\%$ of quality reviews, $n=31/51$); `E016` source-level counter-evidence documents first-time repair accuracy and flawless execution (`R0001`, `R0014`, `R0016`, `R0024`, `R0048`); and reviews report flawless repeated service with zero quality variation (`R0017`, `R0033`) and standardized partner training (`R0040`).
  * Heavy category concentration in sample: Quality complaints in the sample are concentrated in complex manual tasks (Cleaning $93.8\%$, $n=15/16$, and Appliance Repair $61.0\%$, $n=25/41$). However, small sample sizes in other categories (e.g., Women's Salon $n=5$, Men's Grooming $n=5$) prevent drawing reliable conclusions about category-level consistency across the platform.
* **What Remains Unknown:**
  * Whether quality inconsistency directly causes users to churn from the platform or simply causes users to avoid specific categories or request rework.
  * The platform-wide baseline defect rate across all completed service requests.
* **What Phase 2 Research is Required:**
  * Secondary operational and industry benchmarking (Task 8) on defect tolerance and retention impact in on-demand service marketplaces.
  * Operational analysis of Urban Company's 30-day service guarantee and revisit workflows.

---

### A005 — The problem primarily affects the customer side, not only the professional side

**Assumption:** The trust/repeat-booking friction is primarily experienced by customers. The professional side may be affected, but the customer-side impact is the more evidenced and addressable starting point.

* **Why it matters:** If the root cause is actually on the professional side (e.g., professionals have no incentive to return to the same customer, or professionals are burned by the platform's allocation rules), the solution direction changes fundamentally.
* **Current Status:** `PARTIALLY SUPPORTED`
* **Current Confidence:** Medium-Low
* **Calibrated Meaning:** The available evidence is overwhelmingly customer-side because the initial research stream was customer reviews. This represents an evidence-access limitation of customer review mining, NOT empirical proof that the causal root resides on the customer side.
* **Evidence Now Supporting the Assumption:**
  * Customer-facing symptoms and friction are extensively documented across multiple review datasets (`E003`, `E004`, `E005`, `E006`, `E008`, `E009`, `E010`, `E018`).
* **Evidence Weakening the Assumption:**
  * Multiple customer-observed failure modes suggest possible underlying partner-side friction: partner-initiated cancellations (`E005`), no-shows and supply shortages in on-demand chores (`E013`), and technician reluctance to honor platform warranties (`E016`). (Note: while `E014` captures customer-facing post-booking cost inflation and on-site add-on demands, whether this stems from platform take-rate pressure or partner opportunism remains unobserved).
* **What Remains Unknown:**
  * Professional-side incentives, commission deductions, partner utilization rates, and scheduling autonomy.
  * Whether service professionals want repeat customer allocation or prefer algorithmic lead assignment.
  * Partner churn rates and the supply-side cost of partner acquisition and retention.
* **What Phase 2 Research is Required:**
  * Secondary research into gig-economy labor reports, partner union disputes, and public partner sentiment (Task 8).
  * Business model and take-rate teardown (Task 7) evaluating partner payout cuts and platform fee structures.

---

### A006 — Urban Company's primary competitive alternative is the unorganized local market

**Assumption:** When customers leave Urban Company (or don't rebook), they more often go back to finding a local plumber/electrician/cleaner through word-of-mouth referrals than to a competing platform.

* **Why it matters:** This affects how urgently Urban Company needs to solve the repeat-booking problem. If customers defect to another platform, competitive urgency is higher. If they go to the unorganized market, the platform's primary job is to maintain trust superiority over informal alternatives.
* **Current Status:** `UNVALIDATED` (Task 8 primary research omitted; no direct validation available)
* **Current Confidence:** Low
* **Calibrated Meaning:** General industry knowledge regarding India's unorganized home services sector cannot substitute for empirical evidence in this project. Review data contains qualitative mentions of local alternatives, but cannot establish that the unorganized market is empirically the primary competitive alternative for churned customers.
* **Evidence Now Supporting the Assumption:**
  * None direct at the population/churn destination level.
  * Anecdotal qualitative mentions in `PAT-10` ($n=4$): Dissatisfied customers in the review sample explicitly compare platform prices to outside neighborhood technicians or state switching threats/intentions (`R0070`, `R0113`, `R0145`, `R0163` — *"outside mechanic charged ₹200 for same fix"*). Note: `PAT-10` records stated comparisons and threats, NOT verified post-churn defection destinations.
* **Evidence Weakening the Assumption:**
  * The review sample lacks quantitative data on actual customer defection destinations. Customers who leave Urban Company may switch to specialized digital competitors (e.g., NoBroker, MyGate, category-specific vertical startups), utilize housing society in-house maintenance, or defer home maintenance tasks entirely.
* **What Remains Unknown:**
  * Quantitative breakdown of churned customer destinations (unorganized market vs. digital competitors vs. non-consumption).
  * Cross-elasticity of demand between Urban Company and neighborhood technicians across different service categories and income tiers.
* **What Phase 2 Research is Required:**
  * Secondary market research and industry reports (Task 8) evaluating home services market share, competitive positioning, and consumer substitution behavior in urban India.

### A007 — Partners will adopt digital 3-tap quoting over informal verbal quotes

**Assumption:** Service technicians will utilize the in-app 3-tap SKU quoting module on-site rather than communicating quotes verbally and bypassing the digital flow.

* **Why it matters:** If partners bypass the digital flow, customers never see the sunk-cost ledger, certificates cannot be generated, and the product scaffold is rendered non-functional.
* **Current Status:** `UNVALIDATED` (Targeted for Stage 2 Field Usability Pilot, `20_validation_plan.md`)
* **Current Confidence:** Low-Medium
* **Surfaced via:** `21_red_team_review.md` (Question 1)
* **What Remains Unknown:** Partner behavioral compliance under peak daily fatigue; willingness to log non-standard faults.
* **Mitigation / De-Risking:** Hardened partner app so job completion OTP generation is gated on digital quote transmission; 1-tap standard bundles for 80% of routine jobs (`18_prd.md`).

---

### A008 — Customers possess domestic social agency to decline in-home quotes

**Assumption:** Customers (particularly first-time bookers and solo domestic dwellers) feel psychologically safe and empowered to tap "Decline" on their phone with a technician physically present in their home.

* **Why it matters:** If domestic social duress forces customers to accept quotes verbally despite digital options, the scaffold fails to protect customer agency.
* **Current Status:** `UNVALIDATED` (Targeted for Stage 1 Lab & Stage 2 Field Pilot)
* **Current Confidence:** Medium
* **Surfaced via:** `21_red_team_review.md` (Question 2)
* **Mitigation / De-Risking:** Reframed Decline action as an administrative handoff: *"Opt for Diagnostic Safety Certificate & Report"* (`17_ux_flows.md`).

---

### A009 — Doorstep cellular connectivity supports real-time push/socket quote delivery

**Assumption:** Mobile network connectivity (4G/5G) at residential doorsteps, basements, and high-rise apartments is adequate to reliably deliver push notifications and render quote cards without timeouts.

* **Why it matters:** Connection drops cause the customer app to hang, forcing partners back into offline verbal negotiation.
* **Current Status:** `UNVALIDATED`
* **Current Confidence:** Medium-Low
* **Mitigation / De-Risking:** Elevated `FR-13` (Offline Quoting Cache & Graceful Degradation via SQLite) in `01_prd_post_diagnostic_scaffold.md`. (Initial Bluetooth/QR local sync proposal was challenged and superseded by `THR-07` in favor of robust client-side SQLite rate-card caching).

---

### A010 — Providing an itemized diagnosis will not drive disintermediation to offline mechanics

**Assumption:** Customers receiving an itemized diagnostic report will not simply take Urban Company's free inspection and hire a neighborhood local technician to execute the physical repair for cash.

* **Why it matters:** If disintermediation spikes, platform GMV collapses while incurring unrecovered diagnostic fleet costs.
* **Current Status:** `PARTIALLY SUPPORTED`
* **Current Confidence:** Medium
* **Surfaced via:** `21_red_team_review.md` (Question 14)
* **Underlying Logic:** 90-day parts warranty (`E048`) and sunk fee crediting (`E041`) economically disincentivize hiring unverified local mechanics.

---

## Assumption Summary Table

| ID | Assumption | Current Confidence | Status | Underlying Evidence | What Remains Unknown | Phase 2/Validation Research Required |
|:---:|---|:---:|:---:|---|---|---|
| **A001** | Trust and repeat-booking is a meaningful problem area | Medium | `PARTIALLY SUPPORTED` | `E008`, `E009`, `E018`, `E019`; low rebooking complaint volume ($3.4\%$, `E009`) vs pricing ($25.7\%$, `E004`) | Population prevalence; churn causality; retention elasticity | Product walkthrough (Task 6); financial teardown (Task 7); redirected via D004 |
| **A002** | Customers value consistency with the same professional | Medium | `PARTIALLY SUPPORTED` | `E018` ($n=7/179$, $50\%$ of cohort), `E010` ($n=6/179$), `E019` ($n=7/179$, $7/48$ 4-star); counter-evidence `R0013` | Category variation; platform-wide prevalence; willingness to wait/pay | Product walkthrough (Task 6); secondary marketplace benchmarks |
| **A003** | Repeat booking is not easy to discover in current UX | Low | `UNVALIDATED` | No direct UX data; behavioral complaints in `E009` reflect operational outcomes, not UI visibility | App UI hierarchy; existence of "Book Again" CTA; category restrictions | Hands-on product walkthrough (Task 6) |
| **A004** | Inconsistent service quality is a meaningful driver of dissatisfaction | Medium | `PARTIALLY SUPPORTED` | `E003` ($28.5\%$), `E007` ($30.2\%$), `E010` ($n=4$ variance), `E016` ($n=6$ damage); counter-evidence `E003` positive workmanship | Causal retention impact; baseline defect rates; category defect tolerance | Secondary industry benchmarking; warranty/revisit analysis |
| **A005** | Problem primarily affects customer side | Medium-Low | `PARTIALLY SUPPORTED` | Customer symptoms documented (`E003`, `E004`, `E005`); customer review stream is an access constraint | Partner incentives; commission impact; schedule autonomy; supply-side churn | Partner community/labor research; business model/take-rate analysis |
| **A006** | Primary competitive alternative is unorganized market | Low | `UNVALIDATED` | Qualitative mentions in `PAT-10` ($n=4$: `R0070`, `R0113`, `R0145`, `R0163`); stated threats, not observed churn | Churned user destinations; digital competitor defection; category cross-elasticity | Secondary market research & competitive analysis |
| **A007** | Partners will adopt digital 3-tap quoting over informal verbal quotes | Low-Med | `UNVALIDATED` | Surfaced in Red-Team Review; field reality of tool bags, dirty hands, time pressure | Quoting latency under fatigue; compliance without enforcement | Shadowed field usability pilot ($n=25$, Task 18) |
| **A008** | Customers possess domestic social agency to decline in-home quotes | Medium | `UNVALIDATED` | Surfaced in Red-Team Review; in-home social pressure and physical technician presence | Rejection comfort alone at home; verbal vs digital compliance | Comprehension lab testing ($n=20$, Task 18) |
| **A009** | Doorstep cellular connectivity supports real-time push/socket quote delivery | Low-Med | `UNVALIDATED` | High-rise concrete shafts, basements, and dense urban flats across Indian metros | Latency distribution; packet loss at customer door | Technical field audit & offline cache implementation (`FR-13`) |
| **A010** | Itemized diagnosis will not drive disintermediation to offline mechanics | Medium | `PARTIALLY SUPPORTED` | Economic moat of 90-day warranty (`E048`) and prepaid diagnostic fee offset (`E041`) | Local price elasticity; customer willingness to risk unbacked repair | A/B experiment leak tracking (`19_metrics_framework.md`) |

---

*Stage: SCOPING → RESEARCH → SYNTHESIS → VALIDATION — Assumptions updated post-Task 19 Red-Team Review.*  
*Last updated: 2026-09-21*
