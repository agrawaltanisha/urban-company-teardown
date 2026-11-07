# Product Strategy & Marketplace Economics: Post-Diagnostic Decision Scaffold (PDDS)

**Co-Creators:** Anshul Eskey ([LinkedIn](https://www.linkedin.com/in/anshul-eskey-ba0821292/) | [Email](mailto:anshuleskey999@gmail.com)) & Sagun Verma ([LinkedIn](https://www.linkedin.com/in/sagun-verma-655a122a6/) | [Email](mailto:sagunv11@gmail.com))  
**Role:** Product Manager  
**Project:** Urban Company — Two-Sided Home Services Marketplace  
**Related Specs:** [PRD Specification](01_prd_post_diagnostic_scaffold.md) | [Metrics & Experiment Design](01_metrics_and_experiment_design.md) | [Executive Case Study](01_executive_case_study.md)  

---

> [!TIP]
> **Strategy Summary (TL;DR):** This document defines how Urban Company can solve on-site repair pricing volatility without breaking unit economics. By establishing transparent sunk-cost accounting and digital decision agency for consumers while enforcing a strict **100% partner diagnostic fee floor** (`FR-08`), the strategy aligns consumer trust with supply-side retention.

---

## Executive Strategy Statement

> **Transform the post-diagnostic quoting interaction from an opaque, high-pressure in-home negotiation into a structured, customer-empowered decision point that clarifies sunk costs, itemizes scope, and supports informed choice without compromising technician earnings or platform unit economics.**

Urban Company's core value proposition is delivering standardized, high-trust home services in an unorganized market. However, in diagnosis-dependent appliance categories, that trust is acutely vulnerable at the on-site quoting boundary. When physical disassembly uncovers variable scope, customers transition from fixed digital expectations to uncomfortable in-home financial negotiations under the shadow of a mandatory visitation fee (`E041`). 

Our product strategy directly addresses this inflection point. Grounded in **D007**, we anchor our strategy on **O4 (Accept/Reject Decision Support & Sunk-Cost Clarification)**, supported upstream by **O1 (Pre-Diagnostic Price Expectation & Cost Education)**. By establishing decision clarity, transparent cost accounting, and digital agency in the domestic space, we eliminate the feeling of being trapped without attempting to artificially eliminate the unavoidable physical uncertainty of complex repairs.

---

## 1. Strategic Objective

The strategic objective of this product intervention is to **reduce cognitive ambiguity and social duress at the post-diagnostic decision threshold**, enabling first-time and price-sensitive customers to make transparent, confident, and uncoerced repair decisions.

### 1.1 What We Are Trying to Improve
1. **Decision Transparency:** Ensure the customer understands precisely what was diagnosed, what physical work is recommended, what has already been paid, and what additional expenditure is required before any tool touches the machine.
2. **Sunk-Cost Clarity:** Demystify the visitation/diagnostic fee (`E041`) so it is perceived as an understood cost of expert inspection rather than a coercive penalty forcing quote acceptance.
3. **In-Home Decision Agency:** Shift the acceptance/rejection interaction from an awkward, high-pressure verbal standoff with the technician into an objective digital evaluation where declining is a legitimate, frictionless option.

### 1.2 Explicit Hypotheses Boundary (Non-Established Claims)
To maintain strict evidence discipline, we explicitly state that the following business outcomes are **hypotheses under evaluation**, not established facts:
* *Hypothesis:* Reducing post-diagnostic pressure will lower quote abandonment and off-platform disintermediation (`PAT-10`).
* *Hypothesis:* Transparent decision support will improve first-time user trust and downstream repeat booking across other platform verticals.
* *Hypothesis:* Clearer fee accounting will reduce customer support escalation and 1-star public app reviews (`E011`, `E014`).
* *Non-Claim:* We do **not** claim that this strategy will automatically increase top-of-funnel conversion, lift immediate gross revenue, or guarantee repair quote acceptance.

---

## 2. Target User and Business Context

The strategy is strictly targeted at the intersection of the two behavioral segments formalized in [`D006`](../04_Product_Strategy_and_Prioritization/04_decision_log.md):

```
+-------------------------------------------------------------------------+
|                          TARGET USER MATRIX                             |
+------------------------------------+------------------------------------+
|  SEGMENT 1: FIRST-TIME BOOKERS     |  SEGMENT 3: PRICE-SENSITIVE        |
|  (Primary Target — D006)           |  (Secondary Business-Risk — D006)  |
+------------------------------------+------------------------------------+
| * Mental-Model Gap: Expects fixed  | * Benchmark-Driven: Compares rates |
|   e-commerce pricing.              |   against local offline mechanics. |
| * Emotional State: Anxious, easily | * Economic Calculation: Sunk fee   |
|   feels "baited and switched."     |   vs. marginal outside repair cost.|
| * Strategic Need: Psychological    | * Strategic Need: Line-item price  |
|   safety, declining protocol       |   verification, warranty backing,  |
|   clarity, fee demystification.    |   objective value justification.   |
+------------------------------------+------------------------------------+
```

### 2.1 Primary Segment Relevance: Segment 1 (First-Time Bookers)
First-time bookers have no prior experience with Urban Company's staged diagnostic workflow. They anchor their budget expectation to the nominal visitation fee displayed at checkout (e.g., ₹199–₹299). When an on-site technician disassembles the appliance and quotes ₹2,500 for a PCB or motor replacement, new users experience acute cognitive dissonance. They fear they are being exploited by an opportunistic technician. **O4 provides them with a structured platform interface that validates the diagnosis, separates the inspection fee from parts, and provides a clear protocol for what happens if they say no.**

### 2.2 Secondary Segment Relevance: Segment 3 (Price-Sensitive Quote Evaluators)
Price-sensitive customers sit directly at the economic substitution boundary. When faced with an expensive repair quote, they actively calculate whether forfeiting the diagnostic fee (`E041`) and hiring an independent local mechanic is cheaper (`PAT-10`, `R0070`, `R0163`). **O4 directly targets this calculation by providing transparent line-item clarity, explicitly showing what the diagnostic fee covered, and reinforcing the enforceable platform warranty (`E048`) tied to official platform authorization.**

### 2.3 Research Hypothesis: Urgency Dimension as a Behavioral Modifier (Preserving D006)
`D006` canonically established user tenure and price sensitivity as the primary and secondary segmentation axes. In addition to these dimensions, **problem urgency** (e.g., an acute appliance failure causing active kitchen flooding vs. a routine preventive service check) represents an important behavioral modifier:
* **High-Urgency Situations:** Customers may prioritize turnaround speed and immediate authorization over detailed line-item scrutiny.
* **Low-to-Moderate Urgency:** Customers actively inspect quotes, compare outside prices, and deliberate before committing.
* *Epistemic Classification:* Urgency is documented here as a **`[HYPOTHESIS]`** and research consideration for future operational testing. It does not replace or alter canonical decision `D006`, but provides nuance for how decision latency may vary across emergency and scheduled service lines.

---

## 3. Core Product Outcome & Preserving User Agency

### 3.1 The Desired Product Outcome
The success of this strategy is defined by the customer's ability to achieve six clear understandings at the decision point:
1. **Diagnosis Understanding:** Clear comprehension of what specific physical component has failed and why repair/replacement is recommended.
2. **Economic Scope Understanding:** Complete transparency on the financial breakdown: base diagnostic fee, specific parts cost, standardized labor tiers, and taxes.
3. **Accounting of Paid Amounts:** Explicit recognition of what amount has already been charged or authorized (the visitation fee).
4. **Accounting of Additional Amounts:** Precise clarity on the incremental marginal cost required to execute the repair.
5. **Choice Architecture Understanding:** Full visibility into the customer's available paths: authorize full repair, decline repair and pay only visitation fee, or request time to decide.
6. **Informed Choice:** The ability to execute an accept or reject decision with complete dignity and psychological safety in their home.

### 3.2 Non-Negotiable Principle: Preserving Customer Agency
> **We deliberately do NOT optimize blindly for job completion or quote acceptance.**

A platform strategy that treats "quote accepted" as the only successful outcome inevitably resorts to dark patterns, manipulative friction on rejection buttons, or coercive sunk-cost framing. In physical home services:
* Some appliances are genuinely uneconomical to fix (repair cost exceeds depreciated replacement value).
* Some customers legitimately prefer to replace the unit or seek second opinions.
* **A frictionless, transparent quote rejection that leaves the customer feeling respected preserves long-term platform trust and cross-category brand equity.**
* However, declining a quote is a behavioral outcome—it is **NOT** a commercial product success. Preserving agency prevents toxic churn, but the product's ultimate business health requires that a viable proportion of diagnostic visits convert to authorized, paid repairs under fair platform standards.

### 3.3 Decoupling Decision Uncertainty from Price Dissatisfaction (Mechanism A vs. Mechanism B)
To maintain analytical rigor, the product strategy explicitly decouples two fundamentally different drivers of quote rejection:
* **Mechanism A: Decision Uncertainty (Information Asymmetry & Process Opacity)**  
  The customer struggles to decide because they lack structured, verifiable information. They do not know what was physically diagnosed, whether the rate is standard, how their prepaid diagnostic fee is credited, or what their alternatives are. This is a product friction problem.
* **Mechanism B: Price Dissatisfaction / Sticker Shock (Economic Elasticity & Budget Constraints)**  
  The customer understands the diagnosis, scope, and fee credit arithmetic with total clarity, but considers the absolute price too expensive relative to their personal budget, appliance replacement value, or unorganized market alternatives. This is an economic reality.
* **Strategic Boundary of PDDS:**  
  The Post-Diagnostic Decision Scaffold (PDDS) is designed primarily to eliminate **Mechanism A**. It ensures that no customer rejects a quote out of confusion, suspicion, or feeling trapped. It does **NOT** assume that all customer resistance stems from information asymmetry. A customer may thoroughly understand a quote and still rationally reject it under Mechanism B. PDDS honors this distinction by delivering unpressured clarity without relying on manipulative conversion tricks.

---

## 4. Strategic Mechanism: The Tripartite Decision Scaffold

The strategic mechanism operates at the conceptual level, defining how decision support resolves uncertainty at the accept/reject boundary without specifying low-level UI elements:

```
                  THE TRIPARTITE DECISION SCAFFOLD
   
   [ 1. COGNITIVE GROUNDING ]  --> Separates Diagnosis vs. Physical Scope
                                   vs. Rate-Card Pricing
              |
              v
   [ 2. SUNK-COST NEUTRALIZATION ] --> Demystifies Visitation Fee (E041):
                                   Inspection Value Delivered vs. Repair Credit
              |
              v
   [ 3. ASYNCHRONOUS IN-HOME AGENCY ] --> Digital Review Cushion: Removes Direct
                                       Verbal Standoff with On-Site Technician
```

### 4.1 Dimension 1: Cognitive Grounding (Scope & Cost Demarcation)
Uncertainty flourishes when scope and cost are blended into an arbitrary verbal number. The mechanism establishes a rigid conceptual boundary separating:
* **The Inspection Finding:** The objective diagnostic fact (e.g., "compressor capacitor failed").
* **The Physical Remedy:** The exact SKU and labor tier required (`E040`).
* **The Financial Schedule:** Line-item pricing mapped to official rate cards, decoupling parts from labor.

### 4.2 Dimension 2: Sunk-Cost Neutralization (Fee Accounting Transparency)
Customers currently perceive the visitation fee (`E041`) as a coercive trap: "If I say no, I lose ₹299 for nothing." The mechanism reframes the visitation fee from an exit penalty into an explicit financial credit:
* **If Approved:** The visitation fee is formally credited against the total repair invoice (avoiding double-charging).
* **If Declined:** The visitation fee is explicitly accounted for as compensation for the expert diagnostic labor and physical safety inspection already delivered, with the written diagnostic report preserved on the customer's device.

### 4.3 Dimension 3: Asynchronous In-Home Agency (The Social Cushion)
Negotiating money in one's private home with an external service professional creates acute social pressure (`E015`). Customers often agree verbally out of awkwardness, only to feel resentful later (`E014`). The mechanism introduces an **asynchronous digital decision buffer**:
* The quote is formally transmitted to the customer's personal device.
* The customer is provided an explicit, private moment of cognitive review to inspect the terms, review warranty protection (`E048`), and make an unpressured digital decision.
* The technician's workflow transitions from salesperson/negotiator to neutral service partner awaiting platform authorization.

---

## 5. The Complementary Role of Opportunity 1 (Upstream Education)

In accordance with **D007**, **O1 (Pre-Diagnostic Price Expectation & Cost Education)** serves a vital **supporting and preparatory function** upstream, but is strictly subordinated to O4.

```
+----------------------------------+       +----------------------------------+
|   COMPLEMENTARY UPSTREAM (O1)    |       |      PRIMARY STRATEGY (O4)       |
|    Booking & Expectation Stage   | ----> |     The Decision Threshold       |
+----------------------------------+       +----------------------------------+
| * Establishes Two-Stage Mental   |       | * Delivers Structured Itemization|
|   Model before booking.          |       | * Neutralizes Sunk-Cost Duress   |
| * Displays Indicative Historical |       | * Protects In-Home Agency        |
|   Price Bands across categories. |       | * Enforces Formal Customer Choice|
+----------------------------------+       +----------------------------------+
```

### 5.1 How O1 Supports O4
1. **Pre-Visit Mental Model Alignment:** O1 primes first-time bookers before checkout that diagnosis-dependent home services operate in two distinct steps: (1) An expert physical diagnosis, followed by (2) an optional standardized repair quote. This ensures the user does not arrive at the O4 decision point under the illusion that the visitation fee covered all possible repairs.
2. **Anchoring to Realistic Price Ranges:** O1 provides historical category cost bands (e.g., "Typical AC cooling repairs range between ₹800–₹1,800 depending on parts required"), softening the psychological shock when an O4 quote is presented on-site.

### 5.2 Strategic Guardrail Against O1 Creep
* **O1 cannot replace O4:** Upstream education alone cannot eliminate on-site uncertainty because physical hardware failures cannot be diagnosed over the internet.
* **O1 must not depress conversion:** Upstream cost ranges must be presented as contextual educational benchmarks, not intimidating barriers that create top-of-funnel checkout drop-off.
* **O4 remains the primary anchor:** The critical business risk, churn inflection point, and customer vulnerability occur at the in-home accept/reject threshold governed by O4.

---

## 6. Two-Sided Marketplace Considerations

Urban Company is an interdependent triangular marketplace. A product strategy that optimizes solely for consumer comfort while ignoring gig partner economics or platform viability will fail in field execution.

```
                           [ Urban Company Platform ]
                               /                \
               Take-Rate Integrity            Brand Equity & Cross-Category
               & Ops Automation               Customer Lifetime Value
                             /                    \
                            /                      \
        [ Professional Partner ] --------------- [ Consumer / Booker ]
              Earnings Protection &              Decision Agency &
              Low Unpaid App Burden              Sunk-Cost Clarity
```

### 6.1 The Gig Professional / Partner Perspective
* **Earnings Protection:** Technicians depend on high-ticket repair completions to meet their daily earnings goals (`E055`). A strategy that makes quote rejection frictionless risks lowering technician take-home pay if not properly managed.
* **Compensating Diagnostic Labor:** The strategy must fiercely defend the partner's contractual right to 100% of the diagnostic fee payout if the customer declines (`E047`). The technician invested travel time, fuel, and physical labor; they must never be penalized for a customer's decision to decline an uneconomical repair.
* **Minimizing Unpaid Administrative Overhead:** Technicians work with dirty hands, disassembled appliances, and tight schedules. The quoting interaction must not force technicians into tedious, complex mobile data-entry workflows that extend unpaid job duration.
* **Depolarizing the Interaction:** By making the quote an official, system-generated platform artifact, the strategy relieves the technician of having to defend prices, positioning the platform—not the technician—as the author of the rates.

### 6.2 The Urban Company Platform Perspective
* **Margin Integrity & EBITDA Focus:** Urban Company is driving toward full corporate profitability (`E039`). The strategy achieves high operating leverage by solving uncertainty through software workflows and clear accounting rather than hiring expensive human dispute operations (avoiding O6).
* **Mitigating Off-Platform Disintermediation (`PAT-10`):** When customers feel pushed into expensive quotes, they and the technician share an economic incentive to settle off-platform for cash at a discount. By establishing digital quote transparency and explicitly linking platform authorization to a 30-to-90 day service warranty (`E048`), the strategy makes off-platform side deals significantly riskier and less attractive for both parties.
* **Category Diagnostic Variance:** The strategy must accommodate wide operational variance: an AC gas leak check (`E026`) is fundamentally different from a washing machine PCB replacement or a water purifier filter overhaul (`E050`). The framework must remain category-flexible.

---

## 7. Governing Product Principles

The following seven principles govern all downstream feature design, UX workflows, and operational policies:

1. **Decision Clarity Over Persuasion:**  
   The primary job of the interface is to inform, clarify, and empower, not to cajole, pressure, or nudge quote acceptance. An informed decline is a strategic success.
2. **Transparent Demarcation of Scope, Parts, and Labor:**  
   The customer must never receive a blended, opaque total. The platform must explicitly itemize diagnostic fee, physical parts (`E040`), labor tiers, and taxes.
3. **Explicit Sunk-Cost Accounting Without Coercion:**  
   The visitation fee (`E041`) must be transparently accounted for—either credited toward repair or framed as legitimate inspection compensation—without using manipulative language that implies money is "lost" if they decline.
4. **Distinct Separation of Fixed Knowns from Contingent Unknowns:**  
   The product must clearly separate what is currently owed and fixed (the inspection fee) from what is optional and contingent upon customer consent (the proposed repair quote).
5. **Preservation of Customer Agency in the Domestic Sanctuary:**  
   The customer's home is a private space where social pressure is magnified (`E015`). Quoting interactions must provide digital review cushions that allow customers to evaluate options with dignity.
6. **Avoid False Precision on Physical Diagnostics:**  
   The product must never pretend that complex physical breakdowns can be perfectly predicted digitally before disassembly. It must embrace genuine physical diagnostic uncertainty honestly and transparently.
7. **Defend Partner Payouts and Workflow Simplicity:**  
   No solution can erode partner take-home earnings or burden gig workers with excessive on-site app bureaucracy. Diagnostic labor must always be compensated (`E047`, `E055`).

---

## 8. Strategic Hypotheses Framework

The table below catalogs the core hypotheses that anchor this strategy, their supporting evidence, critical unknowns, and falsification criteria:

| # | Strategic Hypothesis | Epistemic Label | Why We Believe It (Supporting Evidence) | What Remains Unknown | Validation / Falsification Event |
|---|---|---|---|---|---|
| **H1** | **Decision Agency Reduces Churn:** Providing a structured, unpressured digital accept/reject flow will preserve first-time customer trust even when quotes are declined. | `HYPOTHESIS` | Qualitative reviews (`E014`, `R0163`) demonstrate that customer rage stems from feeling trapped and overcharged, not from the machine being broken. | True platform repeat booking rate of customers who decline quotes vs. those who accept quotes. | *Falsified if:* Customers who decline quotes have identical platform abandonment rates regardless of whether decision support was used. |
| **H2** | **Sunk-Cost Clarification Mitigates Resentment:** Explicitly accounting for the diagnostic fee as inspection labor prevents the fee from feeling like a coercive penalty. | `HYPOTHESIS` | `E041` confirms mandatory fee structure; review `R0163` highlights visceral anger over paying "for nothing." | Whether customers accept the legitimacy of an inspection-only fee when repairs are deemed impossible. | *Falsified if:* Customer dispute tickets regarding visitation fees remain completely unchanged after fee accounting transparency. |
| **H3** | **Warranty Linking Defends Against Disintermediation:** Explicitly attaching platform warranty guarantees (`E048`) to digital quote acceptance reduces off-platform cash leakage (`PAT-10`). | `HYPOTHESIS` | `PAT-10` documents customers hiring outside mechanics; `E048` and `E049` prove warranty value is exclusive to official invoices. | Customer willingness-to-pay for warranty coverage vs. cash discounts offered by local mechanics. | *Falsified if:* Price-sensitive customers continue to bypass platform billing at identical rates despite prominent warranty disclosures. |
| **H4** | **Upstream Priming (O1) Reduces On-Site Friction:** Displaying category cost bands before booking aligns customer mental models without depressing checkout conversion. | `HYPOTHESIS` | `E014` shows expectation shock accounts for 28.3% of pricing complaints; mental model gap is acute in Segment 1. | Exact price elasticity and conversion drop-off on booking screens when price bands are displayed. | *Falsified if:* Displaying cost ranges causes a statistically significant drop (>5%) in top-of-funnel booking conversion. |
| **H5** | **Partner Compliance is Viable Without Heavy Overhead:** Technicians will adopt digital quote presentation if it relieves them of price defense and protects diagnostic fees. | `HYPOTHESIS` | Precedent exists in AC gas refilling (`E026`); partners prefer avoiding hostile verbal confrontations over rate cards (`E040`). | Partner quoting compliance rate across less-standardized repair verticals (e.g., washing machines, refrigerators). | *Falsified if:* Field technicians actively circumvent the digital quote tool in >20% of bookings to quote verbally. |

---

## 9. Strategic Risks and Trade-Offs

Implementing this strategy introduces six major product and operational tensions:

```
+-------------------------------------------------------------------------+
|                       STRATEGIC RISK BALANCING                          |
+------------------------------------+------------------------------------+
| POTENTIAL DOWNSIDE / RISK          | STRATEGIC MITIGATION               |
+------------------------------------+------------------------------------+
| 1. Softening Job Completion:       | * Prominently reinforce the value  |
|    Making quote rejection easier   |   of immediate repair and platform |
|    might lower partner conversion. |   warranty protection (E048).      |
+------------------------------------+------------------------------------+
| 2. Upstream Funnel Leakage (O1):   | * Use wide, non-threatening median |
|    Showing high repair bands could |   bands; frame ranges as aggregate |
|    intimidate checkout prospects.  |   historical data, not minimums.   |
+------------------------------------+------------------------------------+
| 3. Partner App Evasion:            | * Make digital quote creation      |
|    Technicians with greasy hands   |   extremely lightweight; tie part  |
|    may avoid mobile data logging.  |   warranty claims to in-app entry. |
+------------------------------------+------------------------------------+
| 4. False Precision / SKU Mismatch: | * Maintain clear category "general |
|    Standardized catalogs cannot    |   labor" tiers for complex edge    |
|    capture every bizarre failure.  |   cases where SKUs are unavailable.|
+------------------------------------+------------------------------------+
| 5. Sunk-Cost Resentment Persists:  | * Deliver a tangible written       |
|    Unrepairable appliances still   |   diagnostic safety report to the  |
|    require paying a fee (E041).    |   customer app to prove value.     |
+------------------------------------+------------------------------------+
| 6. Off-Platform Collusion:         | * Remind customers that off-app    |
|    Technician offers cash discount |   cash deals void insurance (E048) |
|    if customer declines on-app.    |   and expose home to liabilities.  |
+------------------------------------+------------------------------------+
```

---

## 10. Strategic Scope Boundaries

To maintain rigorous focus and prevent product diffusion, scope boundaries are strictly enforced:

### 10.1 In Scope
* **Post-Diagnostic Decision Interaction:** The complete on-site flow from technician diagnosis entry to customer accept/reject/pause decision.
* **Quote Transparency & Itemization:** Demarcating inspection fee, parts, labor, and taxes within official platform channels.
* **Sunk-Cost & Visitation Fee Clarification:** Transparently explaining how the diagnostic fee (`E041`) is applied upon approval or settled upon decline.
* **Warranty Entitlement Communication:** Proactively linking quote authorization to enforceable platform guarantees (`E048`, `E049`).
* **Complementary Upstream Education (O1):** Pre-booking mental-model priming and historical price-band disclosure.

### 10.2 Out of Scope
* **General Pricing & Rate-Card Overhaul:** Redefining baseline catalog prices, part markups, or commission take-rates.
* **Cancellation Policy & Fee Redesign:** Re-architecting pre-visit cancellation tiers or dispatch cancellation penalties (`D005`).
* **General Service Quality & Technician Vetting:** Re-engineering technical training, onboarding standards, or field background checks.
* **Customer Support Headcount & AI Chatbot Rebuild:** Building human dispute routing engines or restructuring support tiers (deprioritized O6).
* **Loyalty / Wallet Reinvestment Engines:** Building promotional credit refund programs for unfulfilled visits (deprioritized O5).
* **Broad Rebooking & Continuity Overhaul:** Designing preferred technician booking algorithms or recurring maintenance subscriptions.

---

## 11. Reversal and Invalidation Conditions

This product strategy is an evidence-based thesis. The following empirical findings would fundamentally invalidate our assumptions and mandate a strategic reversal:

1. **Quote Rejection is Statistically Negligible:** If internal telemetry reveals that post-diagnostic quote rejection occurs in $<3\%$ of bookings across all diagnosis-dependent categories, the problem is an isolated edge case, invalidating O4 as a primary strategic bet.
2. **Pricing Magnitude Completely Dominates Decision Agency:** If user testing proves that customer dissatisfaction is 100% driven by the absolute rupee cost of parts and that digital decision support produces zero change in sentiment, decision transparency is insufficient to solve the problem.
3. **Severe In-Home Social Failure Mode:** If field research demonstrates that customers feel equally pressured and coerced regardless of digital interfaces when a technician is physically standing in the room, software-based decision support is an inadequate intervention.
4. **Partner Workflow Rejection:** If field pilot data shows that requiring digital quote logging increases job turnaround time by $>15$ minutes and results in widespread technician pushback or field strikes (`E051`), the operational cost outweighs user benefits.
5. **Category Heterogeneity Renders Standardization Impossible:** If diagnostic complexity varies so violently across appliance models that standardized itemization cannot be maintained without massive manual catalog operations.

---

## 12. Canonical Traceability Matrix

Every core component of this product strategy directly traces back to locked project decisions, evidence matrix entries, and research findings:

| Strategy Dimension | Decision Anchor | Primary Evidence IDs | Qualitative Pattern | Strategic Governance |
|---|---|---|---|---|
| **Problem Definition** | [`D005`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) | `E014`, `E024`, `E025`, `E026`, `E040`, `E041` | `PAT-09` (Technician vs billing separation) | Governs core focus on post-diagnostic uncertainty rather than general pricing complaints. |
| **Target Segments** | [`D006`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) | `E004`, `E014`, `E041`, `PAT-10` | `PAT-10` (Offline defection to local mechanics) | Focuses strategy on First-Time Bookers (Primary) & Price-Sensitive Evaluators (Secondary). |
| **Primary Opportunity (O4)** | [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) | `E026` (AC gas approval), `E041` (visitation fee), `E014` | `PAT-10`, `R0163` | Anchors solution at the immediate physical accept/reject decision boundary. |
| **Complementary Opportunity (O1)** | [`D007`](../04_Product_Strategy_and_Prioritization/04_decision_log.md) | `E014` (expectation shock), `E024`, `E025` | `PAT-09` | Connects pre-booking cost range priming to on-site quoting clarity. |
| **Fee Accounting** | Strategy Sec. 4.2 | `E041` (diagnostic fee policy), `E047` (cancellation pass-through) | `R0163` ("paid for nothing") | Ensures partner is paid for inspection labor while clarifying credit to customer. |
| **Warranty Reinforcement** | Strategy Sec. 4.1 | `E040` (rate card), `E048` (30-90 day guarantee), `E049` | `PAT-10` (defection vs warranty) | Defends platform price premium against unorganized offline competition. |
| **Operational Feasibility** | Strategy Sec. 6 | `E008` (partner welfare), `E039` (FY24 EBITDA), `E055` | `E051` (labor sensitivity) | Rejects expensive human ops (O6) in favor of high-leverage software workflows. |

---

*End of Product Strategy. This canonical document formally anchors Phase 4 (Solution Design, UX Teardown & Redesign, PRD, and Metrics).*
