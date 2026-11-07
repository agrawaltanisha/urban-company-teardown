# PM-01 — Urban Company
## 12 — Behavioral User Segmentation

**Project:** PM-01 (Urban Company)  
**Task:** Task 10 — Behavioral User Segmentation  
**Stage:** ANALYSIS (Phase 3)  
**Status:** CANONICAL — LOCKED BY HUMAN DECISION (D006)  
**Decision Owner:** HUMAN (Project Owner)  
**Canonical Problem Direction:** Post-Diagnostic Price Uncertainty ([`11_problem_definition.md`](02_problem_definition.md) / [`D005`](04_decision_log.md))  
**Primary Target Segment:** Segment 1 — First-Time Diagnosis-Dependent Bookers  
**Secondary Business-Risk Segment:** Segment 3 — Price-Sensitive Quote Evaluators  
**Last Updated:** 2026-09-18  

---

## 1. Governance, Principles & Evidence Constraints

### 1.1 Canonical Problem Anchor
This segmentation is strictly anchored to the canonical problem statement locked in Task 9:

> **"For customers booking diagnosis-dependent home services, the final cost can become uncertain after booking because the exact scope of work is determined only after on-site inspection, while the diagnostic/visitation cost and subsequent repair quote affect the customer's ability to confidently decide whether to proceed."**

### 1.2 Behavioral Segmentation Principles
In accordance with PM portfolio governance and product discovery standards:
1. **Behavioral & Contextual, Not Demographic:** Segmentation is defined strictly by observable actions, service needs, decision context, and response to price uncertainty. No segment is defined by age, gender, geography, income, or lifestyle persona.
2. **Zero Primary Interview Evidence (`GAP-008`):** Due to strict geographic and feasibility constraints, zero live customer interviews were conducted. There are no fabricated personas, simulated user quotes, or synthetic interview transcripts. All behavioral patterns are synthesized from the audited 179-review dataset, product walkthrough observations, and official platform documentation.
3. **Sample-Only Scope:** Review findings (`E001`–`E019`) describe the audited dataset ($N=179$) only. Frequency percentages (e.g., $25.7\%$ pricing mentions in `E004`) reflect sample prominence, not platform-wide population prevalence.
4. **Separation of Booking-Stage Checkout Discrepancy (`E022`):** The ₹99 checkout-stage discrepancy observed in `E020`–`E022` is preserved as a separate pre-payment phenomenon and is **not** used as direct evidence of on-site post-diagnostic pricing uncertainty.
5. **No Solution Bias or "Lock-In" Claims:** Diagnostic and visitation fees (`E041`) are treated as operational business mechanisms rather than intentional "predatory traps" or "lock-in" mechanisms. No solution concepts or feature designs are introduced here.
6. **Human Decision Governance (Task 10.4):** The selection of a single primary target segment is explicitly reserved for the Human Project Owner in Section 4 (`D006`).

---

## 2. Behavioral Segment Definitions

Below are five distinct behavioral segments reflecting different user expectations, decision contexts, and reactions to post-diagnostic price uncertainty in diagnosis-dependent home services.

---

### ==Segment 1: First-Time Diagnosis-Dependent Bookers==

#### Definition
Customers who have never booked a complex, diagnosis-dependent service on Urban Company. They enter the booking flow anchoring heavily on the nominal visitation/inspection fee displayed at checkout, assuming that it either covers the primary repair or that any additional costs will be minor. When the technician completes the on-site inspection and presents an itemized repair estimate for spare parts or specialized labor, these customers experience acute friction because they lacked an upfront mental model for the two-stage quoting structure.

#### Defining Behaviors
* Booking an appliance or repair service with incomplete visibility into final total cost.
* Anchoring expectations to the initial checkout amount or nominal inspection charge.
* Expressing surprise or distress when the technician opens the machine and states that spare parts/gas refilling are required.
* Hesitating at the accept/reject threshold because paying the visitation fee without completing the repair feels like an unrecoverable loss.

#### Trigger / Situation
An essential household appliance (e.g., AC, refrigerator, washing machine, water purifier) malfunctions, and the customer lacks a trusted personal technician, turning to Urban Company for the first time for a professional diagnosis.

#### Job to Be Done (JTBD)
* **Functional:** "When an essential household appliance breaks down and I have no trusted local technician, I want to book a vetted professional to inspect the issue, so I can understand what is broken and get it repaired without being overcharged."
* **Emotional:** Relieve anxiety about equipment failure while avoiding being taken advantage of by an unfamiliar service provider in their home.

#### Price / Trust Trigger
* **Trust Anchor:** Clear upfront communication of what the visitation fee covers and transparent notice that physical parts require separate quotes.
* **Friction Trigger:** The technician verbally announcing a large repair cost on-site without immediate visible proof that the quote matches official platform rates (`E024`).

#### Problem Relevance
This segment experiences post-diagnostic price uncertainty as a **mental-model breakdown**. Because they do not anticipate scope discovery on-site, the shift from a nominal booking fee to a multi-thousand rupee repair quote feels like an unexpected escalation, making the accept/reject decision stressful.

#### Evidence Mapping
* `E041` (`FACT`): Urban Company enforces a visitation/diagnostic fee policy when a customer declines work after inspection.
* `E024` (`FACT`): Help Center FAQ explicitly advises customers on how to verify quotes inside the app.
* `E025` (`FACT`): Official FAQ explains policy on extra charges for spare parts.
* `E014` (`RESEARCH FINDING (community)`): Reviews document customers feeling surprised by post-booking add-ons and parts pricing (`R0058`, `R0090`).
* `E004` (`FACT`): Baseline pricing theme prevalence in $25.7\%$ of reviews ($n=46/179$).

#### Main Risk If Underserved
* **Directly Observed in Reviews:** Customer leaves a negative review complaining of unexpected costs or high charges for minor work (`R0090`).
* **Inference:** Customer perceives the platform as opaque and declines future bookings for complex repair categories.
* **Hypothesis:** Early-lifecycle churn driven by negative first-impression pricing friction.

#### Evidence Confidence
* **Phenomenon Existence:** **High** (Two-stage quoting structure and visitation fees are verified platform facts `E041`, `E024`).
* **Behavioral Interpretation:** **Medium** (Inferred from review text reflecting expectation-vs-reality gaps).
* **Population Prevalence:** **Low / Unmeasured** (Platform-wide proportion of first-time repair bookers is unobserved).

---

### Segment 2: Experienced / Repeat Diagnosis-Dependent Customers

#### Definition
Customers who regularly use Urban Company across service verticals (e.g., grooming, routine cleaning) and are familiar with the app interface, but book diagnosis-dependent categories expecting strict rate-card standardization, professional predictability, and verified digital workflows. When a diagnosis reveals substantial scope expansion, they evaluate the quote not with naive shock, but with scrutiny against published platform rate cards and service warranty guarantees.

#### Defining Behaviors
* Booking diagnosis-dependent services with an existing baseline expectation of platform quality and digital process.
* Insisting on seeing official in-app quotes rather than accepting verbal technician estimates (`E024`).
* Checking whether replacement parts are eligible for platform warranty coverage (`E048`, `E049`).
* Decoupling their evaluation of the technician's manual skill from the platform's pricing/billing policies (`PAT-09`, `E019`).

#### Trigger / Situation
Scheduled seasonal servicing (e.g., pre-summer AC servicing, water filter cartridge replacement) where routine cleaning transitions into unexpected component replacement (e.g., gas leak detected, PCB fault).

#### Job to Be Done (JTBD)
* **Functional:** "When my regular household appliances need maintenance or troubleshooting, I want an Urban Company professional to diagnose the system against published rate cards, so I can authorize necessary repairs without manual negotiation or suspicion of inflated billing."
* **Social / Emotional:** Retain confidence that paying a premium for Urban Company over the unorganized market delivers verified parts, safety, and price standardization.

#### Price / Trust Trigger
* **Trust Anchor:** Technician immediately generating a structured in-app quote matching published rate-card amounts (`E040`) and outlining warranty protection (`E048`).
* **Friction Trigger:** Technician demanding off-app payments, failing to log parts in the app, or quoting rates that contradict official rate cards (`R0073`, `R0092`).

#### Problem Relevance
For repeat customers, post-diagnostic price uncertainty threatens **platform credibility**. These users expect Urban Company to eliminate unorganized market haggling; when on-site scope discovery feels uncontrolled, the platform's core value proposition of standardized pricing degrades.

#### Evidence Mapping
* `E040` (`FACT`): Urban Company publishes granular rate cards for standardized parts (e.g., capacitors, PCB repairs).
* `E026` (`FACT`): Walkthrough confirms formal quote-and-approval policy for variable scope (e.g., AC gas refilling).
* `E018` (`RESEARCH FINDING (community)`): Repeat customers articulate clear expectations of service continuity and familiar standards ($n=7/14$).
* `E019` (`RESEARCH FINDING (community)`): Reviewers actively decouple ratings, praising technician craft while penalizing unexpected platform fees (`R0074`, `R0092`).
* `E048` (`COMPANY CLAIM`): 30-to-90 day service warranty on appliances.

#### Main Risk If Underserved
* **Directly Observed in Reviews:** Rating degradation on 4-star reviews where satisfied users dock stars specifically for unexpected fee additions (`E019`, `R0092`).
* **Inference:** Repeat users downgrade Urban Company to low-complexity categories (e.g., haircuts) while taking major appliance repairs to authorized brand service centers.
* **Hypothesis:** Gradual reduction in multi-category customer lifetime value.

#### Evidence Confidence
* **Phenomenon Existence:** **High** (Rate cards `E040` and quote approval flows `E026` are verified).
* **Behavioral Interpretation:** **High** (Strong verbatim evidence in `E019` showing repeat/discerning customers evaluating billing rigor).
* **Population Prevalence:** **Low / Unmeasured** (Repeat booking rate within repair categories is unknown).

---

### Segment 3: Price-Sensitive Quote Evaluators

#### Definition
Customers who book diagnosis-dependent services on Urban Company primarily for diagnostic convenience or lack of immediate alternatives, but maintain active mental comparisons with the local unorganized market (neighborhood electricians, local mechanics, independent spare parts shops). When presented with an on-site post-diagnostic repair quote, they rigorously calculate whether the quoted amount justifies platform convenience or whether paying the visitation fee and executing the repair through an outside technician is more economical.

#### Defining Behaviors
* Inquiring about parts pricing, labor costs, and rate breakdowns immediately upon diagnosis.
* Comparing the technician's post-diagnostic quote against prior experience or outside price estimates.
* Actively weighing the sunk cost of the diagnostic fee (`E041`) against potential cost savings from outside repair.
* Directly communicating willingness to switch to local mechanics if the quote feels excessive (`PAT-10`).

#### Trigger / Situation
A major appliance breakdown requiring costly parts replacement (e.g., AC compressor or PCB replacement, washing machine motor repair) where the estimated repair cost represents a substantial fraction of the appliance's replacement value.

#### Job to Be Done (JTBD)
* **Functional:** "When an appliance requires a major repair quote after on-site inspection, I want transparent and itemized price justification, so I can verify whether the quote is competitive with the broader market before deciding whether to proceed or hire an alternative provider."
* **Emotional:** Protect personal/household budget from financial exploitation while retaining the power to walk away from an uncompetitive quote.

#### Price / Trust Trigger
* **Trust Anchor:** Transparent, competitive rate cards showing line-item part costs and labor fees, coupled with clear warranty backing that local mechanics cannot offer.
* **Friction Trigger:** Opaque bundled quotes, perceived markups on commodity spare parts, or pressure to decide immediately on-site before researching prices.

#### Problem Relevance
This segment represents the **focal point of the accept/reject decision boundary**. When post-diagnostic uncertainty is high, these customers are the most likely to decline the quote, absorb the visitation fee (`E041`), and hire an external provider, or negotiate off-platform with the technician (`PAT-10`).

#### Evidence Mapping
* `PAT-10` (`RESEARCH FINDING (community)`): Customers explicitly cite substituting Urban Company with local mechanics when charges feel inflated (`R0070`, `R0113`, `R0163`).
* `E014` (`RESEARCH FINDING (community)`): Reviewers report feeling overcharged for parts and minor fixes relative to independent alternatives (`R0090`, `R0163`).
* `E040` (`FACT`): Published rate cards establish benchmark prices for specific repairs.
* `E041` (`FACT`): Mandatory visitation fee charged if customer rejects post-inspection repair.

#### Main Risk If Underserved
* **Directly Observed in Reviews:** Explicit customer defection to offline mechanics (`R0163`: *"Called another mechanic from outside and he did it 200"*).
* **Inference:** High rate of quote rejections and offline disintermediation (customer and technician agreeing to do the job off-platform for cash).
* **Hypothesis:** Revenue loss from aborted jobs where Urban Company captures only a low-margin visitation fee.

#### Evidence Confidence
* **Phenomenon Existence:** **High** (Substitution behavior and price comparison are explicitly documented in `PAT-10`).
* **Behavioral Interpretation:** **High** (Direct verbatim references to outside pricing in `R0070`, `R0163`).
* **Population Prevalence:** **Low / Unmeasured** (Quote rejection frequency across the platform is unquantified).

---

### Segment 4: Urgent / Time-Pressured Repair Customers

#### Definition
Customers facing an acute domestic emergency caused by a sudden equipment failure (e.g., AC failure during extreme heat, refrigerator breakdown threatening perishable food, primary geyser failing in winter). For these users, speed of diagnosis and immediate same-day resolution are paramount. However, when faced with an escalated post-diagnostic quote, their high urgency forces them to accept the quote under duress, creating acute latent resentment if they subsequently feel the technician exploited their urgent vulnerability.

#### Defining Behaviors
* Selecting the earliest available booking slot regardless of potential peak or surge pricing.
* Prioritizing same-day repair completion and immediate on-site parts availability over price shopping.
* Accepting post-diagnostic quotes rapidly under time pressure, even when the quoted amount exceeds initial expectations.
* Expressing post-service anger or leaving negative reviews if the repair proves defective or if the charge felt extortionate after the emergency passes.

#### Trigger / Situation
A sudden household failure that halts essential domestic routines and requires immediate physical intervention within hours.

#### Job to Be Done (JTBD)
* **Functional:** "When an essential household appliance suffers an urgent breakdown disrupting my home, I want an on-site professional to diagnose and resolve the issue immediately, so I can restore domestic normalcy as quickly as possible."
* **Emotional:** Achieve rapid relief from domestic disruption and stress, while avoiding the feeling of being coerced into an inflated price due to lack of time.

#### Price / Trust Trigger
* **Trust Anchor:** Punctual arrival, rapid accurate diagnosis, immediate parts availability, and clear upfront explanation of emergency/parts fees before starting.
* **Friction Trigger:** Technician taking advantage of household urgency to inflate repair costs or failing to complete the repair despite collecting the diagnostic fee.

#### Problem Relevance
This segment experiences post-diagnostic price uncertainty as **coercive pressure**. Because rejecting the quote means starting over with an alternative service provider and delaying resolution, these customers feel forced to accept high quotes on-site, leading to severe trust erosion.

#### Evidence Mapping
* `E014` (`RESEARCH FINDING (community)`): Reviews document customers feeling exploited by inflated charges for rapid or minor fixes (`R0090`: ₹350 for 2-minute work).
* `E017` (`RESEARCH FINDING (community)`): Punctuality and swift problem resolution are the primary anchors of positive satisfaction ($n=41/93$, `R0001`).
* `E026` (`FACT`): Platform mandates customer approval before high-variable work (e.g., gas refills), which creates a pause even during urgent service.
* `E041` (`FACT`): Sunk diagnostic fee compounds pressure to resolve the issue immediately.

#### Main Risk If Underserved
* **Directly Observed in Reviews:** Severe dissatisfaction post-service where customers complain of being overcharged under distress (`R0090`).
* **Inference:** Customer uses Urban Company only as an emergency backup rather than a trusted primary provider.
* **Hypothesis:** High post-service refund requests or charge disputes through payment channels.

#### Evidence Confidence
* **Phenomenon Existence:** **High** (Emergency breakdown dynamics and rapid repair needs are standard home-service contexts).
* **Behavioral Interpretation:** **Medium** (Inferred from reviews emphasizing urgency, minor work charges, and speed).
* **Population Prevalence:** **Low / Unmeasured** (Proportion of bookings driven by emergency vs. scheduled maintenance is unquantified).

---

### Segment 5: Post-Surprise Recovery Customers

#### Definition
Customers who have experienced an unexpected post-diagnostic quote escalation, disputed an on-site charge, or declined a repair quote and are now attempting to navigate platform support, verify quote accuracy, or contest an unfulfilled job fee. This segment represents users in active conflict with the platform's diagnostic-and-quoting mechanics, seeking human escalation, fee refunds, or reassurance that rate cards were followed.

#### Defining Behaviors
* Initiating in-app support chats to dispute an on-site quote or unexpected extra charge.
* Requesting itemized invoice verification or rate-card audits for spare parts installed.
* Attempting to escalate past the automated chatbot to reach a human support supervisor (`PAT-01`, `E011`).
* Refusing to pay or demanding a refund of the diagnostic/visitation fee (`E041`) when a service could not be completed.

#### Trigger / Situation
An on-site diagnosis resulted in an unresolved conflict: the technician demanded an unexpected fee, the quote was rejected but the visitation fee was charged, or an installed part failed immediately without clear warranty recourse.

#### Job to Be Done (JTBD)
* **Functional:** "When I experience an unexpected charge, disputed quote, or failed repair after an on-site diagnosis, I want transparent price verification and responsive human escalation, so I can obtain an explanation, a fair adjustment, or a refund."
* **Emotional:** Regain a sense of justice and platform accountability after feeling mistreated in their private home.

#### Price / Trust Trigger
* **Trust Anchor:** Transparent, frictionless audit of the technician's quote against official rate cards and rapid fee reconciliation.
* **Friction Trigger:** Encountering rigid AI chatbot loops that deflect the dispute, repeat canned text, and block telephone or human escalation (`PAT-01`, `E011`).

#### Problem Relevance
This segment represents the **downstream behavioral crisis** of the locked problem. When post-diagnostic price uncertainty is handled poorly on-site, the customer escalates into the recovery journey; if support fails to provide price clarity or resolution, brand trust collapses entirely.

#### Evidence Mapping
* `E011` / `PAT-01` (`RESEARCH FINDING (community)`): Automated AI chatbot deflection blocks human escalation on financial and service disputes in $21.6\%$ of negative reviews ($n=11/51$, `R0071`, `R0116`, `R0117`, `R0170`).
* `E025` (`FACT`): Help Center specifically includes "What if I am being charged extra?" guidance.
* `E041` (`FACT`): Visitation fee enforcement mechanism creates dispute triggers when customers feel inspection was inadequate.
* `E016` (`RESEARCH FINDING (community)`): Unresolved post-repair disputes when secondary breakdowns occur ($n=6/51$, `R0118`, `R0166`).

#### Main Risk If Underserved
* **Directly Observed in Reviews:** Extreme anger, app uninstallation threats, and public accusations of unethical business practices (`R0117`, `R0170`).
* **Inference:** Permanent customer defection to competitors or offline alternatives.
* **Hypothesis:** Escalation into formal consumer protection complaints or social media backlash.

#### Evidence Confidence
* **Phenomenon Existence:** **High** (Support deflection on disputes is verified in `E011` and `PAT-01`).
* **Behavioral Interpretation:** **High** (Verbatim review evidence confirms dispute escalation paths).
* **Population Prevalence:** **Low / Unmeasured** (Total proportion of disputed quotes across the platform is internal operational data).

---

## 3. Segment Comparison Matrix

The table below contrasts the five behavioral segments across operational, psychological, and evidence dimensions without ranking or declaring a single preferred cohort.

| Dimension | Segment 1: First-Time Bookers | Segment 2: Repeat / Experienced | Segment 3: Price-Sensitive Evaluators | Segment 4: Urgent / Time-Pressured | Segment 5: Post-Surprise Recovery |
|---|---|---|---|---|---|
| **Core Behavior** | Anchors on nominal fee; blindsided by two-stage quoting | Scrutinizes rate cards and in-app quote logging | Compares quote against offline market; calculates trade-off | Prioritizes immediate fix; accepts quote under time duress | Disputes quote, demands fee refund, or seeks quote audit |
| **Triggering Context** | Appliance breakdown; no personal technician | Routine maintenance or seasonal servicing | Major component failure with high part replacement costs | Critical domestic failure disrupting daily living | Post-diagnosis conflict or fee dispute |
| **Primary JTBD** | Find vetted help without being overcharged | Get standardized maintenance without haggling | Verify quote competitiveness vs. local market | Restore appliance functionality immediately | Obtain fair audit, adjustment, or refund |
| **Sensitivity to Price Uncertainty** | High (Expectation shock) | Moderate (Rate-card compliance focus) | Very High (Economic calculation boundary) | High during quoting, but masked by urgency | Very High (Active grievance state) |
| **Key Trust Anchor** | Upfront explanation of two-stage pricing | In-app quote generation and warranty coverage | Granular itemized rate card vs. market parity | Swift arrival and immediate parts availability | Transparent quote audit and human escalation |
| **Relevance to Locked Problem** | Direct (Exposes mental-model gap in quoting flow) | Direct (Exposes quote compliance and rate-card integrity) | Direct (Represents core accept/reject decision boundary) | Direct (Represents accept-under-duress dynamic) | Downstream (Represents resolution failure after quoting friction) |
| **Evidence Strength** | Medium (`E014`, `E024`, `E041`) | High (`E018`, `E019`, `E026`, `E040`) | High (`PAT-10`, `E014`, `E040`, `E041`) | Medium (`E014`, `E017`, `E041`) | High (`E011`, `PAT-01`, `E025`, `E041`) |
| **Key Uncertainty** | First-time booker drop-off rate | Repeat booking frequency in repair categories | Quote rejection rate and offline defection volume | Emergency vs. planned booking ratio | Escalation rate as % of completed diagnoses |

---

## 4. D006 — Primary Segment Selection

**Status:** DECIDED BY HUMAN (Project Owner)  
**Decision Date:** 2026-09-18  
**Associated Decision Log Entry:** [`D006`](04_decision_log.md)

### Strategic Selection

* **PRIMARY TARGET SEGMENT:**  
  **Segment 1 — First-Time Diagnosis-Dependent Bookers**
  * **Human Decision Rationale:** First-time diagnosis-dependent customers experience post-diagnostic price uncertainty at the earliest stage of their relationship with Urban Company, where it can disrupt their mental model of how diagnosis, visitation fees, repair scope, and final pricing work. Solving the problem upstream has the potential to strengthen initial trust and establish more predictable expectations for future usage.
  * **Explicit Evidence Boundary:** The project does **NOT** currently have evidence proving that this problem causes churn, retention loss, or conversion loss; these outcomes remain unproven hypotheses.

* **SECONDARY BUSINESS-RISK SEGMENT:**  
  **Segment 3 — Price-Sensitive Quote Evaluators**
  * **Rationale for Secondary Status:** This segment sits directly at the quote accept/reject boundary and has the clearest observed connection to price comparison, substitution, and potential offline defection (`PAT-10`). However, quote rejection frequency and the magnitude of associated business impact remain unmeasured.

### Candidate Trade-off & Decision Evaluation Matrix

| Candidate Segment | Strategic Status & Evaluation | Trade-offs & Considerations | Critical Evidence Gap |
|---|---|---|---|
| **Segment 1: First-Time Diagnosis-Dependent Bookers** | **SELECTED AS PRIMARY** (Addresses top-of-funnel expectation setting and early trust breakdown) | Upstream UX/education intervention; does not automatically resolve partner-level quoting deviations | No internal data on first-time customer drop-off or post-booking conversion rates |
| **Segment 2: Experienced / Repeat Customers** | Considered (High LTV; values standardization and rate-card adherence) | Repeat users may already possess some familiarity with diagnostic fee mechanics | Platform repeat booking rates in appliance repair categories are unknown (`GAP-004`) |
| **Segment 3: Price-Sensitive Quote Evaluators** | **SELECTED AS SECONDARY BUSINESS-RISK** (Directly captures the accept/reject threshold and offline substitution risk) | Secondary focus to prevent over-indexing on price elasticity rather than trust and expectation clarity | Quote rejection frequency and offline leakage volume are unquantified |
| **Segment 4: Urgent / Time-Pressured Repair Customers** | Considered (Acute domestic crisis and accept-under-duress dynamic) | Highly situational behavior driven by external crisis rather than structural platform expectations | Proportion of repair volume driven by emergency vs. scheduled needs is unobserved |
| **Segment 5: Post-Surprise Recovery Customers** | Considered (Resolves acute downstream dispute and support deflection friction) | Downstream symptom mitigation; reactive rather than preventive | Dispute volume and chatbot containment efficiency metrics are unknown (`GAP-002`) |

---

## 5. Assumptions, Unknowns & Methodological Audit

### 5.1 Key Assumptions
* `A-SEG-01`: Customers in diagnosis-dependent categories exhibit distinct behavioral decision modes (e.g., comparing vs. urgent) rather than uniform price tolerance.
* `A-SEG-02`: On-site quoting friction is a primary driver of quote rejection, rather than customer realization that the appliance is beyond economical repair.
* `A-SEG-03`: The physical presence of a technician in the home creates social and sunk-cost pressure that amplifies price uncertainty.

### 5.2 What Remains Unproven
1. The exact percentage breakdown of Urban Company repair bookings across these five behavioral cohorts.
2. The empirical quote rejection rate following on-site diagnosis.
3. The true rate of offline disintermediation (customers paying technicians cash off-platform).
4. Whether addressing post-diagnostic uncertainty for one segment inadvertently creates friction for another (e.g., requiring more digital quote approvals for urgent users).

### 5.3 Research Integrity Confirmation
* **Zero Fabrication:** No user interviews, participant quotes, or survey statistics were invented.
* **Evidence Traceability:** Every evidence ID referenced (`E004`, `E011`, `E014`, `E016`, `E017`, `E018`, `E019`, `E024`, `E025`, `E026`, `E040`, `E041`, `E048`, `E049`) exists in [`05_evidence_matrix.md`](data/evidence_matrix.md).
* **Isolation of `E022`:** The ₹99 checkout difference is preserved as a separate booking phenomenon and not conflated with post-diagnostic repair uncertainty.
* **Human Decision Formalized:** D006 finalized by Human Project Owner (Segment 1 Primary; Segment 3 Secondary).

---

*End of User Segmentation Document. Canonical segmentation anchors Task 11 (Opportunity Analysis).*

