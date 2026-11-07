# UX Wireframes & Interaction Flows: Post-Diagnostic Decision Scaffold (PDDS)

**Co-Creators:** Anshul Eskey ([LinkedIn](https://www.linkedin.com/in/anshul-eskey-ba0821292/) | [Email](mailto:anshuleskey999@gmail.com)) & Sagun Verma ([LinkedIn](https://www.linkedin.com/in/sagun-verma-655a122a6/) | [Email](mailto:sagunv11@gmail.com))  
**Role:** Product Manager  
**Project:** Urban Company — Two-Sided Home Services Marketplace  
**Related Specs:** [PRD Specification](01_prd_post_diagnostic_scaffold.md) | [Solution Architecture](01_solution_design_architecture.md) | [Executive Case Study](01_executive_case_study.md)  

---

> [!TIP]
> **UX Summary (TL;DR):** This document details the end-to-end user and partner experience, mapping the "Before" (awkward verbal standoff, hidden math, pressure to say yes) against the "After" (automated push notification, 3-tap technician quoting, clear net payable math with inspection fee credit, and structured digital choice).

---

## 1. Executive Summary & Purpose

This document makes concrete the architectural shift established in [`16_solution_design.md`](01_solution_design_architecture.md) by contrasting the **Current User & Partner Experience** against the **Proposed Post-Diagnostic Decision Scaffold (PDDS)**.

```
====================================================================================================
                               THE CORE UX TRANSFORMATION
====================================================================================================

  CURRENT JOURNEY (Observed / Inferred / Unknown Friction Boundary):
  -------------------------------------------------------------------
  [ Checkout: ₹199-₹299 Fee ] ---> [ Partner Arrives & Inspects ] ---> [ On-Site Decision Friction ]
  * Low upfront fee paid           * Physical diagnosis required        * Inferred verbal quote
  * Unclear repair expectations    * In-home private space (E015)       * Sunk fee in diagnosis (E041)
  * No itemized scope card         * Partner app UI unobserved (GAP-009)* Binary coerce / abandon

                                            │
                                            ▼

  PROPOSED JOURNEY (Post-Diagnostic Decision Scaffold):
  ------------------------------------------------------
  [ Upstream Expectation (O1) ] -> [ Diagnostic Hand-off ] -> [ Line-Item Decision Scaffold (O4) ]
  * 2-stage model disclosed        * Partner logs 3-tap SKU    * Objective hardware finding
  * Indicative cost bands          * Rate card mapped (E040)   * Paid fee credited to balance
  * Inspection fee defined         * Offline-resilient sync    * Equal Agency: Accept/Decline/Clarify
====================================================================================================
```

### 1.1 Scope Boundaries & Non-Negotiable Constraints
* **No UI Polish / Wireframe Sprawl:** This document specifies structural, interaction, information, and behavioral states—not final CSS styling or visual design (`DESIGN CONSTRAINT`).
* **No Solution Redesign:** The solution architecture remains anchored to the Post-Diagnostic Decision Scaffold selected in Task 14 (`16_solution_design.md`).
* **Preservation of Locked Decisions:** [`D005`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (Problem), [`D006`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (Segments), and [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (Opportunity) remain fixed.

---

## 2. Epistemic Labeling & Evidence Grounding Rules

In strict compliance with [`EVIDENCE_POLICY.md`], every journey step, system state, and interaction in this artifact is classified under one of four mutually exclusive epistemic states:

1. **`[OBSERVED CURRENT STATE]`:** Grounded in direct, firsthand visual observation from product teardowns, official policy pages, or verified review data (`S005`, `S006`, `S007`–`S013`, `05_evidence_matrix.md`). Cited with exact evidence IDs (e.g., `E024`, `E026`, `E040`, `E041`).
2. **`[INFERRED CURRENT STATE]`:** Logical reconstruction of operational, physical, or behavioral steps that must occur between observed digital screens (e.g., physical mechanical disassembly of appliances), but were not directly visible in captured customer mobile screenshots.
3. **`[UNKNOWN CURRENT STATE]`:** Operational or platform mechanisms where the current evidence base does not provide direct visibility (e.g., partner app internal quoting UI, whether partner app pushes a quote in certain verticals, on-site payment collection mechanism).  
   > [!IMPORTANT]
   > **Epistemic Rule:** Never use an inference to imply the absence of a product capability. The absence of a screen in a customer walkthrough indicates it was not observed, but does not definitively prove the platform lacks that capability in live operations.
4. **`[PROPOSED STATE]` / `[DESIGN PROPOSAL]` / `[DESIGN SPECIFICATION]`:** Forward-looking product mechanics, system behaviors, and partner workflows designed in [`16_solution_design.md`](01_solution_design_architecture.md) to address the locked problem.

---

## 3. Current-State End-to-End User Flow (As-Is Journey)

The current journey for diagnosis-dependent services (e.g., AC breakdown, refrigerator cooling failure, washing machine spin issue) is reconstructed below across nine conceptual stages:

```
================================================================================================================================================================
                                                  CURRENT-STATE DIAGNOSIS-DEPENDENT USER JOURNEY
================================================================================================================================================================
[ Stage 1: Discovery ] ──> [ Stage 2: Booking Expectation ] ──> [ Stage 3: Pro Assignment ] ──> [ Stage 4: On-Site Diagnosis ] ──> [ Stage 5: Visitation Fee ]
                                                                                                                                           │
                                                                                                                                           ▼
[ Stage 9: Work / Exit ] <── [ Stage 8: Accept / Reject / Clarify ] <── [ Stage 7: Evaluation Paralysis ] <── [ Stage 6: Repair Quote Delivery ]
================================================================================================================================================================
```

### 3.1 Step-by-Step Interaction Matrix (Current Experience)

| Stage | User Action | System / Platform State | Partner Action | Information Available to User | Uncertainty Introduced | Evidence Basis | Friction / Risk |
|---|---|---|---|---|---|---|---|
| **1. Service Discovery & Category Selection** | Browses Urban Company home screen; selects repair category (e.g., "AC Service & Repair"). | Displays service cards, marketing banners, and service scope descriptions (`S005`). | Passive / Unassigned. | Category description, starting price or inspection fee teaser (`S005`). | Whether the displayed price represents full repair or merely an inspection. | `[OBSERVED CURRENT STATE]` (`S005`, p. 11, `E026`) | Customer may anchor on low headline number. |
| **2. Booking & Checkout Expectation** | Adds "Check-up / Inspection" or service package to cart; selects date/time slot; accepts terms. | Checkout screen shows amount payable (e.g., ₹199–₹299); references T&Cs, Privacy, Cancellation Policy (`S005`). | Passive / Unassigned. | Line-item for inspection fee; total checkout price; slot confirmation (`S005`). | Potential gap between checkout total and subsequent payment total (`E022`); total repair cost unknown. | `[OBSERVED CURRENT STATE]` (`S005`, p. 23, `E023`, `E022`) | **Expectation Mismatch:** User assumes booking guarantees a complete fix for the checkout fee (`E014`). |
| **3. Professional Assignment** | Waits for scheduled appointment slot. | System matches order to local gig partner; triggers push notification with partner profile (`S006`). Cancellation fee policy activates (`E027`). | Receives dispatch notification on partner app; accepts gig; blocks calendar time (`E027`). | Partner name, rating, arrival window. Cancellation policy applies if cancelled now (`E027`). | Exact arrival punctuality; partner capability; scope of inspection. | `[OBSERVED CURRENT STATE]` (`S006`, p. 1, `E027`, `E028`) | User cancellation penalty risk activated upon assignment (`E027`). |
| **4. On-Site Physical Inspection** | Welcomes partner into private residence; describes appliance symptoms. | System state: "Partner Arrived" or "Job In Progress" (`S005`). | Partner physically inspects and diagnoses appliance. | None digital; partner may explain physical actions verbally. | What the partner is checking; whether partner diagnostics are accurate or fabricated. | `[OBSERVED CURRENT STATE]` (`E015`, `S005`; in-home setting verified); `[INFERRED CURRENT STATE]` (physical disassembly necessitated by appliance mechanics) | Domestic intrusion anxiety (`E015`); inability to verify technical competence independently. |
| **5. Diagnostic / Visitation Charge Trigger** | Listens as partner concludes physical inspection. | **In specified repair flows**, platform policy defines a diagnostic/visitation fee if the customer does not proceed with the repair quote (`E041`, `FACT`). | Partner concludes diagnostic step; determines required parts and labor. | Policy states visitation fee is chargeable if work is declined in specified flows (`E041`). FAQ mentions quote verification (`E024`). | How the visitation fee interacts with subsequent repair charges; whether fee is credited or forfeited. | `[OBSERVED CURRENT STATE]` (`S009`, `E041` in specified repair flows; `E024`, `E025`) | **Sunk-Cost Tension:** In specified categories, customer realizes walking away leaves them responsible for the fee without repair (`E041`, `FACT`; perceived "trap" is a qualitative hypothesis from `R0163`). |
| **6. Repair Recommendation & Quote Delivery** | Asks partner: *"How much will this cost?"* | System maintains static FAQ guidance ("We'll provide a quote and only refill/repair after your approval", `E026`). Digital quote screen not observed in walkthrough. | Partner communicates quote to customer (inferred as verbal on-site communication based on review descriptions; exact transmission channel unobserved). | Unitemized total quote from technician. AC rate card lists fixed part prices (`E040`), but not shown inline in app. | Breakdown of parts vs. labor; whether rate is official platform pricing or partner markup (`E040`). | `[OBSERVED CURRENT STATE]` (`E026`, `E040`, `E024`); `[INFERRED CURRENT STATE]` (verbal quote delivery); `[UNKNOWN CURRENT STATE]` (whether partner app pushes quotes digitally) | **Informational Asymmetry:** No line-item transparency; customer suspects opportunistic gouging (`E014`). |
| **7. Customer Evaluates Quote** | Pauses; mentally compares quote against appliance age and personal budget; feels awkward in partner's presence. | `[UNKNOWN CURRENT STATE]`: Whether customer app displays active prompts during in-home diagnosis. Static booking status visible in `S005`. | Partner waits inside user's private residence (`E015`, `FACT`); interpersonal dynamic inferred. | Memory of quote; external local repair heuristics noted in reviews (`PAT-10`); FAQ accordion in help tab (`E024`, `E025`). | True market value of repair; warranty coverage terms (`E048`, `E049`); consequences of refusal. | `[OBSERVED CURRENT STATE]` (`E015`, `E024`, `E025`); `[INFERRED CURRENT STATE]` (evaluation pause); `[QUALITATIVE FINDING]` (`PAT-10`) | **Negotiation Tension:** Customer experiences social awkwardness challenging the quote in-person (`E015`). |
| **8. Customer Decision (Accept / Reject / Clarify)** | Customer either: (A) agrees, (B) tries to negotiate, or (C) declines repair. | `[UNKNOWN CURRENT STATE]`: Partner app mechanics and job status transition workflow unobserved in `S005`/`S006`. | Partner proceeds with repair or packs tools and requests diagnostic fee payment in specified repair flows (`E041`). | Stated warranty coverage of 30–90 days on invoice items (`E033`, `E034`, `E048`). | Whether unrecorded verbal agreements will be honored under warranty (`E034`); fee receipt delivery. | `[OBSERVED CURRENT STATE]` (`E034`, `E041` in specified categories); `[UNKNOWN CURRENT STATE]` (partner status transition) | If declined, visit may end in mutual friction; customer resents paying fee without repair (`R0163`). |
| **9. Work Execution or Contentious Exit** | Customer pays for repair or pays visitation fee; inspects machine; rates partner. | Final invoice generated; excludes items not captured on platform (`E034`). Support chat deflects disputes (`E011`). `[UNKNOWN CURRENT STATE: Payment collection channel]`. | `[UNKNOWN CURRENT STATE: Partner operational mechanics upon job completion or decline]`. | Final invoice (digital); automated rating prompt (`S005`). Help & Support menu accessible (`E029`). | Whether warranty is valid if unrecorded charges occurred; recourse for defective work (`E016`). | `[OBSERVED CURRENT STATE]` (`S006`, `E034`, `E011`, `E016`); `[UNKNOWN CURRENT STATE]` (payment collection mechanism) | Community reviews include cases describing switching to neighborhood mechanics in contexts involving fee inflation or unresolved disputes (`PAT-10`, `R0070`, `R0163`, `RESEARCH FINDING`); warranty risk (`E034`). |

### 3.2 Category-Specific Variations in the Current Flow
* **AC Repair & Gas Refill:** Official policy specifically states: *"Gas refilling (if required): We'll provide a quote and only refill after your approval"* (`E026`, `FACT`). Rate cards publish explicit tiers (e.g., Inverter PCB repair ₹4,500, capacitor ₹250; `E040`, `FACT`).
* **High-Value Painting / Renovation (Macro-Projects):** Employs an explicit consultation visit and a **35% upfront phased escrow** for jobs $\ge \text{₹25,000}$ (`E042`, `FACT`). Confirms Urban Company recognizes the friction of post-booking pricing in large jobs, but does not deploy this mechanism for daily appliance repairs.
* **Cleaning & Quick Tasks (e.g., Insta Help):** Fixed deterministic pricing at checkout; diagnostic escalation rarely occurs, though surge fees and platform fees still trigger user surprise (`E014`, `FACT`).

---

## 4. Current-State Pain Points & Friction Moments (D005 / O4 Focus)

The current experience exhibits friction at six specific decision boundaries, directly driving the core problem defined in [`D005`](../04_Product_Strategy_and_Prioritization/04_decision_log.md):

```
====================================================================================================
                              CURRENT-STATE FRICTION TAXONOMY
====================================================================================================

  1. UPSTREAM MENTAL-MODEL ANCHORING
     Checkout fee (₹199-₹299) anchors expectation; user assumes it covers basic repair labor (E014).
     
  2. THE BURIED RATE-CARD PARADOX
     Rate cards exist in platform policies (E040), but are buried in FAQ accordions during 
     the active booking and quoting journey (E024, E025).
     
  3. THE VERBAL STANDOFF IN THE DOMESTIC ENVIRONMENT
     Technician communicates repair quote verbally; customer is forced into real-time in-person 
     negotiation inside their own private home (E015).
     
  4. SUNK-COST PERCEPTION & VISIT EXIT FRICTION
     In specified repair flows, the visitation fee policy (E041) is interpreted in reviews as 
     creating a perceived "trap" (R0163); declining feels like throwing money away.
     
  5. UNVERIFIABLE WARRANTY BOUNDARY
     Warranty strictly excludes items not captured on official invoice (E034); community reviews 
     report turning to local mechanics (PAT-10), risking unrecorded repairs and warranty loss.
====================================================================================================
```

1. **Mental-Model Shock (Booking to Diagnosis):**  
   First-time bookers (Segment 1) book an inspection for ₹199–₹299 without understanding that home diagnostics are non-deterministic. When presented with a substantial on-site repair quote that exceeds the initial visitation fee, they may perceive an unexpected cost inflation (`E014`, `RESEARCH FINDING`).
2. **Diagnostic vs. Repair Cost Ambiguity:**  
   In specified repair categories, the platform defines a visitation fee policy (`E041`, `FACT`). However, captured customer walkthrough screens (`S005`) do not display dynamic inline explanation of how that fee interacts with subsequent repair quotes (i.e., whether it is absorbed into repair labor or billed as an additive surcharge).
3. **Absence of Standardized On-Site Scope Demarcation:**  
   In unitemized quotes, the customer has no line-item visibility into how much of the quoted amount represents standardized replacement parts versus labor tiers (e.g., distinguishing an Inverter PCB repair at ₹4,500 from a minor capacitor at ₹250 under `E040`, `FACT`).
4. **Domestic Negotiation Vulnerability:**  
   Because the service takes place in the private home (`E015`, `RESEARCH FINDING`), the physical presence of the technician creates social pressure (`ANALYST SYNTHESIS`). Customers feel uncomfortable rejecting a tradesperson who has disassembled their appliance across their kitchen or living room floor (`R0163`).
5. **Sunk-Cost Resentment on Decline:**  
   In specified repair flows where a diagnostic fee applies (`E041`, `FACT`), paying an inspection fee when an appliance is deemed unrepairable or the quote is declined can generate customer resentment (`R0163`, `HYPOTHESIS`). Community reviews include cases describing switching to neighborhood mechanics in contexts involving fee inflation or perceived diagnostic dead ends (`PAT-10`, `R0070`, `R0163`, `RESEARCH FINDING`).
6. **Information Deflection in Support:**  
   If the customer seeks clarification on whether the quote is official, support directs them to static FAQs (`E024`, `E025`) or deflection chatbots (`E011`), providing zero real-time decision support.

---

## 5. Proposed-State End-to-End User Flow (To-Be Journey)

The proposed experience implements the **Post-Diagnostic Decision Scaffold (PDDS)** defined in [`16_solution_design.md`](01_solution_design_architecture.md). It transforms the ambiguous verbal interaction into a transparent, unpressured digital decision across eight structured stages:

```
================================================================================================================================================================
                                                  PROPOSED-STATE DECISION-SCAFFOLDED JOURNEY
================================================================================================================================================================
[ Step 1: Upstream Context (O1) ] ──> [ Step 2: Diagnostic Hand-Off ] ──> [ Step 3: Diagnostic Comprehension ] ──> [ Step 4: Sunk-Cost Ledger ]
                                                                                                                                │
                                                                                                                                ▼
[ Step 8: Post-Decision State ] <── [ Step 7: Unpressured Choice ] <── [ Step 6: Choice Exploration ] <── [ Step 5: Scope & Rate-Card Card ]
================================================================================================================================================================
```

### 5.1 Step-by-Step Interaction Matrix (Proposed Experience)

#### Step 1: Upstream Expectation Alignment (Complementary O1 Anchor)
* **User Goal:** Book an appliance inspection with realistic expectations of diagnosis and variable repair scope.
* **Information Presented:**
  * `[KNOWN]`: Mandatory physical inspection fee (₹299); technician background check guarantee (`E008`).
  * `[UNKNOWN / VARIABLE]`: Physical failure mode cannot be verified prior to on-site testing.
  * `[CHOICE]`: Confirm booking with two-stage model awareness, or select fixed preventative maintenance package.
  * *Contextual Display:* Indicative category repair bands based on historical median invoices (e.g., *"In AC cooling inspections, common repairs range between ₹800–₹1,800 depending on spare parts"*).
* **Product Behavior:** Displays inline **Two-Stage Home Service Card** in checkout before payment authorization (`DESIGN PROPOSAL`).
* **Partner Behavior:** None (system automated dispatch).
* **Decision Supported:** Committing to an on-site diagnostic visit with aligned financial expectations.
* **Relevant Strategy / Evidence Basis:** [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (O1), `E014` (mitigates price surprise, `RESEARCH FINDING`), `E024`, `E025`, `E041` (in specified repair flows, `FACT`).
* **Uncertainty Remaining:** Does indicative range anchoring slightly depress top-of-funnel booking conversion? (Tracked via Level 3 Guardrail).

#### Step 2: Diagnostic Hand-Off & Digital Logging
* **User Goal:** Allow technician to perform physical check-up while remaining informed of diagnostic progress.
* **Information Presented:**
  * `[KNOWN]`: Partner has arrived and begun physical diagnostic inspection.
  * `[UNKNOWN / VARIABLE]`: Appliance internal physical condition.
  * `[CHOICE]`: Observe physical disassembly or attend to household duties.
* **Product Behavior:** App state updates to: *"Technician Diagnosing Appliance — You will receive an official inspection report and quote on your phone shortly"* (`DESIGN PROPOSAL`).
* **Partner Behavior:** Performs physical diagnostic testing; opens partner app; logs findings using a **3-tap hierarchical selector** (`Category` $\rightarrow$ `Subsystem` $\rightarrow$ `Fault/Part SKU`) (`DESIGN SPECIFICATION`).
* **Decision Supported:** Partner transitioning from physical inspection to official platform record.
* **Relevant Strategy / Evidence Basis:** [`D005`](../04_Product_Strategy_and_Prioritization/04_decision_log.md), `E040` (rate card catalog, `FACT`), `E051` (partner workflow ease, `ANALYST SYNTHESIS`).
* **Uncertainty Remaining:** Can field technicians achieve $>90\%$ app compliance across diverse Indian metros without reverting to verbal quotes?

#### Step 3: Diagnostic Comprehension & Inspection Findings
* **User Goal:** Understand what is actually broken inside the machine in accessible, plain language.
* **Information Presented:**
  * `[KNOWN]`: Identified component failure (e.g., "Inverter PCB - Micro-controller Circuit Burnout"); appliance sub-assembly affected.
  * `[UNKNOWN / VARIABLE]`: Latent secondary electrical damage (flagged if contingent).
  * `[CHOICE]`: Review technical summary or expand for diagnostic details.
  * *Plain-Language Explanation:* Explains component role (e.g., *"The PCB controls compressor speed; without it, cooling does not trigger"*).
* **Product Behavior:** Pushes structured **Diagnostic Finding Notification** to customer app (`DESIGN PROPOSAL`).
* **Partner Behavior:** Cleans hands, steps back to provide physical space, allows customer to review phone.
* **Decision Supported:** Customer evaluating whether physical diagnosis is credible and legitimate.
* **Relevant Strategy / Evidence Basis:** `PAT-09` (decoupling technician skill from billing friction, `RESEARCH FINDING`), `E024` (quote verification, `FACT`).
* **Uncertainty Remaining:** Will non-technical customers understand component descriptions without requesting long verbal debates?

#### Step 4: Sunk-Cost & Financial Ledger Clarification
* **User Goal:** See exactly what the repair will cost and understand what happened to the ₹299 visitation fee already paid.
* **Information Presented:**
  * `[KNOWN]`:
    * Upfront Visitation Fee Paid: **₹299**
    * Required Replacement Part (OEM PCB): **₹2,200**
    * Standard Labor Tier (Level 2 Repair): **₹350**
    * Applicable GST (18% on Labor): **₹63**
    * Total Gross Repair Quote: **₹2,613**
    * **Fee Deduction Credit:** **-₹299** (100% of diagnostic fee credited toward repair)
    * **Net Balance Payable Upon Completion:** **₹2,314**
  * `[UNKNOWN / VARIABLE]`: None for primary scope.
  * `[CHOICE]`: Proceed to review warranty and decision options.
* **Product Behavior:** Renders the **Interactive Sunk-Cost & Fee Ledger** with explicit arithmetic clarity (`DESIGN PROPOSAL`).
* **Partner Behavior:** Awaits customer digital confirmation; does not quote arbitrary verbal numbers.
* **Decision Supported:** Customer evaluating true incremental cash outlay versus walking away.
* **Relevant Strategy / Evidence Basis:** [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (O4), `E041` (fee policy in specified flows, `FACT`), `R0163` (sunk-cost frustration, `RESEARCH FINDING`), `E047` (partner compensation principle, `COMPANY CLAIM`).
* **Uncertainty Remaining:** Does itemizing labor vs parts increase customer pushback on part costs?

#### Step 5: Scope Demarcation, Rate-Card & Warranty Verification
* **User Goal:** Verify that pricing is official Urban Company standard and determine if repair includes warranty protection.
* **Information Presented:**
  * `[KNOWN]`: "Official Rate-Card Verified" badge (`E040`); 30-to-90 Day Service & Parts Warranty seal (`E048`); explicit exclusion terms (`E034`, `E049`).
  * `[UNKNOWN / VARIABLE]`: Part availability timeline (defaults to "On-Truck" or specifies "Procurement Required: 2 hours").
  * `[CHOICE]`: Evaluate platform premium vs. unorganized local alternatives.
* **Product Behavior:** Displays official rate-card assurance seal and binds quote to platform invoice warranty (`DESIGN PROPOSAL`).
* **Partner Behavior:** Ready to answer specific scope inquiries if prompted.
* **Decision Supported:** Justifying platform price premium over neighborhood unorganized mechanics (`PAT-10`).
* **Relevant Strategy / Evidence Basis:** `E040` (`FACT`), `E048` (`COMPANY CLAIM`), `E049` (`FACT`), `PAT-10` (`RESEARCH FINDING`).
* **Uncertainty Remaining:** Does a 90-day warranty overcome price sensitivity for Segment 3 customers facing a platform premium?

#### Step 6: Choice Exploration & Asynchronous Decision Buffer
* **User Goal:** Evaluate options without feeling rushed or socially coerced in their own home.
* **Information Presented:**
  * `[KNOWN]`:
    * Option A: Authorize Repair $\rightarrow$ Work begins immediately; pay ₹2,314 balance upon completion; 90-day warranty activated.
    * Option B: Decline Repair $\rightarrow$ Work stops; machine safely reassembled; pay only ₹299 inspection fee; digital diagnostic summary saved to account.
    * Option C: Need Time to Decide / Request Clarification $\rightarrow$ Allows customer to pause the decision without immediate verbal pressure. *Operational Note (`THR-09`):* Exact operational revisit window and quote-lock policy are designated as **`[OPERATIONAL WINDOW / RE-VISIT POLICY TBD]`** requiring marketplace operations validation, rather than an arbitrary 2-hour SLA.
  * `[CHOICE]`: Select Option A, B, or C with **identical visual weight and zero dark-pattern coercion**.
* **Product Behavior:** Renders **Multi-Option Actionable Choice Interface** on customer device (`DESIGN PROPOSAL`).
* **Partner Behavior:** Remains available on-site in a non-confrontational posture while customer reviews phone.
* **Decision Supported:** Making a conscious, unforced commitment decision or pausing with operational boundaries.
* **Relevant Strategy / Evidence Basis:** [`D005`](../04_Product_Strategy_and_Prioritization/04_decision_log.md), [`D006`](../04_Product_Strategy_and_Prioritization/04_decision_log.md), `E015` (mitigating domestic negotiation vulnerability, `RESEARCH FINDING`), `E026` (`FACT`).
* **Uncertainty Remaining:** Will average customer decision time create excessive idle wait time for field technicians?

#### Step 7: Unpressured Decision Execution
* **User Goal:** Execute choice cleanly with instant digital acknowledgement.
* **Information Presented:**
  * If Authorize tapped: Confirmation modal: *"Repair Authorized — Balance ₹2,314 payable after physical testing."*
  * If Decline tapped: Confirmation modal: *"Repair Declined — Pay ₹299 Diagnostic Fee. Your machine will be safely reassembled. In-app diagnostic summary issued."*
  * If Need Time / Clarify tapped: Customer can review structured FAQs or indicate they need time to evaluate (`[OPERATIONAL POLICY TBD]`).
* **Product Behavior:** Instantly transmits state transition to partner application (`DESIGN PROPOSAL`).
* **Partner Behavior:** Phone vibrates with unambiguous instruction: `START REPAIR`, `REASSEMBLE & COMPLETE INSPECTION`, or `AWAIT CUSTOMER REVIEW`.
* **Decision Supported:** Definitive operational hand-off without verbal haggling.
* **Relevant Strategy / Evidence Basis:** `E026` (customer consent precedent, `FACT`), `E041` (in specified repair flows, `FACT`).
* **Uncertainty Remaining:** Does eliminating social friction lead to an immediate spike in quote rejections? (Monitored via Level 2 metrics).

#### Step 8: Post-Decision State & Job Closure
* **User Goal:** Complete transaction smoothly and receive proof of service delivered.
* **Information Presented:**
  * If Authorized: Real-time repair progress; final invoice generation; digital payment link; 90-day warranty registration (`E033`).
  * If Declined: Digital Diagnostic Finding Summary & itemized fee receipt delivered in-app; receipt confirms ₹299 diagnostic labor; partner rating specifically protected from decline bias (`DESIGN PROPOSAL`). *(Scope Note: Downloadable PDF Diagnostic Safety Certificate is de-scoped from MVP as a later-stage hypothesis — `THR-10`).*
* **Product Behavior:** Issues invoice/summary; credits partner account; safely archives diagnostic data for future bookings (`DESIGN PROPOSAL`).
* **Partner Behavior:** Completes repair or reassembles appliance; collects designated digital payment; departs professionally.
* **Decision Supported:** Closing the service interaction with dignity and platform trust intact.
* **Relevant Strategy / Evidence Basis:** `E034` (`FACT`), `E047` (partner compensation principle, `COMPANY CLAIM`), `R0163` (mitigating churn, `HYPOTHESIS`).
* **Uncertainty Remaining:** Does delivering an in-app diagnostic summary successfully reduce customer resentment regarding the ₹299 diagnostic fee?

---

## 6. Preserving Customer Agency: Hard Design Constraint & Anti-Pattern Rules

A core mandate of [`15_product_strategy.md`](01_product_strategy_and_economics.md) and [`16_solution_design.md`](01_solution_design_architecture.md) is that **customer agency is preserved as a design constraint, not an optimization after-thought**:

```
====================================================================================================
           CUSTOMER AGENCY SPECIFICATION [ILLUSTRATIVE VALUES — NOT COMPANY TELEMETRY]
====================================================================================================

      [ OPTION A: AUTHORIZE ]    [ OPTION B: NEED TIME / CLARIFY ]    [ OPTION C: DECLINE ]
      Solid Primary Action       Secondary Outlined Button            Neutral Administrative Action
      Equal Visual Dignity       Immediate Tech Dispatch Release      Zero Guilt-Trip Protocol
      
      * No deceptive contrast    * Asynchronous quote pause           * No artificial countdowns
      * Clear net payable math   * Operational revisit policy [TBD]   * No hidden penalty traps
====================================================================================================
```

### 6.1 Equal Legitimacy of Choices
* **Legitimate Rejection:** Declining a repair that exceeds the machine's residual economic value is a completely rational consumer decision. The UI must treat `Decline Repair` as an equally valid, respectable outcome—never an error state or an abandonment failure.
* **No Conversion Coercion:** The platform must **not** optimize for "quote conversion rate at all costs." Forcing a reluctant customer into an expensive repair destroys cross-category trust and multi-year LTV (`HYPOTHESIS`, anchored in `R0163`).

### 6.2 Explicit Anti-Pattern Prohibitions (Forbidden UX Mechanics)
1. **No Artificial Urgency Countdowns:** Prohibit fake timers (e.g., *"Technician leaving in 2:00 minutes—accept now!"*).
2. **No Guilt-Trip / Loss-Framing Copy:** Prohibit manipulative microcopy (e.g., *"Don't waste your ₹299 visitation fee!"* or *"Are you sure you want to leave your family without AC?"*). Use strictly neutral accounting language: *"₹299 paid for diagnostic inspection labor."*
3. **No Hidden Decline Buttons:** Prohibit burying the decline action in microscopic grey text or hiding it behind nested sub-menus. `Decline Repair` must appear inline on the primary decision card.
4. **No Forced Pre-Authorization Traps:** Prohibit charging repair amounts prior to on-site diagnostic review.
5. **No Punitive Partner Rating Bias:** Prohibit triggering automated negative feedback surveys against the technician simply because the customer exercised their agency to decline an expensive repair (`DESIGN PROPOSAL`).

---

## 7. Information State Taxonomy across the UX Journey

To maintain rigorous data discipline, all information surfaced across the proposed journey maps to our three-class information taxonomy:

```
+------------------------------------------------------------------------------------------------------------------------------------+
|                                      MAPPING OF INFORMATION STATES ACROSS THE PROPOSED JOURNEY                                     |
+------------------------------------+------------------------------------+----------------------------------------------------------+
| 1. KNOWN DATA                      | 2. UNKNOWN / VARIABLE DATA         | 3. CHOICE ARCHITECTURE                                   |
| (Deterministic Platform Records)   | (Physical / Contingent Realities)  | (Unpressured Customer Action Boundaries)                 |
+------------------------------------+------------------------------------+----------------------------------------------------------+
| • Upfront Diagnostic Fee (₹299)    | • Hidden secondary faults uncovered| • Pre-Booking: Confirm 2-stage model vs cancel.          |
|   paid at checkout in specified    |   only after mechanical teardown   | • Post-Diagnosis: Authorize full repair (Pay ₹2,314).    |
|   flows (E041).                    |   (explicitly flagged if present). | • Post-Diagnosis: Decline repair (Pay only ₹299 fee).    |
| • Official Part Rate-Card SKU      | • Exact parts logistics latency if | • Post-Diagnosis: Request specific on-site clarification.|
|   cost (E040).                     |   not stocked in partner vehicle.  | • Post-Service: Authorize digital payment & invoice.     |
| • Standard Labor Tier price        | • Exact appliance residual lifespan| • Dispute: Escalate unlisted part charges to support.    |
|   allowance (Level 1, 2, 3).       |   post-repair (probabilistic).     |                                                          |
| • Platform Warranty duration       | • Uncatalogued rare legacy machine |                                                          |
|   (30-90 Days: E048).              |   parts (custom invoice fallback). |                                                          |
| • Verified Partner Identity and    |                                    |                                                          |
|   background check status (E008).  |                                    |                                                          |
+------------------------------------+------------------------------------+----------------------------------------------------------+
```

---

## 8. Current vs. Proposed Journey Comparison Table

This matrix summarizes the structural differences across all eleven critical user and operational dimensions, strictly distinguishing observed evidence, inferences, and unknown platform states:

| Journey Dimension | Current Experience (Observed / Inferred / Unknown) | Proposed Experience (PDDS Architecture) | Evidence / Strategy Basis |
|---|---|---|---|
| **1. Upstream Expectation Setting** | Checkout displays low fee (₹199–₹299); terms link referenced (`S005`); customer expectation of full repair inferred from reviews (`E014`, `RESEARCH FINDING`). | Inline Two-Stage Model card at checkout; discloses inspection fee + indicative historical category repair bands. | [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (O1), `E014` (`RESEARCH FINDING`), `E024`, `E025`. |
| **2. Diagnostic Comprehension** | Technician inspects machine; verbal explanation often reported in reviews; in-app diagnostic card unobserved in customer teardown (`S005`) `[UNKNOWN CURRENT STATE: exact delivery format]`. | Digital Diagnostic Finding summary on customer phone; plain-language component role and symptom mapping. | [`D005`](../04_Product_Strategy_and_Prioritization/04_decision_log.md), `PAT-09` (`RESEARCH FINDING`), `E024` (`FACT`). |
| **3. Diagnostic Fee Visibility** | Fee charged in specified repair flows (`E041`); policy defines treatment, but in-app crediting interface unobserved in walkthrough screens. | Interactive Sunk-Cost Ledger explicitly shows: Upfront Fee (-₹299 Credit) + Parts + Labor = Balance Payable. | `E041` (in specified repair flows, `FACT`), `R0163` (`RESEARCH FINDING`), `16_solution_design.md`. |
| **4. Scope Clarity** | Quotes reported as lump sums in customer reviews (`E014`, `R0073`); line-item breakdown unobserved in customer walkthrough `S005` `[UNKNOWN CURRENT STATE: whether partner app supports itemized quote push]`. | Granular itemization: OEM Spare Part SKU, Labor Tier, Taxes, and Net Payable balance. | `E040` (`FACT`), `E026` (`FACT`), `15_product_strategy.md`. |
| **5. Price Composition** | Lump-sum quote without visible itemization in review accounts; customer cannot verify part vs labor breakdown against official rate cards. | Transparent breakdown; rate-card catalog verification badge confirms official pricing. | `E040` (`FACT`), `PAT-10` (`RESEARCH FINDING`), `16_solution_design.md`. |
| **6. Sunk-Cost Understanding** | In specified repair flows (`E041`), community reviews suggest customer fear that declining forfeits fee for zero value (`R0163`, `HYPOTHESIS`); fee accounting not observed inline. | Neutral fee accounting; clarifies fee compensates expert diagnosis; PDF diagnostic certificate issued on decline. | `E041` (in specified flows, `FACT`), `R0163` (`HYPOTHESIS`), `E047` (`COMPANY CLAIM`). |
| **7. Quote Verification** | Help FAQ asks "How can I verify the quote?" (`E024`, `FACT`), but inline verification was unobserved during active service in `S005`. | Real-time digital verification seal generated directly on the active quoting card before approval. | `E024` (`FACT`), `E025` (`FACT`), `E040` (`FACT`). |
| **8. Choice Architecture** | On-site interaction; customer reviews describe awkwardness or pressure (`E015`, `RESEARCH FINDING`); digital accept/decline interface unobserved in `S005` `[UNKNOWN CURRENT STATE: exact decision capture mechanism]`. | Tripartite digital choice interface: `Authorize`, `Decline`, or `Clarify` with equal visual hierarchy. | [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (O4), `E015` (`RESEARCH FINDING`), `E026` (`FACT`). |
| **9. Partner Workflow** | `[UNKNOWN CURRENT STATE: Partner app quoting UI is unobserved in evidence base]`; inferred as informal communication based on customer review accounts. | 3-tap hierarchical SKU selector; offline-resilient sync; automated fee crediting (`[DESIGN PROPOSAL]`). | `E040` (`FACT`), `E051` (`ANALYST SYNTHESIS`), `16_solution_design.md`. |
| **10. Customer Agency** | Structural friction when declining in-home; digital decline mechanism unobserved in `S005`. | Agency preserved as design constraint; frictionless digital decline; dignified conclusion. | `15_product_strategy.md` (Principle 4), `16_solution_design.md`. |
| **11. Support Escalation** | Automated chatbot deflection (`E011`, `RESEARCH FINDING`); post-invoice dispute resolution reported as high friction in reviews. | Pre-decision clarification routed directly to technician on-site; support tickets prevented upstream. | `E011` (`RESEARCH FINDING`), `PAT-01` (`RESEARCH FINDING`), `E029` (`FACT`). |

---

## 9. Parallel Partner Workflow (Field Technician Journey)

To ensure the two-sided marketplace functions smoothly, the partner workflow must minimize cognitive load and eliminate perverse incentives:

```
================================================================================================================================================================
                                                  PARALLEL PARTNER WORKFLOW COMPARISON
================================================================================================================================================================
  CURRENT PARTNER FLOW (Partially Inferred / Largely Unknown):
  [ Arrive at Home ] ──> [ Mechanical Inspection ] ──> [ Quote Formulation ] ───> [ Customer Decision ] ──> [ Job Closure & Payment ]
  * Background checked   * Physical disassembly       * Inferred verbal quote      * Interpersonal dynamic     * UNKNOWN collection mechanism
  * Uniform verified      * Unobserved partner app     * Rate card alignment ?      * High friction reported    * Invoice generated (E034)
  
                                                                   │
                                                                   ▼
  PROPOSED PARTNER FLOW ([DESIGN PROPOSAL]):
  [ Arrive at Home ] ──> [ Disassemble Machine ] ──> [ 3-Tap App Logging ] ───────> [ Await Digital State ] ─> [ Execute or Reassemble ]
  * Background verified  * Standard physical check   * Hierarchical SKU selector    * Phone buzzes with choice   * Authorized: Fix & earn
  * Standard uniform     * Physical fault found      * Offline-cached rate card     * Zero verbal haggling       * Declined: Get ₹299 fee
================================================================================================================================================================
```

### 9.1 Partner Journey Specification

| Stage | Current Partner Reality (Inferred / Unknown) | Proposed Partner Workflow (`[DESIGN PROPOSAL]`) | Design Rationale & Safety Safeguards |
|---|---|---|---|
| **1. Diagnostic Logging** | `[UNKNOWN CURRENT STATE: Partner app quoting interface is unobserved in customer teardowns S005/S006; customer reviews describe verbal quotes]`. | Opens partner app; uses **3-tap hierarchical selector** (`Category` $\rightarrow$ `Subsystem` $\rightarrow$ `Part SKU`). Rate pre-populates (`E040`). | **Zero Essay Writing:** Technicians with greasy hands cannot type paragraphs. 3 taps maximum (`DESIGN SPECIFICATION`). |
| **2. Offline Resilience** | `[UNKNOWN CURRENT STATE: Partner app offline behavior is unobserved]`. | App operates with **graceful degradation**: basic local caching of rate cards and background queue synchronization; specific offline sync protocol requires engineering validation (`[DESIGN CONSTRAINT TO BE DETERMINED]`). | Prevents quoting tool crashes from stalling on-site service delivery (`Failure Mode 9 Mitigation`). De-scopes complex Bluetooth P2P from MVP. |
| **3. Quote Delivery** | Partner communicates quote to customer (inferred as verbal on-site communication based on review descriptions; exact partner app capabilities unobserved). | Taps `Transmit Quote to Customer`; steps back to pack tools or test components while customer reviews phone. | Defuses in-home domestic tension (`E015`); eliminates the awkward verbal standoff. |
| **4. Handling Customer Declines** | In specified repair flows (`E041`), partner collects visitation fee if customer declines; exact partner compensation accounting is unobserved in live operations. | If customer taps `Decline`, partner app displays: `Job Closed — ₹299 Diagnostic Fee Credited to Daily Earnings` (`E047` analogue). | **Compensating Diagnostic Labor:** Protects partner take-home pay; removes incentive to coerce customers (`E047`). |
| **5. Performance Rating Protection** | `[UNKNOWN CURRENT STATE: Current impact of customer quote declines on partner conversion rating is unobserved in evidence base]`. | **Rating Prohibition:** Platform policy explicitly bars customer cancellation/decline surveys from penalizing partner rating (`[DESIGN PROPOSAL]`). | Removes perverse incentive for partners to manipulate or misreport diagnostic findings. |

---

## 10. Conceptual Service Blueprint

This lightweight service blueprint visualizes cross-actor interactions across the four primary operational lanes:

```
================================================================================================================================================================
                                                  CONCEPTUAL SERVICE BLUEPRINT (PDDS)
================================================================================================================================================================
LANE 1: CUSTOMER
  [ View 2-Stage Card ] ──> [ Pay ₹299 Fee ] ──> [ Welcome Partner ] ──> [ View Diagnosis ] ──> [ View Fee Ledger ] ──> [ Tap Authorize / Decline ]
             │                     │                     │                      ▲                         ▲                         │
═════════════╪═════════════════════╪═════════════════════╪══════════════════════╪═════════════════════════╪═════════════════════════╪══════════════════════════
LANE 2: PARTNER
             │                     │             [ Arrive & Inspect ] ──> [ Log 3-Tap SKU ]               │                [ Phone Buzzes Status ]
             │                     │                     │                      │                         │                         │
═════════════╪═════════════════════╪═════════════════════╪══════════════════════╪═════════════════════════╪═════════════════════════╪══════════════════════════
LANE 3: UC PRODUCT (Client App / Partner App)
  [ Display Bands ] ──────> [ Lock ₹299 Slot ] ──> [ Dispatch Partner ] ──> [ Map Catalog ] ────> [ Build Ledger ] ──────> [ State Transition Engine ]
             │                     │                     │                      │                         │                         │
═════════════╪═════════════════════╪═════════════════════╪══════════════════════╪═════════════════════════╪═════════════════════════╪══════════════════════════
LANE 4: UC OPERATIONS & SUPPORT
             │                     │             [ Partner Allocation ]         │                         │                [ Auto-Pay Partner Ledger ]
             │                     │             [ SLA Tracking ]               │                         │                [ Issue Safety Certificate ]
================================================================================================================================================================
```

### 10.1 Key Operational Handoffs
1. **Upstream Booking to Partner Dispatch:** Customer accepts two-stage booking terms; operations engine allocates verified professional (`E008`) and blocks calendar time (`E027`).
2. **On-Site Physical Inspection to Digital Scaffold:** Partner completes mechanical inspection; partner app translates physical SKU selection into standardized customer quote using central rate cards (`E040`).
3. **Customer Decision to Operational Execution:** Customer taps digital decision; platform state engine immediately branches:
   * *Branch A (Authorized):* Activates warranty timer (`E048`), registers parts SKU to invoice (`E034`), authorizes work execution.
   * *Branch B (Declined):* Closes booking, triggers diagnostic labor fee payout to partner account (`E047` analogue), renders downloadable inspection certificate to customer app.

---

## 11. Edge Case Architecture & System Fallback States

To ensure real-world platform reliability, the solution defines concrete handling for eight complex operational edge cases:

```
+------------------------------------------------------------------------------------------------------------------------------------+
|                                               EDGE CASE ARCHITECTURE MATRIX                                                        |
+---+--------------------------------+----------------------------+------------------------------------+-----------------------------+
| # | Edge Case                      | Current Evidence Basis     | Proposed Handling ([DESIGN PROPOSAL])| Remaining Unknown / Gap    |
+---+--------------------------------+----------------------------+------------------------------------+-----------------------------+
```

#### Edge Case 1: Quote Changes After Initial Recommendation (Secondary Scope Uncovered)
* **Current Evidence:** Reviewers cite unexpected price escalations during ongoing repairs (`E014`, `E016`). Physical repairs frequently uncover secondary wear after initial disassembly (e.g., removing a broken motor exposes a rusted axle shaft).
* **Proposed Handling (`[DESIGN PROPOSAL]`):**
  * The primary quote card explicitly includes a **Contingent Scope Disclaimer**: *"Quote covers primary compressor replacement; secondary electrical lines will be verified upon installation."*
  * If secondary failure is uncovered, the partner cannot proceed verbally. They must log an **Incremental Scope Addendum** in the app.
  * Customer receives an **Addendum Approval Card** displaying: *Original Approved Amount* + *Additional Part Cost* = *New Total*.
  * Customer retains full agency to accept addendum or halt work at the previously agreed milestone.
* **Remaining Unknown / Gap:** How often do genuine secondary mechanical faults occur versus opportunistic technician scope creep (`GAP-005`)?

#### Edge Case 2: Multiple Repair Items (Multi-Fault Complex Diagnosis)
* **Current Evidence:** Rate cards publish discrete component prices (`E040`), but complex visits often involve multiple simultaneous defects (e.g., gas leak + burnt capacitor + fan blade damage).
* **Proposed Handling (`[DESIGN PROPOSAL]`):**
  * Partner app allows multi-select SKU entry, automatically applying **Bundled Labor Deductions** (e.g., full labor charged for primary repair; secondary labor discounted by 50% since machine is already disassembled).
  * Customer decision interface displays an expandable line-item list, allowing them to **selectively authorize** specific repairs (e.g., Authorize critical cooling fix; decline optional cosmetic filter replacement).
* **Remaining Unknown / Gap:** Does selective repair authorization cause friction if the partner insists both parts must be replaced together for machine stability?

#### Edge Case 3: Spare Part Availability Uncertainty
* **Current Evidence:** Reviewers report long delays waiting for replacement parts (`R0166`, `E016`).
* **Proposed Handling (`[DESIGN PROPOSAL]`):**
  * When partner selects a SKU, partner app prompts: `Part On-Truck` or `Part Needs Procurement`.
  * If procurement needed, customer card displays: *"Part requires local warehouse pickup. Estimated procurement window: 90 minutes. Partner will return today between 3:00 PM – 4:30 PM."*
  * Sunk-cost ledger explicitly protects customer: if part cannot be procured today, customer may cancel without penalty.
* **Remaining Unknown / Gap:** Real-time visibility into Urban Company micro-warehouse parts inventory across Tier-1 vs Tier-2 cities.

#### Edge Case 4: Customer Declines Repair After Paying Diagnostic / Visitation Fee
* **Current Evidence:** In specified repair flows, policy defines a visitation fee if repair is declined (`E041`, `FACT`); qualitative reviews describe customer frustration when paying fees without receiving a physical repair (`R0163`, `HYPOTHESIS`).
* **Proposed Handling (`[DESIGN PROPOSAL]`):**
  * When `Decline Repair` is confirmed, the app delivers an in-app **Diagnostic Finding Summary & Fee Receipt**.
  * Summary documents: (1) Diagnosed component fault, (2) Recommended remedy, (3) Confirmation that the ₹299 visitation fee compensated on-site diagnostic labor, and (4) Reassurance of zero hidden platform penalties.
  * *Scope Note (`THR-10`):* Formal downloadable PDF "Diagnostic Safety Certificate" generation is de-scoped from the MVP to a later-stage hypothesis, pending empirical evidence on whether customers actually value PDF documents for uncompleted domestic repairs.
* **Remaining Unknown / Gap:** Does delivering an in-app diagnostic summary measurably reduce 90-day platform churn among decliners? (`H4`, tracked in Level 3).

#### Edge Case 4.1: Customer Requests Time to Decide (`THR-09` Operational Clarification)
* **Current Evidence:** Domestic decision-making frequently requires spousal consultation, second opinions, or financial deliberation outside the technician's physical presence (`E015`).
* **Proposed Handling (`[DESIGN PROPOSAL]`):**
  * Customer taps `Need Time to Decide`.
  * The quote state enters an asynchronous pause. The technician is not held captive in the customer's home; the on-site diagnostic visit concludes, and the partner is released for dispatch.
  * *Operational Constraint (`THR-09`):* The exact quote-lock window, redispatch protocol, and second visitation fee treatment are designated as **`[OPERATIONAL WINDOW / RE-VISIT POLICY TBD]`** requiring operational testing, explicitly rejecting arbitrary 2-hour SLA promises that conflict with physical field realities.

#### Edge Case 5: Customer Requests On-Site Clarification Before Deciding
* **Current Evidence:** Customers face deflection chatbots (`E011`, `PAT-01`) or rely on in-person verbal dialogue (`E015`).
* **Proposed Handling (`[DESIGN PROPOSAL]`):**
  * Customer taps `Ask Technician a Question` on the digital card.
  * Displays quick structured prompts (e.g., *"Can this part be repaired instead of replaced?"*, *"Why is labor ₹350 for this fix?"*).
  * Selected question is dispatched directly to the partner's screen, providing structured talking points grounded in official platform guidelines.
  * Prevents central customer support queues from being overwhelmed by on-site questions (`Failure Mode 10 Mitigation`).
* **Remaining Unknown / Gap:** Will customers use in-app prompts if the partner is standing nearby in the home?

#### Edge Case 6: Warranty-Covered or Partially Covered Work
* **Current Evidence:** Official warranty documentation covers 30–90 days on appliance repairs (`E033`, `E048`), but strictly excludes items not on invoice (`E034`) or new post-service issues.
* **Proposed Handling (`[DESIGN PROPOSAL]`):**
  * System checks customer booking history for prior service within 90 days on the same appliance serial/category.
  * If eligible warranty record found, quote card renders in **Warranty Mode**: *Diagnosis: Gas Leak (Covered under 90-day AC Warranty)* $\rightarrow$ *Balance Payable: ₹0*.
  * If work is partially covered (e.g., labor free under warranty, but new physical part excluded), ledger clearly splits: *Covered Labor: ₹0* vs *New Hardware Part: ₹650*.
* **Remaining Unknown / Gap:** Platform accuracy in matching repeat bookings to exact physical appliance units across multi-AC households.

#### Edge Case 7: Category-Specific Quoting Differences & Catalog Gaps
* **Current Evidence:** AC repair is highly standardized (`E026`, `E040`), while chimney or washing machine components are fragmented across dozens of OEM brands.
* **Proposed Handling (`[DESIGN PROPOSAL]`):**
  * For standardized categories: Mandatory 3-tap SKU catalog selection.
  * For unlisted/bespoke parts (Catalog Gap): Partner selects `Unlisted Part / Custom Repair`.
  * Triggers **Custom Estimate Safeguard**: Partner enters estimated part cost; customer sees explicit disclaimer: *"This part is not in the standard catalog. Partner must attach physical purchase invoice upon installation to activate warranty."*
* **Remaining Unknown / Gap:** Proportion of appliance repairs involving legacy or unlisted parts (`GAP-005`).

#### Edge Case 8: Customer Disputes Quoted Amount On-Site
* **Current Evidence:** Service FAQs cover extra charges (`E025`) and quote verification (`E024`), but offer no real-time on-site dispute mechanism.
* **Proposed Handling (`[DESIGN PROPOSAL]`):**
  * If customer flags `Quote Appears Incorrect` on the decision card, system compares partner's entered SKU price against official central database (`E040`).
  * If SKU matches rate card: App displays: *"This is the official Urban Company rate-card price verified across Delhi-NCR."*
  * If partner entered custom labor above threshold: App blocks quote transmission and alerts field operations for rapid price verification.
* **Remaining Unknown / Gap:** Real-time operational latency for field pricing audits.

---

## 12. Guiding UX Principles

Derived directly from [`15_product_strategy.md`](01_product_strategy_and_economics.md) and [`16_solution_design.md`](01_solution_design_architecture.md), these seven principles govern all interaction design in the Post-Diagnostic Decision Scaffold:

```
====================================================================================================
                                      GUIDING UX PRINCIPLES
====================================================================================================

  1. MAKE ECONOMIC STATE LEGIBLE
     Always display the exact financial ledger: paid fees, gross repair costs, fee credits, and net.
     
  2. SEPARATE KNOWN FROM CONTINGENT COST
     Never present an initial diagnosis as an unconditional lifetime guarantee against hidden wear.
     
  3. PRESENT SCOPE BEFORE ASKING FOR COMMITMENT
     Ensure the customer understands what is broken before prompting them to authorize payment.
     
  4. PRESERVE EQUAL LEGITIMACY OF CHOICES (AGENCY)
     Treat declining an uneconomical repair as a completely valid, dignified customer choice.
     
  5. AVOID FALSE PRECISION
     Use realistic cost bands upstream; avoid claiming deterministic precision where variance exists.
     
  6. MINIMIZE PARTNER ADMINISTRATIVE LOAD
     Zero essay typing for technicians; 3-tap maximum quoting; full offline resilience.
     
  7. ESCALATE AMBIGUITY RATHER THAN DISGUISING IT
     Surface catalog gaps and unlisted parts transparently rather than forcing false categorization.
====================================================================================================
```

*(Note: These principles represent intentional product design constraints and standards, not empirically validated behavioral truths).*

---

## 13. End-to-End Traceability Matrix

Every interaction step, system state, and edge case in this document traces directly to locked decisions, strategic principles, and canonical evidence:

| UX Flow Component | Decision Anchor | Strategy Principle (`15_product_strategy.md`) | Solution Component (`16_solution_design.md`) | Epistemic Evidence Base |
|---|---|---|---|---|
| **Upstream 2-Stage Expectation Card** | [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (O1) | Section 5 (O1 Role) | Component 1 (Upstream Card) | `E014` (`RESEARCH FINDING`), `E024` (`FACT`), `E025` (`FACT`), `E041` (in specified flows, `FACT`) |
| **Partner 3-Tap Hierarchical Selector** | [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) | Section 6.1 (Partner Workflow) | Component 6 (Partner Quoting) | `E040` (`FACT`), `E051` (`ANALYST SYNTHESIS`) |
| **Digital Diagnostic Finding Summary** | [`D005`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) | Section 4.1 (Cognitive Grounding) | Component 2 (Diagnostic Summary) | `PAT-09` (`RESEARCH FINDING`), `E024` (`FACT`) |
| **Interactive Sunk-Cost Ledger** | [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (O4) | Section 4.2 (Sunk-Cost Neutralization)| Component 3 (Fee Ledger) | `E041` (in specified flows, `FACT`), `R0163` (`RESEARCH FINDING`), `E047` (`COMPANY CLAIM`) |
| **Rate-Card & Warranty Verification** | [`D006`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (Seg 3) | Section 4.1 (Scope Demarcation) | Component 4 (Warranty Badge) | `E040` (`FACT`), `E048` (`COMPANY CLAIM`), `E049` (`FACT`), `PAT-10` (`RESEARCH FINDING`) |
| **Tripartite Choice Interface** | [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (O4) | Section 4.3 (Asynchronous Agency) | Component 5 (Choice Interface) | `E015` (`RESEARCH FINDING`), `E026` (`FACT`), `E041` (in specified flows, `FACT`) |
| **Diagnostic Certificate on Decline** | [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) (O4) | Section 4.2 (Tangible Diagnostic Value)| Edge Case 4 & Section 8 | `E041` (in specified flows, `FACT`), `R0163` (`HYPOTHESIS`), `E047` (`COMPANY CLAIM`) |
| **Direct On-Site Clarification Routing**| [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) | Section 6.2 (Deflection Mitigation) | Component 5 & Edge Case 5 | `E011` (`RESEARCH FINDING`), `PAT-01` (`RESEARCH FINDING`), `E029` (`FACT`) |

---

## 14. Document Status, Evidence Gaps & Next Stage Gateway

### 14.1 Validation Checklist
- [x] Current-state flow strictly reconstructed from verified evidence (`S005`, `S006`, `S007`–`S013`, `05_evidence_matrix.md`).
- [x] Inferred current states explicitly marked with `[INFERRED CURRENT STATE]`.
- [x] Unobserved platform/operational mechanics explicitly marked with `[UNKNOWN CURRENT STATE]`.
- [x] Proposed states strictly grounded in `16_solution_design.md` and labeled `[DESIGN PROPOSAL]` or `[DESIGN SPECIFICATION]`.
- [x] Locked decisions [`D005`](../04_Product_Strategy_and_Prioritization/04_decision_log.md), [`D006`](../04_Product_Strategy_and_Prioritization/04_decision_log.md), and [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) preserved without modification.
- [x] Customer agency enforced as an unconditional design constraint with explicit anti-pattern rules.
- [x] Information state taxonomy (`KNOWN`, `UNKNOWN / VARIABLE`, `CHOICE`) mapped across all steps.
- [x] Parallel partner flow and lightweight service blueprint included.
- [x] Exhaustive edge case architecture documented across eight scenarios.

### 14.2 Newly Formalized Evidence Gaps (Current Platform State Boundaries)
Following the Task 15.5 evidence-discipline audit, the following operational boundaries are explicitly recorded as evidence gaps rather than assumed platform facts:
* **`GAP-007` (Current On-Site Quote Transmission Mechanism):** Customer walkthrough `S005` captures the policy that a quote must be provided and approved (`E026`), but did not observe an in-app digital quote screen. Whether the live platform currently transmits quotes via SMS, partner app push, or relies primarily on oral communication on-site is unobserved in customer teardown data.
* **`GAP-008` (Current On-Site Payment Collection Channel):** While platform invoices exclude off-invoice items (`E034`), the exact channel through which customers pay for variable repairs or visitation fees on-site (customer in-app link vs. partner UPI QR vs. other means) is unobserved in `S005`/`S006`.
* **`GAP-009` (Partner App Interface & Offline Capabilities):** The partner-facing mobile application was not captured in customer-side walkthroughs (`S005`, `S006`). Its current quoting screens, catalog search latency, and offline caching capabilities remain unobserved.
* **`GAP-010` (Impact of Customer Quote Declines on Partner Conversion):** Whether Urban Company's live partner dispatch algorithms currently penalize partners when customers decline diagnostic repair quotes is unobserved in available platform policies.

---

*With Task 15.5 complete, the audited UX flows are locked. This file serves as the canonical behavioral foundation for **Task 16: Product Requirements Document (`18_prd.md`)**.*
