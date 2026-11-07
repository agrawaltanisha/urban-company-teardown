# PM-01 — Urban Company
## 11 — Problem Definition

**Stage:** SYNTHESIS (Phase 3 — Task 9)  
**Status:** CANONICAL — LOCKED BY HUMAN DECISION (D005)  
**Decision Owner:** HUMAN (Project Owner)  
**Selected Direction:** Candidate 2 — Post-Diagnostic Price Uncertainty  
**Parent Strategy:** D004 (Option 4 — Pricing Transparency / Cancellation Fairness; Focus: Post-Booking Price Predictability)  
**Last Updated:** 2026-09-18  

---

## 1. Canonical Problem Statement

> **"For customers booking diagnosis-dependent home services, the final cost can become uncertain after booking because the exact scope of work is determined only after on-site inspection, while the diagnostic/visitation cost and subsequent repair quote affect the customer's ability to confidently decide whether to proceed."**

---

## 2. Problem Boundary

To maintain rigorous analytical discipline, this problem statement has strict scope boundaries. It is not an omnibus bucket for all platform dissatisfaction.

### IN SCOPE:
* **Diagnosis-dependent home services:** Categories where the underlying issue cannot be fully diagnosed through the app prior to dispatch (e.g., Appliance Repair, AC Servicing & Repair, Plumbing/Electrical troubleshooting).
* **On-site inspection:** The interaction where a professional arrives in the customer's physical home to evaluate the appliance or fixture.
* **Diagnostic / visitation fees:** The mandatory platform or technician fee charged for attending and inspecting the site (`E041`).
* **Post-diagnostic repair quotations:** The itemized quotation or repair estimate generated and communicated to the customer after diagnosis on-site (`E024`, `E040`).
* **Additional work discovered after booking:** Necessary or recommended scope expansion discovered only upon opening/inspecting the equipment (`E025`, `E026`).
* **Customer accept/reject decision after diagnosis:** The decision point where the customer must either authorize the additional repair cost or decline the quote and pay the visitation/diagnostic charge.
* **Price predictability across this journey:** The degree of transparency and variance between what the customer anticipated spending at booking vs. what they are quoted on-site.
* **Clarity of quote / approval mechanisms:** The digital and conversational mechanisms used to present the quote, explain part costs, and capture verified customer consent (`E024`, `E026`).

### OUT OF SCOPE:
* **General Urban Company pricing complaints:** General customer sentiment that baseline services, salon packages, or standard cleaning rates are high or uncompetitive.
* **All cancellation problems:** Partner no-shows, cancellation penalty structures within 24 hours, or general cancellation flows (governed by separate mechanisms; not part of post-diagnostic quoting).
* **General service quality:** Professional punctuality, grooming, technical skill variance, or general workmanship quality.
* **General customer support:** Help center architecture, lack of telephone helpline, or AI chatbot deflection loops (except where a dispute specifically arises from a post-diagnostic quote).
* **General platform trust:** High-level brand perception, trust in background checks, or domestic safety assurance.
* **Rebooking:** Rebooking favorite professionals, partner continuity, or recurring cleaning schedules.
* **The ₹99 booking/payment amount discrepancy as the primary problem:** The checkout-stage price mismatch (`E020`, `E022`) is a separate booking/checkout phenomenon, not the core on-site post-diagnostic repair uncertainty.
* **Retention/churn as an established outcome:** We do not claim or assume that post-diagnostic pricing uncertainty has been proven to cause measurable platform-level churn or lower LTV.
* **Any claim that fees are intentionally hidden:** We do not assert deceptive intent or fraudulent fee concealment by Urban Company.
* **Any claim of customer "lock-in":** We do not frame the diagnostic/visitation fee as an intentional predatory trap or forced lock-in mechanism.

---

## 3. Evidence Mapping

### Primary Evidence Chain
The post-diagnostic uncertainty mechanism is directly grounded in seven specific evidence entries across review mining, product walkthroughs, and official documentation:

1. **`E014` — Post-Booking Pricing & Add-on Complaints (Review Mining):**  
   $28.3\%$ of pricing-themed reviews ($n=13/46$) document unexpected price inflation after booking, specifically including technician on-site add-on demands, parts billing, and scope expansion (`R0058`, `R0090`, `R0092`, `R0113`, `R0163`).
2. **`E024` — In-App Quote Verification Guidance (Product Walkthrough):**  
   Walkthrough of Urban Company Help Center guides explicitly documents that technicians are required to generate an in-app quote for any additional service or spare part before proceeding, cautioning customers to verify the quote inside the app.
3. **`E025` — Extra-Charge Policy Guidance (Product Walkthrough):**  
   Official Help Center content instructs customers that professionals may charge for additional spare parts or labor not covered in the original booking, establishing that on-site scope discovery is an intentional and recognized platform workflow.
4. **`E026` — Gas-Refill Quoting & Customer Approval Workflow (Product Walkthrough):**  
   Walkthrough of AC service flows demonstrates a formalized two-stage process: inspection first, followed by a specific in-app quote for gas charging that requires explicit customer approval before work commences.
5. **`E040` — Granular Rate-Card Pricing Architecture (Secondary Research):**  
   External documentation confirms Urban Company operates standardized rate cards for hundreds of spare parts and diagnostic steps to standardize quoting, yet the selection of required parts occurs during the physical on-site diagnosis.
6. **`E041` — Visitation and Diagnostic Fee Mechanism (Secondary Research & Walkthrough):**  
   Official terms establish a mandatory diagnostic/visitation fee if the customer decides not to proceed with the repair after the professional completes the on-site inspection.
7. **`E042` — High-Value Consultation and Staged Quoting (Secondary Research):**  
   Complex, multi-stage verticals (e.g., painting consultations, deep appliance repair) separate the initial site visit/assessment from the execution phase, creating a distinct post-visit quote approval threshold.

### Supporting Context (With Strict Distinction)
* **`E004` — Pricing-Theme Prevalence:** Pricing transparency and unexpected charges represent $25.7\%$ ($n=46/179$) of all sampled reviews and $37.3\%$ ($n=19/51$) of negative reviews, demonstrating high baseline user sensitivity to financial predictability.
* **`E022` — Booking-Stage Amount Discrepancy (Checkout):** A ₹99 discrepancy between checkout (₹1,098) and payment gateway (₹1,197) observed during the walkthrough.
  * **CRITICAL METHODOLOGICAL NOTE:** `E022` represents a separate checkout/payment UI phenomenon. It must **NOT** be used as direct evidence of post-diagnostic pricing uncertainty. It serves only as secondary context illustrating that price predictability friction can occur at multiple stages of the user journey.

---

## 4. What Remains Unproven

To avoid overclaiming and preserve strict intellectual honesty, the following eight dimensions remain **explicitly unproven hypotheses** that cannot be asserted as verified facts:

1. **Frequency of post-diagnostic quote escalation:** We do not possess platform telemetry showing what percentage of diagnosis-dependent bookings experience an increase above the initial estimate.
2. **Frequency of customers rejecting quotes:** We do not know how often customers decline the post-diagnostic quote and opt to pay only the visitation fee.
3. **Magnitude of price increases after diagnosis:** The average rupee or percentage escalation between the base booking fee and the final invoice across repair categories is unmeasured.
4. **Whether customers perceive the diagnostic fee as unfair:** We do not have quantitative survey or qualitative interview data proving whether customers consider the visitation fee reasonable compensation for the technician's time or an unfair penalty.
5. **Whether this problem materially reduces conversion:** We cannot demonstrate whether uncertainty at the quoting stage causes booking drop-off or post-diagnosis cancellation.
6. **Whether this problem materially reduces repeat booking or retention:** The causal link between post-diagnostic pricing friction and customer churn or lifetime value reduction is not established by the dataset (`GAP-001`).
7. **Whether the dominant issue is UX, policy, or unavoidable service-scope uncertainty:** It remains unproven whether the friction stems primarily from interface communication gaps (poor quote UI), platform commercial policy (fee structure), or the physical reality of diagnosing broken machinery (inherent uncertainty).
8. **Whether this problem is equally important across all diagnosis-dependent categories:** We do not know the relative severity across AC repair, washing machine repair, plumbing, or electrical troubleshooting.
9. **Whether quote rejection is driven by information asymmetry vs. price elasticity (Mechanism A vs. Mechanism B):** We do not have telemetry or research isolating what proportion of customer hesitation stems from process opacity and decision uncertainty (Mechanism A) versus pure price dissatisfaction and budget constraints (Mechanism B).

---

## 5. Affected Segment & Triggering Moments

* **Affected Segment:** Customers booking **diagnosis-dependent home services** (e.g., Appliance Repair, AC Servicing, Water Purifier Maintenance, Electrical/Plumbing Diagnostics) where the full defect cannot be specified at checkout.
* **Triggering Moment:** The physical on-site inspection when the service partner evaluates the problem, identifies necessary parts or repairs, and communicates the revised total cost (via app quote or verbally).
* **The Decision Crisis:** The customer must evaluate a higher quote while weighing the sunk cost of the diagnostic/visitation fee:
  * *Option A:* Accept the quote (risk feeling overcharged or surprised by scope expansion).
  * *Option B:* Reject the quote, pay the diagnostic fee, and absorb an unfulfilled repair (risk wasted money and needing an alternative technician).

---

## 6. Why It Matters

### To the User
* **Financial Anxiety & Sunk Cost Friction:** Customers experience vulnerability when an in-home technician presents a high repair quote. The requirement to pay a visitation fee even if declining creates perceived pressure to proceed despite uncertainty about whether the price is fair.
* **Loss of Agency:** When quotes are delivered without clear, transparent breakdown of parts vs. labor or without verifiable platform backing, users feel they have lost control of the transaction inside their own home.

### To Urban Company
* **Offline Disintermediation Risk:** If the customer perceives the in-app repair quote as inflated by platform margins, the customer and technician face strong incentives to bypass Urban Company, negotiate a cash deal off-platform, and cancel the official job.
* **Escrow / Quoting Friction:** Customer hesitation at the quoting stage stalls service completion, reduces partner hourly productivity, increases customer support dispute volume (`E011`), and damages long-term platform trust.

---

## 7. Problem Selection Record

| Attribute | Detail |
|---|---|
| **Selected Candidate** | **Candidate 2: Post-Diagnostic Price Uncertainty** |
| **Decision Owner** | **HUMAN (Project Owner)** |
| **Decision Date** | 2026-09-18 |
| **Associated Decision Log Entry** | [`D005`](04_decision_log.md) |
| **Alternative Candidates Evaluated** | Candidate 1 (Booking-Stage Amount Mismatch), Candidate 3 (Asymmetric Cancellation Penalties), Candidate 4 (Broad Post-Booking Predictability Synthesis) |
| **Selection Rationale** | Represents an authentic marketplace tension at the boundary between digital booking and physical in-home reality; has direct evidence grounding (`E014`, `E024-E026`, `E040-E042`); offers a focused, addressable product surface; avoids over-broad synthesis while maintaining rigorous scope boundaries. |

---

*End of Problem Definition. This canonical statement anchors Task 10 (Behavioral User Segmentation).*
