# Executive Case Study: Post-Diagnostic Decision Scaffold (PDDS)
## Re-Architecting In-Home Pricing Transparency for Urban Company

**Co-Creators:** Anshul Eskey ([LinkedIn](https://www.linkedin.com/in/anshul-eskey-ba0821292/) | [Email](mailto:anshuleskey999@gmail.com)) & Sagun Verma ([LinkedIn](https://www.linkedin.com/in/sagun-verma-655a122a6/) | [Email](mailto:sagunv11@gmail.com))  
**Role:** Product Manager  
**Project:** Urban Company — Two-Sided Home Services Marketplace  
**Reading Time:** ~6–8 minutes  
**Evidence Base:** 179 Audited Google Play Reviews ([Dataset](../02_Research_and_Data/data/Urban_Company_Cleaned_Dataset.xlsx)), Live App Walkthrough ([Teardown](../01_Context_and_Brief/03_product_context_and_walkthrough.md)), Adversarial Red-Team Stress-Testing (15 Threat Vectors Audited).  

---

> [!TIP]
> **Executive Summary (TL;DR):** This case study re-architects on-site quoting in diagnosis-dependent home services (AC repair, washing machines). Driven by empirical review mining of 179 customer complaints, we killed an initial "rebooking" hypothesis ($3.4\%$ complaints) to solve the dominant friction: on-site price uncertainty ($37.3\%$). We designed the **Post-Diagnostic Decision Scaffold (PDDS)**—a lean 4-primitive mobile decision framework that establishes upfront pricing expectations, structures in-home quote inputs, clarifies sunk-cost accounting, and provides equal digital agency to authorize, clarify, or decline.

---

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                                 EXECUTIVE TEARDOWN SNAPSHOT                            │
├───────────────────┬────────────────────────────────────────────────────────────────────┤
│ The Company       │ Urban Company — India's dominant full-stack home services platform │
│ The Friction Point│ On-site price escalation in diagnosis-dependent appliance repairs  │
│ The Pivot (D004)  │ Shifted from "Rebooking/Partner Continuity" (3.4% complaint share) │
│                   │ to "Post-Diagnostic Price Uncertainty" (37.3% negative share)      │
│ Problem (D005)    │ On-site scope discovery & fee mechanics create decision paralysis  │
│ Segments (D006)   │ Primary: First-Time Bookers | Secondary: Price-Sensitive Evaluators│
│ The Solution      │ Post-Diagnostic Decision Scaffold (PDDS): Lean 4-Primitive MVP     │
│                   │ with 3-tap quoting, sunk-cost ledger, & tripartite decision card   │
│ Primary Metric    │ Decision Comprehension & Clarity (Survey sampling & dispute proxies│
│ Process Metric    │ Post-Diagnostic Decision Completion Rate (PDCR)                    │
│ Guardrail Floors  │ Quote Authorization Volume Floor + Partner Hourly Earnings Floor   │
│ Validation Design │ Proposed Partner-Cohort Randomization / Switchback (THR-03)        │
└───────────────────┴────────────────────────────────────────────────────────────────────┘
```

---

# 1. Executive Summary & The Hook

Every day, thousands of Indian homeowners invite an Urban Company technician into their living room for a routine appliance issue—an air conditioner blowing lukewarm air, or a washing machine failing to spin. The customer has already booked the service, paid a prepaid visitation/diagnostic fee (`₹249`–`₹499`) (`E041` `[FACT]`), and expects a standardized e-commerce repair experience.

Instead, thirty minutes later, the machine lies disassembled across the living room floor. The technician stands over the parts and verbally quotes ₹3,200 for a new motor and gas refill (`PAT-09` `[RESEARCH FINDING]`).

At that precise second, **the platform's hard-won brand trust collapses into perceived entrapment (`R0163` `[RESEARCH FINDING]`).** The customer faces acute information asymmetry: *Is this part actually broken? Is this price fair? Did my ₹249 inspection fee count toward this? If I say no, is my AC left in pieces?*

> [!NOTE]
> **Current-State Quoting Ground Truth:** Available evidence does not establish the complete end-to-end quote presentation flow across all service categories. Review discovery (`E014`) highlights recurring verbal reveals and on-site price opacity.

This case study details the discovery, strategic redirection, and product specification of the **Post-Diagnostic Decision Scaffold (PDDS)**—a software bridge designed to replace coercive in-home verbal standoffs with an autonomous digital decision framework, protecting customer agency without destroying technician earnings or platform unit economics.

---

# 2. Context & Strategic Landscape

Urban Company operates a full-stack, two-sided managed marketplace spanning 50+ cities across India and the UAE (`02_product_context.md` `[FACT]`). Unlike lead-generation directories (Justdial, Sulekha), Urban Company's core value proposition is **standardization, safety, and guaranteed pricing** (`E040` `[FACT]`).

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                      TWO TRANSACTION MODELS ON URBAN COMPANY                    │
├───────────────────────────────────────┬─────────────────────────────────────────┤
│ MODEL A: DETERMINISTIC PRICING        │ MODEL B: DIAGNOSIS-DEPENDENT PRICING    │
│ (Salon, Deep Cleaning, Painting)      │ (AC Repair, Washing Machine, Plumbing)  │
├───────────────────────────────────────┼─────────────────────────────────────────┤
│ • Fixed scope known before booking    │ • Scope physically hidden inside machine│
│ • Deterministic pricing at checkout   │ • Two-Stage model: Fee 1 + Quote 2      │
│ • Zero on-site price negotiation      │ • High in-home pricing volatility       │
│ • High trust & repeat predictability  │ • Acute friction: 37.3% negative reviews│
└───────────────────────────────────────┴─────────────────────────────────────────┘
```

In deterministic categories, standardized pricing works flawlessly. However, in **diagnosis-dependent appliance categories**, hidden physical entropy makes remote upfront pricing impossible (`[ANALYST SYNTHESIS]`). Urban Company consequently operates a mandatory two-stage transaction model:
1. **Stage 1 (Pre-Service):** Customer pays an upfront visitation fee (`E041` `[FACT]`).
2. **Stage 2 (On-Site):** Technician physically inspects the unit and generates a supplemental quote (`[FACT]`).

While economically logical, the platform historically lacked a dedicated digital UX scaffold for Stage 2. The entire quoting moment was left to informal verbal interaction inside the domestic space, creating an operational breeding ground for customer disputes, social awkwardness, and off-platform leakage (`PAT-10` `[RESEARCH FINDING]`).

---

# 3. Evidence-Grounded Problem Discovery

### The Review Mining Audit (179 Reviews across 3 Operational Slices)
To discover systemic friction, we mined an empirical dataset of 179 Google Play app store reviews across 3 operational slices (`05_evidence_matrix.md`, `E001`). Rigorous quantitative categorization revealed a clear distribution:

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                 EMPIRICAL COMPLAINT DISTRIBUTION (NEGATIVE REVIEWS)             │
├─────────────────────────────────────────────────────────────────────────────────┤
│ Pricing Transparency & Surprise Surcharges (E004)        ████████████ 37.3%     │
│ Cancellation Cascades & Partner No-Shows (E005)          ████████████ 37.3%     │
│ App UX / Payment Technical Glitches (E006)               ██████████   31.4%     │
│ Inconsistent Service Quality & Damage (E007)             █████████    28.5%     │
│ Customer Support AI Chatbot Deflection (E011)            ███████      21.6%     │
│ Trust, Safety & Domestic Security Concerns (E008)        █████        15.7%     │
│ Repeat Booking / Partner Continuity (E009, 3.4% full, 5.9% neg) █       3.4%     │
└─────────────────────────────────────────────────────────────────────────────────┘
```

### The Strategic Redirection Pivot (`D004` — Locked)
This project originally launched under a corporate hypothesis: *"Customers want to rebook the same familiar professional to ensure trust and consistency"* (`A001`).

Had we forced that predetermined narrative, we would have built a "Favorite Technician" feature. But the evidence spoke decisively:
- Repeat-booking friction appeared in **only 3.4%** of all sampled reviews ($n=6/179$) and $5.9\%$ of negative reviews ($n=3/51$) (`E009`).
- Pricing opacity, surprise on-site quotes, and perceived fee entrapment dominated **37.3%** of negative sentiment ($n=19/51$) (`E004`, `E014` `[RESEARCH FINDING]`).

> [!NOTE]
> **Evidentiary Boundary (`E014` Contextualization):**  
> Evidence item `E014` reflects 13 specific pricing-related reviews in the audited research sample ($N=179$). This serves strictly as a **qualitative problem-discovery signal** demonstrating user friction mechanisms; it does NOT assert a statistically representative platform-wide population prevalence across Urban Company's annual transactions.

Facing this data, we executed **Decision D004** (`04_decision_log.md`): killing the rebooking feature entirely and pivoting 100% of engineering scope to **Post-Diagnostic Price Uncertainty**.

### The Canonical Problem Statement (`D005` — Locked)
> *"For customers booking diagnosis-dependent home services, the final cost can become uncertain after booking because the exact scope of work is determined only after on-site inspection, while the diagnostic/visitation cost and subsequent repair quote affect the customer's ability to confidently decide whether to proceed."*

### Decoupling Mechanism A vs. Mechanism B (Clarity ≠ Affordability)
To establish rigorous analytical boundaries, we distinguish two fundamentally different causes of quote resistance:
- **Mechanism A (Decision Uncertainty & Lack of Agency):** Customer wants the repair, but feels bewildered by ledger math, distrusts the verbal quote, or feels trapped. **This is what PDDS is designed to solve.**
- **Mechanism B (Price Dissatisfaction / Sticker Shock):** Customer understands the quote perfectly, but finds ₹3,200 objectively too expensive for an older appliance. A digital scaffold clarifies the cost, but cannot eliminate rational price elasticity. (Decline due to price elasticity is an autonomous decision, not a product failure).

---

# 4. Target User Segmentation (`D006`)

Rather than vague demographic personas, segmentation was anchored on empirical behavioral responses to unexpected domestic quotes:

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                             TARGET USER MATRIX (D006)                           │
├───────────────────────────────────────┬─────────────────────────────────────────┤
│ SEGMENT 1: FIRST-TIME DIAGNOSTIC      │ SEGMENT 2: PRICE-SENSITIVE QUOTE        │
│ BOOKERS (Primary Target — D006)       │ EVALUATORS (Secondary Segment — D006)   │
├───────────────────────────────────────┼─────────────────────────────────────────┤
│ • Mental Model: Expects fixed         │ • Mental Model: Actively benchmarks UC  │
│   e-commerce pricing at checkout.     │   against neighborhood offline mechanics│
│ • Friction: Shocked by two-stage quote│ • Friction: Believes platform parts are │
│   feels baited and switched.          │   artificially marked up with fat margin│
│ • Decision Need: Psychological safety │ • Decision Need: Line-item rate card    │
│   and clear sunk-cost ledger.         │   transparency and warranty backing.    │
└───────────────────────────────────────┴─────────────────────────────────────────┘
```

> **Urgency Dimension:** Peak appliance breakdown urgency (e.g. mid-summer AC failure) is treated strictly as a **behavioral modifier / operational hypothesis**, modulating customer decision latency. It is NOT a third production customer segment.

---

# 5. Opportunity Landscape & Prioritization (`D007`)

Guided by comprehensive scoring across opportunities `O1` through `O6` (`05_opportunity_scoring_and_selection.md`), we selected:
- **Primary Anchor (`O4`):** Accept/Reject Decision Support & Sunk-Cost Clarification (Intervenes directly at the decision moment, resolves sunk-cost confusion, and establishes customer agency).
- **Complementary Upstream Anchor (`O1`):** Pre-Diagnostic Price Expectation Setting (Pre-aligns mental models during checkout).
- **Explicit Non-Goals (`[DESIGN DECISION]`):** We did *not* attempt to build algorithmic video pre-diagnosis (technically infeasible for internal physical faults) or flat-rate all-inclusive repair pricing (economically unviable due to adverse selection).

---

# 6. Solution Architecture: The Post-Diagnostic Decision Scaffold (PDDS)

The PDDS is an integrated, dual-app digital decision bridge operating across the Customer App and Partner App. Components are strictly bounded into a **Lean MVP Decision Core** and **Post-MVP Roadmap**:

- **Lean MVP Primitives (C1–C4):**
  1. **C1 — Pre-Quote Expectation Setting (`FR-01`):** Service-page education on the 2-stage model.
  2. **C2 — 3-Tap Standardized Quoting (`FR-02`–`FR-04`):** Standard rate-card selection backed by offline SQLite caching (`THR-07`).
  3. **C3 — Visual Sunk-Cost Ledger (`FR-05`):** Shows exact fee credit applied to repair total.
  4. **C4 — Customer Decision Card (`FR-06`):** Tripartite digital choice: `AUTHORIZE`, `NEED TIME / CLARIFY`, and `DECLINE`.
- **Post-MVP / Phase 2 Roadmap (De-Scoped from MVP):**
  - **Diagnostic Safety Certificate PDF (`THR-10`):** De-scoped to avoid complex document generation pipelines and warranty dispute liability.
  - **Re-visit Fulfillment SLA (`THR-09`):** Operational return policies for "Need Time" quotes are marked `[TBD OPERATIONAL FEASIBILITY]` to avoid partner dispatch schedule traps.

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                                 THE PDDS SYSTEM FLOW                                   │
├────────────────────────────────────────────────────────────────────────────────────────┤
│ 1. UPSTREAM EXPECTATION SETTING (Customer Checkout — Primitive C1)                     │
│    Two-Stage Pricing Card: "₹299 Inspection Today → Transparent Quoting on Site"       │
│                                           │                                            │
│                                           ▼                                            │
│ 2. STANDARDIZED ON-SITE DIAGNOSIS (Partner App — Primitive C2)                         │
│    Technician logs fault via 3-Tap Standard SKU Catalog                                │
│                                           │                                            │
│                                           ▼                                            │
│ 3. THE DECISION BRIDGE (Customer App — Primitives C3 & C4)                             │
│    Instant push/socket renders the Digital Decision Card:                             │
│    ┌───────────────────────────────────────────────────────────────────────┐           │
│    │ DIAGNOSTIC SUMMARY: Burnt Capacitor (Cooling Failure Identified)      │           │
│    │ ───────────────────────────────────────────────────────────────────── │           │
│    │ Gross Repair Scope (OEM Part + Labor):                    ₹1,499      │           │
│    │ LESS: Prepaid Diagnostic Fee Credited:                   - ₹ 299      │           │
│    │ NET ADDITIONAL PAYABLE TODAY:                             ₹1,200      │           │
│    │ ───────────────────────────────────────────────────────────────────── │           │
│    │ [✓ 90-Day Parts & Service Guarantee Badge Included]                   │           │
│    │                                                                       │           │
│    │ [ AUTHORIZE REPAIR ]  [ DECLINE REPAIR ]  [ NEED TIME / CLARIFY SCOPE]│           │
│    └───────────────────────────────────────────────────────────────────────┘           │
│                    │                  │                   │                            │
│                    ▼                  ▼                   ▼                            │
│ 4A. REPAIR PROCEEDS           4B. CLEAN DECLINE   4C. NEED TIME / CLARIFY SCOPE        │
│     Net payable: ₹1,200.      In-app diagnostic   Partner answers scope questions      │
│     Partner executes repair.  summary & fee       or asynchronous quote hold initiated │
│                               receipt issued.     (technician released, revisit TBD).  │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

---

# 7. Metrics & Telemetry Framework

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                                METRICS FRAMEWORK                                │
├─────────────────────────────────────────────────────────────────────────────────┤
│ PRIMARY PRODUCT OUTCOME:                                                        │
│ Decision Comprehension & Clarity (Survey sampling & dispute rate proxies)       │
│ Evaluates whether customer understood scope, fee deduction, and net payable.    │
├─────────────────────────────────────────────────────────────────────────────────┤
│ SECONDARY OPERATIONAL PROCESS METRIC:                                           │
│ Post-Diagnostic Decision Completion Rate (PDCR)                                 │
│ Formula: (Completed Digital Decisions / Eligible Diagnostic Quotes) × 100        │
│ Tracks intentional decision resolution vs. app abandonment.                     │
├─────────────────────────────────────────────────────────────────────────────────┤
│ BEHAVIORAL TERMINAL OUTCOMES:                                                   │
│ • Authorization Rate (%)    • Need Time / Clarify (%)   • Decline Rate (%)      │
├─────────────────────────────────────────────────────────────────────────────────┤
│ BUSINESS GUARDRAILS:                                                            │
│ • Quote Authorization Volume Floor: Monitored against operational baseline     │
│ • Partner Hourly Earnings Floor: Parity across treatment and control cohorts    │
│ • 7-Day Support Billing Dispute Rate: Monitored for escalation reduction        │
│ • Operational Dispatch Burden: Tracking technician idle time and re-visits      │
└─────────────────────────────────────────────────────────────────────────────────┘
```

### Core Telemetry Principle: Decline is NOT Failure
A customer selecting **Decline** represents decision comprehension and proves customer agency. It is **never counted as a product failure**. 

Decision comprehension and commercial outcome must be evaluated separately:
> *"A customer can understand the quote correctly and still decline. Decision comprehension and commercial outcome must be evaluated separately."*

---

# 8. Operational De-Risking & Proposed Validation Design

To de-risk the marketplace before national deployment, validation follows a structured phased rollout:

1. **Phase 1: Comprehension Usability Lab `[PROPOSED VALIDATION PROTOCOL — NOT EXECUTED]`:** Think-aloud testing ensuring users calculate net payable arithmetic correctly without explanation.
2. **Phase 2: Shadowed Field Usability `[PROPOSED PROTOCOL]`:** Silent PM observers shadowing technicians to identify physical tool-handling friction and verify quoting UX latency.
3. **Phase 3: Partner-Cohort Randomization Experiment `[PROPOSED EXPERIMENT DESIGN — NOT EXECUTED]`:** 
   - **Why Geographic Clusters Were Rejected (`THR-03`):** Urban service technicians cross micro-market boundaries dynamically, causing severe treatment-to-control spillover in geographic A/B tests.
   - **Approved Experimental Design:** Technicians are randomized into treatment and control pools (**Partner-Cohort Randomization**) or metropolitan areas alternate in **2-Week Switchback Blocks** to eliminate cross-neighborhood contamination.
4. **Phase 4: Staged Rollout:** Phased deployment across operating cities gated on partner earnings parity.

---

# 9. Adversarial Red-Team Stress-Test Findings

In `05_adversarial_corrections.md`, we subjected the project to 15 adversarial stress tests (`THR-01` through `THR-15`).

### Key Hardened Decisions:
- **THR-01 (Metric Flaw):** Reclassified PDCR from North Star to a secondary process metric; established Decision Comprehension as the primary outcome.
- **THR-03 (Contamination Risk):** Killed geographic cluster A/B testing due to technician mobility; established Partner-Cohort / Switchback design.
- **THR-07 (Overengineering):** Killed Bluetooth/QR peer-to-peer sync; mandated lightweight client-side SQLite rate-card caching.
- **THR-09 (Operational Deadlock):** Killed rigid 2-hour decision timers; established asynchronous quote hold with immediate technician release.
- **THR-10 (MVP Scope Creep):** Moved PDF Diagnostic Safety Certificate generation out of the Lean MVP into Phase 2 exploration.

---

# 10. Reflections & AI Leverage

### Key Product Takeaways
1. **Never Fall in Love with Your Initial Hypothesis:** We began with an instinct that "technician familiarity" was the core retention problem. The empirical evidence proved it was a 3.4% issue, while pricing opacity accounted for 37.3% of negative complaints. The most important PM skill is the humility to pivot when the evidence demands it.
2. **Marketplaces Live and Die by Supply-Side Incentives:** A consumer-facing feature that delights customers at the expense of technician earnings will trigger field rebellion and offline circumvention. The 100% diagnostic fee pass-through (`FR-08`) protects partner livelihoods regardless of customer authorization decisions.

### AI Governance in Product Management
This project leveraged AI as an analytical force multiplier under strict epistemic controls (`AI_PROCESS.md`):
- **Where AI Accelerated:** Mining customer reviews, drafting cross-reference matrices, and stress-testing edge cases.
- **Where Human Judgment Was Supreme:** Executing Decision `D004` (killing the rebooking hypothesis), bounding the problem statement (`D005`), establishing segmentation (`D006`), and enforcing non-negotiable marketplace supply floors.
