# Solution Architecture: Post-Diagnostic Decision Scaffold (PDDS)

**Co-Creators:** Anshul Eskey ([LinkedIn](https://www.linkedin.com/in/anshul-eskey-ba0821292/) | [Email](mailto:anshuleskey999@gmail.com)) & Sagun Verma ([LinkedIn](https://www.linkedin.com/in/sagun-verma-655a122a6/) | [Email](mailto:sagunv11@gmail.com))  
**Role:** Product Manager  
**Project:** Urban Company — Two-Sided Home Services Marketplace  
**Related Specs:** [PRD & Requirements](01_prd_post_diagnostic_scaffold.md) | [UX Wireframes](02_ux_flows_and_wireframes.md) | [Metrics & Experiment Design](01_metrics_and_experiment_design.md)  

---

> [!TIP]
> **Architecture Summary (TL;DR):** The PDDS architecture breaks down into **4 high-leverage Lean MVP primitives**: (1) Upstream expectation alignment (C1), (2) 3-tap technician quoting (C2), (3) real-time sunk-cost ledger (C3), and (4) tripartite choice card (Authorize, Decline, Clarify) (C4). In-app diagnostic summary and fee receipts are provided in MVP, while downloadable PDF certificates are de-scoped to Phase 2 per `THR-10`. Critical guardrail: 100% of diagnostic visitation fees pass through to the partner even upon repair decline (`FR-08`).

---

## 1. Executive Solution Overview & Conceptual Vision

This document translates the canonical strategy defined in [`15_product_strategy.md`](01_product_strategy_and_economics.md) into a comprehensive solution architecture: the **Post-Diagnostic Decision Scaffold (PDDS)**.

```
========================================================================================
                          POST-DIAGNOSTIC DECISION ARCHITECTURE
========================================================================================

   [ UPSTREAM EXPECTATION (O1) ]               [ ON-SITE DECISION SCAFFOLD (O4) ]
   ----------------------------                ----------------------------------
   Pre-Booking Mental-Model Alignment          In-Home Structured Decision Buffer
   
   +---------------------------+               +----------------------------------+
   | Stage 1: Physical Check   |               | 1. Inspection Finding Summary    |
   | (Fixed Visitation Fee)    |               |    (Objective hardware status)   |
   +---------------------------+               +----------------------------------+
                 |                                               |
                 v                                               v
   +---------------------------+               +----------------------------------+
   | Stage 2: Variable Repair  | ------------> | 2. Sunk-Cost & Fee Accounting    |
   | (Rate-Card Price Bands)   |               |    (Paid fee vs. Repair credit)  |
   +---------------------------+               +----------------------------------+
                                                                 |
                                                                 v
                                               +----------------------------------+
                                               | 3. Actionable Choice Interface   |
                                               |    [Proceed] [Decline] [Clarify] |
                                               +----------------------------------+
========================================================================================
```

The solution does **not** attempt to eliminate genuine physical repair uncertainty, which is an inescapable reality of appliance mechanics. Instead, it is designed to address **informational ambiguity, perceived sunk-cost pressure, and in-home negotiation tension** at the moment of quote delivery (DESIGN OBJECTIVE). Grounded in **D007**, the architecture is anchored primarily on **O4 (Accept/Reject Decision Support & Sunk-Cost Clarification)**, supported upstream by **O1 (Pre-Diagnostic Price Expectation & Cost Education)**.

---

## 2. Problem State at the On-Site Decision Moment

To build an effective solution architecture, we first map the hypothesized micro-friction that occurs at the in-home decision boundary:

```
[ Technician Disassembles Appliance ] 
                 |
                 v
[ Physical Fault Identified (e.g. PCB/Compressor) ]
                 |
                 v
   THE OBSERVED / HYPOTHESIZED FRICTION POINT (The "Verbal Standoff")
   -----------------------------------------------------------------
   * Technician states a rough verbal total (e.g., "It will cost ₹2,800").
   * Customer has anchored on the ₹299 booking/visitation fee paid at checkout.
   * Customer has no line-item visibility into parts cost vs. labor tiers.
   * Sunk-cost tension: Customer faces an upfront visitation fee policy (E041, FACT);
     qualitative reviews suggest this creates a perceived trap ("If I say no, I lose ₹299", R0163, HYPOTHESIS).
   * In-home context: Service occurs inside the private residence (E015, RESEARCH FINDING);
     we hypothesize this domestic setting inhibits direct verbal price challenge (ANALYST SYNTHESIS).
   * Customer either accepts resentfully or rejects hostily and defects offline (PAT-10, RESEARCH FINDING).
```

### 2.1 The Customer Dilemma (Segments 1 & 3)
* **First-Time Bookers (Segment 1):** Suffer from mental-model shock. Having booked an inspection for ₹199–₹299, an unexpected quote of ₹2,500 feels like an opportunistic platform "bait-and-switch" (`E014`, `RESEARCH FINDING`). Lacking familiarity with Urban Company's rate cards, they fear partner price-gouging.
* **Price-Sensitive Evaluators (Segment 3):** Suffer from economic evaluation paralysis. Qualitative reviews show customers actively calculate whether paying the mandatory diagnostic fee (`E041`, `FACT`) and calling a local neighborhood mechanic is cheaper (`PAT-10`, `R0070`, `R0163`, `RESEARCH FINDING`). Because the technician communicates a single lump sum verbally, the customer cannot evaluate whether the parts are genuine, whether the rate is official (`E040`, `FACT`), or whether warranty protection justifies the platform premium (`E048`, `COMPANY CLAIM`).

---

## 3. Desired Behavioral & User Outcomes (Preserving Customer Agency)

### 3.1 Hard Design Constraint: Preserving User Agency
> **The solution must NOT be an "acceptance-optimization engine" designed to manipulate customers into authorizing repairs.**

In physical services, a customer's decision to decline an uneconomical repair (e.g., repair cost exceeds depreciated appliance value) is a completely rational and legitimate choice. 
* A product that treats "quote accepted" as the sole measure of success will inevitably deploy dark patterns, conceal cancellation consequences, or guilt-trip customers with sunk fees.
* **Our goal is decision clarity and psychological safety, not forced conversion (DESIGN CONSTRAINT).** We hypothesize that a customer who declines a quote with transparent understanding, receives a written diagnostic report, and feels treated fairly is more likely to retain platform trust across other categories than a customer who felt pressured into an expensive repair (`HYPOTHESIS`, drawing on churn sentiment in `R0163`).

### 3.2 Target User State
Following the intervention, the customer should be able to state:
1. *"I know exactly what is broken in my machine."*
2. *"I know what the initial fee covered and how it applies to this quote."*
3. *"I see the exact rate-card price of the part versus the labor cost."*
4. *"I know my machine carries a warranty if repaired through the app."*
5. *"I feel completely free to decline without awkwardness or penalty."*

---

## 4. Solution Architecture & Evaluation of Candidate Concepts

In accordance with PM design rigor, we evaluated three distinct solution concepts before selecting the primary MVP architecture:

```
+---------------------------------------------------------------------------------------------------+
|                               EVALUATION OF SOLUTION CONCEPTS                                     |
+--------------------------+--------------------------+---------------------------------------------+
| Concept 1 (SELECTED MVP) | Concept 2 (REJECTED)     | Concept 3 (REJECTED)                        |
| The In-App Diagnostic    | Upstream Price-Banded    | Real-Time Two-Party Escrow                  |
| Decision Scaffold        | Booking with Fixed Tiers | & Phone Desk Arbitration                    |
+--------------------------+--------------------------+---------------------------------------------+
| Focus: In-home decision  | Focus: Heavy upfront     | Focus: Real-time human mediation            |
| interface clarifying     | pricing bands & mandatory| and escrow payment holding during           |
| scope, fee, and options. | pre-authorization caps.  | active quoting on-site.                     |
+--------------------------+--------------------------+---------------------------------------------+
```

### 4.1 Concept 1: The In-App Diagnostic Decision Scaffold (Selected MVP)
* **Description:** A dual-app quoting architecture. The technician selects diagnosed faults and required parts from a standardized catalog; the customer receives a structured, private digital card on their phone detailing diagnosis, line-item costs, visitation fee credit, warranty terms, and explicit choice buttons (`Authorize Repair`, `Decline & Pay Inspection Fee`, `Request Technician Explanation`).
* **Why Selected:** It directly targets the core problem (D005) at the actionable decision boundary (D007/O4), preserves customer agency as a design constraint, carries low-to-medium technical complexity, and avoids heavy operational overhead.

### 4.2 Concept 2: Upstream Price-Banded Booking with Mandatory Pre-Authorization (Rejected)
* **Description:** Requires customers at checkout to pre-authorize payment up to a category cap (e.g., ₹2,500 for AC repair). If the technician's diagnosis falls below the cap, work begins automatically without on-site consent.
* **Why Rejected:** Violates customer agency and intensifies top-of-funnel friction. Pre-authorizing large sums intimidates first-time bookers, contradicts the low-commitment nature of inspection bookings, and exacerbates customer fury if an unwanted repair is completed automatically.

### 4.3 Concept 3: Real-Time Two-Party Escrow & Human Phone Arbitration (Rejected)
* **Description:** Customers deposit funds into a platform escrow; if on-site price disputes arise, a live Urban Company desk supervisor dials into a three-way speakerphone call to arbitrate the quote.
* **Why Rejected:** Operationally complex and financially prohibitive. Staffing live human phone arbitrators would introduce heavy operational headcount costs, creating significant feasibility conflict with Urban Company's corporate strategy of narrowing losses and driving toward profitability (`E039`, `COMPANY CLAIM`; `ANALYST SYNTHESIS` rationale for deprioritizing O6) while adding unpredictable on-site delays for field technicians.

---

## 5. Conceptual Experience Architecture (The End-to-End Decision Journey)

The journey progresses across seven sequential steps, transitioning smoothly from upstream expectation setting to on-site decision execution:

```
                                  CONCEPTUAL EXPERIENCE JOURNEY
                                  
  [ Step 1: Upstream Context (O1) ]  --> Pre-booking two-stage model and indicative category ranges
                 |
                 v
  [ Step 2: Diagnostic Hand-off ]    --> Technician completes physical check; logs SKU on partner app
                 |
                 v
  [ Step 3: Diagnostic Comprehension]--> Customer receives structured "Diagnostic Finding" notification
                 |
                 v
  [ Step 4: Sunk-Cost Clarification] --> Customer reviews fee accounting (paid fee credited to repair)
                 |
                 v
  [ Step 5: Scope & Part Breakdown ] --> Line-item visibility: genuine parts, labor tier, warranty badge
                 |
                 v
  [ Step 6: Choice Exploration ]     --> Customer evaluates explicit paths without verbal coercion
                 |
                 v
  [ Step 7: Decision Execution ]     --> Customer taps Authorize or Decline; partner app state updates
```

### Step-by-Step Experience Walkthrough

* **Step 1: Upstream Expectation Alignment (O1 Complementary):**  
  At checkout, before confirming the booking, the customer views an informational module establishing the **Two-Stage Home Service Model**: (1) Physical Diagnostic Visit (₹199–₹299 inspection fee), followed by (2) Optional Repair Scope based on standardized rate cards. Historical category cost bands are displayed contextually (e.g., *"In 72% of AC cooling jobs, repairs range between ₹800–₹1,800 depending on spare parts"*).
* **Step 2: Diagnostic Completion & Digital Scope Hand-off:**  
  The technician disassembles the appliance in the home, identifies the defective component, and enters the diagnosis into the partner app by selecting standardized items from a simplified catalog (e.g., `Category: Refrigerator` $\rightarrow$ `Subsystem: Cooling` $\rightarrow$ `Part: Defrost Sensor`).
* **Step 3: Diagnostic Comprehension & Inspection Findings:**  
  A digital card is generated on the customer's mobile app: *"Diagnostic Complete: Your Refrigerator Defrost Sensor has failed."* The card explains in plain language what the component does and why replacement is necessary.
* **Step 4: Cost Composition & Sunk-Cost Clarification:**  
  The interface explicitly presents the financial ledger:
  * Amount Paid Upfront (Visitation Fee): **₹299**
  * Cost of Replacement Part: **₹650**
  * Labor Tier (Level 2 Repair): **₹350**
  * Applicable Taxes: **₹180**
  * Total Repair Quote: **₹1,180**
  * **Fee Treatment:** *"Your ₹299 inspection fee is fully credited toward this repair. Balance payable upon completion: ₹881."*
* **Step 5: Scope & Part-Level Repair Understanding:**  
  The customer sees that the part is backed by Urban Company's **30-to-90 Day Service & Parts Warranty** (`E048`) and verified against official platform rate cards (`E040`).
* **Step 6: Choice Exploration & Actionable Decision Threshold:**  
  The customer is provided an explicit, unpressured decision interface on their own device, containing three unambiguous options:
  1. **Authorize Repair (Pay Balance ₹881 upon completion):** Work begins immediately; warranty activated.
  2. **Decline Repair (Pay Only Diagnostic Fee ₹299):** Work halts; digital inspection report saved to account; partner paid diagnostic fee; no hostility.
  3. **Ask Technician for Clarification:** Prompts partner app with specific customer questions (e.g., *"Explain why replacement is needed over repair"*).
* **Step 7: Decision Execution & State Hand-off:**  
  When the customer makes their digital selection, the technician's phone buzzes with the confirmed status. If authorized, the technician begins repair. If declined, the job cleanly closes, the diagnostic fee receipt is generated, and the visit concludes without verbal haggling.

---

## 6. Key Solution Components & Information Taxonomy

### 6.1 Strict Information State Taxonomy
To ensure clarity, the architecture strictly categorizes all displayed data into three mutually exclusive information classes:

```
+---------------------------------------------------------------------------------------------------+
|                                  INFORMATION STATE TAXONOMY                                       |
+-----------------------------------+-----------------------------------+---------------------------+
| 1. KNOWN DATA                     | 2. UNKNOWN / VARIABLE DATA        | 3. CHOICE ARCHITECTURE    |
+-----------------------------------+-----------------------------------+---------------------------+
| * Amount already paid / authorized| * Hidden secondary failures only  | * Path A: Authorize full  |
|   (Visitation Fee: E041).         |   discoverable after primary part |   repair at quoted rate.  |
| * Diagnosed component failure     |   replacement (flagged clearly).  | * Path B: Decline repair; |
|   (verified physical finding).    | * Unconfirmed parts availability  |   pay only inspection fee.|
| * Standardized part cost (E040).  |   requiring secondary procurement.| * Path C: Request in-app  |
| * Labor tier allowance.           | * Variable aesthetic/pipe repair  |   scope clarification.    |
| * Official warranty duration.     |   beyond standard rate cards.     |                           |
+-----------------------------------+-----------------------------------+---------------------------+
```

### 6.2 Solution Component Profiles (MVP vs. Later-Stage Classification)

#### Component 1: Upstream Two-Stage Expectation Card (O1 Complementary) — `[MVP CORE]`
* **Scope Classification:** **`MVP CORE`**. Direct, low-complexity informational card integrated into the checkout flow to align customer expectations early.
* **User Need:** Understand before booking that home repairs cannot be priced with 100% certainty over the internet.
* **Product Purpose:** Align mental models at checkout; eliminate the false belief that ₹299 covers all repairs.
* **Information Shown:** Two-stage journey graphic; visitation fee definition; indicative category price bands based on historical median invoices.
* **Decision Supported:** Committing to an on-site diagnosis with aligned financial expectations.
* **Evidence Basis:** `E014` qualitative signal ($n=13$ pricing reviews), `E024`, `E025`, `E041`.
* **Key Uncertainty:** Does displaying historical price bands reduce top-of-funnel booking conversion?

#### Component 2: The Digital Diagnostic Finding Summary — `[MVP CORE]`
* **Scope Classification:** **`MVP CORE`**. Core prerequisite for cognitive grounding and informed customer consent.
* **User Need:** Proof that the technician actually diagnosed a genuine hardware problem rather than making up an arbitrary fix.
* **Product Purpose:** Translate physical machine failure into accessible plain-language diagnostics.
* **Information Shown:** Identified fault name; plain-language component role; symptom connection (e.g., *"Why your AC is not cooling"*); diagnostic photos uploaded by technician (optional for high-ticket parts).
* **Decision Supported:** Trusting that the physical diagnosis is legitimate.
* **Evidence Basis:** `PAT-09` (decoupling technician competence from billing friction), `E024`.
* **Key Uncertainty:** Will technicians reliably upload diagnostic photos or input accurate diagnostic descriptions?

#### Component 3: Line-Item Cost Composition & Sunk-Cost Ledger — `[MVP CORE]`
* **Scope Classification:** **`MVP CORE`**. Heart of the decision scaffold addressing the core problem (D005) and opportunity (D007).
* **User Need:** Total transparency on where their money goes and what happens to the money already paid.
* **Product Purpose:** Dissect the quote into parts, labor, and taxes, while explicitly crediting the upfront visitation fee.
* **Information Shown:** Upfront visitation fee (Paid); Replacement Part SKU cost; Labor tier cost; Taxes; Net balance payable. Explicit fee treatment: *"100% of your ₹299 inspection fee is deducted from this quote."*
* **Decision Supported:** Evaluating whether the incremental repair cost represents fair value.
* **Evidence Basis:** `E040` (granular rate cards), `E041` (visitation fee mechanics), `R0163` (sunk-cost rage).
* **Key Uncertainty:** Does seeing the breakdown of parts vs. labor increase price disputes if customers consider parts expensive?

#### Component 4: Standardized Rate-Card & Warranty Verification Badge — `[MVP CORE]`
* **Scope Classification:** **`MVP CORE`**. Essential for price-sensitive Segment 3 evaluators benchmarking against unorganized offline mechanics.
* **User Need:** Reassurance that the quote is official Urban Company pricing, not an arbitrary partner markup.
* **Product Purpose:** Defend the platform price premium over local mechanics (`PAT-10`) by attaching enforceable guarantees.
* **Information Shown:** "Official Rate-Card Verified" seal; 30-to-90 Day Service Guarantee badge (`E048`); terms of warranty exclusions (`E049`).
* **Decision Supported:** Deciding whether to proceed with Urban Company vs. hiring an outside unorganized mechanic.
* **Evidence Basis:** `E040`, `E048`, `E049`, `PAT-10`.
* **Key Uncertainty:** Does the presence of a 30-to-90 day warranty justify a 20–30% price premium for price-sensitive Segment 3 users?

#### Component 5: Multi-Option Actionable Choice Interface — `[MVP CORE / OPERATIONAL POLICY TBD]`
* **Scope Classification:** **`MVP CORE`** (Interface) / **`OPEN QUESTION`** (Operational Re-Visit Window).
* **User Need:** The ability to accept, decline, or pause the repair quote without feeling socially coerced in their home.
* **Product Purpose:** Provide an asynchronous digital decision buffer designed to reduce in-person pressure in the domestic environment (`E015`, `RESEARCH FINDING` on in-home personal vulnerability; `DESIGN OBJECTIVE`).
* **Information Shown:** Two primary action buttons of equal visual hierarchy: `Authorize Repair (Pay Net Balance later)` and `Decline Repair (Pay ₹299 Diagnostic Fee now)`; secondary link `Need Time to Decide / Ask Question`.
* **Decision Supported:** Making an unpressured, definitive accept or reject decision, or requesting time to deliberate.
* **Operational Mechanism (`THR-09` Resolution):** The interface provides a "Need Time to Decide" option allowing the customer to review the diagnosis and quote without verbal coercion. *Operational note:* The exact revisit window, redispatch protocol, and quote-lock duration are designated as **`[OPERATIONAL WINDOW / RE-VISIT POLICY TBD]`** requiring marketplace operations validation, rather than an arbitrary 2-hour SLA that breaks domestic reality.
* **Evidence Basis:** `E026` (precedent customer approval for AC gas, `FACT`), `E014` (fee surprise, `RESEARCH FINDING`), `E015` (in-home context, `RESEARCH FINDING`), `E041` (visitation fee policy, `FACT`).
* **Key Uncertainty:** Will making quote rejection frictionless on mobile depress technician job completion rates?

#### Component 6: Partner Quoting & Scope Input Module (Technician-Facing) — `[MVP STREAMLINED / LATER-STAGE ENABLERS DE-SCOPED]`
* **Scope Classification:** **`MVP STREAMLINED`**. Limited to a lightweight 3-tap diagnostic SKU picker mapped to top-20 high-frequency repair parts.
* **Scope De-Scoping Note (`THR-02`):** Complex production enablers—such as real-time multi-vertical dynamic catalog overhauls, offline Bluetooth P2P sync, and automated fraud-telemetry algorithms—are **explicitly de-scoped from the MVP** and moved to later-stage technical infrastructure.
* **User Need:** A fast, low-friction tool to log the on-site quote without typing long paragraphs with dirty hands.
* **Product Purpose:** Standardize field quoting and feed data into the customer's decision interface.
* **Information Shown:** Hierarchical diagnostic selector (System $\rightarrow$ Subsystem $\rightarrow$ SKU); pre-populated rate-card prices; simple toggle for common labor tiers.
* **Decision Supported:** Technician submitting an official quote to the platform for instant customer routing.
* **Evidence Basis:** `E040` (rate card catalog, `FACT`), `E026` (`FACT`), `E051` (partner agency sensitivity, `ANALYST SYNTHESIS`).
* **Key Uncertainty:** Can the partner UI be simplified enough to achieve $>90\%$ field compliance without verbal bypass?

---

## 7. Two-Sided Marketplace & Partner Experience Design

```
+---------------------------------------------------------------------------------------------------+
|                             CROSS-ACTOR MARKETPLACE IMPACT MATRIX                                 |
+--------------------------+---------------------------------+--------------------------------------+
| ACTOR                    | WHAT IMPROVES / VALUE CREATED   | POTENTIAL FRICTION / DESIGN MITIGATION|
+--------------------------+---------------------------------+--------------------------------------+
| **Customer**             | * Total price clarity.          | * Information overload if quote is   |
| (Segments 1 & 3)         | * Sunk-cost demystification.    |   over-complex $\rightarrow$ Use progressive |
|                          | * In-home decision agency       |   disclosure (DESIGN PROPOSAL).      |
|                          |   (DESIGN OBJECTIVE).           |                                      |
+--------------------------+---------------------------------+--------------------------------------+
| **Gig Professional**     | * Intended to reduce burden of  | * Fear of lost earnings from quote   |
| (Service Partner)        |   defending prices verbally     |   rejection $\rightarrow$ Proposed policy:   |
|                          |   (DESIGN GOAL).                |   ensure diagnostic fee pass-through |
|                          | * Proposed compensation for     |   (drawing on partner compensation   |
|                          |   diagnostic labor.             |   principle in E047, COMPANY CLAIM;  |
|                          |                                 |   DESIGN PROPOSAL).                  |
+--------------------------+---------------------------------+--------------------------------------+
| **Urban Company**        | * Clean digital job state logs. | * Technical catalog maintenance.     |
| (Platform)               | * Designed to reduce cash       | * Software development investment.   |
|                          |   leakage (HYPOTHESIS).         |                                      |
|                          | * Intended to protect multi-    |                                      |
|                          |   category LTV (HYPOTHESIS).    |                                      |
+--------------------------+---------------------------------+--------------------------------------+
```

### 7.1 Proposed Field Technician Workflow Specifications (Solution Requirements)
1. **Zero Essay Writing (Proposed Requirement):** Technicians should not be asked to write free-form diagnostic essays on-site. Quoting should rely on a maximum of **three taps** within hierarchical dropdowns or image selectors (`DESIGN SPECIFICATION`).
2. **Offline-Resilient Workflow (`THR-07` — Graceful Degradation):** Basements, utility balconies, and bathrooms often have weak cellular connectivity. The quoting tool workflow should degrade gracefully when connectivity is limited, relying on basic local caching and background queue synchronization. *Engineering note:* Specific offline/degraded-mode behavior requires engineering validation (`[DESIGN CONSTRAINT TO BE DETERMINED]`); custom peer-to-peer Bluetooth handshakes are de-scoped from the MVP.
3. **Partner Fee Pass-Through Economics (`THR-11` — Open Business Question):** When a customer declines a repair quote, the partner's financial compensation for diagnostic inspection labor represents an **`[OPEN BUSINESS QUESTION]`**. While inspired by the partner welfare principle in historical corporate disclosures (`E047` where cancellation fees were passed through to partners, `COMPANY CLAIM`), the exact commercial pass-through percentage, partner hourly earnings impact, and platform margin absorption under quote decline must be validated before rollout because the research available in this case does not expose Urban Company's internal payout contracts.
4. **No Rating Penalties for Customer Declines (Proposed Policy):** In home services, equipment is frequently unrepairable or uneconomical. The solution proposes that Urban Company should **not** penalize a partner's platform rating or dispatch priority if a customer declines a quote, provided the diagnostic report was completed accurately (`DESIGN PROPOSAL`). Penalizing partner conversion would incentivize high-pressure verbal coercion and fraud (`ANALYST SYNTHESIS`).

---

## 8. Comprehensive Failure Modes & Mitigation Framework

The table below analyzes the ten mandatory failure modes, their root causes, and explicit design mitigations:

| # | Failure Mode | Why It Could Happen | Evidence / Assumption Basis | Strategic Mitigation Concept | Leading Warning Signal |
|---|---|---|---|---|---|
| **1** | **Cognitive Overload** | Showing excessive technical jargon, part numbers, and multi-tier tax calculations overwhelms the user. | `ASSUMPTION`: Users want clarity, not an engineering manual. | Use progressive disclosure: show summary card first (Total + Diagnosis), with tap-to-expand for granular SKUs. | High time-on-screen (>5 mins) paired with elevated abandonment without decision. |
| **2** | **Quote Interpreted as Guaranteed Final Cost** | Disassembly reveals secondary hidden faults (e.g., rusted shaft discovered after motor removal). | `FACT`: Physical repairs frequently have contingent hidden scope. | Explicitly label contingent secondary risks upfront: *"Quote covers motor; secondary wear will be confirmed upon installation."* | Support tickets claiming "Price increased after I already approved the quote." |
| **3** | **Standardization Fails Across Categories** | AC repairs are highly standardized, but chimney or washing machine parts are wildly fragmented. | `FACT` (`E026` vs. diverse appliance market): Catalog fragmentation is high. | Provide standardized "General Repair / Component Labor" tiers where specific hardware SKUs are absent. | Technicians frequently selecting "Other / Unlisted Part" in the partner app. |
| **4** | **Partner Avoidance & Verbal Workarounds** | Technicians find mobile quote entry tedious and continue quoting verbally to save time. | `RESEARCH FINDING` (`PAT-09`, `E014` qualitative signal): Technicians prefer informal verbal agreements. | Block job completion and payment collection in the partner app until a digital quote has been acknowledged by the customer. | High variance between partner arrival time and digital quote generation timestamps. |
| **5** | **Rejection Spikes Without Improved Understanding** | Making rejection frictionless causes customers to decline legitimate, competitively priced repairs. | `HYPOTHESIS`: Reducing social duress may soften immediate job completion. | Prominently highlight the 30–90 day platform warranty and safety inspection value before the final decline tap. | Quote decline rate jumps by $>10\%$ while diagnostic customer satisfaction remains flat. |
| **6** | **Underlying Price Disputes Persist (Mechanism B)** | Customers understand the quote perfectly, but find official rate-card parts simply too expensive (`THR-05`). | `RESEARCH FINDING` (`PAT-10`): Customers benchmark against cheap, unorganized local mechanics. | Acknowledge that PDDS targets Mechanism A (uncertainty) and cannot eliminate Mechanism B (price elasticity). Transparently benchmark genuine OEM warranty value, but accept rational quote decline without resorting to coercive retention tricks. | Post-visit survey responses citing "Price too high" despite 5-star clarity ratings. |
| **7** | **Diagnostic-Fee Friction Persists** | Customer whose machine is declared "unrepairable" still resents paying the ₹299 inspection fee. | `FACT` (`E041`), `RESEARCH FINDING` (`R0163`): Paying for a broken appliance feels like extortion. | In MVP, deliver clear in-app diagnostic summary and itemized fee receipt explaining inspection labor delivered. *(Scope Note: Formal downloadable PDF 'Diagnostic Safety Certificate' is de-scoped to a later-stage hypothesis — `THR-10`).* | Support tickets demanding diagnostic fee refunds on unrepairable visits. |
| **8** | **Sunk-Cost Framing Interpreted as Coercion** | Customer feels that showing "₹299 paid" is an aggressive psychological trick to force them to proceed. | `ASSUMPTION`: Fee transparency must remain strictly neutral. | Use neutral accounting language ("Inspection labor fee paid") rather than loss-framing ("Don't lose your ₹299!"). | User feedback in research describing the interface as "pushy" or "manipulative." |
| **9** | **Catalog / Rate-Card SKU Mapping Failures** | Technician enters a non-standard part that fails to map to central rate cards, causing app errors. | `FACT` (`E040` covers common parts; rare parts unlisted). | Implement a rapid fallback to pre-approved "Custom Labor + Actual Part Invoice" workflow with customer sign-off. | App error telemetry showing quoting tool crash or fallback triggers. |
| **10** | **Escalation Becomes Support Bottleneck** | Customers tap "Request Clarification" expecting instant live human agent chat, overwhelming support. | `RESEARCH FINDING` (`E011`, `PAT-01`): Chatbot deflection is already a crisis. | Route clarification requests **directly to the technician's device on-site**, not to central remote customer support queues. | Surge in central ticket volume triggered from the on-site quoting interface. |

---

## 9. Measurement Architecture & Metric Hierarchy

To evaluate the solution empirically, we define a three-level measurement hierarchy. In accordance with evidence policy, all business outcomes are defined as **measurements and hypotheses**, not established facts.

```
========================================================================================
                          SOLUTION MEASUREMENT HIERARCHY
========================================================================================

  LEVEL 1: UNDERSTANDING & DECISION QUALITY
  -----------------------------------------
  * Quote Comprehension Score (%)        * Fee Treatment Recognition Rate (%)
  * Scope Distinction Accuracy (%)       * Decision Agency Score (CSAT 1-5)

                                 |
                                 v

  LEVEL 2: BEHAVIORAL OUTCOMES
  ----------------------------
  * Time-to-Decision (Minutes)           * On-Site Rejection Rate (%)
  * In-App Clarification Rate (%)        * Post-Quote Cancellation Dispute Rate (%)

                                 |
                                 v

  LEVEL 3: MARKETPLACE & BUSINESS HYPOTHESES
  ------------------------------------------
  * Legitimate Job Completion Rate (%)   * Partner Effective Hourly Take-Home (₹)
  * Off-Platform Defection Rate (Proxy)  * Cross-Category 90-Day Rebooking Rate (%)
========================================================================================
```

### 9.1 Level 1: Understanding & Decision Quality
1. **Quote Comprehension Score (%):**
   * *Definition:* Percentage of users in post-visit pulse surveys who correctly identify whether parts, labor, or both were included in their quote.
   * *Why It Matters:* Measures whether the interface successfully eliminated cognitive ambiguity.
   * *Caveat:* Relies on survey sampling; must be collected within 2 hours of visit completion.
2. **Fee Treatment Recognition Rate (%):**
   * *Definition:* Percentage of users who accurately report whether their upfront fee was credited toward the repair or retained for diagnosis.
   * *Why It Matters:* Validates whether the sunk-cost clarification mechanism worked.
3. **Decision Agency Rating (1–5 Scale):**
   * *Definition:* Customer response to: *"I felt empowered and unpressured in deciding whether to proceed with this repair."*
   * *Why It Matters:* Core user-agency check to confirm social duress was mitigated.

### 9.2 Level 2: Behavioral Outcomes
1. **Time-to-Decision (Minutes):**
   * *Definition:* Duration between digital quote presentation on customer app and tap on `Authorize` or `Decline`.
   * *Why It Matters:* Extremely short duration (<15 secs) suggests customer was coerced by partner; extremely long (>20 mins) suggests decision paralysis.
2. **On-Site Quote Rejection Rate (%):**
   * *Definition:* Proportion of generated quotes where customer chooses `Decline Repair`.
   * *Why It Matters:* Tracks whether clarifying the decline option impacts customer choice patterns.
   * *Caveat:* An increase in rejection is not necessarily bad if it reflects filtering out uneconomical repairs and preserving long-term trust.
3. **On-Site In-App Clarification Rate (%):**
   * *Definition:* Percentage of quoting events where customer triggers `Ask Technician for Clarification`.
   * *Why It Matters:* Identifies categories where standardized catalog descriptions are failing to explain faults.

### 9.3 Level 3: Marketplace & Business Outcomes (Hypotheses Under Test)
1. **Quote-Related Support Dispute Rate (%):**
   * *Definition:* Percentage of diagnosis-dependent bookings that generate customer support tickets regarding "overcharging," "fee surprises," or "unauthorized work."
   * *Hypothesis:* Will decrease significantly as line-item transparency removes the basis for disputes.
2. **Partner Diagnostic Workflow Duration (Minutes):**
   * *Definition:* Incremental time added to partner on-site duration specifically to log the digital quote.
   * *Guardrail Metric:* Must not add $>4$ minutes to on-site partner time.
3. **90-Day Cross-Category Repeat Booking Rate (%):**
   * *Definition:* Proportion of first-time bookers who book any Urban Company service within 90 days of an uncompleted (declined) repair visit.
   * *Hypothesis:* Preserving agency and transparency during a declined repair preserves platform relationship equity compared to current hostile exits (`R0163`).
4. **Partner Weekly Take-Home Pay (₹):**
   * *Guardrail Metric:* Partner earnings must not degrade as a result of digital quoting compliance.

---

## 10. Staged Experimentation & Validation Plan

To validate the solution safely without destabilizing field operations or partner earnings, we propose a four-stage rollout:

```
+---------------------------------------------------------------------------------------------------+
|                                   STAGED EXPERIMENTATION ROADMAP                                  |
+--------------------------+--------------------------+----------------------+----------------------+
| STAGE 1: COMPREHENSION   | STAGE 2: USABILITY &     | STAGE 3: CONTROLLED  | STAGE 4: MARKETPLACE |
| VALIDATION (Lab / Proto) | IN-HOME SHADOWING        | REGIONAL A/B TEST    | LIQUIDITY MONITORING |
+--------------------------+--------------------------+----------------------+----------------------+
| * Formative testing with | * Field shadowing with   | * 50/50 randomized   | * Full category roll |
|   first-time bookers.    |   technicians in 1 city. |   split in 2 metros. |   with supply guards.|
+--------------------------+--------------------------+----------------------+----------------------+
```

### Stage 1: Comprehension & Clarity Validation
* **Core Question:** Can first-time customers accurately understand the fee ledger and scope breakdown within 30 seconds of viewing the card?
* **Hypothesis:** A structured line-item card will achieve $>85\%$ comprehension on paid vs. additional amounts compared to $<40\%$ under baseline text summaries.
* **Evidence Needed:** Formative prototype testing with real home service users evaluating mock AC and refrigerator quotes.
* **Primary Metric:** Comprehension test score across 5 objective understanding questions.
* **Decision Rule:** Advance to Stage 2 only if $\ge 80\%$ of participants correctly identify fee crediting and warranty duration.

### Stage 2: In-Home Usability & Field Shadowing
* **Core Question:** Does the digital quoting flow work smoothly in the physical presence of a technician without creating social awkwardness or network timeouts?
* **Hypothesis:** Technicians can generate a digital quote in $<3$ minutes using the hierarchical selector; customers review and respond on their own device.
* **Evidence Needed:** 25 shadowed in-home visits in one pilot zone (e.g., Gurgaon Central) across AC and Washing Machine repairs.
* **Primary Metric:** Partner quote logging completion time; customer perceived awkwardness score.
* **Decision Rule:** Advance only if partner logging time is $<4$ minutes and no technical offline failures occur.

### Stage 3: Controlled Regional Product Experiment (A/B Test)
* **Core Question:** Does the Post-Diagnostic Decision Scaffold reduce billing dispute tickets and protect long-term retention without collapsing job completion?
* **Hypothesis:** Treatment arm will see a significant drop in billing dispute tickets with no statistically significant decline in partner weekly earnings.
* **Setup:** 50/50 randomized split of first-time diagnosis-dependent bookings across two mature service clusters for 6 weeks.
* **Primary Metric:** Post-service pricing dispute rate (`E014`).
* **Guardrail Metrics:** Partner job completion rate (cannot drop by $>5\%$); top-of-funnel booking conversion (for O1 module); Partner weekly earnings.
* **Decision Rule:** Scale treatment platform-wide if pricing disputes decrease by $\ge 20\%$ while partner earnings remain neutral.

### Stage 4: Marketplace Guardrail & Supply Liquidity Monitoring
* **Core Question:** Does platform-wide rollout trigger partner evasion or geographic supply reallocations?
* **Monitoring:** Weekly cohort tracking of partner app compliance rates, off-platform cash leakage proxies, and warranty claim volumes.

---

## 11. MVP vs. Later-Stage Scope Boundaries

To prevent scope creep and ensure rapid, high-confidence delivery, features are strictly partitioned:

```
+---------------------------------------------------------------------------------------------------+
|                                  MVP VS. LATER-STAGE SCOPE MATRIX                                 |
+----------------------------------------------------+----------------------------------------------+
| IN MVP SCOPE (Phase 4 Immediate Delivery)          | LATER-STAGE ROADMAP (Post-Validation)        |
+----------------------------------------------------+----------------------------------------------+
| * O1 Upstream Informational Card at Checkout.      | * Real-time dynamic category price-estimator |
| * Partner 3-tap hierarchical SKU quoting module.   |   using machine-learning computer vision.    |
| * Customer Line-Item Cost & Sunk-Cost Ledger Card. | * Automated appliance trade-in / replacement |
| * Explicit Authorize vs. Decline digital buttons.  |   commerce engine for unrepairable units.    |
| * Official Rate-Card & Warranty Verification Badge.| * Video-consultation second-opinion channel. |
| * Automated visitation fee crediting logic.        | * Downloadable PDF Diagnostic Safety Cert    |
| * Direct on-site partner clarification trigger.    |   (`THR-10` de-scoped from MVP).             |
| * In-app diagnostic summary & fee receipt.         | * Complex multi-stage diagnostic holds.      |
+----------------------------------------------------+----------------------------------------------+
```

---

## 12. Canonical Traceability Matrix & Audit of Inherited Claims

### 12.1 Traceability Matrix
Every architectural component of this solution traces back to locked project decisions, canonical evidence IDs, and product strategy principles:

| Solution Architecture Element | Decision Anchor | Primary Evidence Base | Product Strategy Anchor (`15_product_strategy.md`) |
|---|---|---|---|
| **Upstream Expectation Card** | [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (O1) | `E014` (expectation shock, `RESEARCH FINDING`), `E024` (`FACT`), `E025` (`FACT`), `E041` (`FACT`) | Section 5: Complementary Role of Opportunity 1 |
| **Digital Diagnostic Finding** | [`D005`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) | `PAT-09` (technician vs billing, `RESEARCH FINDING`), `E024` (`FACT`) | Section 4.1: Cognitive Grounding |
| **Sunk-Cost & Fee Ledger** | [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (O4) | `E041` (`FACT`), `R0163` (`RESEARCH FINDING`), `E047` (`COMPANY CLAIM`) | Section 4.2: Sunk-Cost Neutralization |
| **Rate-Card & Warranty Badge** | [`D006`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (Segment 3) | `E040` (`FACT`), `E048` (`COMPANY CLAIM`), `E049` (`FACT`), `PAT-10` (`RESEARCH FINDING`) | Section 4.1: Scope & Cost Demarcation |
| **Multi-Option Choice Interface**| [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (O4) | `E026` (`FACT`), `E015` (in-home context, `RESEARCH FINDING`) | Section 4.3: Asynchronous In-Home Agency |
| **Partner Quoting Module** | [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) | `E008` (`COMPANY CLAIM`), `E040` (`FACT`), `E051` (`ANALYST SYNTHESIS`) | Section 6.1: Partner Perspective & Payouts |

### 12.2 Explicit Audit of Inherited Strategic Claims
To prevent ungrounded assertions from leaking into solution design, we explicitly audit claims inherited from strategy:
1. *Inherited Statement:* "Without compromising technician earnings."  
   *Audit Verdict:* **Design intention and constraint, NOT an established fact.** If quote rejection increases, partner earnings could fall unless offset by proposed diagnostic fee pass-through (drawing on the partner compensation principle in historical company claim `E047`, `DESIGN PROPOSAL`) and increased daily job throughput. Partner weekly earnings is strictly designated as a **Level 3 Guardrail Metric** in our experimentation plan.
2. *Inherited Statement:* "Mitigates off-platform leakage (`PAT-10`)."  
   *Audit Verdict:* **Behavioral hypothesis under evaluation.** We do not have internal telemetry proving that warranty badging eliminates cash side-deals. It remains a hypothesis (`H3`) to be tested in regional pilots.
3. *Inherited Statement:* "Preserves long-term platform trust and retention."  
   *Audit Verdict:* **Long-term strategic hypothesis.** The causal link between on-site decision clarity and 90-day repeat booking is an empirical question tracked via Level 3 measurement, not an assumed certainty.
4. *Inherited Statement:* "Customers feel trapped by diagnostic fees (`E041`)."  
   *Audit Verdict:* **Analyst synthesis and behavioral hypothesis.** `E041` is a verified `FACT` confirming the existence of a mandatory visitation fee policy when repairs are declined. However, interpreting this mechanism as creating an acute "customer trap" is an `ANALYST SYNTHESIS`, supported qualitatively by community complaints (`R0163`, `E014`), not an established factual property of the policy itself.
5. *Inherited Statement:* "Social duress prevents on-site price challenge (`E015`)."  
   *Audit Verdict:* **Analyst synthesis.** `E015` is a `RESEARCH FINDING` establishing that services take place inside the customer's private residence, creating personal vulnerability and expectations of safety. While we hypothesize that this domestic setting creates social awkwardness and inhibits aggressive verbal price haggling, the existence of acute "social duress" is an `ANALYST SYNTHESIS` and behavioral hypothesis, not an experimentally proven fact.

---

*End of Solution Design. This canonical document formally anchors Task 15 (UX Flows & Teardown), Task 16 (PRD), and Phase 4 execution.*
