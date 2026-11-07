# Metrics Framework & Experimentation Protocol: Post-Diagnostic Decision Scaffold (PDDS)

**Co-Creators:** Anshul Eskey ([LinkedIn](https://www.linkedin.com/in/anshul-eskey-ba0821292/) | [Email](mailto:anshuleskey999@gmail.com)) & Sagun Verma ([LinkedIn](https://www.linkedin.com/in/sagun-verma-655a122a6/) | [Email](mailto:sagunv11@gmail.com))  
**Role:** Product Manager  
**Project:** Urban Company — Two-Sided Home Services Marketplace  
**Related Specs:** [PRD Specification](01_prd_post_diagnostic_scaffold.md) | [Validation Plan](02_validation_and_rollout_plan.md) | [Executive Case Study](01_executive_case_study.md)  

---

> [!TIP]
> **Metrics & Experiment Protocol (TL;DR):** Establishes the measurement system for PDDS: Primary Product Outcome is **Decision Comprehension & Clarity**, supported by secondary operational process metric **Post-Diagnostic Decision Completion Rate (PDCR)** and behavioral outcomes (Authorize, Need Time, Decline). Enforces non-negotiable business guardrails: **Quote Authorization Volume Floor** and **Partner Hourly Earnings Floor**. Specifies proposed validation via **Partner-Cohort Randomization** or **Switchback Blocks** (`THR-03`) `[PROPOSED EXPERIMENT DESIGN — NOT EXECUTED]`.

---

## Document Governance & Epistemic Taxonomy

Every definition, threshold, formula, and operational assumption in this document carries an explicit epistemic label adhering to the project Evidence Policy:

| Tag | Epistemic Definition |
|:---|:---|
| `[FACT]` | Verified platform policy, published rate-card rule, or documented platform telemetry from primary sources. |
| `[RESEARCH FINDING]` | Statistically analyzed pattern from the 179-review empirical dataset (`05_evidence_matrix.md`, `E001`). |
| `[COMPANY CLAIM]` | Public assertion from Urban Company leadership, IPO prospectus, or corporate communication without independent audit. |
| `[ANALYST SYNTHESIS]` | Logical inference, market mechanism, or mathematical formulation derived by cross-referencing findings. |
| `[ASSUMPTION]` | Unverified operational parameter or numerical baseline required for modeling; pending production telemetry audit. |
| `[HYPOTHESIS]` | Formally testable proposition regarding user behavior, partner response, or platform economics; strictly unproven. |
| `[DESIGN DECISION]` | Deliberate choice made in metric architecture, North Star selection, or experimentation design. |
| `[DESIGN SPECIFICATION]` | Functional rule defining measurement logic, instrumentation events, or telemetry schema. |
| `[ANALYTICS REQUIREMENT]` | Telemetry event, property schema, or data pipeline that must be instrumented by engineering. |

---

# 1. Product & Business Context

### 1.1 Product Initiative
**Post-Diagnostic Decision Scaffold (PDDS)** (Internal Code: `O4-PDDS`).

### 1.2 The Problem Being Measured (`D005` — Locked)
> *"For customers booking diagnosis-dependent home services, the final cost can become uncertain after booking because the exact scope of work is determined only after on-site inspection, while the diagnostic/visitation cost and subsequent repair quote affect the customer's ability to confidently decide whether to proceed."*

In diagnosis-dependent categories (appliance repairs, AC servicing, water purifier overhauls), physical disassembly on-site creates a two-stage transaction model (`E041` `[FACT]`). Customers pay an upfront visitation/diagnostic fee, but receive variable repair quotes in their private living space (`E022`, `PAT-09` `[RESEARCH FINDING]`). This creates information asymmetry, perceived entrapment, social awkwardness with the technician, and cognitive friction (`R0163` `[RESEARCH FINDING]`).

### 1.3 Target Segments (`D006` — Locked)
- **Primary Target Segment:** Segment 1 — First-Time Diagnosis-Dependent Bookers (`D006` `[DESIGN DECISION]`).
- **Secondary Business-Risk Segment:** Segment 3 — Price-Sensitive Quote Evaluators (`D006` `[DESIGN DECISION]`).

### 1.4 Business & User Objective Alignment
- **User Objective:** Arrive at an informed, transparent, and uncoerced decision (Authorize, Decline, or Clarify) within 90 seconds of diagnosis, with 100% clarity on scope, parts, warranty, and sunk-cost fee crediting (`[DESIGN DECISION]`).
- **Business Objective:** Eliminate quote-stage customer drop-off, off-platform disintermediation (`PAT-10`), and post-service billing disputes (`E014`), while protecting partner on-site productivity and take-home earnings (`[DESIGN DECISION]`).

---

# 2. Primary Product Success & Operational Metrics Hierarchy

### 2.1 Primary Product Success Metric: Decision Quality & Comprehension Rate

```
┌─────────────────────────────────────────────────────────────────────────┐
│                    PRIMARY PRODUCT SUCCESS METRIC                       │
│             Quote Decision Quality & Comprehension Rate                 │
└─────────────────────────────────────────────────────────────────────────┘
```

#### Specification & Measurement
$$\text{Decision Comprehension Rate} = \left( \frac{\sum \text{Customers Passing 1-Click Post-Decision Comprehension Pulse}}{\sum \text{Completed On-Site Quote Decision Sessions}} \right) \times 100\%$$

- **Measurement Instrument:** A non-intrusive 1-click in-app pulse triggered immediately following an Authorize or Decline action:
  1. *Net Payable Arithmetic:* Did the customer correctly identify that their prepaid diagnostic fee was deducted from the total quote?
  2. *Scope Clarity:* Did the customer understand which physical part was diagnosed as faulty?
  3. *Agency Rating:* Did the customer feel in control of their choice (rated $\ge 4.2 / 5.0$)?
- **Target:** $\ge 80.0\%$ comprehension pass rate (`[PROPOSED TARGET]`).
- **Why This is the Primary Product Metric:** The core problem statement (`D005`) is *price uncertainty and decision ambiguity*. The true test of product success is whether the customer understands the scope, arithmetic, and options—regardless of whether they authorize or decline.

---

### 2.2 Secondary Operational Process Metric: Post-Diagnostic Decision Completion Rate (PDCR)

```
┌─────────────────────────────────────────────────────────────────────────┐
│                 SECONDARY OPERATIONAL PROCESS METRIC                    │
│            Post-Diagnostic Decision Completion Rate (PDCR)              │
└─────────────────────────────────────────────────────────────────────────┘
```

#### Mathematical Formula
$$\text{PDCR} = \left( \frac{\sum \text{Jobs with Definitive Digital Outcome within On-Site Session}}{\sum \text{Eligible On-Site Diagnostic Quotes Rendered}} \right) \times 100\%$$

Where:
- **Eligible On-Site Diagnostic Quotes Rendered ($Q_{\text{rendered}}$):** Total service orders in diagnosis-dependent categories where the partner triggers the on-site quote via the partner app (`pdds_quote_rendered` event) (`[ANALYTICS REQUIREMENT]`).
- **Definitive Digital Outcome ($D_{\text{outcome}}$):** Any quote reaching an explicit digital state:
  1. `AUTHORIZE`: Full or itemized scope authorized for on-site repair.
  2. `DECLINE`: Quote formally declined; diagnostic fee settled, in-app diagnostic summary archived, and job closed cleanly.
  3. `PAUSE_OR_CLARIFY`: Customer requests structured clarification or selects "Need Time to Decide" (`[OPERATIONAL WINDOW TBD]`).
- **Session Abandonment (Failure Mode):** A quote that expires without a digital action, triggers app force-close, or where the partner resorts to an offline verbal transaction (`[ANALYTICS REQUIREMENT]`).

#### Critical Metric Boundary (`THR-01` Resolution)
> **PDCR is an OPERATIONAL PROCESS COMPLETION metric, NOT a commercial success metric.**

Treating `DECLINE` as equivalent to `AUTHORIZE` for business health is fundamentally flawed: in an extreme scenario, 100% of customers could decline quotes, generating a record 100% PDCR while completely destroying platform revenue and partner income. 
* **Decline is NOT a commercial win:** A decline is a legitimate customer right that preserves brand trust and prevents toxic churn, but commercial viability requires healthy authorization volumes.
* **Metric Pairing:** PDCR must always be evaluated alongside **Quote Authorization Rate** and **Partner Hourly Earnings Guardrails**.

---

### 2.3 Behavioral Outcomes & Non-Negotiable Business Guardrails

| Outcome Tier | Metric Name | Definition & Target | Epistemic Status |
|:---|:---|:---|:---|
| **Behavioral Conversion** | **Quote Authorization Rate** | % of quotes authorized for platform repair (Target: $\ge 68.0\%$). | `[PROPOSED TARGET]` |
| **Behavioral Conversion** | **Clean Decline Rate** | % of quotes declined without support disputes or verbal friction. | `[PROPOSED TARGET]` |
| **Business Guardrail** | **Quote Authorization Volume Floor** | Absolute weekly volume of authorized jobs must not drop below seasonal baseline. | `[PROPOSED GUARDRAIL]` |
| **Supply Guardrail** | **Partner Hourly Earnings Floor** | Partner average hourly take-home pay must not decline by $>1.5\%$ vs. control. | `[PROPOSED GUARDRAIL]` |
| **Platform Guardrail** | **7-Day Billing Dispute Rate** | $\le 1.2\%$ of completed bookings generating overcharging complaints. | `[PROPOSED GUARDRAIL]` |
| **Process Metric** | **Baseline PDCR** | Estimated at $18.5\%$ under status quo verbal quoting. | `[ASSUMPTION]` |
| **Process Metric** | **Target PDCR** | $\ge 82.0\%$ digital capture of quote decisions. | `[PROPOSED TARGET]` |

---

# 3. Hierarchical Metric Tree

The metric tree connects daily operational software levers to the North Star, leading behavioral outcomes, and long-term platform retention.

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                         PRIMARY PRODUCT SUCCESS METRIC                                 │
│             Quote Decision Quality & Comprehension Rate (Target: ≥ 80%)                │
└───────────────────────────────────────────┬────────────────────────────────────────────┘
                                            │
                                            ▼
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                        SECONDARY OPERATIONAL PROCESS METRIC                            │
│                 Post-Diagnostic Decision Completion Rate (PDCR ≥ 82%)                  │
└───────────────────────────────────────────┬────────────────────────────────────────────┘
                                            │
         ┌──────────────────────────────────┴──────────────────────────────────┐
         │                                                                     │
         ▼                                                                     ▼
┌─────────────────────────────────┐                   ┌──────────────────────────────────┐
│          INPUT METRICS          │                   │    BEHAVIORAL OUTCOME METRICS    │
│      (Direct Product Levers)    │                   │   (Immediate Behavioral States)  │
└────────────────┬────────────────┘                   └────────────────┬─────────────────┘
                 │                                                     │
 ┌───────────────┼───────────────┐                     ┌───────────────┼───────────────┐
 │               │               │                     │               │               │
 ▼               ▼               ▼                     ▼               ▼               ▼
Input 1         Input 2         Input 3               Output 1        Output 2        Output 3
Partner 3-Tap   Card Render     Pre-Diag View         Quote Authorize Clean Decline   Need Time /
Compliance Rate Rate            Rate                  Rate (≥68%)     Rate            Clarify Rate
(≥92%)          (≥98%)          (≥75%)                [Commercial     [Legitimate     [Operational
 │               │               │                     Success]        Agency]         Pause TBD]
 ├─ Quoting      ├─ Push Socket  ├─ Card View          └───────┬───────┴───────┬───────┘
 │  Latency      │  Latency      │  on Booking                 │               │
 └─ Error Rate   └─ App Focus    └─ Click-to-Expand            ▼               ▼
                                                        Quote Abandon-  Offline Bypass
                                                        ment Rate (<5%) Rate (<3%)
                                                               │
                                                               ▼
                                              ┌──────────────────────────────────┐
                                              │      BUSINESS & SUPPLY GUARDRAILS │
                                              │    (Trust & Marketplace Health)  │
                                              └────────────────┬─────────────────┘
                                                               │
                                               ┌───────────────┴───────────────┐
                                               │                               │
                                               ▼                               ▼
                                      7-Day Billing Dispute           Partner Hourly Earnings
                                      Ticket Rate (≤1.2%)             Floor (Drop ≤1.5% vs Ctrl)
```

---

# 4. Detailed Supporting Metric Definitions

### 4.1 Input Metrics (Controllable Engineering & Design Levers)

These metrics represent the direct physical performance and delivery quality of the PDDS system components (`18_prd.md`).

| Metric Name | Exact Formula | Strategic Intent | Tracking Cadence | Target | Status |
|:---|:---|:---|:---|:---|:---|
| **Partner Quoting Module Compliance Rate (PQCR)** | $\frac{\text{Digital Quotes Formulated via 3-Tap Module}}{\text{Total On-Site Physical Inspections Completed}} \times 100$ | Measures whether service technicians adopt the standardized digital catalog (`FR-04`) vs attempting off-app verbal quotes. | Hourly by city | $\ge 92.0\%$ `[PROPOSED TARGET]` | `[ANALYTICS REQUIREMENT]` |
| **Decision Card Render Rate (DCRR)** | $\frac{\text{Successful Customer App Card Renders}}{\text{Quotes Pushed by Partner Client}} \times 100$ | Technical delivery reliability across iOS/Android WebSocket and push notification conduits (`FR-06`). | Real-time | $\ge 98.5\%$ `[PROPOSED TARGET]` | `[ANALYTICS REQUIREMENT]` |
| **Pre-Diagnostic Anchor Exposure Rate (PDAE)** | $\frac{\text{Diagnosis-Dependent Bookings with Two-Stage Card Rendered}}{\text{Total Diagnostic Category Bookings}} \times 100$ | Ensures first-time bookers (`D006`) are pre-educated on the two-stage model and visitation fee policy upstream (`FR-01`). | Daily | $\ge 90.0\%$ `[PROPOSED TARGET]` | `[ANALYTICS REQUIREMENT]` |
| **Sunk-Cost Ledger Interaction Rate (SLIR)** | $\frac{\text{Sessions where Customer Taps/Expands Sunk-Cost Ledger Tooltip}}{\text{Total Decision Cards Rendered}} \times 100$ | Measures customer engagement with the fee crediting line item and breakdown mechanics (`FR-06`). | Daily | $\ge 40.0\%$ `[PROPOSED TARGET]` | `[ANALYTICS REQUIREMENT]` |
| **Partner Quoting Latency (PQL)** | $\text{Median seconds from on-site diagnosis to quote transmission via app}$ | Protects technician productivity; ensures digital quoting does not add excessive overhead to the physical visit. | Daily (P50/P90) | $\text{P50} \le 75\text{s}$, $\text{P90} \le 120\text{s}$ | `[DESIGN SPECIFICATION]` |

---

### 4.2 Output Metrics (Immediate Behavioral Conversion States)

These metrics track the distribution of choices made when customers interact with the Actionable Choice Interface (`FR-06`).

| Metric Name | Exact Formula | Interpretation & Boundary Rule | Target Range | Status |
|:---|:---|:---|:---|:---|
| **Quote Authorization Rate (QAR)** | $\frac{\text{Jobs where Customer Digitally Taps Authorize}}{\text{Total Quotes Rendered}} \times 100$ | Standard, healthy acceptance of recommended repair scope. Commercial success driver. | $\ge 68.0\%$ `[PROPOSED TARGET]` | `[DESIGN SPECIFICATION]` |
| **Clean Decline Rate (CDR)** | $\frac{\text{Jobs where Customer Digitally Taps Decline}}{\text{Total Quotes Rendered}} \times 100$ | Healthy exercise of customer agency. Decline is an acceptable behavioral outcome that prevents toxic churn, but is **NOT** a commercial product success; triggers in-app diagnostic summary and fee receipt. | $20.0\% - 30.0\%$ | `[DESIGN SPECIFICATION]` |
| **Need Time / Clarify Rate (NTCR)** | $\frac{\text{Jobs where Customer Pauses or Explores Scope Details}}{\text{Total Quotes Rendered}} \times 100$ | Indicates customer paused to consult family or explore FAQs. Revisit policy designated as `[OPERATIONAL POLICY TBD]`. | $10.0\% - 15.0\%$ | `[DESIGN SPECIFICATION]` |
| **Session Abandonment Rate (SAR)** | $\frac{\text{Quotes Expiring or Dismissed Without Choice Submission}}{\text{Total Quotes Rendered}} \times 100$ | Direct operational defect. Indicates UX confusion, technical failure, or offline technician intervention. | $\le 5.0\%$ | `[DESIGN SPECIFICATION]` |
| **Offline Override Bypass Rate (OOBR)** | $\frac{\text{Jobs Closed with "Customer Declined App Tap" Manual Override}}{\text{Total Quotes Rendered}} \times 100$ | Core fraud and compliance indicator; flags technician evading the digital scaffold. | $\le 3.0\%$ | `[DESIGN SPECIFICATION]` |

---

### 4.3 Proxy & Lagging Platform Metrics (Long-Term Trust & Retention)

| Metric Name | Exact Formula | Business Impact | Measurement Window | Target | Status |
|:---|:---|:---|:---|:---|:---|
| **7-Day Billing Dispute Rate** | $\frac{\text{Support Tickets with "Hidden Charge" / "Overcharging" Tag}}{\text{Completed Diagnosis-Dependent Bookings}} \times 100$ | Direct measurement of problem resolution (`D005`, `E014`). Validates that cost ambiguity was eliminated. | Rolling 7-day post-service window | $\le 1.2\%$ (vs $\approx 4.8\%$ current baseline `[ASSUMPTION]`) `[PROPOSED TARGET]` | `[ANALYTICS REQUIREMENT]` |
| **1-Star Price Distress Review Rate** | $\frac{\text{Public Play Store Reviews Mentioning Price / Scam / Cheating}}{\text{Total Category App Store Reviews}} \times 100$ | Protects platform public brand reputation and consumer acquisition trust (`05_evidence_matrix.md`, `PAT-10`). | Monthly rolling aggregate | $\le 2.0\%$ (vs $\approx 7.2\%$ current baseline `[ASSUMPTION]`) `[PROPOSED TARGET]` | `[RESEARCH FINDING]` |
| **90-Day Cross-Vertical Rebooking Rate** | $\frac{\text{Customers Booking Another UC Vertical within 90 Days}}{\text{Customers Experiencing Diagnostic Quote Event}} \times 100$ | Ultimate verification of `D004`: proving that fair, transparent repair interactions preserve long-term platform LTV. | 90 days post-quote | $\ge 32.0\%$ (Treatment cohort vs Control) `[PROPOSED TARGET]` | `[HYPOTHESIS]` |

---

# 5. Marketplace Guardrail Metrics & Non-Negotiables

Because Urban Company is a tightly balanced, dual-sided service marketplace, an intervention that empowers the customer must never destabilize technician supply, platform economics, or operational capacity. 

The following guardrails represent **non-negotiable circuit-breaker boundaries**. Any breach triggers automated alerts and freezes progressive rollout.

```
┌──────────────────────────────────────────────────────────────────────────┐
│                      MARKETPLACE GUARDRAIL BOUNDARIES                    │
├──────────────────────────┬───────────────────────┬───────────────────────┤
│ Partner Supply Health    │ Platform Economics    │ Customer Trust Health │
│ • Hourly Take-Home (≥0%) │ • Funnel Drop (≤1.5%) │ • Dispute Rate (≤1.2%)│
│ • Idle Latency (≤+120s)  │ • Support Cost (≤₹0)  │ • Cancellation (≤2.5%)│
└──────────────────────────┴───────────────────────┴───────────────────────┘
```

### Guardrail Specification Matrix

| Guardrail Name | Dimension | Protection Rationale | Safe Threshold | Immediate Circuit-Breaker Action | Status |
|:---|:---|:---|:---|:---|:---|
| **Partner Hourly Take-Home Pay** | Supply-Side Economics | If transparent declining causes partner net daily earnings to collapse, technicians will strike, bypass the app, or churn (`02_product_context.md`). | $\ge -2.0\%$ variance vs control group (normalized for seasonal demand) | If treatment partner daily earnings drop $> 5.0\%$, immediately adjust partner visitation fee floor credit (`[DESIGN PROPOSAL]`). | `[DESIGN DECISION]` |
| **Partner Quoting Workflow Overhead** | Operational Productivity | High daily job volume requires minimal on-site friction; complex software interactions increase on-site idle time and reduce capacity (`[OPERATIONAL HYPOTHESIS]`). | Latency threshold to be established during field testing (`[DESIGN SPECIFICATION]`) | Quoting flow auto-reverts to single-tap standard bundles if latency P90 exceeds operational limits. | `[DESIGN SPECIFICATION]` |
| **Post-Quote Job Cancellation Rate** | Funnel Conversion | Customers must not cancel the booking entirely to evade paying the legitimate diagnostic/visitation fee (`E041`). | Total cancellation rate after technician arrival $\le 2.5\%$ | Enforce immediate automated capture of pre-authorized visitation fee upon arrival confirmation. | `[FACT]` |
| **Customer Support Cost per Order (CPOR)** | Operating Margin | The digital scaffold must deflect billing confusion inquiries, not spawn new waves of explanatory calls. | Blended support cost per order must not increase ($\Delta \text{CPOR} \le ₹0.00$) | If billing inquiry volume spikes $> 10\%$, pause rollout and audit visual ledger copy. | `[DESIGN DECISION]` |
| **Off-Platform Leakage Proxy** | Marketplace Disintermediation | Technicians offering under-the-table cash deals to do the repair cheaper without platform warranty (`PAT-10`). | Job marked "Declined" but customer cancellation survey cites "Work Done by Local Person" $< 1.5\%$ | Trigger automated algorithmic audit on technician accounts exhibiting abnormal decline-to-completion ratios. | `[ANALYST SYNTHESIS]` |

---

# 6. Counter-Metrics & Anti-Gaming Framework

Every marketplace product intervention creates incentives for gaming. The PDDS instrumentation includes explicit counter-metrics designed to detect and deter unintended or malicious behaviors.

```
┌────────────────────────────────────────────────────────────────────────────────┐
│                       GAMING & ABUSE DETECTION FRAMEWORK                       │
├──────────────────────────┬─────────────────────────────┬───────────────────────┤
│ Attack / Gaming Vector   │ Behavioral Manifestation    │ Algorithmic Detection │
├──────────────────────────┼─────────────────────────────┼───────────────────────┤
│ 1. Partner Phone Grab    │ Tech submits customer choice│ Latency < 4 seconds   │
│ 2. Digital Low-Balling   │ Tech quotes part, adds cash │ SKU vs Invoice Mismatch│
│ 3. Rush-Dismissal Panic  │ Customer panic-cancels      │ Instant back-navigation│
│ 4. Fee Credit Confusion  │ Customer expects free repair│ Repeat dispute filings │
└──────────────────────────┴─────────────────────────────┴───────────────────────┘
```

### Detailed Gaming Counter-Measures

#### 1. Coercive Authorisation ("Phone Grab" Attack)
- **The Risk:** An aggressive technician takes the customer's smartphone under the guise of "helping them set it up" and taps "Authorize" on their own quote.
- **Counter-Metric:** **Sub-4-Second Authorisation Rate (S4AR)** `[PROPOSED THRESHOLD — REQUIRING OPERATIONAL VALIDATION]`.
- **Proposed Detection Logic:**
  $$\text{Flag if: } t(\text{customer\_decision\_submitted}) - t(\text{customer\_card\_rendered}) < 4.0\text{ seconds} \quad \text{`[PROPOSED THRESHOLD]`}$$
  *Operational Note:* The 4.0-second cutoff is an initial heuristic hypothesis. Autonomous comprehension latency must be baselined empirically during pilot instrumentation.
- **Proposed Mitigation:** Sub-4s authorisations trigger an automated post-service SMS verification check or secondary confirmation on high-value quotes (>₹1,500) (`[DESIGN PROPOSAL — TBD ENGINEERING VALIDATION]`).

#### 2. Digital Low-Balling with Offline Cash Supplement
- **The Risk:** To ensure the quote is authorized digitally, the partner selects an artificially cheap diagnostic SKU on the app (e.g., "General Cleaning ₹299"), while verbally charging the customer an extra ₹1,200 in cash for an unrecorded capacitor.
- **Counter-Metric:** **Appliance Category Spare Part Discordance Index**.
- **Detection Logic:** Compare technician's digital SKU history against the category average parts replacement frequency. If a partner registers 3x more zero-part repairs than their peers while receiving low CSAT, flag for field supervisor mystery audit.

#### 3. Premature Rush-Decline
- **The Risk:** Customer opens the quote modal, panics at the gross price, and taps "Decline" immediately without noticing that their ₹249 diagnostic fee has already been credited.
- **Counter-Metric:** **Unexpanded Ledger Decline Rate (ULDR)**.
- **Detection Logic:** Tracks % of decline events where `pdds_ledger_interacted == FALSE`. If $>30\%$ of declines occur without expanding the price breakdown, the UI must be updated to force inline expanded display rather than collapsed tooltips (`[DESIGN DECISION]`).

---

# 7. Telemetry & Data Instrumentation Dictionary

Engineering must instrument the following atomic telemetry events across Customer App (iOS/Android), Partner App (Android), and Core Invoicing Microservices.

### Event Dictionary Schema

| Event Name | Emitter Client | Trigger Condition | Mandatory Payload Properties | Epistemic Status |
|:---|:---|:---|:---|:---|
| `pdds_quote_rendered` | Partner Client | Partner selects SKUs and taps "Send Digital Quote to Customer" (`FR-04`). | `job_id`, `partner_id`, `category_id`, `gross_quote_inr`, `parts_count`, `has_custom_sku` (bool), `time_to_quote_sec` | `[ANALYTICS REQUIREMENT]` |
| `pdds_card_rendered` | Customer Client | Push/socket received; PDDS Decision Card successfully displayed on screen (`FR-06`). | `job_id`, `customer_id`, `render_channel` (socket/push), `diagnostic_fee_credited_inr`, `net_payable_inr`, `is_first_time_booker` (bool) | `[ANALYTICS REQUIREMENT]` |
| `pdds_ledger_interacted` | Customer Client | Customer taps price breakdown or sunk-cost explanatory tooltip (`FR-06`). | `job_id`, `interaction_type` (expand/collapse/tooltip), `time_spent_viewing_ms`, `scroll_depth_pct` | `[ANALYTICS REQUIREMENT]` |
| `pdds_clarify_triggered` | Customer Client | Customer taps "Need Time to Decide / Clarify Scope" CTA (`FR-07`). | `job_id`, `clarification_topic` (parts/pricing/warranty), `session_duration_sec`, `subsequent_action` (auth/decline/exit) | `[ANALYTICS REQUIREMENT]` |
| `pdds_decision_submitted`| Customer Client | Customer submits final definitive choice via Decision Interface (`FR-07`). | `job_id`, `selected_action` (AUTHORIZE/DECLINE/NEED_TIME), `net_amount_inr`, `decision_latency_sec` | `[ANALYTICS REQUIREMENT]` |
| `pdds_diagnostic_summary_rendered`| Core Platform / Customer Client | Customer taps Decline; in-app diagnostic summary & fee receipt displayed (`FR-08`). | `job_id`, `receipt_id`, `parts_identified_count`, `dispatch_latency_ms` (PDF Safety Certificate is de-scoped to later-stage P2 hypothesis) | `[ANALYTICS REQUIREMENT]` |
| `pdds_offline_override` | Partner Client | Partner records customer inability to access smartphone; standard graceful degradation invoked. | `job_id`, `partner_id`, `override_reason_code`, `customer_presence_confirmed` (bool), `supervisor_alert_dispatched` (bool) | `[ANALYTICS REQUIREMENT]` |

---

# 8. Experimentation Protocol & A/B Test Design

### 8.1 Experiment Hypothesis

$$\begin{aligned}
H_0: & \text{ Implementation of PDDS produces no statistically significant difference in Decision Comprehension} \\
     & \text{ (Net Payable Arithmetic Comprehension), Post-Diagnostic Decision Completion Rate, or 7-Day Billing Disputes.} \\
H_1: & \text{ Implementation of PDDS significantly increases Decision Comprehension (} \ge 80\% \text{) and Post-Diagnostic Decision} \\
     & \text{ Completion Rate (} \ge 85\% \text{), and decreases 7-Day Billing Disputes by } \ge 25\%, \text{ while maintaining Quote} \\
     & \text{ Authorization Volume and Partner Hourly Take-Home Pay at or above pre-specified operational guardrail floors.}
\end{aligned}$$

---

### 8.2 Unit of Randomization & Contamination-Aware Design (`[PROPOSED EXPERIMENT DESIGN]`)

```
┌────────────────────────────────────────────────────────────────────────────────┐
│            CONTAMINATION-AWARE EXPERIMENT RANDOMIZATION DESIGN                │
├──────────────────────────────────┬─────────────────────────────────────────────┤
│ Primary Proposal: Partner-Cohort │ Alternative Proposal: Switchback Design     │
│ Randomization                    │ (Time-Based Market Alternation)             │
├──────────────────────────────────┼─────────────────────────────────────────────┤
│ • Isolates partner workflow habit│ • Eliminates cross-job partner confusion    │
│ • Eliminates intra-day switching │ • Controls for localized micro-market demand │
│ • Prevents on-site confusion     │ • Absorbs fluid geographic technician travel│
└──────────────────────────────────┴─────────────────────────────────────────────┘
```

#### Why Micro-Market Geohash Randomization Fails (Technician Mobility Spillover)
In urban home services, service technicians do not remain confined to a single Geohash or pin code. Technician movement across geographic boundaries can create treatment spillover; the degree of cross-cluster mobility would require validation from operational dispatch data (`[OPERATIONAL HYPOTHESIS]`). If randomization were purely geographic (e.g., Geohash-6 or pin code):
1. **Intra-Day Partner Contamination:** A single technician servicing jobs across adjacent neighborhoods could alternate between the legacy workflow on Job 1 and the PDDS workflow on Job 2 within a short window. This creates behavioral dissonance, training failure, and corrupted execution.
2. **Customer Network Spillover:** Adjacent households in the same apartment complex or residential society serviced by different technicians would receive radically different quoting interfaces.

#### Candidate Proposals to Mitigate Contamination:
1. **Partner-Cohort Randomization (`[PROPOSED EXPERIMENT DESIGN]`):**
   - Randomization is executed at the **Service Partner Fleet level** across balanced partner cohorts.
   - Cohorts are balanced on baseline category GMV, historical completion rate, and average tenure.
   - A technician assigned to Treatment uses PDDS for **all** eligible diagnosis jobs across their route; a technician assigned to Control uses the legacy flow.
   - Partner hubs and morning briefing clusters are grouped into the same variant where feasible to mitigate hub-level cross-talk, though residual hub contamination and partner churn remain documented risks.
2. **Switchback / Time-Based Cluster Design (`[PROPOSED EXPERIMENT DESIGN]`):**
   - Alternatively, entire metropolitan clusters alternate between Treatment and Control in multi-day switchback blocks with buffer washout windows (block length and washout period to be determined during experiment design based on operational carryover characteristics).
   - Designed to mitigate simultaneous cross-treatment exposure within a market, subject to seasonal demand swings and customer carryover constraints.

---

### 8.3 Pilot Market Selection & Randomization Protocol (`THR-03`)

Rather than a geographic cluster A/B test (which was explicitly **rejected in `THR-03`** due to technician cross-neighborhood mobility creating treatment-to-control spillover), the proposed experiment is deployed via **Partner-Cohort Randomization** within high-density operating markets, with **2-Week Switchback Blocks** as an operational alternative:

| Selection Criterion | Operational Requirement | Rationale for Criterion |
|:---|:---|:---|
| **1. Diagnosis-Dependent Category Share** | AC Repair, Appliance Repair, and Water Purifiers constitute $\ge 45\%$ of total category GMV in market. | Ensures rapid sample accumulation without prolonged experiment duration. |
| **2. Partner Density & Fleet Stability** | Active category partner fleet size $\ge 400$ technicians; 60-day partner attrition rate $< 6\%$. | Prevents capacity bottlenecks from confounding fulfillment latency. |
| **3. High Mix of First-Time Bookers** | First-time category bookers comprise between $35\% - 55\%$ of monthly order volume. | Ensures adequate statistical representation of Primary Target Segment 1 (`D006`). |
| **4. Customer Support Capacity** | Local support hub equipped with specialized Tier-2 billing escalation agents. | Guarantees support tickets are accurately tagged with PDDS reason codes without operational backlog. |
| **5. Seasonal Demand Neutrality** | Experiment timing must avoid extreme summer peak (AC over-demand) or monsoon lulls. | Extreme demand surges artificially inflate quote acceptance, obscuring baseline product friction. |

#### Approved Deployment Architecture
- **Primary Design:** **Partner-Cohort Randomization** within Delhi-NCR and Bengaluru metro fleets. Technicians are randomized 1:1 into Treatment (PDDS flow) and Control (legacy flow) cohorts balanced on tenure and historical GMV.
- **Alternative Design:** **2-Week Switchback Blocks** alternating entire metropolitan operating zones between Treatment and Control with buffer washout windows to eliminate intra-day partner confusion.

---

### 8.4 Illustrative Statistical Power & Sample Size Modeling

> [!NOTE]
> **Governance Context (`THR-12`):** The following calculations represent a `[HISTORICAL MODELING ASSUMPTION — NOT OBSERVED TELEMETRY]` constructed to demonstrate two-proportion statistical mechanics. Public researchers do not have access to internal Urban Company production baselines. In production execution, sample sizes will be dynamically calibrated on observed baseline variance during Phase 1 dogfooding.

#### Statistical Parameters
- **Significance Level ($\alpha$):** $0.05$ (two-tailed test; 95% confidence).
- **Statistical Power ($1 - \beta$):** $0.80$ (80% power to detect true effect).
- **Allocation Ratio:** $1:1$ (50% Treatment: PDDS Flow; 50% Control: Legacy Flow).

#### Illustrative Sample Size Computation (Secondary Process Metric: PDCR)
- **Hypothesized Baseline Conversion ($p_1$):** $18.5\%$ ($0.185$) `[HISTORICAL MODELING ASSUMPTION]`.
- **Hypothesized Minimum Detectable Effect (MDE):** $+15.0\%$ absolute lift ($p_2 = 33.5\%$).
- **Standard Formula:**
  $$n = \frac{\left( Z_{\alpha/2}\sqrt{2 \bar{p}(1-\bar{p})} + Z_{\beta}\sqrt{p_1(1-p_1) + p_2(1-p_2)} \right)^2}{(p_2 - p_1)^2}$$
  Where $\bar{p} = \frac{p_1 + p_2}{2} = 0.26$, $Z_{\alpha/2} = 1.96$, $Z_{\beta} = 0.8416$.

$$\begin{aligned}
n_{\text{variant}} & \approx \frac{\left( 1.96\sqrt{2(0.26)(0.74)} + 0.8416\sqrt{(0.185)(0.815) + (0.335)(0.665)} \right)^2}{(0.335 - 0.185)^2} \\
& \approx 133 \text{ completed diagnostic visits per cohort [ILLUSTRATIVE]}
\end{aligned}$$

#### Illustrative Dispute Metric Sample Size
- **Hypothesized Baseline Dispute Rate ($p_1$):** $4.8\%$ ($0.048$) `[HISTORICAL MODELING ASSUMPTION]`.
- **Hypothesized MDE:** $-1.5\%$ absolute reduction ($p_2 = 3.3\%$).
- Applying the two-proportion test formula for a low-incidence metric yields:
  $$n_{\text{variant}} \approx 2,420 \text{ bookings per cohort} \implies N_{\text{total}} \approx 4,840 \text{ [ILLUSTRATIVE SCENARIO]}$$

#### Experiment Duration Policy
- **Protocol Minimum Duration:** **21 full days (3 complete 7-day business cycles)** (`[DESIGN DECISION]`).
  - *Rationale:* Must run for minimum 3 full weeks to smooth out weekday vs weekend booking behavior, capture pay-day cyclicality, and allow 7-day post-service billing dispute tickets to mature.

---

### 8.5 Decision Rules & Rollout Thresholds

The decision to graduate the experiment from pilot clusters to general availability across all 50+ Urban Company operating cities is governed by explicit statistical gates. 

> [!IMPORTANT]
> **Commercial Metric Governance Principle:**  
> A user selecting **Decline** is treated as a clean operational process completion, **NEVER as a commercial product win**. Commercial viability requires that Quote Authorization Volume and Partner Take-Home Earnings remain at or above established guardrail floors.

```
┌────────────────────────────────────────────────────────────────────────────────┐
│                         EXPERIMENT SHIP DECISION MATRIX                        │
├────────────────────────────────────┬───────────────────────────────────────────┤
│ SHIP / SCALE (100% Pan-India)      │ • Decision Comprehension ≥ 80%            │
│                                    │ • Quote Authorization Volume at/above     │
│                                    │   pre-specified operational floor         │
│                                    │ • PDCR exhibits statistically significant │
│                                    │   lift (p < 0.05) vs Control              │
│                                    │ • 7-Day Billing Disputes decrease ≥ 20%   │
│                                    │ • Partner Hourly Earnings delta ≥ -2.0%   │
│                                    │ • Booking-to-Job Cancellations delta ≤ 0% │
├────────────────────────────────────┼───────────────────────────────────────────┤
│ ITERATE / REVISE                   │ • PDCR improves, but Partner Overhead     │
│                                    │   P90 exceeds 120 seconds                 │
│                                    │ • Authorization rate softens below target │
│                                    │   due to unaddressed price elasticity     │
│                                    │ • Partner dissatisfaction over unrecovered│
│                                    │   diagnostic effort on clean declines     │
├────────────────────────────────────┼───────────────────────────────────────────┤
│ NO-SHIP / AUTOMATED ROLLBACK       │ • Quote Authorization Volume collapses    │
│                                    │ • Partner Hourly Take-Home drops > 5.0%   │
│                                    │ • Off-platform bypass rate exceeds 5.0%   │
│                                    │ • Total completed job conversion drops    │
│                                    │   > 2.5% statistically significant        │
└────────────────────────────────────┴───────────────────────────────────────────┘
```

---

# 9. Implementation Checklist & Sign-Off Gates

Before code deployment to the pilot clusters, the following analytical readiness checks must be completed:

- [x] **North Star Formulation:** Primary Product Success locked as `Decision Quality & Comprehension`; Secondary Process Metric locked as `Post-Diagnostic Decision Completion Rate (PDCR)` (`D005`).
- [x] **Metric Tree Causality:** All input levers (`PQCR`, `DCRR`, `PDAE`, `SLIR`) causally connect to Decision Comprehension and Process Completion.
- [x] **Multi-Sided Guardrails:** Quote Authorization Volume floor, partner earnings floor, workflow overhead, and cancellation thresholds established.
- [x] **Anti-Gaming Defenses:** Sub-4s authorization flags (`[PROPOSED THRESHOLD]`) and unexpanded decline monitors specified.
- [x] **Telemetry Schema:** Full event dictionary (`pdds_*`) defined with exact payload schemas.
- [x] **Statistical Protocol:** Contamination-aware Partner-Cohort / Switchback A/B design sized for 21 days across 4,840 bookings (`[PROPOSED EXPERIMENT DESIGN]`).
- [x] **Epistemic Discipline:** 100% of claims labeled with project epistemic taxonomy.

---

*This document establishes the formal quantitative governance framework for `20_validation_plan.md`.*
