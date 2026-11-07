# Product Requirements Document (PRD)
# Post-Diagnostic Decision Scaffold (PDDS)

**Co-Creators:** Anshul Eskey ([LinkedIn](https://www.linkedin.com/in/anshul-eskey-ba0821292/) | [Email](mailto:anshuleskey999@gmail.com)) & Sagun Verma ([LinkedIn](https://www.linkedin.com/in/sagun-verma-655a122a6/) | [Email](mailto:sagunv11@gmail.com))  
**Role:** Product Manager  
**Project:** Urban Company — Two-Sided Home Services Marketplace  
**Feature:** Post-Diagnostic Decision Scaffold (PDDS)  
**Related Specs:** [Solution Architecture](01_solution_design_architecture.md) | [UX Wireframes](02_ux_flows_and_wireframes.md) | [Metrics & A/B Design](01_metrics_and_experiment_design.md) | [Executive Case Study](01_executive_case_study.md)  

---

> [!TIP]
> **PRD Quick View:** This PRD specifies the **Post-Diagnostic Decision Scaffold (PDDS)**. It replaces high-pressure verbal in-home repair quotes with a 4-primitive Lean MVP decision flow: upstream expectation setting (C1), 3-tap technician quoting (C2), transparent sunk-cost ledger (C3), and a tripartite customer decision card (C4). Critical guardrail: 100% of diagnostic visitation fees pass through to the partner even upon repair decline (`FR-08`). Downloadable PDF certificates are de-scoped to Phase 2 (`THR-10`).

---

## Table of Contents
1. [Document Governance & Epistemic Taxonomy](#document-governance--epistemic-taxonomy)
2. [Executive Product Summary](#1-executive-product-summary)
3. [Problem Definition](#2-problem-definition)
4. [Target Users & Segmentation](#3-target-users--segmentation)
5. [System Architecture & Feature Specifications](#4-system-architecture--feature-specifications)
6. [User Stories & Acceptance Criteria](#5-user-stories--acceptance-criteria)
7. [Telemetry & Analytics Specification](#6-telemetry--analytics-specification)
8. [Risks, Mitigations & Edge Cases](#7-risks-mitigations--edge-cases)

---

## Document Governance & Epistemic Taxonomy

Every requirement, statement, and operational assumption in this document carries an explicit epistemic label adhering to the project Evidence Policy:

| Tag | Epistemic Definition |
|:---|:---|
| `[FACT]` | Verified platform policy, published pricing term, or documented FAQ from primary platform sources. |
| `[RESEARCH FINDING]` | Statistically analyzed pattern from the 179-review empirical dataset (`05_evidence_matrix.md`, `E001`). |
| `[COMPANY CLAIM]` | Public assertion or commitment from Urban Company leadership / IPO prospectus without independent audit. |
| `[ANALYST SYNTHESIS]` | Logical inference or market mechanism derived by cross-referencing findings. |
| `[ASSUMPTION]` | Unverified operational condition required for system function; pending telemetry verification. |
| `[HYPOTHESIS]` | Testable proposition regarding user behavior or business outcome; strictly unproven. |
| `[DESIGN DECISION]` | Deliberate choice made in solution architecture to resolve trade-offs. |
| `[DESIGN PROPOSAL]` | Proposed marketplace policy or partner rule requiring operational and executive sign-off. |
| `[DESIGN SPECIFICATION]` | Functional rule defining software behavior under specified conditions. |
| `[ANALYTICS REQUIREMENT]` | Telemetry event or data schema that must be instrumented by engineering. |

---

# 1. Executive Product Summary

### Product & Initiative Name
**Post-Diagnostic Decision Scaffold (PDDS)** (Internal Code: `O4-PDDS`).

### The Core Problem
For customers booking diagnosis-dependent home services (e.g., appliance repairs), the final cost is inherently unknown before on-site inspection. After a professional diagnoses the fault, customers receive an unexpected repair quote while having already incurred a diagnostic/visitation fee (`E041` `[FACT]`). This creates acute uncertainty: customers struggle to understand what work is proposed, whether the quote is standard, and whether their sunk visitation fee is credited toward the repair, resulting in perceived entrapment (`E014`, `E015`, `R0163` `[RESEARCH FINDING]`).

### Target Users
- **Primary Segment:** First-Time Diagnosis-Dependent Bookers (`D006` `[DESIGN DECISION]`).
- **Secondary Business-Risk Segment:** Price-Sensitive Quote Evaluators (`D006` `[DESIGN DECISION]`).
- **Urgency Dimension:** Behavioral modifier / hypothesis only (`[BEHAVIORAL MODIFIER]`).

### Strategic Opportunity Alignment
- **Primary Anchor:** `O4` — Accept/Reject Decision Support & Sunk-Cost Clarification (`D007` `[DESIGN DECISION]`).
- **Complementary Support:** `O1` — Pre-Diagnostic Price Expectation & Cost Education (`D007` `[DESIGN DECISION]`).

### Core Product Objective
Empower customers to make an informed, confident, and autonomous post-diagnostic decision (Authorize, Decline, or Clarify) by providing structured diagnostic findings, transparent rate-card pricing, clear sunk-cost ledger accounting, and explicit warranty coverage—without optimizing coercively for repair acceptance (`[DESIGN DECISION]`).

### MVP Concept (Strictly C1–C4 Primitives)
A dual-app software scaffold comprising:
1. **C1 — Upstream Expectation:** Two-Stage Cost Expectation Card during booking (`O1`, `FR-01`).
2. **C2 — Standardized Quoting:** Partner Diagnostic Quoting Module enabling standard 3-tap SKU selection on-site (`FR-02`–`FR-04`).
3. **C3 — Sunk-Cost Ledger:** Digital Diagnostic Finding & Sunk-Cost Ledger Card on Customer App (`FR-05`).
4. **C4 — Tripartite Choice:** Digital Decision Interface (`AUTHORIZE`, `NEED TIME / CLARIFY`, `DECLINE`) (`FR-06`).
*(Phase 2 Roadmap: Automated Downloadable PDF Diagnostic Certificate de-scoped per `THR-10` — MVP delivers in-app diagnostic summary and fee receipt).*

### Business Context & Strategic Bounds
In diagnosis-dependent categories, customer trust collapses at the quote presentation moment, causing disputes and off-platform attrition (`E014`, `PAT-10` `[RESEARCH FINDING]`). PDDS establishes an auditable, system-mediated decision bridge. It does **not** redesign Urban Company's baseline pricing structure, warranty terms, or cancellation policies (`[DESIGN DECISION]`).

---

# 2. Problem Definition

### Canonical Problem Statement (`D005` — Locked)
> *"For customers booking diagnosis-dependent home services, the final cost can become uncertain after booking because the exact scope of work is determined only after on-site inspection, while the diagnostic/visitation cost and subsequent repair quote affect the customer's ability to confidently decide whether to proceed."*

### Why the Problem Exists
Home appliance repair involves physical entropy and hidden failure modes that cannot be diagnosed remotely (`[ANALYST SYNTHESIS]`). A service cannot be priced deterministically at booking. Consequently, platforms operate a two-stage transaction model:
1. **Stage 1:** Customer pays a visitation/diagnostic fee (`E041` `[FACT]`) to dispatch a professional for physical disassembly and testing.
2. **Stage 2:** Professional presents a supplemental repair quote on-site (`[FACT]`).

### Where it Occurs in the Journey
The problem occurs at the precise transition between on-site physical inspection and repair commencement (`17_ux_flows.md` Step 4 `[DESIGN SPECIFICATION]`). The customer is physically in their home alongside the technician, facing an unbudgeted quote while uncertain of their rights, the scope validity, and the fate of their visitation fee (`E015` `[RESEARCH FINDING]`).

### Customer Uncertainty at the Decision Point
1. **Scope Ambiguity:** Inability to verify if the diagnosed part failure actually requires replacement (`PAT-09` `[RESEARCH FINDING]`).
2. **Economic Composition Confusion:** Inability to tell whether the new quote includes or excludes the previously paid diagnostic fee (`R0163` `[RESEARCH FINDING]`).
3. **Price Arbitrariness:** Suspicion that the technician is pricing opportunistically on-the-spot (`E014` `[RESEARCH FINDING]`).
4. **Sunk-Cost Entrapment:** Belief that rejecting the repair means forfeiting the diagnostic fee with zero tangible value received (`R0163` `[RESEARCH FINDING]`).

### Epistemic Boundary on Downstream Effects
The following business impacts are **hypotheses to test**, not established baseline facts:
- Quote conversion lift (`[HYPOTHESIS]`).
- 90-day repeat booking retention improvement (`[HYPOTHESIS]`).
- Reduction in customer support billing disputes (`[HYPOTHESIS]`).
- Impact on technician weekly take-home pay (`[HYPOTHESIS]`).
- Elimination of off-platform defection to local repairers (`[HYPOTHESIS]`).

---

# 3. Target Users & Segmentation

### Primary User Segment: First-Time Diagnosis-Dependent Bookers (`D006`)
- **Context:** Booking an appliance repair (e.g., AC not cooling, washing machine drum error) on Urban Company for the first time (`[DESIGN SPECIFICATION]`).
- **User Need:** Needs clear mental models for how two-stage pricing works; requires transparent fault validation before committing significant funds.
- **Pain / Uncertainty:** Experienced initial booking fee as the "price of service"; feels blindsided when quoted ₹1,500–₹4,000 for parts on-site (`E014` `[RESEARCH FINDING]`).
- **Job-to-be-Done (JTBD):** *"When my appliance fails unexpectedly, I want to understand exactly what is broken and what the repair will cost, so that I can decide whether fixing it is financially sensible without feeling exploited."*
- **Known Evidence:** 28.3% of negative customer reviews cite fee surprises and quote escalation (`E014` `[RESEARCH FINDING]`); in-home vulnerability intensifies pressure (`E015` `[RESEARCH FINDING]`).
- **Unknowns:** Exact proportion of first-time vs repeat bookers who drop off at on-site quote presentation (`GAP-010` `[ANALYTICS REQUIREMENT]`).

### Secondary Segment: Price-Sensitive Quote Evaluators (`D006`)
- **Context:** Pragmatic homeowners or tenants evaluating repair feasibility against replacement cost or local unorganized alternatives (`[DESIGN SPECIFICATION]`).
- **User Need:** Line-item breakdown, benchmark rate-card verification, and written warranty guarantees (`E040`, `E048` `[FACT]`).
- **Pain / Uncertainty:** Fears technician quote inflation; considers paying only the inspection fee and sourcing a neighborhood mechanic (`PAT-10` `[RESEARCH FINDING]`).
- **JTBD:** *"When presented with a major repair estimate, I want to verify that the quote matches official platform rates and carries a genuine guarantee, so that I don't overpay compared to the local market."*
- **Known Evidence:** Community reviews document switching to neighborhood technicians when platform quotes appear inflated (`PAT-10` `[RESEARCH FINDING]`).
- **Unknowns:** Customer price-elasticity threshold where replacement of appliance is favored over repair (`[ASSUMPTION]`).
- **Operationalization Note (`THR-08`):** Price-Sensitive Quote Evaluators represent a conceptual business-risk segment. Operationalizing this segment in production via automated targeting proxies would require extensive behavioral research and telemetry validation before deployment, rather than arbitrary dwell or click thresholds.

### Out-of-Scope Users
- Customers booking fixed-scope catalog services (e.g., standard cleaning, salon, pest control) (`[DESIGN DECISION]`).
- Commercial or enterprise property facility managers (`[DESIGN DECISION]`).

---

# 4. Core Product Goal

### Unified Product Objective
> **To enable customers facing an on-site appliance repair quote to fully comprehend the diagnostic finding, scope of work, cost composition (separating sunk visitation fee from additional repair cost), rate-card benchmark, and warranty coverage, so that they can make an autonomous, pressure-free decision (Authorize, Decline, or Clarify) within the app.**

### What the Goal is NOT
- **Anti-Goal:** It is **NOT** to maximize quote acceptance rates (`[DESIGN DECISION]`).
- **Anti-Goal:** It is **NOT** to convince customers to repair aging appliances when replacement is more rational (`[DESIGN DECISION]`).
- **Anti-Goal:** It is **NOT** to reduce partner diagnostic compensation (`[DESIGN PROPOSAL]`).

---

# 5. Success Definition & Metrics Hierarchy

```
                      LEVEL 1: PRIMARY PRODUCT SUCCESS
                    Decision Comprehension & Agency
                  [Measured via In-App Pulse & Audit]
                                  │
                                  ▼
                     LEVEL 2: BEHAVIORAL SIGNALS
              Decision Latency │ In-App Clarifications
               Decline Agency  │ Rate-Card Verifications
                                  │
                                  ▼
                LEVEL 3: MARKETPLACE GUARDRAILS & HYPOTHESES
               Partner Workflow Time │ Partner Earnings Neutrality
             Support Billing Disputes │ 90-Day Cross-Category Retention
```

### Level 1: Primary Product Success (Decision Quality & Comprehension)
1. **Quote Ledger Comprehension Score:** % of customers who correctly identify (in a 1-question post-decision pulse) that their diagnostic fee was deducted from the total repair quote (`[DESIGN SPECIFICATION]`).
2. **Decision Agency Index:** Customer self-reported rating (1 to 5 scale) on: *"I felt fully in control of the decision to proceed or decline the repair"* (Target: ≥4.2/5.0) (`[DESIGN SPECIFICATION]`).
3. **Scope Clarity Rate:** % of customers reporting they clearly understood which physical component was being serviced or replaced (`[DESIGN SPECIFICATION]`).

### Level 2: Behavioral Signals (System Interaction)
1. **Self-Service Clarification Rate:** % of quote presentations where the customer taps "Clarify Scope" to view rate card / fault explainers rather than verbally debating the partner (`[ANALYTICS REQUIREMENT]`).
2. **Decision Latency:** Median elapsed time between partner quote transmission and customer in-app decision submission (Target: ≤3.0 minutes) (`[ANALYTICS REQUIREMENT]`).
3. **Explicit Decline Execution Rate:** Rate of customers selecting "Decline & Pay Inspection Only" without abandoning the session or calling support (`[ANALYTICS REQUIREMENT]`).

### Level 3: Marketplace Guardrails & Business Hypotheses
1. **Partner Workflow Overhead (Guardrail):** Median time required for partner to select diagnosis SKU and transmit quote (Strict Guardrail: ≤90 seconds; must not exceed 180 seconds) (`[DESIGN SPECIFICATION]`).
2. **Partner Earnings Neutrality (Guardrail):** Partner average hourly earnings in test cohorts must not decline by >2% compared to control (`[DESIGN PROPOSAL]`).
3. **Post-Service Billing Dispute Rate (Hypothesis):** Escalations to customer support regarding "overcharging" or "hidden fees" within 7 days of service (Hypothesized reduction: ≥25%) (`[HYPOTHESIS]`).
4. **90-Day Repeat Booking Rate (Hypothesis):** Repeat booking across any UC category among users exposed to PDDS vs control (`[HYPOTHESIS]`).

---

# 6. Core Product Principles

| # | Principle | Product Implementation & Implication |
|:---|:---|:---|
| **1** | **Decision Clarity over Persuasion** | The interface presents neutral, factual information. It must never employ urgency countdowns, artificial discounts, or fear-based messaging (`[DESIGN DECISION]`). |
| **2** | **Strict Cost Separation** | The UI strictly separates: (a) Amount Already Paid, (b) Diagnostic Credit Applied, (c) Net Additional Payable, and (d) Taxes (`[DESIGN SPECIFICATION]`). |
| **3** | **Known vs Contingent Separation** | Work confirmed by physical inspection is labeled `[CONFIRMED]`. Contingent work that depends on opening sealed assemblies is explicitly labeled `[POSSIBLE ADDITIONAL]` (`[DESIGN SPECIFICATION]`). |
| **4** | **Scope Understandability** | Technical fault jargon must be accompanied by plain-language customer explanations (e.g., "Capacitor Failure: Prevents the outdoor fan motor from starting") (`[DESIGN SPECIFICATION]`). |
| **5** | **Neutral Sunk-Cost Visibility** | Sunk diagnostic fees must be displayed as an informative ledger credit, never with coercive loss framing like "Don't waste your ₹299" (`[DESIGN DECISION]`). |
| **6** | **Equally Legitimate Choices** | Authorize (Green), Decline (Neutral Outline), and Clarify (Subtle Link) must all be visually accessible on the primary screen viewport without hidden scrolls (`[DESIGN SPECIFICATION]`). |
| **7** | **Avoid False Precision** | If an exact part price depends on OEM supplier inventory, display the official rate-card range rather than an unverified pinpoint figure (`[DESIGN SPECIFICATION]`). |
| **8** | **Minimal Partner Burden** | Quoting must require ≤3 taps on mobile for standard faults. Partners must never be forced to type long text descriptions on-site (`[DESIGN SPECIFICATION]`). |
| **9** | **Escalate Genuine Ambiguity** | When a partner encounters an unlisted fault or non-standard appliance model, provide an explicit "Custom Inspection" fallback rather than forcing a fake SKU (`[DESIGN SPECIFICATION]`). |
| **10** | **Respect Category Heterogeneity** | System rules must reflect category realities: AC repairs have high part standardization, while plumbing/carpentry have highly variable scope (`[ANALYST SYNTHESIS]`). |

---

# 7. User Journey & Entry Conditions

### Entry Trigger & Preconditions
- **Precondition 1:** Customer has booked an eligible diagnosis-dependent service category (AC, Refrigerator, Washing Machine, Microwave, Water Purifier) (`[DESIGN SPECIFICATION]`).
- **Precondition 2:** Diagnostic/visitation fee was collected at checkout or verified as authorized on arrival (`E041` `[FACT]`).
- **Entry Event:** Partner completes physical inspection, opens UC Partner App, and marks "Inspection Complete" (`17_ux_flows.md` Step 4 `[DESIGN SPECIFICATION]`).

### State Machine & Core Journey
```
[1. Booking / Checkout]
  │  └─ Customer views Two-Stage Cost Expectation Card (O1)
  ▼
[2. Physical Diagnosis]
  │  └─ Partner inspects appliance, disassembles assembly on-site
  ▼
[3. Partner Quoting Module]
  │  └─ Partner selects diagnosed fault via 3-tap hierarchical taxonomy
  ▼
[4. Customer PDDS Presentation]
  │  ├─ View 1: Digital Diagnostic Finding Summary
  │  ├─ View 2: Line-Item Cost & Sunk-Cost Ledger
  │  ├─ View 3: Official Rate-Card & Warranty Badge
  │  └─ View 4: Tripartite Choice Module
  ▼
[5. Customer Post-Diagnostic Decision]
  ├── AUTHORIZE REPAIR ──► Partner executes repair; ledger settles net payable
  ├── DECLINE REPAIR   ──► Digital Certificate issued; ₹299 credited to partner
  └── CLARIFY ON-SITE  ──► Direct communication screen; rate-card explainer
```

### Exit States
1. **State A: Authorized** — Customer authorizes proposed scope. Partner app unlocks repair checklist. Final invoice equals `[Quoted Total] - [Diagnostic Fee Paid]` (`[DESIGN SPECIFICATION]`).
2. **State B: Declined** — Customer declines repair. Job closes as "Inspection Completed Only." Customer receives downloadable Diagnostic Report; partner receives diagnostic compensation (`E047`, `E041` `[DESIGN PROPOSAL]`).
3. **State C: Clarification Requested** — Customer initiates on-site query or requests partner walkthrough before deciding (`[DESIGN SPECIFICATION]`).
4. **State D: Scope Exception / Revision** — Additional physical damage discovered during repair. Triggers mandatory secondary delta-authorization (`[DESIGN SPECIFICATION]`).

---

# 8. MVP Functional Requirements Matrix

| ID | Feature Area | User Need & Strategy Basis | Priority | Acceptance Criteria Summary | Dependencies | Open Questions |
|:---|:---|:---|:---:|:---|:---|:---|
| **FR-01** | Upstream Expectation Card | O1 / D007: Pre-diagnostic mental model of two-stage pricing (`15_product_strategy.md`) | **P0** | Shows clear 2-stage breakdown before checkout: ₹299 inspection vs ₹X repair range. | Booking Funnel CMS | GAP-007 |
| **FR-02** | Partner 3-Tap SKU Quoting | E051: Minimize partner cognitive & operational burden on-site (`16_solution_design.md`) | **P0** | Partner selects Category → Assembly → Fault in ≤3 taps; auto-populates price from rate card. | Rate Card Catalog | GAP-009 |
| **FR-03** | Digital Diagnostic Summary | PAT-09: Decouple technical fault explanation from partner verbal friction | **P0** | Customer screen displays verified symptom, fault component, and plain-language explanation. | Partner Quoting App | None |
| **FR-04** | Sunk-Cost Ledger Card | R0163: Eliminate fee confusion & perceived loss of visitation fee (`17_ux_flows.md`) | **P0** | Displays explicit arithmetic: Total Parts + Labor - Paid Diagnostic Fee = Net Additional Payable. | Billing Engine | GAP-008 |
| **FR-05** | Rate-Card & Warranty Badge | E040, E048: Reassure price sensitivity & ensure post-repair protection | **P0** | Direct hyperlink to UC official rate card + explicit 30/60/90-day warranty guarantee badge. | Warranty Service | E048 Claim Audit |
| **FR-06** | Tripartite Choice Interface | Principle 6: Preserve non-coercive agency across Authorize, Decline, and Clarify | **P0** | Screen displays: (1) Primary "Authorize Repair", (2) Equal "Decline Repair", (3) "Need Time to Decide / Clarify Scope" (`[OPERATIONAL WINDOW TBD]`). | Customer App Client | Revisit SLA TBD (`THR-09`) |
| **FR-07** | Automated Fee Crediting | E041: Operationalize diagnostic fee offset against total repair bill | **P0** | Diagnostic fee paid at booking is automatically subtracted from final payable amount upon repair completion. | Payment Gateway | GAP-008 |
| **FR-08** | In-App Diagnostic Summary & PDF Certificate | R0163: Provide tangible deliverable when customer declines repair | **P2 (Later-Stage)** | In MVP, delivers in-app diagnostic summary and fee receipt. Formal downloadable PDF certificate generation is de-scoped to a later-stage hypothesis (`THR-10`). | App Notification Service | Valuation of PDF (`THR-10`) |
| **FR-09** | Secondary Scope Amendment | Principle 3: Prevent unapproved on-site quote inflation during disassembly | **P0** | If new fault found during work, partner must submit secondary delta quote; requires explicit re-authorization. | Partner / User Sync | GAP-007 |
| **FR-10** | Partner Agency Protection | E051: Protect partner rating from customer quote rejections | **P0** | Declining a quote does NOT count against partner service completion score or rating. | Partner Rating Engine | `[DESIGN PROPOSAL]` |
| **FR-11** | Interactive Rate-Card Explainer | O1 / Secondary Segment: Deep-dive component cost comparison | **P1** | Modal showing platform median, low, and high rates for specific appliance model. | Analytics Data Pipeline | Data Coverage |
| **FR-12** | Multilingual Quote Presentation | Accessibility: Regional language support for diverse customer/partner base | **P1** | Diagnostic summary toggleable between English, Hindi, and top regional languages. Treated as design consideration / research question (`THR-13`). | Localization Service | Translation QA |
| **FR-13** | Offline Quoting Cache & Graceful Degradation | Resilience: Support basements and low-connectivity residential areas (`RSK-06`) | **P1 (Graceful)** | Partner app caches rate card locally and syncs queue in background. Offline protocol requires validation (`[DESIGN CONSTRAINT TO BE DETERMINED]`); Bluetooth P2P de-scoped (`THR-07`). | Local Mobile Storage | Engineering Validation |

---

# 9. Detailed Functional Specifications (P0 Requirements)

### FR-01: Upstream Two-Stage Expectation Card
- **Trigger:** Customer navigates to checkout for any diagnosis-dependent service (`[DESIGN SPECIFICATION]`).
- **Preconditions:** Service category flag `is_diagnosis_dependent == True` (`[DESIGN SPECIFICATION]`).
- **Information Available:** Diagnostic fee (`E041` `[FACT]`), typical category repair cost range (`[FACT]`), fee crediting policy (`E041` `[FACT]`).
- **System Behavior:** Renders an unskippable inline visual card above payment CTA:
  ```
  ┌───────────────────────────────────────────────────────────┐
  │ TWO-STAGE PRICING MODEL                                   │
  │ • Stage 1 (Today): ₹299 Diagnostic Inspection             │
  │   Technician arrives, inspects, and identifies fault.     │
  │ • Stage 2 (On-Site): Transparent Repair Quote             │
  │   If you approve repair, ₹299 is deducted from bill.      │
  │   If you decline, pay only ₹299 for the expert diagnosis. │
  └───────────────────────────────────────────────────────────┘
  ```
- **User Action:** Customer reviews card and taps "Proceed to Pay Diagnostic Fee" (`[DESIGN SPECIFICATION]`).
- **Resulting State:** Booking confirmed; transaction logged with `diagnostic_fee_prepaid = True` (`[DESIGN SPECIFICATION]`).
- **Failure Behavior:** If range data is unavailable, card displays standard policy text without numeric estimate range (`[DESIGN SPECIFICATION]`).

---

### FR-02: Partner 3-Tap SKU Quoting Module
- **Trigger:** Partner taps "Enter Diagnostic Findings" in UC Partner App on-site (`[DESIGN SPECIFICATION]`).
- **Preconditions:** Partner GPS verified at customer premises; job status is `IN_PROGRESS` (`[ASSUMPTION]`).
- **Information Available:** Pre-loaded category taxonomy, appliance sub-systems, verified rate-card SKUs (`E040` `[FACT]`).
- **System Behavior:**
  1. *Tap 1 (Assembly):* e.g., "Cooling System / Compressor".
  2. *Tap 2 (Component & Fault):* e.g., "Capacitor 45uF — Burnt / Failed".
  3. *Tap 3 (Resolution SKU):* e.g., "Replace Capacitor (Standard OEM Compatible)".
  - System automatically calculates Rate Card Standard Price: ₹850 (`E040` `[FACT]`).
  - System verifies warranty entitlement: "90-Day Parts & Service Guarantee" (`E048` `[COMPANY CLAIM]`).
- **User Action:** Partner reviews generated line items and taps "Submit Quote to Customer" (`[DESIGN SPECIFICATION]`).
- **Resulting State:** Job status transitions to `QUOTE_PENDING_CUSTOMER_APPROVAL`; payload pushed to Customer App (`[DESIGN SPECIFICATION]`).
- **Failure Behavior:** If fault not listed in standard catalog, partner taps "Custom Part / Complex Fault" triggering mandatory photo upload and supervisor review path (`[DESIGN SPECIFICATION]`).

---

### FR-03: Digital Diagnostic Finding Summary
- **Trigger:** Customer app receives quote push notification or opens active service card (`[DESIGN SPECIFICATION]`).
- **Preconditions:** Job state is `QUOTE_PENDING_CUSTOMER_APPROVAL` (`[DESIGN SPECIFICATION]`).
- **Information Available:** Diagnosed component name, observed failure mode, plain-language description (`[DESIGN SPECIFICATION]`).
- **System Behavior:** Displays clean diagnostic card:
  - **Component:** Outdoor Unit Run Capacitor.
  - **Identified Defect:** Electrical burnout causing compressor startup failure (`[DESIGN SPECIFICATION]`).
  - **Why Repair Needed:** Prevents motor from engaging; fan runs but no cooling generated (`[DESIGN SPECIFICATION]`).
  - **Component Verification:** Verified Genuine Part / Compatible OEM Specification (`E040` `[FACT]`).
- **User Action:** Customer views and digests fault context before viewing cost (`[DESIGN SPECIFICATION]`).
- **Acceptance Criteria:** 100% of standard catalog SKUs map to verified plain-language consumer descriptions (`[DESIGN SPECIFICATION]`).

---

### FR-04: Sunk-Cost & Fee Ledger Card
- **Trigger:** Customer scrolls to pricing section on Quote Screen (`[DESIGN SPECIFICATION]`).
- **Preconditions:** FR-03 rendered successfully (`[DESIGN SPECIFICATION]`).
- **Information Available:** Diagnostic fee paid at booking (`E041` `[FACT]`), rate-card part cost, rate-card labor cost, applicable taxes (`[FACT]`).
- **System Behavior:** Renders the Ledger Card with clear visual arithmetic:
  ```
  ┌───────────────────────────────────────────────────────────┐
  │ COST & PAYMENT SUMMARY                                    │
  │ Standard Repair & Part Cost:                    ₹850      │
  │ Professional Labor & Fitting:                   ₹249      │
  │ Applicable Taxes (GST):                          ₹99      │
  │ ───────────────────────────────────────────────────────── │
  │ Total Repair Value:                           ₹1,198      │
  │ Less Inspection Fee Paid:                     - ₹299 [CREDIT]
  │ ───────────────────────────────────────────────────────── │
  │ NET ADDITIONAL AMOUNT PAYABLE:                  ₹899      │
  └───────────────────────────────────────────────────────────┘
  ```
- **Acceptance Criteria:** Net additional payable must match `[Total Value] - [Diagnostic Fee]` down to exact rupee (`[DESIGN SPECIFICATION]`).

---

### FR-05: Rate-Card & Warranty Verification Badge
- **Trigger:** Rendered concurrently with Ledger Card (`[DESIGN SPECIFICATION]`).
- **System Behavior:** Displays verifiable trust attributes:
  - **Official Rate-Card Match:** Green verification checkmark: *"Verified against Urban Company AC Repair Rate Card v2026.2"* (`E040` `[FACT]`).
  - **Interactive Rate Card Link:** Tapping opens modal showing full catalog prices for AC electrical parts (`[DESIGN SPECIFICATION]`).
  - **Warranty Guarantee:** *"Includes 90-Day Protection on Capacitor & Labor. Free replacement if issue recurs"* (`E048` `[COMPANY CLAIM]`).
  - **Exclusion Link:** Tapping opens transparent exclusion rules (physical external damage, unauthorized tampering) (`E049` `[FACT]`).

---

### FR-06: Tripartite Choice Interface (Equal-Agency Architecture)
- **Trigger:** Customer views bottom action pane of Quote Screen (`[DESIGN SPECIFICATION]`).
- **System Behavior:** Renders three distinct, un-obscured decision actions:
  1. **Primary Button:** `[AUTHORIZE REPAIR — PAY NET BALANCE ON COMPLETION]` (Solid Green / Brand Fill).
  2. **Secondary Button:** `[DECLINE REPAIR — PAY ₹0 MORE]` (Neutral Outline, equal font weight).
  3. **Clarification / Pause Action:** `[Need Time to Decide / Discuss Scope with Professional]` (Underlined text link).
- **Operational Constraint (`THR-09` — Revisit Window TBD):**
  - Selecting "Need Time to Decide" allows the customer to pause the decision without immediate verbal pressure.
  - The technician is not held captive in the living room; the diagnostic visit concludes cleanly.
  - *Operational Policy:* The exact quote-lock duration, partner redispatch protocol, and second visitation fee treatment are designated as **`[OPERATIONAL WINDOW / RE-VISIT POLICY TBD]`** requiring operational testing, explicitly rejecting arbitrary 2-hour SLA promises that conflict with physical field realities.
- **Hard Constraints (Anti-Dark-Patterns):**
  - Decline button must **NOT** be hidden behind a dropdown, faint gray text, or multiple confirmation loops (`[DESIGN DECISION]`).
  - Clicking Decline must **NOT** trigger guilt-inducing copy (e.g., *"Are you sure you want to lose your ₹299 inspection credit?"*) (`[DESIGN DECISION]`).
  - No countdown timer on quote validity (`[DESIGN DECISION]`).

---

### FR-07: Automated Fee Crediting & Final Settlement
- **Trigger:** Customer taps "Authorize Repair" and technician marks "Job Completed" (`[DESIGN SPECIFICATION]`).
- **System Behavior:**
  - Invoicing engine generates tax invoice reflecting total service value (₹1,198) minus prepay credit (₹299), showing net balance ₹899 (`[DESIGN SPECIFICATION]`).
  - Customer payment link/QR code prompts strictly for ₹899 (`[DESIGN SPECIFICATION]`).
  - Partner payout credit registers ₹299 diagnostic labor credit + net repair labor earnings (`E047` `[DESIGN PROPOSAL]`).

---

### FR-08: In-App Diagnostic Summary on Decline (MVP Core) & PDF Certificate (Later-Stage Hypothesis — `THR-10`)
- **Trigger:** Customer taps "Decline Repair" and confirms choice (`[DESIGN SPECIFICATION]`).
- **System Behavior (MVP Core):**
  - Displays neutral in-app confirmation screen: *"Repair Declined. You have paid ₹299 for the expert diagnostic inspection."*
  - Automatically saves an in-app Diagnostic Finding Summary to Customer Order History:
    - Appliance category and reported symptom.
    - Timestamp and technician identity.
    - Precise fault identified: e.g., *"Burnt 45uF Capacitor"*.
    - Standardized part SKU and estimated repair cost if booked later.
    - Appliance Operational Status: *"Non-Operational / Unsafe to run without repair"*.
  - Delivers an itemized fee receipt confirming that the ₹299 fee compensated on-site diagnostic labor delivered.
- **Later-Stage Scope Note (`THR-10`):** Formal on-the-fly downloadable PDF "Diagnostic Safety Certificate" generation is **de-scoped from the MVP** to a later-stage hypothesis, pending research on whether customers actually derive tangible value from PDF certificates for uncompleted domestic repairs.

---

### FR-09: Secondary Scope Amendment (Delta Authorization)
- **Trigger:** Partner uncovers additional unobserved secondary fault after disassembling unit (`[DESIGN SPECIFICATION]`).
- **Preconditions:** Job is in `REPAIR_IN_PROGRESS` status (`[DESIGN SPECIFICATION]`).
- **System Behavior:**
  - Partner cannot unilaterally increase final invoice amount (`[DESIGN SPECIFICATION]`).
  - Partner app requires submitting a "Scope Amendment" specifying new secondary SKU (`[DESIGN SPECIFICATION]`).
  - Customer app enters "Delta Review State" with push notification:
    ```
    ┌───────────────────────────────────────────────────────────┐
    │ ADDITIONAL SCOPE DISCOVERED                               │
    │ While replacing the capacitor, the technician discovered  │
    │ damaged wiring harness insulation requiring replacement.  │
    │ Additional Part & Labor:                        + ₹350    │
    │ New Total Net Payable:                          ₹1,249    │
    │ [APPROVE ADDITIONAL WORK]   [DECLINE & PROCEED WITH CAP]  │
    └───────────────────────────────────────────────────────────┘
    ```
  - If customer declines delta, partner is instructed to complete only initial authorized scope (`[DESIGN SPECIFICATION]`).

---

### FR-10: Partner Agency & Rating Protection
- **Trigger:** Customer selects "Decline Repair" (`[DESIGN SPECIFICATION]`).
- **System Behavior:**
  - Payout engine credits the diagnostic fee payout share to partner wallet (`E047` `[DESIGN PROPOSAL]`; exact economics treated as `[OPEN BUSINESS QUESTION — THR-11]`).
  - The decline event is tagged as `QUOTE_DECLINED_BY_CUSTOMER` and strictly isolated from the partner's Job Completion Rate (JCR) and Partner Rating algorithms (`[DESIGN PROPOSAL]`).
  - In-app feedback prompt to customer evaluates the technician solely on diagnostic competence and punctuality (`PAT-09`), preventing billing-discontent bleeding into partner reviews (`[DESIGN SPECIFICATION]`).

---

### FR-13: Offline Quoting Cache & Graceful Degradation (`THR-07`)
- **Trigger:** Partner client experiences intermittent connectivity or socket timeout in basement/utility dead zones (`[DESIGN SPECIFICATION]`).
- **Preconditions:** Category rate card cached locally to mobile storage (`[DESIGN SPECIFICATION]`).
- **System Behavior (MVP Core):**
  - Partner app switches smoothly to offline quoting mode; renders pre-cached rate-card SKUs without blocking the diagnostic workflow.
  - The quote is stored locally and queued for background transmission when cellular/Wi-Fi connectivity is restored (`[DESIGN SPECIFICATION]`).
  - The customer workflow degrades gracefully: if real-time push fails, the quote state updates as soon as network packets are exchanged, or customer can view quote via refreshed pull.
- **Scope De-Scoping Note (`THR-07`):** Custom Bluetooth LE peer-to-peer handshakes, camera-based QR code syncing, encrypted P2P tokens, and offline GSM gateways are **explicitly de-scoped from the MVP**. Specific offline synchronization behavior and degraded-mode thresholds require engineering validation (`[DESIGN CONSTRAINT TO BE DETERMINED]`).

---

# 10. Information State Taxonomy

To prevent ambiguity between deterministic system facts and variable on-site conditions, all data rendered within PDDS must adhere to this three-class taxonomy:

```
┌───────────────────────────────────────────────────────────────────────────┐
│                           INFORMATION MODEL                               │
├─────────────────────────┬───────────────────────────┬─────────────────────┤
│      1. KNOWN DATA      │  2. UNKNOWN / CONTINGENT  │  3. CHOICE PATHS    │
│  (System-Deterministic) │    (Inspection-Dependent) │ (Customer-Executed) │
├─────────────────────────┼───────────────────────────┼─────────────────────┤
│ • Paid Visitation Fee   │ • Internal secondary wear │ • Authorize Quote   │
│ • Diagnosed Primary SKU │ • Part inventory latency  │ • Decline Quote     │
│ • Catalog Rate-Card Sum │ • Non-standard OEM model  │ • Request Clarify   │
│ • Net Payable Ledger    │ • Variable welding/piping │ • Escalate Issue    │
│ • Warranty Duration     │ • Structural accessibility│                     │
└─────────────────────────┴───────────────────────────┴─────────────────────┘
```

### Class 1: KNOWN Information
- **Presentation Rule:** Presented with high visual confidence and numeric certainty (`[DESIGN SPECIFICATION]`).
- **Prohibited Inference:** Never suggest a fixed price includes uninspected auxiliary components (`[DESIGN SPECIFICATION]`).
- **Missing Data Handling:** If a rate-card SKU lacks a pre-set price, the system must force a manual review state rather than displaying ₹0 (`[DESIGN SPECIFICATION]`).

### Class 2: UNKNOWN / VARIABLE Information
- **Presentation Rule:** Must be explicitly qualified with explanatory copy: *"Final price may vary if internal tubing is corroded"* (`[DESIGN SPECIFICATION]`).
- **Prohibited Inference:** Must never present potential or contingent work as mandatory or already confirmed (`[DESIGN SPECIFICATION]`).
- **Missing Data Handling:** Partner must record visual photo proof before submitting contingent scope items (`[DESIGN SPECIFICATION]`).

### Class 3: CHOICE Paths
- **Presentation Rule:** Actionable controls must clearly state financial and operational consequences of selection (`[DESIGN SPECIFICATION]`).
- **Prohibited Inference:** Must not imply that choosing "Decline" forfeits support or leaves the customer stranded without documentation (`[DESIGN DECISION]`).

---

# 11. User Stories

### Primary Segment: First-Time Diagnosis-Dependent Bookers
1. **US-01 (Pre-Booking Clarity):** *"As a first-time booker, I want to understand that my initial ₹299 fee covers diagnostic inspection and will be credited toward any subsequent repair, so that I am not startled when the technician presents a repair estimate on-site."*
2. **US-02 (Diagnostic Comprehension):** *"As a homeowner with limited technical knowledge, I want the app to explain what part is broken in simple terms, so that I don't feel dependent solely on the technician's verbal assertion."*
3. **US-03 (Sunk-Cost Settle):** *"As a budget-conscious customer, I want to see exactly how my initial ₹299 payment reduces the total repair bill, so that I know I am only paying the incremental difference."*
4. **US-04 (Autonomous Decline):** *"As a customer deciding not to proceed, I want to decline the repair directly within the app without awkward confrontation, so that I retain control over my spending."*
5. **US-05 (In-App Diagnostic Record):** *"As a customer who pays for diagnosis only, I want an in-app diagnostic summary and fee receipt detailing the fault and part needed, so that I have a verified digital record for the ₹299 paid."* *(Phase 2 Roadmap: Downloadable PDF certificate — `THR-10`)*

### Secondary Segment: Price-Sensitive Quote Evaluators
6. **US-06 (Rate-Card Validation):** *"As a price-sensitive customer, I want to verify that my quote matches the official Urban Company rate card, so that I know the technician hasn't inflated the price based on my neighborhood."*
7. **US-07 (Warranty Assurance):** *"As a cautious customer evaluating high repair costs, I want written confirmation of the 90-day parts warranty, so that I can justify fixing the appliance rather than buying a new one."*
8. **US-08 (Delta Scope Control):** *"As a customer who approved an initial quote, I want to be asked for explicit permission if additional parts are discovered during repair, so that I never receive a surprise bill at final payment."*

### Partner / Professional Persona
9. **US-09 (Fast Quoting):** *"As a service professional on a tight schedule, I want to select repair parts from a 3-tap mobile catalog, so that I can give the customer an official quote in under 2 minutes without handwriting paperwork."*
10. **US-10 (Fair Compensation):** *"As an expert technician, I want to be compensated fairly for my diagnostic labor and have my rating protected when a customer declines a quote, so that I am never penalized for delivering an honest inspection."*

---

# 12. Concrete Behavioral Acceptance Criteria

### P0 Acceptance Criteria (Engineering Verification Checklist)

- [ ] **AC-01 (Pre-Booking Card):** When an eligible repair service is loaded in the checkout flow, the Two-Stage Cost Expectation Card must render with the exact verified category diagnostic fee (`E041`) and explain the credit mechanism before payment authorization.
- [ ] **AC-02 (Fee Separation):** The Quote Screen must render three distinct numeric rows: (1) `Total Repair & Parts Value`, (2) `Less Diagnostic Fee Paid`, and (3) `Net Additional Payable`.
- [ ] **AC-03 (Arithmetic Integrity):** The UI must dynamically calculate `Net Additional Payable = Total Repair Value - Paid Fee`. If `Total Repair Value < Paid Fee`, `Net Additional Payable` must equal ₹0 (no negative balance displayed).
- [ ] **AC-04 (Decline Path Parity):** The "Decline Repair" button must be visible on the initial quote viewport alongside "Authorize Repair" on viewports of 360px width or greater without vertical scrolling.
- [ ] **AC-05 (Decline Flow Completion):** Selecting "Decline Repair" must transition the service state to `COMPLETED_DIAGNOSIS_ONLY` within ≤2 network round-trips and suppress further payment requests.
- [ ] **AC-06 (In-App Diagnostic Record):** Upon transition to `COMPLETED_DIAGNOSIS_ONLY`, the system must render an in-app diagnostic summary screen within ≤2.0 seconds containing partner name, date, diagnosed component, and prepaid fee receipt. *(Downloadable PDF generation is de-scoped to Phase 2 roadmap per `THR-10`).*
- [ ] **AC-07 (Partner Payout Separation):** When a quote is declined, the partner ledger must credit diagnostic labor payout (`E047`) and log partner rating impact as `NEUTRAL / EXCLUDED`.
- [ ] **AC-08 (Rate Card Audit Link):** Tapping "View Rate Card" on the Quote Screen must open a read-only catalog view filtered specifically to the active appliance category within ≤1.0 second.
- [ ] **AC-09 (Warranty Confirmation):** Every approved quote must display an explicit warranty validity duration (e.g., 30, 60, or 90 days) alongside an expandable list of standard exclusion terms (`E048`, `E049`).
- [ ] **AC-10 (Secondary Quote Lock):** Once a quote is authorized, the final invoice cannot exceed the authorized amount unless a secondary scope amendment (FR-09) is explicitly accepted by the customer.

---

# 13. Scope & Prioritization Matrix

```
┌───────────────────────────────────────────────────────────────────────────┐
│                        MVP SCOPE SPECIFICATION                            │
├─────────────────────────────────────┬─────────────────────────────────────┤
│         IN SCOPE (P0 / MVP)         │         EXCLUDED (OUT OF MVP)       │
├─────────────────────────────────────┼─────────────────────────────────────┤
│ • Pre-booking Two-Stage Card (O1)   │ • ML dynamic price estimation       │
│ • Partner 3-tap SKU Quoting Module  │ • In-app live video escalation desk │
│ • Customer Diagnostic Finding Card  │ • Appliance scrap / trade-in market │
│ • Sunk-cost fee ledger accounting   │ • Universal cancellation redesign   │
│ • Official Rate Card & Warranty tag │ • Broad marketplace loyalty wallets │
│ • Tripartite Choice UI (Auth/Dec)   │ • Multi-stage diagnostic escrow     │
│ • Digital Diagnostic Certificate    │ • Automated third-party part buying │
│ • Partner rating decline protection │ • Customer telephony masking rework │
└─────────────────────────────────────┴─────────────────────────────────────┘
```

### Prioritization Categorization
- **P0 (Must-Have for MVP Launch — Lean Decision Core):** FR-01, FR-02, FR-03, FR-04, FR-05, FR-06, FR-07, FR-09, FR-10. These represent the lean, focused closed-loop system required to deliver transparency, demystify fee crediting, and preserve customer agency without unnecessary infrastructure bloat.
- **P1 (Operational Enhancements & Graceful Degradation):** FR-11 (Interactive rate card comparison), FR-12 (Multilingual localization as a design consideration / research question — `THR-13`), FR-13 (Offline quoting cache with basic queue sync and graceful degradation — `THR-07`).
- **P2 (Later-Stage Hypotheses & Evaluative Features):** FR-08 (Downloadable PDF Diagnostic Safety Certificate — de-scoped to test whether users value formal PDF docs — `THR-10`), automated appliance replacement recommendation engine, partner quote accuracy benchmarking algorithm.

---

# 14. Non-Functional Requirements (NFRs)

### 1. Decision Latency & Performance
- **NFR-01 (Quote Push Latency):** When the partner submits a quote, the Customer App must receive and render the PDDS Quote Screen within ≤3.0 seconds under 4G network conditions (`[DESIGN SPECIFICATION]`).
- **NFR-02 (Catalog Search Responsiveness):** Partner app hierarchical SKU selector must filter and return category parts in ≤200ms on standard mid-tier Android devices (`[DESIGN SPECIFICATION]`).

### 2. Operational & Offline Resilience
- **NFR-03 (Offline Quote Formulation):** If mobile network connectivity is lost on-site, the Partner App must allow full quote formulation using locally cached rate-card data (`GAP-009` `[DESIGN SPECIFICATION]`).
- **NFR-04 (State Recovery):** If the customer app crashes or battery dies during quote review, reloading the app must restore the Quote Screen state immediately without resetting partner inputs (`[DESIGN SPECIFICATION]`).

### 3. Auditability & Financial Integrity
- **NFR-05 (Quote Immutability):** Every submitted quote must generate an immutable, timestamped JSON event payload capturing partner SKU selections, rate-card baseline prices, and customer decision timestamps for support auditing (`[ANALYTICS REQUIREMENT]`).
- **NFR-06 (Double Billing Prevention):** Payment systems must enforce a database-level idempotency key ensuring a diagnostic fee cannot be charged twice or omitted from final invoice reconciliation (`[DESIGN SPECIFICATION]`).

### 4. Accessibility & Clarity Standards
- **NFR-07 (Typography & Contrast):** All pricing figures and status labels must meet WCAG 2.1 AA standards (minimum 4.5:1 contrast ratio against background) (`[DESIGN SPECIFICATION]`).
- **NFR-08 (Plain Language Compliance):** Technical component names must include parenthetical functional descriptions (e.g., *"Thermostat (Temperature Sensor)"*) (`[DESIGN SPECIFICATION]`).

---

# 15. Partner & Three-Party Marketplace System

```
                  ┌─────────────────────────────────────────┐
                  │             URBAN COMPANY               │
                  │   Rate Card Governance & Fee Ledger     │
                  └────────────┬───────────────┬────────────┘
                               │               │
                     Payout &  │               │ Quoting
                     Policy    │               │ Scaffold
                               ▼               ▼
                  ┌────────────────┐       ┌────────────────┐
                  │    PARTNER     │◄─────►│    CUSTOMER    │
                  │  Professional  │       │ Decision Maker │
                  └────────────────┘       └────────────────┘
                             In-Home Interaction &
                             Physical Appliance Diagnosis
```

### 1. Partner Operational Workflow
- **Diagnostic Capture:** Partner must be equipped with an intuitive, standardized quoting tool requiring minimal typing to prevent on-site delays (`E051` `[ANALYST SYNTHESIS]`).
- **Time Overhead Constraint:** Formulating and transmitting a quote must take ≤90 seconds for 80% of standard repairs (`[DESIGN SPECIFICATION]`).

### 2. Partner Compensation Policy (`[DESIGN PROPOSAL]`)
- Under no circumstances should a customer decline cause the partner to forfeit fair compensation for physical inspection labor.
- Drawing on the partner protection principle in Urban Company's historical partner welfare disclosures regarding cancellation fee pass-through (`E047` `[COMPANY CLAIM]`), the proposed product mandates that 100% of the platform-defined diagnostic labor share must be credited to the partner upon verified completion of on-site inspection, regardless of whether the customer authorizes or declines the subsequent repair (`[DESIGN PROPOSAL]`).

### 3. Partner Performance Rating Protection (`[DESIGN PROPOSAL]`)
- Customer quote rejection must **never** be treated as a service cancellation or partner failure (`[DESIGN PROPOSAL]`).
- Declines must be excluded from partner fulfillment score calculations to eliminate partner pressure to coerce customers into unneeded repairs (`[DESIGN PROPOSAL]`).

---

# 16. Edge Cases & Exception Workflows

### 1. Quote Changes After Initial Recommendation
- **Scenario:** Partner submits quote for Capacitor; upon installing, discovers motor windings are seized (`[DESIGN SPECIFICATION]`).
- **Product Behavior:** System blocks partner from editing original quote. Requires initiation of FR-09 (Secondary Scope Amendment) displaying delta cost. Customer must explicitly authorize delta; if declined, initial work is rolled back or settled safely (`[DESIGN SPECIFICATION]`).
- **Unresolved Policy:** Policy for labor allocation if customer aborts halfway through multi-stage repair (`GAP-008`).

### 2. Multiple Interdependent Repair Items
- **Scenario:** Diagnosis reveals both a PCB failure and a sensor fault (`[DESIGN SPECIFICATION]`).
- **Product Behavior:** Ledger renders modular multi-item breakdown with independent checkboxes if items are mechanically separable, or an "All-or-Nothing Package" if technically interdependent (`[DESIGN SPECIFICATION]`).

### 3. Part Availability Uncertainty
- **Scenario:** Fault diagnosed requires an OEM part not carried in partner vehicle inventory (`[DESIGN SPECIFICATION]`).
- **Product Behavior:** Quote explicitly flags: *"Part Requires Sourcing (Estimated 24-48 hr procurement)"*. Gives customer option to authorize procurement visit or decline with Diagnostic Certificate (`[DESIGN SPECIFICATION]`).

### 4. Customer Declines After Paying Diagnostic Fee
- **Scenario:** Customer evaluates ₹2,500 quote on an old machine and decides to replace the appliance (`[DESIGN SPECIFICATION]`).
- **Product Behavior:** Selecting "Decline" immediately triggers FR-08, delivering a Diagnostic Safety Certificate. Partner collects zero cash on-site; system settles diagnostic fee via prepaid booking (`[DESIGN SPECIFICATION]`).

### 5. Customer Requests On-Site Clarification
- **Scenario:** Customer does not understand why both gas refill and coil brazing are quoted (`[DESIGN SPECIFICATION]`).
- **Product Behavior:** Customer taps "Clarify Scope". App presents interactive diagram of AC refrigerant cycle. If still unresolved, prompts: *"Discuss with technician on site. Your quote remains saved"* (`[DESIGN SPECIFICATION]`).

### 6. Warranty-Covered or Partially Covered Work
- **Scenario:** Appliance was serviced by UC 45 days prior and qualifies for 90-day warranty (`E048` `[COMPANY CLAIM]`).
- **Product Behavior:** System checks order history linked to appliance serial number. If valid, quote auto-applies `WARRANTY_DISCOUNT = 100%` on eligible parts, showing Net Payable ₹0 (`[DESIGN SPECIFICATION]`).

### 7. Category-Specific Quoting Variations
- **Scenario:** Water Purifier filter replacement vs Plumbing pipe burst (`[ANALYST SYNTHESIS]`).
- **Product Behavior:** System applies category rules: Water Purifiers use strict SKU filter cartridges (`E040`); Plumbing uses base time-plus-materials rate ranges (`[DESIGN SPECIFICATION]`).

### 8. Customer Disputes Quote Authenticity
- **Scenario:** Customer claims local market charges half the rate-card price (`PAT-10` `[RESEARCH FINDING]`).
- **Product Behavior:** App displays "Why Urban Company Pricing?" breakdown: highlights 90-day warranty (`E048`), background-verified technicians, and standardized genuine parts (`E040`). Customer retains full right to decline without penalty (`[DESIGN SPECIFICATION]`).

---

# 17. Metrics & Measurement Framework

| Metric Name | Category | Exact Definition | Why It Matters | Interpretation Caveat | Segment Relevance |
|:---|:---|:---|:---|:---|:---|
| **Quote Ledger Comprehension Rate** | Primary Success | % of customers correctly identifying net payable arithmetic in 1-click survey. | Direct measure of problem resolution (`D005`). | Self-reported survey data; sample size dependent. | Primary Segment |
| **Decision Agency Score** | Primary Success | Average score (1–5) on post-decision perceived agency prompt. | Proves customer does not feel trapped (`R0163`). | Must benchmark against current-state baseline. | Primary & Secondary |
| **Post-Diagnostic Decision Completion Rate (PDCR)** | Secondary Process | % of presented quotes reaching an explicit digital outcome (Authorize, Decline, Clarify/Pause). | Measures operational capture of explicit customer choices, eliminating verbal dropouts. | **Process completion only (`THR-01`):** 100% decline would produce 100% PDCR while destroying revenue; must be strictly coupled with Quote Acceptance Volume Floor and Partner Earnings Guardrails. | Both Segments |
| **Self-Service Clarification Rate** | Behavioral | % of quote views triggering in-app rate-card / explainer modals. | Measures engagement with transparent information. | High rates could indicate confusing copy if not paired with clarity. | Secondary Segment |
| **Decision Latency** | Behavioral | Elapsed seconds between quote render and customer choice submission. | Measures decision friction and cognitive ease. | Extremely fast latency (<10s) may indicate blind clicking. | Both Segments |
| **Clean Decline Rate** | Behavioral | % of customers declining quote who complete session without support escalation. | Validates decline is experienced as a legitimate, friction-free choice. | Decline rate itself is neutral; escalation rate is critical. Decline is never counted as a commercial product success. | Secondary Segment |
| **Partner Quoting Overhead** | Guardrail | Median time for partner to formulate and transmit quote in app. | Protects partner operational productivity. | Network connectivity drops may inflate apparent time. | Partner Persona |
| **Partner Hourly Earnings** | Guardrail | Average partner take-home pay per on-duty hour in test vs control. | Ensures platform changes do not impair technician livelihood. | Must normalize for seasonal AC demand swings. | Partner Persona |
| **Billing Support Dispute Rate** | Hypothesis | % of completed jobs resulting in "overcharging" support tickets within 7 days. | Primary business hypothesis: clarity reduces post-service friction. | Downstream lag of 7–14 days required for data maturity. | Both Segments |
| **90-Day Cross-Category Repeat Rate** | Hypothesis | % of customers booking another UC category within 90 days of quote event. | Ultimate platform trust metric (`15_product_strategy.md`). | Long measurement horizon; multi-factor attribution. | Primary Segment |

---

# 18. Experimentation & Validation Roadmap

```
STAGE 1: Comprehension Lab Validation (Usability Testing)
   │  └─ Prototype test with 20 users; validate mental model & ledger arithmetic
   ▼
STAGE 2: Shadowed Field Usability Pilot
   │  └─ 25 live customer-partner visits in single metro; shadow on-site quoting
   ▼
STAGE 3: Contamination-Aware Controlled Experiment [PROPOSED EXPERIMENT DESIGN]
   │  └─ Partner-Cohort Randomization or Switchback Design (Gurgaon & Bengaluru)
   ▼
STAGE 4: Marketplace Operational Rollout & Guardrail Monitoring
      └─ Progressive category rollout gated by partner earnings and dispute data
```

### Stage 1: Comprehension Lab Validation
- **Primary Question:** Do users facing a two-stage quote understand why the diagnostic fee is credited?
- **Hypothesis:** ≥80% of test participants can correctly calculate net payable without facilitator prompt (`[HYPOTHESIS]`).
- **Primary Measure:** Pass rate on 3 standardized scenario comprehension questions (`[DESIGN SPECIFICATION]`).
- **Iteration Trigger:** If <75% comprehend fee credit, redesign ledger visual hierarchy (`[DESIGN DECISION]`).

### Stage 2: Shadowed Field Usability Pilot
- **Primary Question:** Does the 3-tap quoting module function smoothly in real home conditions without partner resistance?
- **Primary Measure:** Median partner quote creation time; observed customer verbal hesitation (`[DESIGN SPECIFICATION]`).
- **Guardrail:** Partner workflow time must be ≤120 seconds (`[DESIGN SPECIFICATION]`).
- **Iteration Trigger:** If partners resort to manual verbal quoting or complain of app complexity (`[DESIGN SPECIFICATION]`).

### Stage 3: Contamination-Aware Controlled Experiment (`[PROPOSED EXPERIMENT DESIGN]` — `THR-03`)
- **Primary Question:** Does PDDS increase decision comprehension and reduce billing disputes while maintaining partner economic neutrality?
- **Experimental Design Rationale (`THR-03`):** Technician mobility across contiguous geographic pin codes and micro-markets causes severe cross-cell contamination under simple geographic cluster randomization. To mitigate spillover, the experiment proposes:
  1. **Partner-Cohort Randomization:** Randomizing specific technician cohorts to treatment or control protocols regardless of dispatch geohash; OR
  2. **Switchback / Time-Based Design:** Alternating treatment and control schedules across pilot metros (e.g., alternating days or multi-day time blocks).
- **Hypothesis:** Treatment cohort exhibits ≥25% drop in billing disputes with zero statistically significant drop in partner earnings (`[PROPOSED EXPERIMENT TARGET]`).
- **Primary Measure:** Support dispute rate per 1,000 completed bookings (`[ANALYTICS REQUIREMENT]`).
- **Guardrails:** Partner hourly earnings drop ≤2%; job cancellation without fee payment ≤1% (`[DESIGN SPECIFICATION]`).
- **Design Status:** Labeled strictly as **`[PROPOSED EXPERIMENT DESIGN]`**; exact statistical power, cluster parameters, and duration require validation by experimentation engineering.

### Stage 4: Marketplace Operational Monitoring
- **Primary Question:** Does increased decision transparency preserve supply-side retention over 60 days?
- **Primary Measure:** Partner monthly retention and active hours in treatment zones (`[ANALYTICS REQUIREMENT]`).
- **Iteration Trigger:** Any sustained drop in partner supply hours triggers immediate policy review (`[DESIGN PROPOSAL]`).

---

# 19. Dependencies & Technical Preconditions

### Known Dependencies
1. **Catalog Rate-Card Repository:** Structured pricing catalog mapping appliance components to standard prices (`E040` `[FACT]`).
2. **Checkout Diagnostic Fee Surcharge Module:** Platform capability to isolate and bill a diagnostic/visitation fee at booking (`E041` `[FACT]`).
3. **Customer & Partner Mobile App Clients:** iOS and Android native containers capable of push-triggered modal state rendering (`[FACT]`).
4. **Automated Invoicing Engine:** Service calculating line-item GST and applying pre-payment credit lines (`[FACT]`).

### Dependencies to Validate (`[ASSUMPTION]`)
1. **Partner Real-Time Quoting Service:** Verification of whether current partner app has real-time socket connection or relies on polling (`GAP-009`).
2. **Dynamic PDF Generation Infrastructure:** High-throughput generation of Diagnostic Certificates upon decline event (`[LATER-STAGE ENABLER — DE-SCOPED FROM MVP — THR-10]`).
3. **Partner Rating Exclusion Rules:** Architectural capability to isolate `QUOTE_DECLINED` tags from partner rating scoring pipeline (`GAP-010`, `[DESIGN PROPOSAL]`).

### Partner Hardware & OS Performance Considerations (`[DESIGN CONSTRAINTS]`)
*Surfaced via `21_red_team_review.md` (Question 12): Addressing real-world Indian gig-worker device fragmentation.*
1. **Target Device Baseline:** Partner client must run reliably on budget Android devices common among gig workers (e.g., Android 10+, 2GB RAM class hardware).
2. **Memory & Performance Budgets (`THR-12` Classification):**
   - Client-side catalog storage footprint: `[TBD — ENGINEERING VALIDATION REQUIRED]`. Must be minimized to avoid consuming worker device storage.
   - Quoting module peak RAM allocation: `[TBD — ENGINEERING VALIDATION REQUIRED]`. Must avoid triggering OS-level background termination (`OutOfMemory` kills) on aggressive Android OEM skins (MIUI, Funtouch).
   - Cold-start time to quoting interface: `[TBD — ENGINEERING VALIDATION REQUIRED]`. Must ensure fluid field operation without stalling the on-site visit.
3. **Battery & Screen Ergonomics:**
   - High-contrast sunlight UI theme for outdoor utility balconies.
   - Touch target minimum size: $\ge 48 \times 48\text{ dp}$ with generous hit-slop padding to accommodate technicians with soiled hands or protective gloves.

---

# 20. Telemetry & Analytics Requirements

The following event schema must be instrumented by engineering (`[ANALYTICS REQUIREMENT]`):

| Event Name | Trigger Context | Required Payload Parameters |
|:---|:---|:---|
| `pdds_upstream_card_viewed` | Pre-booking checkout screen loads | `service_category`, `diagnostic_fee_amount`, `user_booking_history_count` |
| `pdds_partner_quote_started` | Partner taps "Enter Diagnostic Findings" | `job_id`, `partner_id`, `timestamp_start` |
| `pdds_partner_quote_submitted` | Partner transmits quote to customer | `job_id`, `sku_list`, `total_quote_value`, `diagnostic_credit_value`, `net_payable` |
| `pdds_quote_screen_rendered` | Quote appears on customer screen | `job_id`, `customer_id`, `connection_type`, `render_latency_ms` |
| `pdds_rate_card_clicked` | Customer taps "View Official Rate Card" | `job_id`, `sku_viewed`, `dwell_time_seconds` |
| `pdds_warranty_details_clicked`| Customer taps warranty badge | `job_id`, `warranty_days_displayed` |
| `pdds_decision_submitted` | Customer taps Authorize, Decline, or Clarify | `job_id`, `decision_action` (`AUTH` / `DEC` / `CLARIFY`), `time_to_decision_sec` |
| `pdds_certificate_generated` | Diagnostic Certificate issued on decline | `job_id`, `certificate_id`, `delivery_channel` (`IN_APP` / `PDF`) |
| `pdds_delta_quote_initiated` | Secondary scope amendment triggered | `job_id`, `initial_quote_val`, `delta_quote_val`, `delta_sku` |
| `pdds_post_decision_pulse_rated`| Customer responds to 1-click agency prompt| `job_id`, `agency_score_1_to_5`, `ledger_comprehension_flag` |

---

# 21. Rollout & Risk Gating Strategy

```
Phase 1: Internal Sandbox Testing (End-to-End Simulation)
   │
Phase 2: Closed Alpha Pilot (Single Category: AC Repair, Gurgaon Central)
   │  └─ Gated by Partner Workflow Time ≤ 90s & App Crash Free Rate ≥ 99.5%
   ▼
Phase 3: Contamination-Aware Beta Rollout (Partner-Cohort or Switchback Design, Delhi NCR & Bengaluru) [`PROPOSED EXPERIMENT DESIGN`]
   │  └─ Gated by Partner Earnings Neutrality & Zero Increase in Escalations
   ▼
Phase 4: General Availability (All Diagnostic Categories Across Metros)
```

### Rollout Halt / Reversal Triggers (Immediate Kill-Switch)
The rollout will be immediately suspended and reverted to baseline if:
1. Partner quoting time exceeds 180 seconds on average, leading to on-site partner revolt (`[DESIGN SPECIFICATION]`).
2. Partner weekly take-home earnings drop by >5% due to improper fee settlement (`[DESIGN PROPOSAL]`).
3. Customer on-site abandonment increases by >3% without executing an in-app choice (`[DESIGN SPECIFICATION]`).
4. System fails to deliver diagnostic fee credit to partner on declined jobs (`[DESIGN PROPOSAL]`).

---

# 22. PRD Risk Register

| Risk Event | Why It Matters | Impact & Likelihood | Mitigation Strategy | Early Warning Signal | Owner |
|:---|:---|:---:|:---|:---|:---|
| **R-01: Partner Cognitive Friction** | If quoting is too slow, partners will quote verbally off-platform. | High / Medium | 3-tap SKU taxonomy; local caching; zero freeform text entry. | Partner quote creation duration >120s. | Product / Ops |
| **R-02: Perceived Sunk-Cost Pressure** | Showing the fee could make customers feel pressured to authorize. | High / Low | Neutral ledger design; explicit "Decline = Pay ₹0 More" button. | Drop in Decision Agency Index ratings. | Product Design |
| **R-03: Surge in Quote Rejections** | Transparent pricing might lead more customers to decline repairs. | Medium / Medium | Ensure decline is treated as legitimate; provide in-app diagnostic summary and fee receipt (PDF certificate de-scoped to later-stage hypothesis — `THR-10`). | Decline rate increases >15% without drop in disputes. | Business / PM |
| **R-04: Off-Platform Local Leaks** | Customer takes diagnosis and hires local mechanic (`PAT-10`). | High / Medium | Highlight 90-day warranty (`E048`) and standardized parts pricing (`E040`). | Post-decline repeat bookings plummet. | Retention PM |
| **R-05: Non-Standard Fault Failure** | Rare appliance models lack catalog rate-card mapping. | Medium / High | Provide "Custom Inspection" fallback with supervisor assist. | High volume of "Custom SKU" selections. | Operations Ops |
| **R-06: Partner Supply Pushback** | Technicians fear transparency will lower their earnings. | High / Low | Guarantee diagnostic labor payout (`[OPEN BUSINESS QUESTION — THR-11]`); protect fulfillment rating. | Partner app NPS / churn spike. | Partner Ops |
| **R-07: In-Home Partner Defiance / Collusion** | Partner tells customer to ignore the app and pay cash (`THR-06`). | High / Low | Treated as residual marketplace risk / hypothesis to monitor. Require in-app customer authorization before partner app unlocks. | Discrepancy between quote status and GPS time. | Trust & Safety |
| **R-08: Secondary Fault Friction** | Customer feels cheated when a second fault is found during repair. | High / Medium | Mandatory FR-09 delta quote with photo proof and customer sign-off. | Escalations regarding "bill increase halfway". | Product Ops |
| **R-09: Intermittent Connectivity** | Apartment basements lack 4G connectivity for real-time quoting. | Medium / High | Full local rate-card cache on partner app with graceful background queue sync; Bluetooth P2P de-scoped (`THR-07`). | Timeout errors on quote transmission. | Engineering |
| **R-10: False Warranty Expectations**| Customer expects warranty on unserviced parts of old appliance. | Medium / Medium | Clear inline badge explaining warranty applies solely to replaced SKU. | Disputes regarding unrelated secondary failures. | Support Ops |
| **R-11: Support Team Overwhelm** | Clarification requests flood live customer service. | Low / Low | Route clarifications on-site directly to the active technician. | Spike in quote-stage chat ticket volume. | Support Lead |

---

# 23. Open Questions & Knowledge Gap Register

The following items are recognized knowledge gaps and operational dependencies requiring active validation (`GAP-007` to `GAP-010`):

| Question ID | Unresolved Operational / Telemetry Question | Impact on Specification | Validation Plan |
|:---|:---|:---|:---|
| **GAP-007** | What is the exact current on-site quote transmission protocol used by Urban Company partners? | Informs whether native push or SMS fallback is required for customer quote delivery. | Shadow 10 live partner visits in Phase 1 pilot. |
| **GAP-008** | How is the net payment collected on-site (partner QR code, customer app payment gateway, or cash)? | Dictates payment gateway webhook integration rules for fee offsetting. | Consult internal UC payments engineering documentation. |
| **GAP-009** | What are the exact offline capabilities and storage limits of the UC Partner Android app? | Constrains the size and update frequency of the local rate-card cache. | Technical architecture review with Partner Platform Lead. |
| **GAP-010** | What is the historical baseline quote rejection rate and its impact on partner ranking algorithms? | Establishes statistical baseline for Experiment Stage 3 guardrails. | Analytics pull on diagnostic-only booking completion codes. |
| **OQ-01** | What proportion of appliance repairs involve unlisted or obsolete OEM spare parts? | Determines capacity requirements for the custom supervisor quoting desk. | Review 6 months of historical technician invoice adjustments. |
| **OQ-02** | What is the exact category variance in diagnostic fee pricing across Tier-1 vs Tier-2 cities? | Ensures dynamic expectation cards pull localized price figures accurately. | Audit published city-level service rate cards. |

---

# 24. Explicit Scope Boundaries (Non-Goals)

To preserve engineering focus and prevent scope creep, the following areas are **strictly excluded** from the PDDS MVP release:

1. **No Universal Pricing Restructuring:** PDDS does not alter Urban Company's baseline rate-card prices, labor rates, or commission take-rates (`[DESIGN DECISION]`).
2. **No General Cancellation Rework:** Cancellations occurring prior to partner arrival on-site are handled by existing platform policies and are out of scope (`[DESIGN DECISION]`).
3. **No General Customer Support Overhaul:** PDDS does not replace or redesign the Zendesk/in-app support ticket routing system (`[DESIGN DECISION]`).
4. **No Appliance Buyback / Trade-In Engine:** Recommending or facilitating the purchase of new replacement appliances is deferred to future portfolio initiatives (`[DESIGN DECISION]`).
5. **No Telephony Masking Changes:** Voice call privacy mechanisms between customer and partner remain unmodified (`[DESIGN DECISION]`).
6. **No Speculative Machine Learning Estimators:** The MVP relies strictly on deterministic rate-card matching, not unverified AI price prediction algorithms (`[DESIGN DECISION]`).

---

# 25. End-to-End Traceability Matrix

| PRD Requirement | Decision Anchor | Strategy Principle | Solution Component | UX Flow Step | Core Evidence ID | Target Metric |
|:---|:---|:---|:---|:---|:---|:---|
| **FR-01 (Upstream Card)** | D007 (O1) | Principle 2 (Cost Separation) | Component 1 (`16_solution_design.md`) | UX-01 (`17_ux_flows.md`) | `E041`, `E014` | Upstream Dropoff / Comprehension |
| **FR-02 (Partner Quoting)**| D007 (O4) | Principle 8 (Minimal Burden) | Component 6 (`16_solution_design.md`) | UX-04 (`17_ux_flows.md`) | `E051`, `E040` | Partner Quoting Overhead (≤90s) |
| **FR-03 (Diagnostic Summary)**| D005 / D006 | Principle 4 (Scope Clarity) | Component 2 (`16_solution_design.md`) | UX-04 (`17_ux_flows.md`) | `PAT-09`, `E015` | Scope Clarity Rating |
| **FR-04 (Sunk-Cost Ledger)**| D005 / D007 | Principle 2 & 5 (Cost Ledger) | Component 3 (`16_solution_design.md`) | UX-04 (`17_ux_flows.md`) | `R0163`, `E041` | Ledger Comprehension Score |
| **FR-05 (Rate-Card & Warranty)**| D006 (Sec) | Principle 3 (Known vs Variable) | Component 4 (`16_solution_design.md`) | UX-04 (`17_ux_flows.md`) | `E040`, `E048` | Rate-Card Verifications |
| **FR-06 (Tripartite Choice)**| D007 (O4) | Principle 6 (Equal Agency) | Component 5 (`16_solution_design.md`) | UX-04 (`17_ux_flows.md`) | `R0163`, `E015` | Decision Agency Score (≥4.2) |
| **FR-07 (Fee Crediting)** | D005 / D007 | Principle 2 (Cost Separation) | Component 3 (`16_solution_design.md`) | UX-05A (`17_ux_flows.md`)| `E041`, `E047` | Billing Dispute Rate |
| **FR-08 (Diagnostic Cert)** | D007 (O4) | Principle 5 (Sunk-Cost Value) | Component 5 (`16_solution_design.md`) | UX-05B (`17_ux_flows.md`)| `R0163`, `PAT-10` | Clean Decline Rate |
| **FR-09 (Delta Scope Lock)** | D005 | Principle 3 (Scope Transparency) | Component 6 (`16_solution_design.md`) | UX-07 (`17_ux_flows.md`) | `E014`, `E026` | Secondary Scope Dispute Rate |
| **FR-10 (Partner Protection)**| D007 (O4) | Principle 8 (Supply Protection) | Component 6 (`16_solution_design.md`) | UX-05B (`17_ux_flows.md`)| `E047`, `E051` | Partner Hourly Take-Home Pay |

---

# 26. PRD Quality & Evidence Audit

Before final release, this PRD was subjected to a comprehensive internal quality audit against project standards:

### 1. Evidence Discipline Compliance
- [x] **No Inferred Behavior Treated as Fact:** Current-state quoting and payment mechanisms are explicitly flagged as unobserved (`GAP-007`, `GAP-008`).
- [x] **E041 Scope Qualified:** Diagnostic/visitation fee policy is strictly designated as applying to specified diagnosis-dependent repair flows, never as a universal platform rule.
- [x] **PAT-10 Framing:** Quoted accurately as qualitative community review evidence documenting customer switching to neighborhood mechanics; no unverified claims of platform-wide defection rates.
- [x] **E047 & E048 Attribution:** Partner diagnostic labor compensation and 90-day warranty coverage are explicitly attributed as company claims/precedents and labeled `[COMPANY CLAIM]` / `[DESIGN PROPOSAL]`.

### 2. Product Logic & Agency Protection
- [x] **Decision Chain Traceability:** 100% of P0 requirements directly trace to locked anchors D005, D006, and D007.
- [x] **O4 Primary / O1 Complementary:** O4 drives the on-site decision scaffold; O1 is scoped strictly as an upstream expectation setting card.
- [x] **Customer Agency Hard Constraint:** Decline is fully supported as an equal, respectable, friction-free choice with zero loss-framing copy or artificial urgency countdowns.
- [x] **Partner Neutrality:** Explicit mechanisms protect partner earnings and performance ratings from customer quote rejections.

### 3. Engineering Feasibility & Scope Discipline
- [x] **No Invented Backend Architecture:** No speculative database schemas, API contracts, or infrastructure designs were created.
- [x] **Explicit Non-Goals:** Clean exclusions of general pricing overhauls, cancellation redesigns, and speculative ML price models.
- [x] **Testable Acceptance Criteria:** Every functional requirement specifies concrete trigger, system behavior, and verifiable pass/fail condition.

---
*Canonical PRD `18_prd.md` complete and locked for Product Review.*
