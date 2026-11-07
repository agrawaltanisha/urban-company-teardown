# PM-01 — Urban Company
## 05 — Evidence Matrix

**Stage:** RESEARCH → ANALYSIS  
**Purpose:** Record, classify, and trace every piece of load-bearing evidence gathered, with explicit labels for type, confidence, hypothesis relationships, competing interpretations, scope limitations, and source-level counter-evidence.  
**Last updated:** 2026-09-17 (Post-Audit Calibration)  

> **Hard Rules (EVIDENCE_POLICY.md & AGENTS.md):**
> 1. **Zero Fabrication:** Every evidence entry must cite a valid Source ID registered in [`04_source_log.md`](../02_source_log.md). No imaginary quotes, metrics, or sources.
> 2. **Sample-Only Scope:** All review-mining statistics and patterns describe this sampled dataset only ($N=179$) collected across three slices (`Most Relevant 5 Star`, `Most Relevant 4 Star`, `Newest`). They must **NEVER** be generalized as platform-wide metrics (e.g., claiming Urban Company has a 14.5% cancellation rate is prohibited; the factual statement is that 14.5% of reviewed sample entries mentioned cancellations).
> 3. **Non-Causal Discipline:** Data points demonstrate sample frequency and qualitative co-occurrence; they do not establish causal proof.
> 4. **Preserve Contradictions:** Do not selectively discard conflicting evidence; log opposing observations explicitly in both detailed records and the Contradictions Log.
> 5. **Hypothesis Anchorage:** Hypotheses H1–H5 are formally defined in [`08_problem_discovery.md`](../01_problem_discovery_review_mining.md) (lines 32–156). Customer review mappings reflect customer-perceived symptoms and sentiment salience; they do not constitute direct verification of platform-side algorithms or macro business metrics.

---

## Evidence Classification System

Per [`EVIDENCE_POLICY.md`]:

| Label | Evidence Level | Operational Meaning in this Matrix |
|---|---|---|
| `FACT` | Level 1 / 2 | Deterministic dataset facts verified directly from audited project data or verified primary records |
| `RESEARCH FINDING (community)` | Level 4 | Qualitative signals and behavioral patterns extracted from public user review text (sample-only) |
| `ASSUMPTION` | — | Stated operational belief tracked in `06_assumption_log.md`; requires validation |
| `HYPOTHESIS` | — | Testable proposition tracked in `08_problem_discovery.md` |
| `ESTIMATE` | Level 5 | Derived quantitative calculation with transparent methodology shown |

### Dual-Confidence Calibration Framework (Approved Methodology)

For qualitative research findings and edge-case patterns, confidence is decoupled into two explicit dimensions rather than an arbitrary single-rating score:
* **High Confidence** refers to: **Phenomenon Existence, Concrete Mechanism, and Verbatim Traceability**. Confirms that the specific failure mode, charge, or behavior is verified by unambiguous primary review text (exact monetary penalties, explicit physical damage descriptions, or verbatim quotations).
* **Medium Confidence** refers to: **Prevalence, Recurrence Breadth, and Sample Generalizability**. Acknowledges that the absolute number of cases in the sample is small ($n \le 7$) or concentrated within specific categories/ratings, preventing platform-wide prevalence claims without internal operational data.
* *Guidance:* Small sample size ($n < 10$) alone does not trigger a downgrade if the mechanism and verbatim evidence are incontrovertible; instead, the dual treatment transparently reports both existence fidelity (High) and sample prevalence limits (Medium).

---

## Evidence Registry Summary

| Evidence ID | Claim / Finding Summary | Evidence Type | Source ID | Confidence | Hypothesis Relationship (H1–H5) | Sample Population |
|---|---|---|---|---|---|---|
| **E001** | Dataset size ($N=179$) across 3 Google Play slices | `FACT` | S001, S002, S003 | High | Baseline parameter (None) | Entire dataset ($N=179$) |
| **E002** | Valid rating ($n=139$, 77.7%) and unrecoverable rating ($n=40$, 22.3%) counts | `FACT` | S001, S002, S003 | High | Baseline parameter (None) | Entire dataset ($N=179$) |
| **E003** | Quality-related themes appear in 28.5% ($n=51/179$) of reviews | `FACT` | S001, S003 | High | Consistent with `H2` (salience of workmanship; indirect on retention impact) | Sample ($N=179$) |
| **E004** | Pricing-related themes appear in 25.7% ($n=46/179$) of reviews | `FACT` | S001, S003 | High | Competing friction area (None) | Sample ($N=179$) |
| **E005** | Cancellation-related themes appear in 14.5% ($n=26/179$) of reviews | `FACT` | S001, S003 | High | Symptom consistent with `H3` (liquidity/matching stress; unverified algorithm) | Sample ($N=179$) |
| **E006** | App/UX-related themes appear in 26.8% ($n=48/179$) of reviews | `FACT` | S001, S003 | High | Weakly / Indirectly relevant to `H1` (predominantly support/dispute UX, not rebooking UX) | Sample ($N=179$) |
| **E007** | Professional behavior themes appear in 30.2% ($n=54/179$) of reviews | `FACT` | S001, S003 | High | Consistent with `H2` (Inverse signal: partner conduct anchors satisfaction; indirect on H2 inconsistency) | Sample ($N=179$) |
| **E008** | Trust-related themes appear in 7.8% ($n=14/179$) of reviews | `FACT` | S001, S003 | High | Supports post-booking domestic trust in reformulated `H4` (Two-Stage Trust Model); pre-booking trust unassessed | Sample ($N=179$) |
| **E009** | Rebooking-related themes appear in 3.4% ($n=6/179$) of reviews | `FACT` | S001, S003 | High | Supports existence of `H1` friction ($n=3$); low sample volume challenges `H1` dominance | Sample ($N=179$) |
| **E010** | Consistency-related themes appear in 3.4% ($n=6/179$) of reviews | `FACT` | S001, S003 | High | Consistent with `H2` (documents longitudinal variance, but indirect on retention reduction) | Sample ($N=179$) |
| **E011** | AI chatbot deflection wall blocks escalation to human agents ($n=11/51$ negative cohort) | `RESEARCH FINDING (community)` | S001, S004 | High (mechanism) / Negative-skew caveat | Indirect / Amplifies `H2` (blocks dispute remediation when quality fails) | Negative cohort ($n=11/51$) |
| **E012** | Asymmetric cancellation penalties levied on platform/partner failures ($n=5/26$) | `RESEARCH FINDING (community)` | S001, S004 | Medium (prevalence) / High (mechanism) | Policy symptom consistent with `H3`; internal rules unobserved | Cancellation cohort ($n=5/26$) |
| **E013** | Chronic partner no-shows and cancellations in Insta Help ($n=11/26$ in vertical) | `RESEARCH FINDING (community)` | S001, S004 | High (vertical) / Negative-skew caveat | Strong vertical-specific operational pattern; consistent with `H3` on-demand stress, unproven at platform level | Insta Help cohort ($n=11/26$) |
| **E014** | Post-booking checkout surge, platform fees, and add-on inflation ($n=13/46$) | `RESEARCH FINDING (community)` | S001, S004 | High (pricing line items) | Competing friction area (None) | Pricing cohort ($n=13/46$) |
| **E015** | In-home privacy and domestic boundary breaches create acute fear ($n=4/14$) | `RESEARCH FINDING (community)` | S001, S004 | Medium (prevalence) / High (existence) | Supports post-booking domestic trust in reformulated `H4` (Two-Stage Trust Model); pre-booking unassessed | Trust cohort ($n=4/14$) |
| **E016** | Secondary appliance damage and collateral breakdown post-repair ($n=6/51$) | `RESEARCH FINDING (community)` | S001, S004 | Medium (prevalence) / High (existence) | Consistent with `H2` (severe quality defects destroy trust; indirect on aggregate rebooking) | Quality cohort ($n=6/51$) |
| **E017** | Partner punctuality and courtesy anchor 5-star repeat satisfaction ($n=41/93$) | `RESEARCH FINDING (community)` | S001, S004 | High (dominant positive signal) | Consistent with `H2` (Inverse signal: confirms sensitivity to partner quality; indirect on inconsistency) | Positive cohort ($n=41/93$) |
| **E018** | Repeat customers prefer known partners; reassignment causes anxiety ($n=7/14$) | `RESEARCH FINDING (community)` | S001, S004 | Medium (low $n=7$, high fidelity) | Consistent with `H1` (customer desire) and `H3` (liquidity symptom; rules unobserved) | Rebooking cohort ($n=7/14$) |
| **E019** | Reviewers decouple ratings: praise gig worker while docking platform ($n=7/48$) | `RESEARCH FINDING (community)` | S001, S004 | Medium (prevalence) / High (verbatim text) | Indirect / Structural context for `H1`, `H2` (trust resides in partner, not platform) | 4-Star cohort ($n=7/48$) |
| **E038** | Indian gig workforce projected to grow from 7.7M (2020-21) to 23.5M by 2030 | `FACT` | S020, S021 | High | DOES NOT ADDRESS | Macro Indian Economy |
| **E039** | UC reported FY24 revenue of INR 827 crore (30% YoY growth) and PBT loss narrowed to 93 crore | `COMPANY CLAIM (attributed)` | S007 | High | DOES NOT ADDRESS | Internal Financials |
| **E040** | UC's AC rate-card source lists fixed prices for specified parts/services (e.g., ₹4500 inverter PCB, ₹250 capacitor) | `FACT` | S009 | High | MIXED | Product Features |
| **E041** | UC charges a visitation/diagnostic fee in specified repair flows; policy states how fee is treated if quote is accepted/declined | `FACT` | S009 | High | SUPPORTS WITH INTERPRETATION CAVEAT | Product Policy |
| **E042** | UC requires at-home consultation, exact quoting, and 35% upfront booking for painting ≥ ₹25,000 | `FACT` | S010 | High | SUPPORTS (CONTEXTUAL) | Product Policy |
| **E043** | Thumbtack operates primarily as a lead-generation platform utilizing custom estimates and competitive bidding | `FACT` | S018 | High | DOES NOT ADDRESS | Competitor Model |
| **E044** | Reddit discussions allege substantial customer markup from TaskRabbit's Trust & Support Fee | `RESEARCH FINDING (community)` | S015, S019 | Low | DOES NOT ADDRESS / CONTEXTUAL ANALOGUE | Competitor Model |
| **E045** | TaskRabbit caps material expense reimbursements at $100 ($150 dump fees) and forbids expensing logistics | `FACT` | S016 | High | DOES NOT ADDRESS | Competitor Policy |
| **E046a** | UC India offers free cancellations up to 24h before high-value jobs, but charges penalties within 24h (e.g., ₹1000 painting) | `FACT` | S012 | High | MIXED / CONTEXTUAL | Product Policy |
| **E046b** | UC Singapore imposes strict cancellation penalties within 24h window (SGD 20 cleaning) | `FACT` | S013 | High | MIXED / CONTEXTUAL | Product Policy |
| **E047** | As part of 12-point program, UC transfers 100% of last-minute customer cancellation fees to the affected partner | `COMPANY CLAIM (attributed)` | S008 | High | MIXED / CONTEXTUAL | Company Claim |
| **E048** | UC provides a 30-day baseline service guarantee, up to 90-days on critical appliances, up to INR 10,000 damage protection | `COMPANY CLAIM (attributed)` | S011 | High | DOES NOT ADDRESS | Company Claim |
| **E049** | UC extended warranty strictly excludes third-party repair, commercial use, aesthetic defects, consequential loss | `FACT` | S011 | High | DOES NOT ADDRESS | Product Policy |
| **E050** | UC Native RO water purifier engineered with self-regulating mechanisms to offer 2-year warranty | `COMPANY CLAIM (attributed)` | S007, S011 | High | DOES NOT ADDRESS / CONTEXTUAL ANALOGUE | Product Feature |
| **E051** | Worker/labor organizations have alleged that auto-assign strips professionals of agency and subjects them to arbitrary blocks | `ANALYST SYNTHESIS` | Unregistered | Medium | DOES NOT ADDRESS | External Labor Movement |
| **E052** | UC announced reduction in max commission slab from 30% to 25% (average 20-22%) and slashed max monthly penalty to ₹1,500 | `COMPANY CLAIM (attributed)` | S008 | High | DOES NOT ADDRESS | Company Claim |
| **E053** | UC claims to have removed all temporary algorithmic blocks except for verified quality failures (estimated 80% reduction) | `COMPANY CLAIM (attributed)` | S008 | High | DOES NOT ADDRESS | Company Claim |
| **E054** | Fairwork India Ratings scored UC 8/10 in 2019, downgraded to 6/10 in 2024 (stripped points for fair representation) | `FACT` | S014 | High | DOES NOT ADDRESS | Independent Audit |
| **E055** | UC reports top 20% partners earn ₹42,792/month net; female partners average 23% higher hourly earnings than male | `COMPANY CLAIM (attributed)` | S007 | High | DOES NOT ADDRESS | Company Claim |
| **E056** | Analyst synthesis based on cited labor literature; not independently quantified for Urban Company's median partner population | `ANALYST SYNTHESIS` | Unregistered | Medium | DOES NOT ADDRESS | Independent Finding |

---

## Detailed Evidence Records

### [E001] Dataset Size and Sampling Architecture
* **Evidence Statement:** The audited review-mining dataset consists of exactly $N=179$ user reviews collected across three distinct operational slices on the Google Play Store.
* **Evidence Type:** `FACT` (Audited dataset property)
* **Source ID:** `S001` ([`PM01_Urban_Company_Cleaned.xlsx`](Urban_Company_Cleaned_Dataset.xlsx)), `S002` ([`DATA_QUALITY_ANALYSIS.md`](data_quality_analysis.md)), `S003` ([`DESCRIPTIVE_ANALYSIS.md`](descriptive_analysis.md))
* **Underlying Metric / Observation:** Total records = 179. Sheet 1 (`Most Relevant 5 Star`) = 57 reviews; Sheet 2 (`Most Relevant 4 Star`) = 47 reviews; Sheet 3 (`Newest`) = 75 reviews. Date span: 2019-06-12 to 2026-09-15.
* **Confidence Level:** **High** — Deterministic row count verified by programmatic audit.
* **Confidence Rationale:** Verified directly from cleaned workbook; raw file preserved 100% unchanged.
* **Hypothesis Relationship:** None (Dataset architectural parameter).
* **Competing Interpretation:** Slices represent purposive sampling targeting high-rating and recent sentiment, not a uniform random sample of all historical transactions.
* **Scope Limitation:** Sample-only parameter. Does not represent total Urban Company app download or review volume.

---

### [E002] Rating Provenance and Missing Rating Distribution
* **Evidence Statement:** Of the 179 reviews in the sample, 139 (77.7%) contain verified original star ratings, while 40 (22.3%) have unrecoverable missing ratings resulting from a source extraction bug.
* **Evidence Type:** `FACT` (Audited dataset property)
* **Source ID:** `S001`, `S002`, `S003`
* **Underlying Metric / Observation:** $N_{\text{valid}} = 139$ (5.0 stars = $n=91$ [65.5% of valid]; 4.0 stars = $n=48$ [34.5% of valid]; 1.0–3.0 stars = 0 valid sampled). $N_{\text{missing}} = 40$ (all located in Sheet 3 `Newest`; audited and labeled `[RATING UNAVAILABLE]` with zero synthetic ratings invented).
* **Confidence Level:** **High** — 100% audited row-by-row against review text under strict zero-fabrication rules.
* **Confidence Rationale:** Confirmed in `DATA_QUALITY_ANALYSIS.md` Section 2.
* **Hypothesis Relationship:** None (Dataset architectural parameter).
* **Competing Interpretation:** Missing ratings stem from a scraper extraction failure on the Play Store web interface, not user unwillingness to provide a rating.
* **Scope Limitation:** Confined to the extraction pipeline artifact; rating-based statistics must exclude the 40 missing rows.

---

### [E003] Quality-Related Theme Prevalence
* **Evidence Statement:** Service quality and workmanship themes appear in 28.5% ($n=51/179$) of the reviewed sample, showing extreme vertical concentration in Home Cleaning (93.8% of sample cleaning reviews) and Appliance Repair (61.0% of sample appliance reviews).
* **Evidence Type:** `FACT` (Sample descriptive frequency)
* **Source ID:** `S001`, `S003` (`DESCRIPTIVE_ANALYSIS.md` Section 3.1, 3.4 & 4 Theme 14)
* **Underlying Metric / Observation:** 
  * Total quality-themed reviews: $n=51/179$ (28.5% of sample); valid ratings $n=40/139$ (28.8%); missing ratings $n=11/40$ (27.5%). Valid rating distribution: 5-star $n=30/91$ (33.0%), 4-star $n=10/48$ (20.8%).
  * Sentiment & Sub-Theme Breakdown (Disambiguated Denominators):
    * *Positive Workmanship:* $n=31$ ($31/51 = 60.8\%$ of quality-themed reviews; $31/93 = 33.3\%$ of all positive reviews in sample).
    * *Negative Defects & Collateral Damage:* $n=14$ ($14/51 = 27.5\%$ of quality-themed reviews; $14/51 = 27.5\%$ of all negative reviews in sample).
    * *Mixed Quality Evaluations:* $n=5$ ($5/51 = 9.8\%$ of quality-themed reviews; $5/30 = 16.7\%$ of all mixed reviews in sample).
    * *Neutral:* $n=1$ ($1/51 = 2.0\%$ of quality-themed reviews; $1/5 = 20.0\%$ of neutral reviews).
  * Vertical concentration within sample: Home Cleaning $n=15/16$ (93.8%), Appliance Repair $n=25/41$ (61.0%), Home Maintenance $n=1/7$ (14.3%), Platform $n=7/86$ (8.1%), Insta Help $n=2/26$ (7.7%).
* **Confidence Level:** **High** — Rigorous semantic coding across all records with explicit numerators and denominators.
* **Confidence Rationale:** Direct mathematical frequency derived from audited data.
* **Hypothesis Relationship:** Consistent with `H2` (Service quality inconsistency) on the premise of quality salience: demonstrates that service execution is a primary customer evaluative criterion (28.5% of sample). It does **not** directly prove that quality inconsistency reduces aggregate repeat booking rates, as macro retention metrics require operational data.
* **Competing Interpretation:** Customers review service quality disproportionately in technical or deep-cleaning trades because physical outcomes are highly visible, whereas routine tasks generate less commentary.
* **Scope Limitation:** Sample descriptive frequency; cannot be generalized as the macro platform defect or satisfaction rate.

---

### [E004] Pricing-Related Theme Prevalence
* **Evidence Statement:** Pricing-related themes appear in 25.7% ($n=46/179$) of the reviewed sample, with negative pricing friction appearing in 37.3% ($n=19/51$) of negative reviews.
* **Evidence Type:** `FACT` (Sample descriptive frequency)
* **Source ID:** `S001`, `S003` (`DESCRIPTIVE_ANALYSIS.md` Section 3.1 & 4 Theme 15)
* **Underlying Metric / Observation:** 
  * Total pricing-themed reviews: $n=46/179$ (25.7% of sample); valid ratings $n=33/139$ (23.7%); missing ratings $n=13/40$ (32.5%). Valid rating distribution: 4-star $n=16/48$ (33.3%) vs 5-star $n=17/91$ (18.7%).
  * Sentiment Breakdown (Disambiguated Denominators):
    * *Positive Pricing Praise:* $n=17$ ($17/46 = 37.0\%$ of pricing-themed reviews; $17/93 = 18.3\%$ of all positive reviews in sample) praising reasonable rates and transparency (`R0001`, `R0008`, `R0033`, `R0035`).
    * *Negative Pricing Friction:* $n=19$ ($19/46 = 41.3\%$ of pricing-themed reviews; $19/51 = 37.3\%$ of all negative reviews in sample) citing checkout platform fees (₹166 on ₹1,055 bill, `R0092`), default surge pricing (₹150–₹200, `R0058`, `R0165`), cancellation fines (₹50, `R0115`), and minor fix overcharges (`R0090`).
    * *Mixed Pricing:* $n=8$ ($8/46 = 17.4\%$ of pricing-themed reviews; $8/30 = 26.7\%$ of mixed reviews).
    * *Neutral:* $n=2$ ($2/46 = 4.3\%$ of pricing-themed reviews; $2/5 = 40.0\%$ of neutral reviews).
* **Confidence Level:** **High** — Clear frequency and recurring specific price points.
* **Confidence Rationale:** Supported by explicit billing figures cited by independent reviewers.
* **Hypothesis Relationship:** None mapped directly to H1–H5. Documents that pricing transparency and fee stacking represent a major friction area competing with trust/rebooking as a primary driver of user dissatisfaction.
* **Competing Interpretation:** Price sensitivity may reflect customer resistance to platform monetization fees (platform fees, convenience charges) rather than dissatisfaction with baseline labor costs.
* **Scope Limitation:** Sample descriptive finding; does not reflect average order value or price elasticity across all categories.

---

### [E005] Cancellation-Related Theme Prevalence
* **Evidence Statement:** Cancellation-related themes appear in 14.5% ($n=26/179$) of the reviewed sample, clustering heavily in Insta Help & Daily Services where cancellations represent 42.3% of vertical reviews and 42.3% of all cancellation reviews.
* **Evidence Type:** `FACT` (Sample descriptive frequency)
* **Source ID:** `S001`, `S003` (`DESCRIPTIVE_ANALYSIS.md` Section 3.1, 3.4 & 4 Theme 16)
* **Underlying Metric / Observation:** 
  * Total cancellation-themed reviews: $n=26/179$ (14.5% of sample); valid ratings $n=13/139$ (9.4%); missing ratings $n=13/40$ (32.5%). Negative sentiment $n=19/51$ (37.3% of negative sample reviews).
  * Vertical Concentration & Dual-Denominator Disambiguation:
    * Reviews in Insta Help vertical mentioning cancellation: $n=11$.
    * *Denominator 1 (Vertical Base):* $11 / 26 = \mathbf{42.3\%}$ of all reviews in the Insta Help vertical ($n=26$) mentioned cancellation.
    * *Denominator 2 (Cancellation Base):* $11 / 26 = \mathbf{42.3\%}$ of all cancellation-themed reviews in the sample ($n=26$) occurred in the Insta Help vertical.
    * *(Note: Both denominators equal 26 by numerical coincidence; they represent distinct populations).*
    * Other verticals: Platform, App & Support $n=8/86$ (9.3%), Appliance Repair $n=6/41$ (14.6%), Home Maintenance $n=1/7$ (14.3%), Cleaning $n=0/16$ (0.0%).
* **Confidence Level:** **High** — Statistically pronounced concentration in on-demand chores.
* **Confidence Rationale:** Verified cross-tabulation in `DESCRIPTIVE_ANALYSIS.md`.
* **Hypothesis Relationship:** Symptom consistent with `H3` (Platform allocation rules constrain continuity). Customer-reported cancellation friction confirms acute supply-demand matching failure, but represents a customer-facing symptom rather than direct proof of internal platform allocation algorithms.
* **Competing Interpretation:** High cancellation in Insta Help reflects short-lead-time dispatch challenges in low-ticket chores rather than systemic platform-wide matching failure.
* **Scope Limitation:** Sample descriptive frequency; cannot be extrapolated as platform-wide cancellation rate.

---

### [E006] App/UX-Related Theme Prevalence
* **Evidence Statement:** App/UX-related themes appear in 26.8% ($n=48/179$) of the reviewed sample, spanning positive booking flow praise (19.4% of positive reviews) and negative support/channel friction (31.4% of negative reviews).
* **Evidence Type:** `FACT` (Sample descriptive frequency)
* **Source ID:** `S001`, `S003` (`DESCRIPTIVE_ANALYSIS.md` Section 3.1 & 4 Theme 17)
* **Underlying Metric / Observation:** $n=48/179$ total (26.8% of sample); valid ratings $n=36/139$ (25.9%); missing ratings $n=12/40$ (30.0%). Valid ratings: 4-star $n=18/48$ (37.5%), 5-star $n=18/91$ (19.8%). Positive UX $n=18/93$ (19.4% of positive sample) citing smooth booking and intuitive slot selection; negative UX $n=16/51$ (31.4% of negative sample) citing repetitive AI chatbots, missing telephone helplines, and address confirmation bugs.
* **Confidence Level:** **High** — Broadly represented across the dataset.
* **Confidence Rationale:** Verified thematic breakdown in `DESCRIPTIVE_ANALYSIS.md`.
* **Hypothesis Relationship:** Weakly / Indirectly relevant to `H1` (Repeat-booking UX friction). While demonstrating that UX friction exists in the review sample (26.8%), the qualitative substance is heavily dominated by post-service dispute resolution and AI chatbot deflection (Theme 17 / `E011`) rather than pre-booking rebooking discovery friction.
* **Competing Interpretation:** Negative App/UX comments are often downstream expressions of anger toward physical service execution or billing disputes rather than usability flaws in core app software.
* **Scope Limitation:** Play Store reviews inherently over-index on app interface feedback compared to off-platform customer touchpoints.

---

### [E007] Professional Behavior Theme Prevalence
* **Evidence Statement:** Professional behavior is the most prevalent positive operational theme in the sample, appearing in 30.2% ($n=54/179$) of all reviews and 45.1% ($n=41/91$) of 5-star reviews.
* **Evidence Type:** `FACT` (Sample descriptive frequency)
* **Source ID:** `S001`, `S003` (`DESCRIPTIVE_ANALYSIS.md` Section 3.1 & 3.2)
* **Underlying Metric / Observation:** $n=54/179$ total (30.2% of sample); valid ratings $n=51/139$ (36.7%); missing ratings $n=3/40$ (7.5%). 5-star $n=41/91$ (45.1%), 4-star $n=10/48$ (20.8%). Overwhelmingly positive sentiment ($n=41/93$, 44.1% of positive reviews) citing punctuality, polite conduct, discipline, uniform standards, and tidy cleanup.
* **Confidence Level:** **High** — Dominant qualitative theme in positive feedback.
* **Confidence Rationale:** Consistent phraseology (`professional`, `punctual`, `polite`) verified across 54 reviews.
* **Hypothesis Relationship:** Consistent with `H2` (Inverse Signal). Confirms that customer evaluation of service quality is heavily anchored in individual partner interpersonal conduct, supporting the premise of H2 that partner performance drives retention; indirect on the negative mechanism of quality inconsistency reducing rebooking.
* **Competing Interpretation:** High ratings for courtesy may reflect low baseline expectations in the unorganized domestic services market in India, where basic punctuality generates outsized customer delight.
* **Scope Limitation:** Sample descriptive finding.

---

### [E008] Trust-Related Theme Prevalence
* **Evidence Statement:** Explicit trust-related themes appear in 7.8% ($n=14/179$) of reviews in the sample; while quantitatively low, negative trust reviews ($n=8/51$, 15.7% of negative reviews) detail severe domestic sanctuary breaches and safety concerns.
* **Evidence Type:** `FACT` (Sample descriptive frequency)
* **Source ID:** `S001`, `S003` (`DESCRIPTIVE_ANALYSIS.md` Section 3.1 & 4 Theme 11)
* **Underlying Metric / Observation:** $n=14/179$ total (7.8% of sample); valid ratings $n=7/139$ (5.0%); missing ratings $n=7/40$ (17.5%). Positive trust $n=5/93$ (5.4% of positive sample) citing badges, background checks, and feeling safe; negative trust $n=8/51$ (15.7% of negative sample) citing unauthorized washroom usage (`R0143`), video call surveillance into home (`R0109`), cheating/fraud claims (`R0136`, `R0144`), and used parts installed (`R0160`).
* **Confidence Level:** **High** — Direct frequency count from audited data.
* **Confidence Rationale:** Verified in `DESCRIPTIVE_ANALYSIS.md` Section 4.
* **Hypothesis Relationship:** Directly supports the post-booking domestic execution trust component of reformulated `H4` (**Two-Stage Trust Model**). Demonstrates that acute trust deficits occur post-booking inside the customer's private home ($n=8/14$ negative trust reviews). Retains the explicit boundary that review data reflects only transacting users and cannot evaluate pre-booking drop-off among prospective users who never booked; the pre-booking platform trust component is **not** disproven.
* **Competing Interpretation:** Trust is a latent baseline expectation that is rarely mentioned unless an acute, dramatic domestic boundary violation occurs.
* **Scope Limitation:** Sample descriptive frequency; represents rare, high-severity negative tail events.

---

### [E009] Rebooking-Related Theme Prevalence
* **Evidence Statement:** Explicit rebooking-related themes appear in only 3.4% ($n=6/179$) of the reviewed sample, split evenly between repeat usage satisfaction ($n=3$) and repeat booking friction ($n=3$).
* **Evidence Type:** `FACT` (Sample descriptive frequency)
* **Source ID:** `S001`, `S003` (`DESCRIPTIVE_ANALYSIS.md` Section 3.1 & 4 Theme 12)
* **Underlying Metric / Observation:** $n=6/179$ total (3.4% of sample); valid ratings $n=5/139$ (3.6%); 4-star $n=3/48$ (6.2%), 5-star $n=2/91$ (2.2%), missing ratings $n=1/40$ (2.5%). 
  * Positive repeat praise $n=3$ (`R0017`, `R0033`, `R0059`).
  * Repeat friction $n=3$ (prepaid package failure on rebooking `R0073`, 3 of 5 bookings cancelled by platform `R0101`, bot booking loops 4–5 times `R0176`).
* **Confidence Level:** **High** — Verified exact count across dataset.
* **Confidence Rationale:** Audited against all 179 rows.
* **Hypothesis Relationship:** 
  * *Supports existence of `H1` friction:* Demonstrates that repeat booking friction does occur for users attempting multiple transactions ($n=3$).
  * *Challenges dominance of `H1`:* Low absolute sample frequency ($3.4\%$) challenges the premise that rebooking UX friction is the primary or dominant customer pain point relative to quality (28.5%), pricing (25.7%), or cancellations (14.5%).
* **Competing Interpretation:** App store reviewers typically review a single recent transaction rather than longitudinal booking mechanics; rebooking intent is often latent.
* **Scope Limitation:** Sample descriptive frequency; does not measure actual platform repeat retention or rebooking rates.

---

### [E010] Consistency-Related Theme Prevalence
* **Evidence Statement:** Longitudinal consistency themes appear in 3.4% ($n=6/179$) of reviews in the sample, documenting both uniform high standards ($n=2$) and quality degradation or partner variance over time ($n=4$).
* **Evidence Type:** `FACT` (Sample descriptive frequency)
* **Source ID:** `S001`, `S003` (`DESCRIPTIVE_ANALYSIS.md` Section 3.1 & 4 Theme 13)
* **Underlying Metric / Observation:** $n=6/179$ total (3.4% of sample); valid ratings $n=4/139$ (2.9%); 5-star $n=3/91$ (3.3%), 4-star $n=1/48$ (2.1%), missing ratings $n=2/40$ (5.0%).
  * Positive uniformity mentions: $n=2$ (`R0017`, `R0040`).
  * Variance across professionals & degradation mentions: $n=4$ (comprising 3 mixed-sentiment reviews and 1 negative-sentiment review per `DESCRIPTIVE_ANALYSIS.md` Section 4: disconnect between pro and platform `R0074`, cleaning below standard `R0147`, service degrading over time `R0117`, personnel changed without consent `R0179`).
* **Confidence Level:** **High** — Verified count from descriptive analysis.
* **Confidence Rationale:** Documented in `DESCRIPTIVE_ANALYSIS.md` Section 4 Theme 13.
* **Hypothesis Relationship:** Consistent with `H2` (Service quality inconsistency). Directly documents quality variance and arbitrary partner changes across repeated bookings, supporting H2's premise; indirect on aggregate retention impact.
* **Competing Interpretation:** Consistency complaints require multi-booking history; reviewers with only one booking cannot evaluate longitudinal consistency.
* **Scope Limitation:** Sample descriptive frequency.

---

### [E011] AI Chatbot Deflection and Inaccessible Human Support
* **Evidence Statement:** Reviewers report being trapped in automated AI chatbot loops that offer repetitive canned responses, prevent escalation to human agents, and provide no telephone helpline when service failures or billing disputes occur.
* **Evidence Type:** `RESEARCH FINDING (community)`
* **Source ID:** `S001`, `S004` ([`QUALITATIVE_PATTERN_ANALYSIS.md`](qualitative_pattern_analysis.md) `PAT-01`)
* **Underlying Metric / Observation:** Supported by $n=11/179$ reviews (6.1% of sample, 21.6% of negative reviews). Rating distribution: 9 missing ratings (81.8%), 2 4-star ratings, 0 5-star ratings. Representative reviews:
  * `R0071` (Rating: 4.0): *"The AI support is NOT customer oriented, did not allow me to raise a support issue directly... extremely frustrating."*
  * `R0108` (Rating: `[UNAVAILABLE]`): *"ai help support is a waste of time... using the money with pack and not providing service."*
  * `R0116` (Rating: `[UNAVAILABLE]`): *"finally after ~10 hours it's connected to an agent... you people are a copy pest."*
  * `R0117` (Rating: `[UNAVAILABLE]`): *"Their service has started degrading by the day and their nonsensical AI customer support is full of repeated messages."*
  * `R0170` (Rating: `[UNAVAILABLE]`): *"I am searching for any helpline number or chat box but the company is acting so smart, they have not provided any customer support number."*
* **Confidence Level:** **High (Mechanistic Verification) / Negative-Skew Caveat** — Repeated independently across multiple categories with explicit descriptions of identical bot loop barriers; note that 9 of 11 reviews stem from the unrated Sheet 3 (`Newest`) extraction bug, which over-indexes on negative recent sentiment.
* **Confidence Rationale:** Grounded in 11 specific review records citing identical UX barriers.
* **Hypothesis Relationship:** Indirect / Amplifies `H2`. While not direct proof that service quality is inconsistent, bot deflection blocks dispute remediation when quality failures occur, exacerbating customer churn.
* **Source-Level Counter-Evidence / Contradicting Reviews:**
  * `R0010` (Rating: 5.0): *"Their customer care is prompt and they always call before arrival for confirmation."*
  * `R0085` (Rating: 4.0): *"Thank you, Urban Company, for the quick resolution... customer support addressed it promptly."*
* **Competing Interpretation:** Automated chatbot deflection successfully resolves 80%+ of routine inquiries (order status, invoice retrieval) but completely fails on high-stakes edge cases (damages, disputed refunds).
* **Scope Limitation:** Community review evidence; internal customer care resolution metrics remain an unmeasured gap (`GAP-002`).

---

### [E012] Asymmetric Cancellation Penalties on Platform-Side Delivery Failures
* **Evidence Statement:** Customers report being penalized with cancellation fees (typically ₹50) or forfeited prepaid packages even when the cancellation was caused by professional no-shows, worker refusals, or platform scheduling errors.
* **Evidence Type:** `RESEARCH FINDING (community)`
* **Source ID:** `S001`, `S004` (`QUALITATIVE_PATTERN_ANALYSIS.md` `PAT-02`)
* **Underlying Metric / Observation:** Supported by $n=5/179$ reviews (2.8% of sample, 19.2% of cancellation reviews). Rating distribution: 3 4-star, 2 missing ratings. Representative reviews:
  * `R0072` (Rating: 4.0): *"You then ask me to cancel that booking instead of letting me use it within the 1 month validity. Canceling means I lose money."*
  * `R0084` (Rating: 4.0): *"u cahrge us cancellation charges which was hidden. cancellation was due to some emergency and requested to reschedule."*
  * `R0104` (Rating: 4.0): *"had to cancel my original booking as I could not get my required slot and was charged cancellation fees."*
  * `R0115` (Rating: `[UNAVAILABLE]`): *"forced me to either reschedule or pay a ₹50 cancellation fee."*
  * `R0145` (Rating: `[UNAVAILABLE]`): *"I made a booking and the insta help said she won't come... I was being charged 50 more for cancellation while this wasn't even done from my end."*
* **Confidence Level:** **Medium (Prevalence in Sample) / High (Mechanistic Verification)** — The specific penalty mechanism and ₹50 fee are verified across independent records, but absolute sample frequency is small ($n=5$).
* **Confidence Rationale:** Verified against exact review quotes and ratings; official cancellation policy rules require secondary verification (`GAP-003`).
* **Hypothesis Relationship:** Symptom consistent with `H3` (Platform allocation rules). Documents customer-facing penalty enforcement on unfulfilled bookings; internal allocation and penalty algorithms require supply-side verification.
* **Source-Level Counter-Evidence / Contradicting Reviews:**
  * `R0001`, `R0008`, `R0033` (Rating: 5.0): Praise transparent, stress-free billing with zero hidden fees or unexpected charges.
* **Competing Interpretation:** The cancellation fee is an automated policy intended to compensate gig partners for dispatch transit, but platform logic fails to verify partner no-show status before applying the fine.
* **Scope Limitation:** Describes user perception in 5 sampled cases; official partner terms must be triangulated in Phase 2 (`GAP-003`).

---

### [E013] Insta Help Supply Fragility and Chronic Cancellation Cascades
* **Evidence Statement:** On-demand domestic services (Insta Help) suffer from acute supply instability, resulting in repeated partner no-shows, work refusals upon arrival, and automated cancellation cascades.
* **Evidence Type:** `RESEARCH FINDING (community)`
* **Source ID:** `S001`, `S004` (`QUALITATIVE_PATTERN_ANALYSIS.md` `PAT-03`)
* **Underlying Metric / Observation:** Supported by $n=11/179$ reviews (6.1% of dataset, 42.3% of all Insta Help reviews). Rating distribution: 8 missing ratings (72.7%), 2 5-star (ironic/contradictory), 1 4-star. Representative reviews:
  * `R0009` (Rating: 5.0 [Contradiction]): *"If the service cannot provide help within a reasonable time, why is it marketed as 'Insta Help'?"*
  * `R0108` (Rating: `[UNAVAILABLE]`): *"Even after your booking is confirmed they keep cancelling... not providing service."*
  * `R0126` (Rating: `[UNAVAILABLE]`): *"On both occasions, I booked Insta Help, but the person assigned to provide the service did not arrive at all."*
  * `R0136` (Rating: `[UNAVAILABLE]`): *"Instant helper visits and denies the work appointed for... All service men are LOOTERS here."*
  * `R0176` (Rating: `[UNAVAILABLE]`): *"They seem to use bot profiles to accept bookings, only to cancel when the actual time arrives. This has happened to me 4–5 times."*
* **Confidence Level:** **High (Within Category) / Negative-Skew Caveat** — Extreme statistical concentration in Insta Help ($n=11/26$); heavily drawn from unrated Sheet 3 ($n=8/11$).
* **Confidence Rationale:** Over 40% of reviews in this vertical report identical operational breakdowns.
* **Hypothesis Relationship:** Strong vertical-specific operational pattern consistent with on-demand supply stress. Direct evidence that dispatch fails in on-demand domestic chores ($42.3\%$ in Insta Help); treated as a category-specific operational breakdown and NOT classified as proven platform-wide marketplace allocation failure. `H3` requires secondary operational validation in Phase 2.
* **Source-Level Counter-Evidence / Contradicting Reviews:**
  * `R0076` (Rating: 4.0): Maid arrives and performs work, though minor timing extension friction is noted.
  * `R0152` (Rating: 5.0): *"good clean maids we got always."*
* **Competing Interpretation:** Low ticket sizes and high transit costs in Insta Help incentivize partners to reject assigned chores in favor of private offline domestic work.
* **Scope Limitation:** Specific to the Insta Help vertical; does not describe scheduled appliance or salon services.

---

### [E014] Post-Booking Cost Inflation and Hidden Surcharges
* **Evidence Statement:** Customers experience unexpected checkout price inflation through automated weekend surge pricing, platform fees, and on-site technician add-on demands, undermining Urban Company's standardized pricing proposition.
* **Evidence Type:** `RESEARCH FINDING (community)`
* **Source ID:** `S001`, `S004` (`QUALITATIVE_PATTERN_ANALYSIS.md` `PAT-04`)
* **Underlying Metric / Observation:** Supported by $n=13/179$ reviews (7.3% of total dataset, 28.3% of pricing reviews). Rating distribution: 9 4-star ratings, 4 missing ratings. Representative reviews:
  * `R0058` (Rating: 4.0): *"I was loaded ₹150 additionally for choosing from the available options by default with no explanation of why. It is unfair trade practice unless you bring clarity..."*
  * `R0060` (Rating: 4.0): *"The payment amount shown while confirming invoice and final payment is different... fix this bug."*
  * `R0073` (Rating: 4.0): *"even after you take a prepaid package they still keep asking you for extra money."*
  * `R0090` (Rating: 4.0): *"The technician completed the work in just 2 minutes, but I was charged ₹350... clearly overpriced for minor fix."*
  * `R0092` (Rating: 4.0): *"My only concern is the final bill, where the app fee (₹166) and GST (₹34) were added to a ₹1,055 service."*
  * `R0165` (Rating: `[UNAVAILABLE]`): *"booking a slot always end up on weekend with extra 200."*
* **Confidence Level:** **High** — Specific monetary line items cited across independent reviews.
* **Confidence Rationale:** Verified against exact numerical entries in `QUALITATIVE_PATTERN_ANALYSIS.md`.
* **Hypothesis Relationship:** None mapped directly to H1–H5. Identifies price inflation as an independent friction area competing with trust/rebooking.
* **Source-Level Counter-Evidence / Contradicting Reviews:**
  * `R0001`, `R0008`, `R0033`, `R0035` (Rating: 5.0): Explicitly praise "reasonable rates", "fair estimates", and "transparent pricing".
* **Competing Interpretation:** Platform fees and surge pricing are deliberate monetization levers that conflict with early-stage consumer expectations of free convenience.
* **Scope Limitation:** Sample descriptive finding.

---

### [E015] In-Home Privacy and Domestic Discretion Breaches
* **Evidence Statement:** Reviewers report severe violations of domestic boundaries during in-home service delivery, including unauthorized washroom use, invasive remote video monitoring, and socio-religious friction.
* **Evidence Type:** `RESEARCH FINDING (community)`
* **Source ID:** `S001`, `S004` (`QUALITATIVE_PATTERN_ANALYSIS.md` `PAT-05`)
* **Underlying Metric / Observation:** Supported by $n=4/179$ reviews (2.2% of dataset, 28.6% of trust reviews). Rating distribution: 4 missing ratings (all negative). Representative reviews:
  * `R0109` (Rating: `[UNAVAILABLE]`): *"someone was watching my home via a video call, which made me feel uncomfortable."*
  * `R0143` (Rating: `[UNAVAILABLE]`): *"I have had instances of them using my home washroom without my knowledge. It seems unsafe..."*
  * `R0164` (Rating: `[UNAVAILABLE]`): *"Workforce discrimination by their religious community, worst capitalist take ever."*
  * `R0179` (Rating: `[UNAVAILABLE]`): *"insta help now a days they are taking muslim aslo i don't think so this is not recommended in some family... have to be conscious."*
* **Confidence Level:** **Medium (Prevalence in Sample) / High (Phenomenon Existence & Verbatim Traceability)** — Grounded in explicit qualitative user accounts of domestic boundary violations; low absolute review volume ($n=4$), but acute brand and domestic safety risk.
* **Confidence Rationale:** Grounded in qualitative synthesis; represents critical qualitative tail risks.
* **Hypothesis Relationship:** Directly supports the post-booking domestic execution trust component of reformulated `H4` (**Two-Stage Trust Model**). Demonstrates that severe trust breaches occur post-booking inside the customer's private home. Explicitly retains the boundary that review data reflects only transacting customers and cannot evaluate pre-booking drop-off among non-bookers; the pre-booking platform trust component is **not** disproven.
* **Source-Level Counter-Evidence / Contradicting Reviews:**
  * `R0036`, `R0052`, `R0056` (Rating: 5.0): Highly praise worker background verification, skill certification, and feeling completely safe welcoming cleaners into their homes.
* **Competing Interpretation:** Video calls are intended as technician remote quality audits (praised in `R0048`) that alarm customers when miscommunicated; washroom use reflects lack of civic sanitation for mobile gig workers.
* **Scope Limitation:** Low sample size ($n=4$); describes acute tail risks rather than median user sentiment.

---

### [E016] Secondary Appliance Damage and Defective Repairs
* **Evidence Statement:** Maintenance visits in appliance and repair verticals occasionally trigger secondary electrical or mechanical damage, resulting in collateral property breakdown and protracted warranty claims.
* **Evidence Type:** `RESEARCH FINDING (community)`
* **Source ID:** `S001`, `S004` (`QUALITATIVE_PATTERN_ANALYSIS.md` `PAT-06`)
* **Underlying Metric / Observation:** Supported by $n=6/179$ reviews (3.4% of dataset, 11.8% of quality reviews). Rating distribution: 5 missing ratings, 1 4-star rating. Representative reviews:
  * `R0079` (Rating: 4.0): *"UC's 'Native' brand filter's electrical connectors are not compatible with Kent... safety hazard."*
  * `R0111` (Rating: `[UNAVAILABLE]`): *"Buy a new AC from the market and—courtesy of Urban Company—convert it into an old, broken-down, and unrepaired one."*
  * `R0118` (Rating: `[UNAVAILABLE]`): *"After AC cleaning, whole AC got Complaint and not working properly. NO Customer Care to contact."*
  * `R0127` (Rating: `[UNAVAILABLE]`): *"my fan switch stopped working and taps are broken after their cleaning and I have developed rashes after their pedicure."*
  * `R0160` (Rating: `[UNAVAILABLE]`): *"I paid for a new spare part, but an old/used part was installed... Very poor after-sales support."*
  * `R0166` (Rating: `[UNAVAILABLE]`): *"water will be dripping for next 24 hours (electrical equipment). Causing leakage... I'm still waiting for warranty claim after 15 days."*
* **Confidence Level:** **Medium (Prevalence across Platform) / High (Phenomenon Existence & Severity)** — Grounded in explicit physical damage reports, but small sample count ($n=6$) clustered almost entirely in Appliance Repair ($n=5/6$).
* **Confidence Rationale:** Verified across independent reviews in appliance categories.
* **Hypothesis Relationship:** Consistent with `H2` (Service quality inconsistency). Demonstrates that service quality inconsistency includes severe negative outcomes that destroy customer confidence; indirect on aggregate repeat-booking reduction.
* **Source-Level Counter-Evidence / Contradicting Reviews:**
  * `R0001`, `R0014`, `R0016`, `R0024`, `R0048` (Rating: 5.0): Describe flawless, long-lasting repairs where technicians swiftly diagnosed gas leaks, noise, and complex circuit issues.
* **Competing Interpretation:** Pre-existing appliance age and wear may cause fragile components to fail during cleaning, which customers attribute to technician negligence.
* **Scope Limitation:** Clustered primarily in Appliance Repair ($n=5/6$); not generalizable to salon or cleaning verticals.

---

### [E017] Partner Demeanor and Punctuality as Loyalty Anchor
* **Evidence Statement:** The primary driver of 5-star ratings and positive customer loyalty is partner interpersonal conduct: punctual arrival, polite manners, disciplined execution, and respectful behavior.
* **Evidence Type:** `RESEARCH FINDING (community)`
* **Source ID:** `S001`, `S004` (`QUALITATIVE_PATTERN_ANALYSIS.md` `PAT-07`)
* **Underlying Metric / Observation:** Supported by $n=15/179$ reviews in core cohort (8.4% of total sample; backed by 54 reviews across professional behavior theme, 30.2% of sample). Rating distribution: 100% 5-star ratings ($n=15/15$). Representative reviews:
  * `R0001` (Rating: 5.0): *"The technician arrived on time, quickly identified the issue, and repaired the machine professionally."*
  * `R0002` (Rating: 5.0): *"The electrician did a very good job. He demonstrated a positive attitude, good behaviour, and excellent work discipline."*
  * `R0003` (Rating: 5.0): *"Punctual and very polite behavior. Clean work done."*
  * `R0021` (Rating: 5.0): *"Very professional and well mannered. Did a clean job without creating any mess."*
  * `R0040` (Rating: 5.0): *"The professionals are punctual, well-trained, and courteous. Booking is always smooth."*
  * `R0055` (Rating: 5.0): *"Courteous behaviour and high level of expertise."*
* **Confidence Level:** **High** — Dominant positive signal across the entire 5-star review slice.
* **Confidence Rationale:** Verified against 15 specific 5-star reviews citing identical behavioral traits.
* **Hypothesis Relationship:** Consistent with `H2` (Inverse Signal). Confirms that customer satisfaction is highly sensitive to individual partner behavioral quality, supporting the premise that partner quality drives repeat intent; indirect on the negative mechanism of inconsistency-driven churn.
* **Source-Level Counter-Evidence / Contradicting Reviews:**
  * `R0099` (Rating: 4.0): *"Professionals should come as per scheduled time since we are working professionals... delay happened."*
  * `R0161` (Rating: `[UNAVAILABLE]`): *"Very unprofessional service. There are no one responsible."*
* **Competing Interpretation:** High praise for basic punctuality reflects historically poor reliability in the unorganized local market rather than exceptional platform innovation.
* **Scope Limitation:** Sample descriptive finding.

---

### [E018] Repeat-Booking Preference and Partner Reassignment Friction
* **Evidence Statement:** Repeat customers develop trust in specific individual service professionals and express frustration when the platform arbitrarily reassigns unfamiliar partners without user control or notification.
* **Evidence Type:** `RESEARCH FINDING (community)`
* **Source ID:** `S001`, `S004` (`QUALITATIVE_PATTERN_ANALYSIS.md` `PAT-08`)
* **Underlying Metric / Observation:** Supported by $n=7/179$ reviews (3.9% of sample, 50.0% of rebooking/consistency cohort). Rating distribution: 4 5-star, 2 4-star, 1 missing rating. Representative reviews:
  * `R0017` (Rating: 5.0): *"I have booked multiple services via them: mostly for haircuts (men and women)... My experience has been great each and every time."*
  * `R0033` (Rating: 5.0): *"i am using urban services regularly never disappointment."*
  * `R0059` (Rating: 4.0): Long-term regular customer docking 1 star because support access degraded.
  * `R0068` (Rating: 4.0): *"the app is convenient one stop... Shortlist and show only trusted top professionals."*
  * `R0152` (Rating: 5.0): *"good clean maids we got always."*
  * `R0179` (Rating: `[UNAVAILABLE]`): *"in some time they will change the person with out our knowledge once Booking is down they should take priority."*
* **Confidence Level:** **Medium** — Low absolute sample count ($n=7$), but delivers direct qualitative validation of customer desire for partner continuity and reassignment friction.
* **Confidence Rationale:** Grounded in specific review text articulating preference for familiar workers.
* **Hypothesis Relationship:** Consistent with `H1` (supports customer desire for repeat booking continuity and friction upon reassignment) and `H3` (symptom consistent with platform prioritizing liquidity over continuity); internal allocation rules remain an unobserved supply-side mechanism.
* **Source-Level Counter-Evidence / Contradicting Reviews:**
  * `R0013` (Rating: 5.0): Customer books across diverse categories seamlessly without expressing preference for individual workers.
* **Competing Interpretation:** Reassignment is dictated by geographic dispatch efficiency and partner availability rather than intentional platform hostility to continuity.
* **Scope Limitation:** Qualitative community signal; cannot evaluate platform-wide repeat booking rates without internal data (`GAP-001`).

---

### [E019] Decoupled Evaluation of Gig Partner vs. Corporate Platform
* **Evidence Statement:** Reviewers explicitly bifurcate their service evaluation: praising the individual human professional while penalizing or condemning Urban Company corporate policies, fees, rating pressure, and automated support.
* **Evidence Type:** `RESEARCH FINDING (community)`
* **Source ID:** `S001`, `S004` (`QUALITATIVE_PATTERN_ANALYSIS.md` `PAT-09`)
* **Underlying Metric / Observation:** Supported by $n=7/179$ reviews (3.9% of sample; 14.6% of all 4-star reviews, $n=7/48$). Rating distribution: 6 4-star ratings, 1 5-star rating. Representative reviews:
  * `R0074` (Rating: 4.0): *"the 4 star rating is for the professionals and not for UC. please maintain consistency."*
  * `R0091` (Rating: 4.0): *"customers should not be asked to give a 5-star rating before the work is completed. It is unethical."*
  * `R0092` (Rating: 4.0): Technician praised for good work, but rating docked over platform fee of ₹166.
  * `R0093` (Rating: 4.0): Rating docked 1 star from 5 to 4 because one service line was unsatisfactory while the technician was good.
  * `R0095` (Rating: 4.0): Praises technician service but expresses concern regarding injured worker welfare.
  * `R0147` (Rating: 5.0): *"full marks for the staff, but there is still some scope for improvement in meeting the company’s promised service standards."*
* **Confidence Level:** **Medium (Sample Prevalence) / High (Textual Evidence & Verbatim Clarity)** — Grounded in unmistakable, explicit user statements separating partner from platform; sample size is focused ($n=7$, 14.6% of 4-star reviews).
* **Confidence Rationale:** Direct verbatim quotations in 7 explicit review texts.
* **Hypothesis Relationship:** Indirect / Structural Context for `H1` and `H2`. Demonstrates that customer trust resides primarily with the individual professional, while the platform layer is perceived as introducing financial and operational friction; does not directly measure repeat-booking UX or aggregate quality consistency.
* **Source-Level Counter-Evidence / Contradicting Reviews:**
  * `R0136`, `R0144` (Rating: `[UNAVAILABLE]`): Conflates partner and platform into a single negative judgment (*"All service men are LOOTERS here"*, *"worst company... cheaters"*).
* **Competing Interpretation:** Customers sympathize with gig workers and avoid penalizing them with low star scores, directing their frustration toward corporate policies instead.
* **Scope Limitation:** Highly clustered in 4-star reviews ($n=6/7$); descriptive of this sample only.

---

## Task 6 — Human Product Walkthrough Evidence (S005, S006)

### A. Pre-Payment / Booking-Stage Transparency (E020 – E023)

### [E020] Service and Cart Displayed Price Consistency
* **Evidence Statement:** The Foam-jet service for 2 ACs was displayed in the service catalogue, service detail page, cart, and initial checkout screen at ₹1,098 (with a crossed-out prior price of ₹1,198 and a "₹100 saved" discount badge).
* **Evidence Type:** `FACT`
* **Source ID:** `S005` (pages 5, 8, 20, 23)
* **Underlying Metric / Observation:** Directly captured in screenshots across multiple consecutive screens in the booking flow on 18 Sep 2026.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S005`).
* **D004 Investigation Relationship:** Establishes the baseline reference price presented to the customer during discovery, cart review, and checkout address/time selection.
* **Scope Limitation:** Directly observed on iOS app in Mumbai Central on 18 Sep 2026 for AC service category; does not capture dynamic pricing rules in other cities, times, or service categories.

---

### [E021] Payment-Screen Displayed Payable Amount
* **Evidence Statement:** The payment screen header subtitle displayed "Amount to pay: ₹1,197" for the AC service booking.
* **Evidence Type:** `FACT`
* **Source ID:** `S005` (pages 24, 26)
* **Underlying Metric / Observation:** Directly captured on the payment method selection screen.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S005`).
* **D004 Investigation Relationship:** Establishes the final payable amount requested from the customer at the payment gateway stage.
* **Scope Limitation:** Directly observed on iOS app in Mumbai Central on 18 Sep 2026 for a single booking attempt.

---

### [E022] Displayed Price Difference Across Booking Stages
* **Evidence Statement:** The walkthrough observed a ₹99 difference between the service/cart amount (₹1,098) shown earlier in the flow and the subsequent payment-screen amount (₹1,197). The captured screens do not establish the cause or composition of the difference.
* **Evidence Type:** `FACT`
* **Source ID:** `S005` (pages 23, 24, 26)
* **Underlying Metric / Observation:** Exact numerical difference: ₹1,197 - ₹1,098 = ₹99. The captured payment screens display the total amount payable but do not show an itemized line-item breakdown explaining the ₹99 increment.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Directly observed across consecutive screens in `S005`.
* **D004 Investigation Relationship:** Directly relevant to price transparency across booking and payment stages. The walkthrough observed a ₹99 difference between the amount displayed during checkout and the subsequent payment-screen amount, without a visible itemized explanation on the captured payment screen. Direct post-booking price revision was not observed in the walkthrough. Post-booking/on-site pricing mechanics were observed only through the documented quote-and-approval policy for variable work such as gas refilling.
* **Competing Interpretation:** The ₹99 difference may represent a platform fee, convenience fee, taxes (GST), or a surge charge calculated at checkout that was not captured in the screenshot or collapsed behind a details accordion.
* **Scope Limitation:** This establishes a displayed amount difference across booking stages. It does not establish the cause of the difference.

---

### [E023] Checkout Cancellation Policy and Legal Terms Reference
* **Evidence Statement:** The checkout screen displayed legal agreement text stating: "By proceeding, you agree to our T&C, Privacy and Cancellation Policy."
* **Evidence Type:** `FACT`
* **Source ID:** `S005` (page 23)
* **Underlying Metric / Observation:** Directly visible below the address selection card prior to initiating payment.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S005`).
* **D004 Investigation Relationship:** Relevant to cancellation fairness investigation; establishes that the cancellation policy is referenced before payment commitment, though specific fee rules are not presented inline on the checkout card itself.
* **Scope Limitation:** Observed on checkout screen of iOS walkthrough; does not establish whether customers click, read, or understand the referenced policy.

---

### B. Post-Booking / On-Site Price Mechanics (E024 – E026)

### [E024] Service Detail Guidance on Quote Verification
* **Evidence Statement:** The service detail page FAQ explicitly includes the question: "How can I verify the quote shared?"
* **Evidence Type:** `FACT`
* **Source ID:** `S005` (page 14)
* **Underlying Metric / Observation:** Observed under the FAQ accordion section of the AC Foam-jet service detail screen.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S005`).
* **D004 Investigation Relationship:** Relevant to post-booking/on-site pricing mechanics. The product includes dedicated FAQ entries covering quote verification and extra charges.
* **Scope Limitation:** Observed in AC repair/service vertical; does not establish customer awareness, comprehension, or technician on-site quoting compliance.

---

### [E025] Service Detail Guidance on Extra Charges
* **Evidence Statement:** The service detail page FAQ explicitly includes the question: "What if I am being charged extra?"
* **Evidence Type:** `FACT`
* **Source ID:** `S005` (page 14)
* **Underlying Metric / Observation:** Observed under the FAQ accordion section of the AC Foam-jet service detail screen.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S005`).
* **D004 Investigation Relationship:** Relevant to post-booking/on-site pricing mechanics. The product includes dedicated FAQ entries covering quote verification and extra charges.
* **Scope Limitation:** Establishes presence of FAQ in UI; does not measure frequency of extra charges or operational effectiveness of dispute resolution.

---

### [E026] AC Gas-Refill Quoting and Approval Policy
* **Evidence Statement:** The AC service description states that if gas refilling is required, Urban Company will provide a quote and refill only after customer approval.
* **Evidence Type:** `FACT`
* **Source ID:** `S005` (page 11)
* **Underlying Metric / Observation:** Observed in Step 4 of the 5-step service process walkthrough ("Gas refilling (if required): We'll provide a quote and only refill after your approval").
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S005`).
* **D004 Investigation Relationship:** Relevant to post-booking/on-site pricing mechanics. The service description states that gas refilling, if required, requires a quote and customer approval.
* **Scope Limitation:** Policy disclosure in UI; does not observe technician on-site compliance or operational enforcement.

---

### C. Cancellation Policy (E027 – E028)

### [E027] Assignment-Based Cancellation Fee Trigger Policy
* **Evidence Statement:** The cancellation policy states that professionals block time for jobs, cancellations can result in lost revenue for professionals, and cancellation fees apply once a professional has been assigned.
* **Evidence Type:** `FACT`
* **Source ID:** `S006` (page 1)
* **Underlying Metric / Observation:** Observed in the in-cart cancellation policy modal.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S006`).
* **D004 Investigation Relationship:** Directly relevant to cancellation fairness; explains the platform's stated economic rationale (partner time-blocking) and trigger condition (partner assignment) for charging fees.
* **Scope Limitation:** The walkthrough does not establish the exact fee amount, fee scale, or whether rules vary by service vertical.

---

### [E028] Fee-Free Cancellation Grace Period Policy
* **Evidence Statement:** The cancellation policy states that customers have some time after placing a request to cancel without incurring a fee.
* **Evidence Type:** `FACT`
* **Source ID:** `S006` (page 1)
* **Underlying Metric / Observation:** Text states: "You can cancel for free some time after placing the request... without incurring a fees."
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S006`).
* **D004 Investigation Relationship:** Relevant to cancellation fairness; confirms the stated existence of a grace period.
* **Scope Limitation:** The exact time window (in minutes or hours) is not quantified in the captured modal text.

---

### D. Post-Service Recovery / Warranty (E033 – E034)

### [E033] UC Warranty Covered Service Categories
* **Evidence Statement:** The UC Warranty documentation specifies coverage for appliance repairs (AC, RO, washing machine repairs, etc.), pest control services, and painting services.
* **Evidence Type:** `FACT`
* **Source ID:** `S006` (page 6)
* **Underlying Metric / Observation:** Observed under the "Claim Warranty" help article.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S006`).
* **D004 Investigation Relationship:** Relevant to post-service quality assurance and secondary defect recovery (`E016`).
* **Scope Limitation:** Informational policy statement; does not measure warranty claim approval rates or claim processing times.

---

### [E034] UC Warranty Explicit Exclusions Policy
* **Evidence Statement:** The UC Warranty documentation explicitly excludes new issues occurring post-service and any item or service not mentioned on the invoice.
* **Evidence Type:** `FACT`
* **Source ID:** `S006` (page 6)
* **Underlying Metric / Observation:** Observed under the "Claim Warranty" help article ("What is not covered under warranty?").
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S006`).
* **D004 Investigation Relationship:** The walkthrough observed that any item or service not mentioned on the invoice is excluded from the stated warranty coverage. This may create a recovery boundary for work performed or charges incurred without being reflected on the platform invoice.
* **Scope Limitation:** Stated exclusion policy; does not observe dispute adjudication between customer and technician claims.

---

### E. Account Architecture & Observability Boundaries (E029 – E032, E035 – E037)

### [E029] Help & Support Primary Profile Navigation Access
* **Evidence Statement:** The user profile tab contains a prominent top-level navigation entry for "Help & support".
* **Evidence Type:** `FACT`
* **Source ID:** `S005` (page 27), `S006` (page 2)
* **Underlying Metric / Observation:** Displayed as a primary menu item with an icon in the Account screen.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S005`, `S006`).
* **D004 Investigation Relationship:** Establishes baseline discoverability of help channels from the main profile interface.
* **Scope Limitation:** Observed pre-booking on an account with zero active orders; live order escalation path was not observable.

---

### [E030] Help Center Information Architecture Categories
* **Evidence Statement:** The Help Center interface presents top-level categories including "Account", "Getting started with UC", "Payment & UC Credits", "UC Plus Membership", "UC Safety", and "Claim Warranty".
* **Evidence Type:** `FACT`
* **Source ID:** `S006` (page 3)
* **Underlying Metric / Observation:** Directly visible on the main Help & support landing screen.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S006`).
* **D004 Investigation Relationship:** Confirms that payment disputes, safety concerns, and warranty claims have designated informational categories in the support hierarchy.
* **Scope Limitation:** Establishes informational category architecture; does not observe ticketing, live chat, or human escalation workflows.

---

### [E031] Professional Background Verification Policy Disclosure
* **Evidence Statement:** The UC Safety article states that Urban Company conducts background verification on all service professionals.
* **Evidence Type:** `FACT`
* **Source ID:** `S006` (page 4)
* **Underlying Metric / Observation:** Observed under the "Safety at Urban Company" help article.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S006`).
* **D004 Investigation Relationship:** Relevant to platform trust (`H4`); confirms platform's stated commitment to pre-vetting service personnel.
* **Scope Limitation:** Stated policy disclosure only; does not observe operational vetting rigor or field enforcement.

---

### [E032] In-App SOS Emergency Button Disclosure
* **Evidence Statement:** The UC Safety article states that an SOS button is available in the app to provide critical emergency support for customers and professionals.
* **Evidence Type:** `FACT`
* **Source ID:** `S006` (page 4)
* **Underlying Metric / Observation:** Observed under the "Safety at Urban Company" help article.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S006`).
* **D004 Investigation Relationship:** Relevant to in-home domestic safety and customer trust (`H4`).
* **Scope Limitation:** Establishes stated feature existence in policy documentation; SOS button placement and response handling during active bookings were not observed.

---

### [E035] Profile Navigation Entry for "My Bookings"
* **Evidence Statement:** The user profile contains a dedicated "My Bookings" entry.
* **Evidence Type:** `FACT`
* **Source ID:** `S005` (page 27), `S006` (page 2)
* **Underlying Metric / Observation:** Visible as a primary section header/navigation row in the Account profile tab.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S005`, `S006`).
* **D004 Investigation Relationship:** Confirms presence of an order management hub in the product navigation.
* **Scope Limitation:** Navigational presence only.

---

### [E036] Walkthrough Account Historical Bookings State
* **Evidence Statement:** Opening "My Bookings" on the test account displayed an empty state ("No bookings yet").
* **Evidence Type:** `FACT`
* **Source ID:** `S005` (page 28)
* **Underlying Metric / Observation:** Empty state screen displaying illustration and message that no past or ongoing bookings exist.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Direct visual observation from firsthand iOS product walkthrough screenshots (`S005`).
* **D004 Investigation Relationship:** Confirms that the walkthrough account had no prior booking history.
* **Scope Limitation:** Specific to the test account used for the walkthrough.

---

### [E037] Rebooking Flow Observability Constraint
* **Evidence Statement:** Rebooking was not observable because the test account had no historical bookings.
* **Evidence Type:** `FACT`
* **Source ID:** `S005` (page 28)
* **Underlying Metric / Observation:** Absence of historical booking records prevented rendering or testing any "Book Again", repeat-pro, or historical rebooking workflows.
* **Confidence Level:** **High (Direct Firsthand Product Observation)**
* **Confidence Rationale:** Documented consequence of empty state in `S005` page 28.
* **D004 Investigation Relationship:** Confirms that `GAP-004` (rebooking feature status) remains unobserved on this account rather than non-existent in the app.
* **Scope Limitation:** Does NOT imply or establish that Urban Company lacks a rebooking feature; indicates only that rebooking was unobservable in this specific test state.

---

## Evidence Count by Hypothesis

Hypotheses H1–H5 are formally defined in [`08_problem_discovery.md`](../01_problem_discovery_review_mining.md) (lines 32–156). Review evidence mappings reflect customer sentiment and perceived friction; they do not constitute direct verification of platform-side algorithms or macro business metrics:

| Hypothesis | Description | Supporting / Consistent Evidence IDs | Contradicting / Challenging Evidence IDs | Net Assessment in Current Stage |
|---|---|---|---|---|
| **H1** | Repeat-booking friction exists in the UX | `E006` (indirect App/UX), `E009` (repeat friction $n=3$), `E018` (reassignment friction $n=7$), `E019` (structural context), `E035` (My Bookings exists), `E037` (rebooking unobserved) | `E009` (low volume in sample pushes against dominance/primacy) | **Partially Supported (Qualitative Signal)**: Reassignment friction and desire for known partners exist for repeat bookers, but explicit rebooking complaints are rare (3.4% of sample) compared to pricing and support. Walkthrough confirms My Bookings hub exists (`E035`), but rebooking flow was unobservable on new account (`E037`). |
| **H2** | Service quality inconsistency reduces repeat booking | `E003` (salience), `E007` (inverse conduct signal), `E010` (variance), `E011` (support amplification), `E016` (severe defects), `E017` (inverse conduct signal), `E019` (structural context), `E033` (warranty coverage), `E034` (warranty exclusions) | None | **Directionally Supported (Premise & Salience Supported; Retention Impact Indirect)**: Quality and conduct are salient (28.5% and 30.2%) and quality variance/collateral damage is documented, but customer reviews cannot measure aggregate repeat-booking reduction. Walkthrough confirms warranty coverage exists (`E033`) but explicitly excludes uninvoiced items (`E034`). |
| **H3** | Continuity constrained by platform allocation rules | `E005` (cancellations), `E012` (penalties), `E013` (Insta Help fragility), `E018` (reassignment friction), `E027` (assignment cancellation fee trigger), `E028` (fee-free period) | None | **Partially Supported (Symptom-side Only)**: Review evidence confirms customer-facing symptoms (forced cancellations, partner reassignments, automated penalties). Walkthrough confirms cancellation fees are triggered by professional assignment (`E027`) and that a fee-free window exists (`E028`). Internal allocation algorithms require secondary operational triangulation. |
| **H4** | Two-Stage Trust Model: Pre-Booking Platform Trust vs. Post-Booking Domestic/Service-Execution Trust | `E008` (domestic trust themes), `E015` (in-home boundary breaches), `E016` (collateral damage), `E031` (background verification disclosure), `E032` (SOS button disclosure) | None (pre-booking platform trust unassessed in reviews, not disproven) | **Reformulated / Partially Supported**: Acute trust breaches occur post-booking inside the domestic space (washroom use, video calls, collateral damage). Walkthrough shows platform actively communicates pre-booking trust anchors (background verification in `E031`, SOS button in `E032`). |
| **H5** | Continuity creates supply-side tensions | None (in customer review dataset) | None | **Unassessed via Customer Reviews**: Customer reviews provide zero visibility into supply-side economics or partner allocation incentives; requires Phase 2 operational/industry research. |

---

## Evidence Count by Type

| Evidence Type | Count | Entries Included | Primary Sources Cited |
|---|:---:|---|---|
| `FACT` | 38 | `E001` – `E010`, `E020` – `E038`, `E040` – `E043`, `E045`, `E046a`, `E046b`, `E049`, `E054` | S001–S006, S009, S010, S012, S013, S014, S016, S018, S020, S021 |
| `RESEARCH FINDING (community)` | 10 | `E011` – `E019`, `E044` | S001, S004, S015, S019 |
| `COMPANY CLAIM (attributed)` | 7 | `E039`, `E047`, `E048`, `E050`, `E052`, `E053`, `E055` | S007, S008, S011 |
| `ANALYST SYNTHESIS` | 2 | `E051`, `E056` | Unregistered |
| `ASSUMPTION` | 0 | Tracked in `06_assumption_log.md` | — |
| `HYPOTHESIS` | 0 | Tracked in `08_problem_discovery.md` | — |
| `ESTIMATE` | 0 | Reserved for Phase 3/4 Modeling | — |
| **GAP-008** | **Lack of Direct Primary Interview Validation** | `RESEARCH LIMITATION` | None | Low | DOES NOT ADDRESS | Methodological Gap |
| **Total Evidence Entries** | **57** | `E001` – `E056` | All entries traceable |

---

## Pattern Log

Synthesized from [`QUALITATIVE_PATTERN_ANALYSIS.md`](qualitative_pattern_analysis.md) and grounded directly in evidence entries `E001`–`E019`:

| Pattern ID | Pattern Name | Supporting Evidence IDs | Contradicting Evidence / Reviews | Hypotheses Touched | Confidence | Competing Interpretation | Scope Limitation |
|---|---|---|---|---|---|---|---|
| **PAT-01** | AI Chatbot Deflection Wall & Inaccessible Human Support | `E006`, `E011` ($n=11$) | `R0010`, `R0085` (praise prompt care) | H2 (indirect amplification) | High (mechanism) / Caveat on unrated skew | Deflection succeeds for routine tasks but fails on complex edge cases | Review-mined cohort; internal resolution rates unknown (`GAP-002`) |
| **PAT-02** | Asymmetric Cancellation Penalties on Platform Failures | `E005`, `E012` ($n=5$) | `R0001`, `R0008`, `R0033` (transparent billing) | H3 (symptom-side) | Medium (prevalence) / High (mechanism) | Fee intended to compensate partner transit, but logic fails on partner no-shows | 5 review instances; official policy to be triangulated in Phase 2 |
| **PAT-03** | Insta Help Supply Fragility & Chronic Cancellation Cascades | `E005`, `E013` ($n=11$) | `R0076`, `R0152` (maids arrived clean) | H3 (symptom-side) | High (within vertical) | Low partner margin leads workers to prioritize offline full-day contracts | Confined to on-demand domestic chores; not seen in salon/appliance |
| **PAT-04** | Post-Booking Cost Inflation & Hidden Surcharges | `E004`, `E014` ($n=13$) | `R0001`, `R0008`, `R0033`, `R0035` (praise fair pricing) | None | High | Intentional platform monetization fees (platform fee, weekend surge) | Sample descriptive finding |
| **PAT-05** | In-Home Privacy & Domestic Discretion Breaches | `E008`, `E015` ($n=4$) | `R0036`, `R0052`, `R0056` (feel completely safe) | H4 (supports post-booking domestic trust) | Medium (prevalence) / High (existence) | Remote diagnostic video calls miscommunicated; washroom use reflects lack of facilities | Low sample size ($n=4$); describes rare, acute tail risks |
| **PAT-06** | Secondary Appliance Damage & Defective Repairs | `E003`, `E016` ($n=6$) | `R0001`, `R0014`, `R0016`, `R0024`, `R0048` (flawless repairs) | H2 (consistent with defect severity) | Medium (prevalence) / High (existence) | Pre-existing appliance corrosion fails during chemical washing | Clustered in Appliance Repair ($n=5/6$) |
| **PAT-07** | Partner Demeanor & Punctuality as Brand Loyalty Anchor | `E007`, `E017` ($n=15$) | `R0099`, `R0161` (delayed arrival, unprofessional) | H2 (inverse signal) | High | Low offline industry baseline makes basic punctuality feel delightful | Sample descriptive finding |
| **PAT-08** | Repeat-Booking Preference & Partner Reassignment Friction | `E009`, `E010`, `E018` ($n=7$) | `R0013` (books across categories seamlessly) | H1, H3 (consistent with customer friction) | Medium | Reassignment optimizes city-wide dispatch liquidity and prevents disintermediation | Low absolute sample count ($n=7$) |
| **PAT-09** | Decoupled Evaluation of Gig Partner vs. Corporate Platform | `E010`, `E019` ($n=7$) | `R0136`, `R0144` (conflate worker with company) | H1, H2 (structural context) | Medium (prevalence) / High (verbatim text) | Customers sympathize with gig workers and dock ratings for corporate fees | Clustered in 4-star reviews ($n=6/7$) |
| **PAT-10** | Local & Competitor Substitution as Churn Workaround | `E004`, `E014`, `R0070`, `R0113`, `R0145`, `R0163` ($n=4$) | `R0063` (UC preferred over local vendors) | H2 (indirect) | Medium | Low switching friction in urban home services allows rapid return to offline mechanics | Low sample frequency ($n=4$); requires market triangulation |

---

## Contradictions Log

Record opposing evidence pairs without prematurely resolving them:

| Contradiction ID | Positive Signal | Negative Signal | Supporting Evidence IDs | Possible Explanations | What Cannot Yet Be Concluded | Further Research Needed |
|---|---|---|---|---|---|---|
| **CON-001** | **Safety & Background Verification Praise:** Users praise feeling completely safe welcoming verified workers into their homes (`R0036`, `R0052`, `R0056`). | **Acute Domestic Sanctuary Breaches:** Users report unannounced washroom usage (`R0143`), video call surveillance (`R0109`), and theft accusations (`R0136`). | `E008`, `E015`, `E017` | Standard vetting handles baseline identity checks, but in-home behavioral etiquette and remote diagnostic communication break down on edge cases. | Cannot conclude whether Urban Company's background verification is failing or whether complaints represent isolated partner conduct failures. | Review official Urban Company safety protocols and technician video call policies in Phase 2. |
| **CON-002** | **Repeat Booking Satisfaction:** Long-term customers report multi-year satisfaction with zero disappointments across regular haircuts and services (`R0017`, `R0033`, `R0059`). | **Partner Reassignment Friction & Package Failure:** Users report that platform arbitrarily changes assigned personnel (`R0179`) and prepaid packages fail on subsequent bookings (`R0073`). | `E009`, `E010`, `E018` | Repeat satisfaction is high when service quality is uniform, but friction arises when customers specifically desire the same individual professional. | Cannot conclude whether Urban Company lacks a preferred-pro feature or whether customers simply do not discover it (`GAP-004`). | Conduct hands-on product walkthrough of rebooking flow in Task 6. |
| **CON-003** | **Transparent & Fair Pricing Praise:** Multiple 5-star reviews praise reasonable rates, transparent estimates, and good value for money (`R0001`, `R0008`, `R0033`, `R0035`). | **Hidden Surcharges & Cancellation Fines:** Users cite default weekend surge (₹200), checkout platform fees (₹166), and unfair cancellation charges (₹50) on unfulfilled jobs (`R0058`, `R0092`, `R0145`). | `E004`, `E012`, `E014` | Baseline service menu prices are competitive and clear, but checkout add-on fee stacking creates perceived bait-and-switch friction. | Cannot conclude whether fee stacking has increased churn across the entire user base without financial data. | Triangulate Urban Company take-rate and fee policy changes via business press in Task 7. |
| **CON-004** | **Prompt Customer Care Praise:** 5-star reviews note prompt customer care resolution and proactive pre-arrival confirmation calls (`R0010`, `R0085`). | **Rigid AI Chatbot Deflection Loop:** Users report that AI support gives repeated unhelpful canned responses and completely blocks access to human agents (`R0071`, `R0116`, `R0170`). | `E006`, `E011` | Pre-booking communication and automated scheduling run smoothly, but post-service dispute escalation channels are heavily gated to reduce support overhead. | Cannot conclude whether human support is completely eliminated or only hidden behind a multi-step deflection maze. | Inspect current in-app support ticketing flow during product walkthrough in Task 6. |

---

## Methodological Audit & Evidence Boundaries

1. **Zero-Fabrication Audit:** Every evidence entry (`E001`–`E019`), pattern (`PAT-01`–`PAT-10`), and contradiction (`CON-001`–`CON-004`) traces directly to audited project files (`PM01_Urban_Company_Cleaned.xlsx`, `DESCRIPTIVE_ANALYSIS.md`, `QUALITATIVE_PATTERN_ANALYSIS.md`). Zero synthetic ratings, quotes, or metrics have been introduced.
2. **Conservative Hypothesis Calibration:** Hypotheses H1–H5 are formally defined in `08_problem_discovery.md`. Mappings are explicitly labeled as *consistent with*, *indirect*, *symptom-side*, or *inverse signal* to prevent conflating customer-perceived sentiment with verified platform algorithms or macro retention impact. `H5` remains unmapped in this matrix because customer reviews provide zero visibility into supply-side economics.
3. **Competing Interpretations Present:** Every non-trivial entry records plausible alternative operational, behavioral, or algorithmic explanations.
4. **Boundary Reminder for Downstream Tasks:** The 19 evidence entries describe this 179-review dataset only. They provide grounded qualitative hypotheses to guide Stage 2 triangulation and Stage 3 analysis, not definitive platform-wide truths.
5. **Parallel Problem Scope for Phase 2 Research:** Based on human review, Phase 2 research scope is broadened to investigate four parallel friction tracks without declaring any single problem as final:
   - *Track A: Trust & Repeat-Booking Friction* (relationship continuity vs. algorithm liquidity)
   - *Track B: Post-Service Failure and Recovery* (AI chatbot deflection, absence of human escalation, warranty resolution)
   - *Track C: Pricing Transparency & Fee Stacking* (checkout platform fees, surge pricing, unexpected on-site add-ons)
   - *Track D: Cancellation & Fulfillment Reliability* (on-demand Insta Help supply fragility, partner no-shows, cancellation fines)
   The purpose is to determine which problem is best supported after multi-source triangulation (product walkthrough, financial teardown, secondary industry research) in Phase 2.

---

## DeepSeek Audit Verification & Calibration Log

This log records the item-by-item verification of the independent DeepSeek audit against primary project source records:

| Audit Item | DeepSeek Criticism | Source Verification Determination | Action Taken in Matrix |
|---|---|---|---|
| **H1–H5 Availability** | Claimed H1–H5 definitions were not provided in source files | **REJECTED** — Factually incorrect. `08_problem_discovery.md` lines 32–156 explicitly defines H1 through H5, including rationales, test criteria, and invalidation rules. | Retained formal anchorage to `08_problem_discovery.md`, while adding explicit labels that review mappings are provisional/symptom-level. |
| **E003 Denominators** | $n=31/51$ positive workmanship is denominator-ambiguous | **VALID / ACCEPTED** — `DESCRIPTIVE_ANALYSIS.md` reports $31/93$ positive sentiment and $14/51$ negative sentiment. | Disambiguated both denominators: $31/51$ (60.8%) of quality reviews; $31/93$ (33.3%) of all positive reviews in sample. |
| **E004 Denominators** | Positive pricing $n=17$ lacks denominator | **VALID / ACCEPTED** — `DESCRIPTIVE_ANALYSIS.md` Theme 15 reports $n=17/93$ positive and $n=46$ total pricing. | Explicitly added both: $17/46$ (37.0% of pricing reviews) and $17/93$ (18.3% of positive reviews). |
| **E005 Denominators** | Insta Help $n=11/26$ (42.3%) is ambiguous | **VALID / ACCEPTED** — Coincidental equality: total Insta Help reviews = 26; total cancellation reviews = 26. | Explicitly split and labeled both denominators: $11/26$ (42.3%) of Insta Help reviews, and $11/26$ (42.3%) of cancellation reviews. |
| **E010 Sentiment** | Matrix called $n=4$ "negative variance/degradation"; source is mixed/negative | **VALID / ACCEPTED** — `DESCRIPTIVE_ANALYSIS.md` Theme 13 has 3 mixed and 1 negative reviews for variance. | Corrected wording to "variance/degradation mentions $n=4$ (3 mixed sentiment, 1 negative sentiment)." |
| **E012 Confidence** | High confidence with $n=5$ is aggressive | **PARTIALLY ACCEPTED** — Mechanism is verified, but sample count is small. | Calibrated to **Medium (Prevalence in Sample) / High (Mechanistic Verification)**. Added counter-evidence. |
| **E016 Confidence** | High confidence with $n=6$ clustered in Appliance Repair | **PARTIALLY ACCEPTED** — Acute damage verified, but narrow vertical concentration. | Calibrated to **Medium (Prevalence across Platform) / High (Phenomenon Existence & Severity)**. |
| **E019 Confidence** | High confidence with $n=7$ clustered in 4-star is debatable | **PARTIALLY ACCEPTED** — Supported by verbatim text, but focused behavioral cohort. | Calibrated to **Medium (Sample Prevalence) / High (Textual Evidence & Verbatim Clarity)**. |
| **H2 Mapping Rigor** | Broad quality/conduct prevalence mapped to H2 without proof of retention impact | **VALID / ACCEPTED** — Customer reviews show salience, not macro churn causality. | Relabeled E003, E007, E010, E011, E016, E017, E019 as indirect / consistent-with / inverse signal. Downgraded H2 net assessment from "Strongly Supported" to "Directionally Supported (Premise & Salience Supported; Retention Impact Indirect)". |
| **H3 Mapping Rigor** | Cancellations/reassignment mapped to H3 infer allocation rules from customer perception | **VALID / ACCEPTED** — Customers observe symptoms, not internal algorithms. | Relabeled E005, E012, E013, E018 as symptom-side evidence consistent with H3; noted internal rules require secondary validation. |
| **H4 Mapping Rigor** | Post-service breaches do not disprove pre-booking deficits | **VALID / ACCEPTED** — Sample of existing bookers cannot measure non-user hesitation. | Refined wording: challenges exclusive pre-booking framing of H4, but does not disprove pre-booking hesitation for non-users. |
| **E009 Interpretation** | Low rebooking volume contradicts dominance, not existence | **VALID / ACCEPTED** — Low sample frequency ($3.4\%$) challenges primacy, while $n=3$ confirms friction exists. | Explicitly split into: supports existence of friction ($n=3$); challenges dominance/primacy ($3.4\%$). |
| **Omitted Counter-Evidence** | Detailed qualitative records lacked source-level contradicting reviews | **VALID / ACCEPTED** — `QUALITATIVE_PATTERN_ANALYSIS.md` contained specific contradicting reviews in PAT sections. | Added dedicated `Source-Level Counter-Evidence / Contradicting Reviews` line to every qualitative entry E011–E019. |
| **Negative Skew Caveats** | Missing-rating extraction bug created negative sentiment bias in Sheet 3 | **VALID / ACCEPTED** — E011, E013, E014, E015 draw heavily from Sheet 3 unrated reviews. | Added explicit negative-skew caveats to confidence rationales for affected entries. |
| **Sample-Only Language** | Ensure every percentage states sample-only | **VALID / ACCEPTED** — Must prevent population generalization. | Audited and enforced explicit "sample-only" / "reviewed sample" phrasing throughout matrix. |

---

## Task 7 — Triangulation Research & Financial Context (S007–S022)

### F. Macro Context & Market Baselines (E038, E043–E045, E054, E056)

### [E038] Indian Gig Workforce Macro Projections
* **Evidence Statement:** The Indian gig workforce is projected by institutional sources to expand from 7.7 million (2020–2021) to 23.5 million by the end of the decade.
* **Evidence Type:** `FACT`
* **Source ID:** `S020`, `S021` (NITI Aayog / Economic Survey 2023-2024)
* **Confidence Level:** **High** — Sourced from institutional macro projections.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS** (Establishes broader market size only).
* **Scope Limitation:** Macro estimate; provides no specific insight into Urban Company's market share or operational friction.

### [E043] Analogue Competitor: Thumbtack Lead-Gen Model
* **Evidence Statement:** Thumbtack operates primarily as a lead-generation platform utilizing custom estimates and competitive professional bidding rather than standardized rate cards.
* **Evidence Type:** `FACT`
* **Source ID:** `S018` (Thumbtack Terms of Use)
* **Confidence Level:** **High** — Confirmed by platform's official ToS.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS** (Provides architectural analogue for comparison).
* **Scope Limitation:** Different geographic market and platform architecture.

### [E044] Analogue Competitor: TaskRabbit Trust & Support Fee Friction
* **Evidence Statement:** Reddit discussions allege substantial customer markup from TaskRabbit's Trust & Support Fee (e.g., 30-40% markup claims).
* **Evidence Type:** `RESEARCH FINDING (community)`
* **Source ID:** `S015`, `S019` (TaskRabbit Policies, Reddit Forums)
* **Confidence Level:** **Low** — Validates existence of intense consumer anger toward percentage-based fees, though exact 40% figures from Reddit lack statistical rigor.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS / CONTEXTUAL ANALOGUE** (Shows a competing platform whose post-booking pricing is arguably worse than UC's; comparative context).
* **Scope Limitation:** Subjective community perception on a competitor platform.

### [E045] Analogue Competitor: TaskRabbit Expense Caps
* **Evidence Statement:** TaskRabbit caps material expense reimbursements at $100 ($150 for dump fees) and explicitly forbids expensing operational logistics like parking and fuel.
* **Evidence Type:** `FACT`
* **Source ID:** `S016` (TaskRabbit Expense Policy)
* **Confidence Level:** **High** — Confirmed by platform's official policy.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS** (Highlights how competitor platforms cap material costs to limit post-booking price escalation).
* **Scope Limitation:** Policy applies to TaskRabbit only.

### [E054] Fairwork India Ratings Degradation
* **Evidence Statement:** Urban Company's Fairwork India Rating declined from 8/10 in 2019 to 6/10 in 2024, explicitly losing points for fair representation due to a lack of collective bargaining and automated disciplinary mechanics.
* **Evidence Type:** `FACT`
* **Temporal Label:** HISTORICAL (2019 and 2024 assessment years)
* **Source ID:** `S014` (Fairwork India Ratings)
* **Confidence Level:** **High** — Institutional academic rating.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS** (Highlights macro labor tension, but does not provide specific post-booking pricing friction data).
* **Scope Limitation:** High-level platform score does not parse individual transaction-level pricing disputes.

### [E056] Hidden Worker Expenses & True Margin Unpredictability
* **Evidence Statement:** Analyst synthesis based on cited labor literature; not independently quantified for Urban Company's median partner population. Net-net earnings of median gig workers are often highly volatile because they are unadjusted for hidden operational capital expenditures.
* **Evidence Type:** `ANALYST SYNTHESIS`
* **Source ID:** Underlying primary source not yet independently registered (via `S022` Synthesis).
* **Confidence Level:** **Medium** — Established sociological and economic gap in gig labor studies.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS** (Relates to supply-side margin opacity rather than consumer post-booking price predictability).
* **Scope Limitation:** Represents an ongoing research gap (`GAP-006`).

### G. Financials, Policies & Engineering Mitigation (E039–E042, E046–E053, E055)

### [E039] Urban Company FY24 Financial Trajectory
* **Evidence Statement:** Urban Company reported FY24 consolidated revenue of INR 827 crore (30% YoY growth) while narrowing PBT losses to INR 93 crore.
* **Evidence Type:** `COMPANY CLAIM (attributed)`
* **Temporal Label:** HISTORICAL (FY2024)
* **Source ID:** `S007` (Annual Business Summary FY2024)
* **Confidence Level:** **High** — Official corporate financial disclosure.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS** (Establishes platform's drive toward profitability).
* **Scope Limitation:** Does not disclose granular category-level unit economics or dispute resolution costs.

### [E040] Upfront Granular Rate Card for Parts
* **Evidence Statement:** Urban Company's AC rate-card source lists fixed prices for specified parts/services (e.g., inverter PCB repair ₹4,500, minor capacitor ₹250).
* **Evidence Type:** `FACT`
* **Source ID:** `S009` (Urban Company AC Pricing Rate Card)
* **Confidence Level:** **High** — Verified from official platform pricing schedules.
* **D004 Investigation Relationship:** **MIXED** (Rate card transparency for parts supports partial transparency but leaves end-to-end cost unpredictable).
* **Scope Limitation:** Does not account for unanticipated, non-catalogued bespoke parts.

### [E041] Diagnostic Visitation Fee Mechanism
* **Evidence Statement:** Urban Company charges a visitation/diagnostic fee in specified repair flows; the cited policy states how that fee is treated when the customer accepts or declines the repair quote.
* **Evidence Type:** `FACT`
* **Source ID:** `S009` (Urban Company Policies)
* **Confidence Level:** **High** — Official platform operational mechanism.
* **D004 Investigation Relationship:** **SUPPORTS WITH INTERPRETATION CAVEAT** (The existence of the visitation fee is a fact consistent with post-booking friction. Interpretation: creates lock-in).
* **Scope Limitation:** Does not establish the statistical frequency with which initial diagnostic visits result in price escalations and subsequent abandonment (`GAP-005`).

### [E042] Phased Escrow for Macro-Projects
* **Evidence Statement:** Urban Company requires at-home consultation, exact quoting, and 35% upfront booking for painting ≥ ₹25,000.
* **Evidence Type:** `FACT`
* **Source ID:** `S010` (Urban Company Painting Services)
* **Confidence Level:** **High** — Official platform pricing mechanism for large tasks.
* **D004 Investigation Relationship:** **SUPPORTS (CONTEXTUAL)** (Confirms UC treats high-value post-booking pricing as a distinct problem class. It is evidence the platform acknowledges the friction, not direct evidence of customer impact).
* **Scope Limitation:** Applies only to specific macro-project categories (painting, renovations).

### [E046a] India Cancellation Penalties by Vertical
* **Evidence Statement:** Urban Company offers free cancellations up to 24 hours before scheduled jobs, but imposes strict penalties within the 24-hour window (e.g., ₹1,000 for painting).
* **Evidence Type:** `FACT`
* **Geography:** India
* **Temporal Label:** UNCLEAR (policy snapshot as of 2024; current enforcement unverified)
* **Source ID:** `S012` (Urban Company Cancellation Policy)
* **Confidence Level:** **High** — Verified from platform policies.
* **D004 Investigation Relationship:** **MIXED / CONTEXTUAL** (Cancellation penalties are relevant to Option 4).
* **Scope Limitation:** Exact penalty caps may vary by time remaining.

### [E046b] Singapore Cancellation Penalties
* **Evidence Statement:** Urban Company Singapore imposes strict cancellation penalties within the 24-hour window (e.g., SGD 20 for cleaning).
* **Evidence Type:** `FACT`
* **Geography:** Singapore
* **Temporal Label:** UNCLEAR (policy snapshot as of 2024; current enforcement unverified)
* **Source ID:** `S013` (Urban Company Singapore Cleaning Services Page)
* **Confidence Level:** **High** — Verified from platform policies.
* **D004 Investigation Relationship:** **MIXED / CONTEXTUAL** (Cancellation penalties are relevant to Option 4).
* **Scope Limitation:** Specific to the Singapore market.

### [E047] Pass-Through Cancellation Fee Policy
* **Evidence Statement:** As part of its 12-point partner welfare program, Urban Company transfers 100% of last-minute customer cancellation fees directly to the affected partner.
* **Evidence Type:** `COMPANY CLAIM (attributed)`
* **Temporal Label:** HISTORICAL (2021 program announcement)
* **Source ID:** `S008` (Urban Company 12-Point Program PR)
* **Confidence Level:** **High** — Official corporate policy announcement.
* **D004 Investigation Relationship:** **MIXED / CONTEXTUAL** (Shows UC has taken steps to make cancellation penalties less punitive to customers/partners. Relevant to Option 4).
* **Scope Limitation:** Represents intended platform policy; does not measure edge-case payout failures.

### [E048] Standard Warranty & Damage Protection
* **Evidence Statement:** Urban Company provides a baseline 30-day service guarantee, up to 90 days for critical appliances, and advertises customer protection up to INR 10,000 for damages incurred during service.
* **Evidence Type:** `COMPANY CLAIM (attributed)`
* **Temporal Label:** UNCLEAR (policy as cited; current enforcement unverified)
* **Source ID:** `S011` (Urban Company Warranty Policy)
* **Confidence Level:** **High** — Advertised platform marketing claim.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS** (contextual to recovery/guarantees).
* **Scope Limitation:** Advertised policy parameters only.

### [E049] Extended Warranty Exclusions
* **Evidence Statement:** The extended warranty heavily protects the platform by excluding third-party repairs, commercial use, aesthetic defects, consequential loss, and is strictly non-refundable once activated.
* **Evidence Type:** `FACT`
* **Source ID:** `S011` (Urban Company Extended Warranty ToS)
* **Confidence Level:** **High** — Verifiable legal terms.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS** directly.
* **Scope Limitation:** Legal T&Cs; does not track specific claim rejection rates.

### [E050] Engineering Mitigation: Native RO Warranty
* **Evidence Statement:** Urban Company engineered the Native RO water purifier with self-regulating mechanisms to offer a 2-year warranty.
* **Evidence Type:** `COMPANY CLAIM (attributed)`
* **Temporal Label:** CURRENT (product spec at time of research)
* **Source ID:** `S007`, `S011` (Urban Company Product Specs)
* **Confidence Level:** **High** — Official product hardware specification.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS / CONTEXTUAL ANALOGUE** (If UC can engineer out post-booking unpredictability in one product, it demonstrates the problem can be solved. It is not direct evidence of current customer friction).
* **Scope Limitation:** Specific to a single proprietary hardware product.

### [E051] Algorithmic Auto-Assign & Labor Union Protests
* **Evidence Statement:** Worker/labor organizations have alleged that the "auto-assign" feature strips professionals of agency and subjects them to arbitrary ID blocking for rejecting unprofitable tasks.
* **Evidence Type:** `ANALYST SYNTHESIS`
* **Source ID:** Underlying primary source not yet independently registered (via `S022` Synthesis).
* **Confidence Level:** **Medium** — Underlying primary source not yet independently registered.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS** directly.
* **Scope Limitation:** External qualitative labor reporting.

### [E052] Reductions in Commission and Penalty Caps
* **Evidence Statement:** The company announced a reduction in the maximum commission slab from 30% to 25% (bringing the average to 20-22%) and reduced the maximum monthly penalty cap per partner to ₹1,500.
* **Evidence Type:** `COMPANY CLAIM (attributed)`
* **Temporal Label:** HISTORICAL (2021-2024 policy change)
* **Source ID:** `S008` (Urban Company PR)
* **Confidence Level:** **High** — Official corporate disclosure.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS** directly.
* **Scope Limitation:** Does not account for indirect penalties or search ranking demotions.

### [E053] Removal of Temporary Algorithmic Blocks
* **Evidence Statement:** Urban Company claims to have removed all temporary algorithmic blocks on partners, except those related to verified quality failures, projecting an estimated 80% reduction in overall blocks.
* **Evidence Type:** `COMPANY CLAIM (attributed)`
* **Temporal Label:** HISTORICAL (company estimate at time of program announcement)
* **Source ID:** `S008` (Urban Company PR)
* **Confidence Level:** **High** — Official corporate claim.
* **D004 Investigation Relationship:** **DOES NOT ADDRESS** directly.
* **Scope Limitation:** Stated corporate policy change (company estimate, not independently audited).

### [E055] Partner Earnings Metrics
* **Evidence Statement:** Urban Company reports its top 20% of partners earn ₹42,792/month net, with female partners averaging 23% higher hourly earnings compared to males.
* **Evidence Type:** `COMPANY CLAIM (attributed)`
* **Temporal Label:** HISTORICAL (FY2024 disclosure)
* **Source ID:** `S007` (Urban Company Financials)
* **Confidence Level:** **High** (For top 20% tier) / **Low** (For median extrapolation).
* **D004 Investigation Relationship:** **DOES NOT ADDRESS** directly.
* **Scope Limitation:** Top-decile only; does not describe median worker reality.


---

*Stage: RESEARCH → ANALYSIS — Evidence Matrix fully verified, calibrated, and auditable.*  
*Last updated: 2026-09-18*


### H. Methodological Limitations (GAP-008)

### [GAP-008] Lack of Direct Primary Interview Validation
* **Evidence Statement:** Primary research (live user interviews) was omitted due to feasibility constraints. We lack controlled qualitative validation of user mental models surrounding post-booking pricing, cancellation reactions, and alternative-provider switching behavior.
* **Evidence Type:** `RESEARCH LIMITATION`
* **Source ID:** None (Omitted Task 8)
* **Confidence Level:** **Low** (Represents an absence of evidence).
* **D004 Investigation Relationship:** **DOES NOT ADDRESS**
* **Scope Limitation:** All user-side qualitative evidence relies exclusively on asynchronous public review mining and walkthroughs.
