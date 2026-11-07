# PM-01 — Urban Company: Trust & Repeat-Booking in a Two-Sided Marketplace
## 09 — Canonical User Research Summary: Review-Mining Evidence

**Stage:** RESEARCH → ANALYSIS  
**Document Type:** Canonical User Research Synthesis (Stage 1 Foundation)  
**Primary Source Citations:** `S001` ([`PM01_Urban_Company_Cleaned.xlsx`](data/Urban_Company_Cleaned_Dataset.xlsx)), `S002` ([`DATA_QUALITY_ANALYSIS.md`](data/data_quality_analysis.md)), `S003` ([`DESCRIPTIVE_ANALYSIS.md`](data/descriptive_analysis.md)), `S004` ([`QUALITATIVE_PATTERN_ANALYSIS.md`](data/qualitative_pattern_analysis.md))  
**Audited Evidence Registry:** [`05_evidence_matrix.md`](data/evidence_matrix.md) (`E001`–`E019`, `PAT-01`–`PAT-10`, `CON-001`–`CON-004`)  
**Last Updated:** 2026-09-18 (Post-Task 2 Audit & Human Decision Review)  

---

> [!IMPORTANT]
> **Evidence Governance & Methodological Boundaries (EVIDENCE_POLICY.md & AGENTS.md):**
> 1. **Level 4 Community Evidence:** All data in this document represents public Google Play Store customer reviews (`S001`). It is classified as **Level 4 Community Evidence / `RESEARCH FINDING (community)`**. It is highly effective for discovering recurring behavioral patterns, stated frictions, and verbatim user mental models, but is **NOT statistically representative** of Urban Company's aggregate customer population or total transaction volume.
> 2. **Sample-Only Scope ($N=179$):** All percentages, metrics, and frequencies describe this specific sampled dataset only. They must never be generalized as macro platform metrics (e.g., observing that 14.5% of sampled reviews mention cancellations does not mean Urban Company has a 14.5% platform cancellation rate).
> 3. **Non-Causal Discipline:** Review frequency demonstrates salience and co-occurrence within the sample; it does not prove causal business impact (such as churn or retention reduction).
> 4. **Zero Fabrication:** Every quote, count, and observation traces directly to primary review records and audited evidence entries (`E001`–`E019`). Zero synthetic personas, quotes, or ratings have been introduced.
> 5. **Preservation of Contradictions:** Opposing observations (e.g., safety praise vs. domestic boundary violations) are preserved as unresolved dialectical tensions rather than selectively discarded.

---

## 1. Research Methodology (Google Play Store Review Mining)

### 1.1 Sampling Architecture & Provenance
The initial qualitative evidence base was established through systematic review mining of the Urban Company Android Application on the Google Play Store (`S001`), executed between June 2019 and September 2026:

* **Sample Size:** Exactly $N = 179$ user reviews.
* **Review Slices Sampled:**
  * `Sheet 1: Most Relevant 5 Star` ($n = 57$ reviews, 31.8% of sample) — captured to isolate primary drivers of customer satisfaction, loyalty anchors, and positive retention triggers.
  * `Sheet 2: Most Relevant 4 Star` ($n = 47$ reviews, 26.3% of sample) — captured specifically to analyze "near-miss" transactions where customers liked the service but docked one star due to specific UI, pricing, or operational frictions.
  * `Sheet 3: Newest` ($n = 75$ reviews, 41.9% of sample) — captured to evaluate uncurated, recent real-time operational sentiment and emerging failure modes.
* **Date Span:** Reviews span from **2019-06-12** to **2026-09-15** (7.25-year longitudinal window).
* **Research Pipeline:**
  1. *Extraction & Ingestion:* Public reviews extracted into a structured workbook (`PM01_Urban_Company_Cleaned.xlsx`).
  2. *Data Integrity Audit:* Programmatic audit conducted in [`DATA_QUALITY_ANALYSIS.md`](data/data_quality_analysis.md) (`S002`), establishing deterministic row counts and documenting extraction anomalies.
  3. *Taxonomy Normalization & Coding:* Normalization of 475 unique topic strings into 8 core operational themes in [`DESCRIPTIVE_ANALYSIS.md`](data/descriptive_analysis.md) (`S003`).
  4. *Candidate Pattern Synthesis:* Thematic clustering into 10 candidate behavioral patterns with counter-evidence in [`QUALITATIVE_PATTERN_ANALYSIS.md`](data/qualitative_pattern_analysis.md) (`S004`).
  5. *Audited Evidence Registry:* Formal codification into [`05_evidence_matrix.md`](data/evidence_matrix.md) (`E001`–`E019`).

### 1.2 Explicit Methodological Limitations
To maintain senior PM rigor and prevent overclaiming in portfolio review, this research operates under six structural limitations:

1. **Self-Selection Bias:** Public app store reviews are voluntarily submitted by users with extreme experiences (delight or intense frustration). Moderate, uneventful transactions are under-represented.
2. **Public-Review Bias:** Users frequently post on the Google Play Store as an escalation channel of last resort when in-app private customer support fails, skewing the tone toward public accountability.
3. **Review-Slice Skew:** Purposive sampling targeting 5-star, 4-star, and recent reviews introduces intentional distribution biases. Valid ratings are heavily weighted toward positive sentiment ($65.5\%$ 5-star, $34.5\%$ 4-star), while recent reviews contain concentrated negative operational feedback.
4. **Missing Star Ratings ($n=40$):** An unrecoverable scraping extraction bug affected 40 reviews in Sheet 3 (`Newest`), where star ratings were lost. These reviews are analyzed textually under strict zero-fabrication rules (`[RATING UNAVAILABLE]`), and rating-specific calculations explicitly exclude them.
5. **Inability to Observe Non-Users:** App store reviews capture transacting customers. They provide zero visibility into prospective users who abandoned during onboarding, dropped off due to pre-booking distrust, or never downloaded the app.
6. **Inability to Observe Internal Operational Realities:** Public reviews reveal customer-facing symptoms, but cannot observe server-side dispatch logic, partner cancellation penalties, true unit economics, or aggregate retention curves.

---

## 2. Sample Profile & Vertical Context

### 2.1 Sample Rating and Sentiment Composition
All metrics report explicit numerators and denominators to guarantee mathematical reproducibility:

| Parameter | Count ($n$) | Share (%) | Population Definition | Provenance & Audit Reference |
|---|:---:|:---:|---|---|
| **Total Sampled Reviews** | 179 | 100.0% | Entire reviewed dataset ($N_{\text{total}}$) | `E001` / `S001` Sheet 1, 2, 3 |
| **Valid Numeric Ratings** | 139 | 77.7% | Reviews with verified Play Store star scores ($N_{\text{valid}}$) | `E002` / `S002` Section 2 |
| — *5.0 Star Ratings* | 91 | 65.5% | Share of valid ratings ($n / N_{\text{valid}}$) | `E002` ($n=57$ Sheet 1; $n=34$ Sheet 3) |
| — *4.0 Star Ratings* | 48 | 34.5% | Share of valid ratings ($n / N_{\text{valid}}$) | `E002` ($n=47$ Sheet 2; $n=1$ Sheet 3) |
| — *1.0 to 3.0 Star Ratings* | 0 | 0.0% | Share of valid ratings ($n / N_{\text{valid}}$) | Zero sampled in Sheet 1/2; Sheet 3 unrated |
| **Missing Rating Placeholders** | 40 | 22.3% | Reviews with extraction loss ($n / N_{\text{total}}$) | `E002` (Sheet 3 `[RATING UNAVAILABLE]`) |
| **Cleaned Sentiment: Positive** | 93 | 52.0% | Reviews classified with positive sentiment ($n / N_{\text{total}}$) | `S003` Section 2.3 |
| **Cleaned Sentiment: Negative** | 51 | 28.5% | Reviews classified with negative sentiment ($n / N_{\text{total}}$) | `S003` Section 2.3 |
| **Cleaned Sentiment: Mixed** | 30 | 16.8% | Reviews classified with mixed sentiment ($n / N_{\text{total}}$) | `S003` Section 2.3 |
| **Cleaned Sentiment: Neutral** | 5 | 2.8% | Reviews classified with neutral sentiment ($n / N_{\text{total}}$) | `S003` Section 2.3 |

### 2.2 Service Vertical Context
Reviews were mapped across six normalized service categories to isolate category-specific operational dynamics:

| Service Vertical | Review Count ($n$) | Sample Share (%) [$N=179$] | Qualitative Concentration & Vertical Characteristics |
|---|:---:|:---:|---|
| **Platform, App & Support** | 86 | 48.0% | General platform feedback, UI navigation, payment gateway, checkout fees, AI chatbot support loops. |
| **Appliance Repair & Servicing** | 41 | 22.9% | AC cleaning/repair, RO water purifier servicing, washing machine maintenance, microwave repair. High-ticket, technical trades. |
| **Insta Help & Daily Services** | 26 | 14.5% | On-demand instant domestic help (cleaning, dishwashing, cooking). Short dispatch lead times, high operational fragility. |
| **Home Cleaning & Pest Control** | 16 | 8.9% | Deep home cleaning, bathroom cleaning, kitchen degreasing, sofa shampooing. High physical intimacy and domestic inspection. |
| **Home Maintenance & Repairs** | 7 | 3.9% | Electricians, plumbers, carpenters, minor home fixes. Rapid emergency fix requests. |
| **Beauty, Salon & Spa** | 3 | 1.7% | At-home haircuts, facials, waxing, pedicure. High personal grooming trust, repeat partner preference. |

---

## 3. Core Thematic Findings

Across the 179 reviews, **571 topic mentions** were coded across 8 core operational dimensions. Review counts are **non-mutually exclusive** (a single review discussing a rude technician and an unexpected bill surcharge is tagged in both Professional Behavior and Pricing). 

Frequencies indicate **commentary prevalence within this review sample**, not business priority or platform-wide incident rates:

| Theme | Sample Count ($n$) | Sample Share (%) [$N=179$] | Key Evidence Signals from Reviews | Important Analytical Caveat | Evidence ID |
|---|:---:|:---:|---|---|:---:|
| **Professional Behavior** | 54 | 30.2% | Most prevalent positive operational theme ($n=41/93$, 44.1% of positive reviews). Punctuality, polite conduct, hygiene standards, and professional uniforms anchor 5-star ratings (`R0001`, `R0003`, `R0021`). | Acts as an inverse signal for H2; high customer delight over basic punctuality may reflect historically low baseline reliability in India's unorganized local market. | `E007` |
| **Quality-related** | 51 | 28.5% | Workmanship is highly salient: $n=31/51$ positive quality praise ($31/93 = 33.3\%$ of positive sample) and $n=14/51$ negative defect complaints ($14/51 = 27.5\%$ of negative sample). Concentrates heavily in Home Cleaning ($93.8\%$, $n=15/16$) and Appliance Repair ($61.0\%$, $n=25/41$). | Confirms service execution is a primary customer evaluative criterion, but review data cannot prove that quality variance reduces aggregate repeat-booking retention. | `E003` |
| **App/UX-related** | 48 | 26.8% | Dual-nature theme: booking flow convenience praised ($n=18/93$ positive), while negative UX ($n=16/51$ negative) is dominated by repetitive AI chatbot deflection loops and missing telephone helplines (`R0071`, `R0116`). | Negative UX comments represent post-service dispute resolution failures rather than pre-booking discovery friction, providing indirect rather than direct support for H1. | `E006` |
| **Pricing-related** | 46 | 25.7% | Highly contentious: 17 reviews praise transparent rates, but 19 negative reviews (37.3% of negative cohort) cite checkout fee stacking (platform fees ₹166, GST ₹34), weekend surge (₹150–₹200), and cancellation fines (`R0058`, `R0092`). | Identifies pricing transparency as an independent friction area that competes directly with trust/rebooking as a primary driver of customer dissatisfaction. | `E004` |
| **Cancellation-related** | 26 | 14.5% | Extreme category concentration: 11 of 26 cancellation mentions occur in Insta Help ($42.3\%$ of vertical base; $42.3\%$ of sample cancellations). Involves repeated partner no-shows and asymmetric ₹50 cancellation fines (`R0108`, `R0145`). | Confined heavily to on-demand domestic chores; cannot be extrapolated as a platform-wide cancellation rate across scheduled trades like appliance repair or salon. | `E005` |
| **Trust-related** | 14 | 7.8% | Low frequency but extreme severity: positive trust ($n=5/93$ positive) anchored in background check badges; negative trust ($n=8/51$ negative) centers on domestic privacy breaches (unannounced washroom use `R0143`, video surveillance `R0109`) and integrity/fraud grievances (used parts installed `R0160`, cheating claims `R0136`). | Supports post-booking domestic execution trust in reformulated H4 (**Two-Stage Trust Model**). Pre-booking platform trust remains unassessed in reviews (non-bookers cannot be observed). | `E008` |
| **Rebooking-related** | 6 | 3.4% | Evenly split between long-term multi-year repeat satisfaction ($n=3$, `R0017`, `R0033`, `R0059`) and repeat booking friction ($n=3$, package failure `R0073`, booking bot loops `R0176`). | Low absolute sample frequency ($3.4\%$) challenges the premise that rebooking UX friction is the dominant customer pain point relative to pricing (25.7%) or quality (28.5%). | `E009` |
| **Consistency-related** | 6 | 3.4% | Captures longitudinal performance: 2 reviews praise uniform standards, while 4 reviews document service degradation over time, quality drops, and arbitrary partner substitutions (`R0074`, `R0117`, `R0179`). | Directly documents quality variance across repeat visits, supporting H2's premise; cannot measure aggregate churn causality. Requires multi-booking user history. | `E010` |

---

## 4. Candidate Behavioral Patterns

Synthesized from [`QUALITATIVE_PATTERN_ANALYSIS.md`](data/qualitative_pattern_analysis.md) and grounded in audited evidence entries `E011`–`E019`, the following 10 candidate patterns capture recurring behavioral phenomena across the sample:

| Pattern ID & Name | Evidence IDs | What Reviews Show | Contradicting Evidence / Counter-Signals | Evidence Strength & Confidence | Scope Limitations & Boundaries |
|---|---|---|---|---|---|
| **PAT-01: AI Chatbot Deflection Wall & Inaccessible Human Support** | `E006`, `E011` | Customers facing post-service failures (delays, damages, payment mismatches) get trapped in repetitive automated chatbot loops with no option to escalate to human agents or telephone helplines (`R0071`, `R0116`, `R0170`). | `R0010`, `R0085` (praise prompt customer care resolution and proactive arrival calls). | **High (Mechanism) / Negative-Skew Caveat** ($n=11/179$; 9 from unrated Sheet 3) | Captures post-service dispute failures; internal first-contact resolution rates are an unobserved gap (`GAP-002`). |
| **PAT-02: Asymmetric Cancellation Penalties on Platform Failures** | `E005`, `E012` | Customers report being penalized with ₹50 cancellation fees or forfeited prepaid packages even when the cancellation resulted from partner no-shows or platform scheduling errors (`R0072`, `R0115`, `R0145`). | `R0001`, `R0008`, `R0033` (praise transparent, stress-free billing with zero hidden fees). | **Medium (Prevalence $n=5$) / High (Mechanistic Verification)** | Describes customer perception of unfair penalty logic; official platform cancellation rules require Phase 2 validation (`GAP-003`). |
| **PAT-03: Insta Help Supply Fragility & Cancellation Cascades** | `E005`, `E013` | On-demand instant domestic help suffers chronic supply-matching breakdowns, leading to repeated partner no-shows, worker refusals upon arrival, and cascading cancellations (`R0108`, `R0126`, `R0176`). | `R0076`, `R0152` (clean maids arrived as booked, positive cleaning outcome). | **High (Within Vertical $n=11/26$, 42.3%) / Negative-Skew Caveat** | Strong vertical-specific operational breakdown; cannot be generalized as a platform-wide dispatch failure across scheduled services. |
| **PAT-04: Post-Booking Cost Inflation & Hidden Surcharges** | `E004`, `E014` | Customers experience price inflation through automated weekend surge fees (₹150–₹200), checkout platform convenience fees (₹166), and on-site technician add-on demands (`R0058`, `R0090`, `R0092`). | `R0001`, `R0008`, `R0033`, `R0035` (praise reasonable rates, fair estimates, transparent pricing). | **High (Factual Pricing Details)** ($n=13/179$; 28.3% of pricing cohort) | Reflects monetization friction and fee-stacking perceptions; does not reflect customer price elasticity across all categories. |
| **PAT-05: In-Home Privacy & Domestic Discretion Breaches** | `E008`, `E015` | Critical domestic boundary violations during service delivery: unannounced washroom usage (`R0143`), remote video surveillance into private homes (`R0109`), and socio-religious/communal discomfort (`R0164`, `R0179`). | `R0036`, `R0052`, `R0056` (praise worker background vetting, skill certification, feeling completely safe). | **Medium (Prevalence $n=4$) / High (Phenomenon Existence & Tail Severity)** | Rare, high-severity tail risks that destroy domestic sanctuary trust; does not reflect median customer sentiment. |
| **PAT-06: Secondary Appliance Damage & Defective Repairs** | `E003`, `E016` | Appliance maintenance visits occasionally cause collateral electrical or mechanical damage (broken switches, leaking AC units, incompatible purifier connectors) with stalled warranty claims (`R0079`, `R0111`, `R0166`). | `R0001`, `R0014`, `R0016`, `R0024`, `R0048` (flawless repairs where technicians quickly resolved complex faults). | **Medium (Prevalence $n=6$) / High (Phenomenon Existence & Verbatim Traceability)** | Clustered heavily in Appliance Repair ($n=5/6$); not generalizable to cleaning, salon, or maintenance verticals. |
| **PAT-07: Partner Demeanor & Punctuality as Loyalty Anchor** | `E007`, `E017` | The dominant driver of 5-star ratings and customer loyalty is individual partner conduct: punctuality, polite demeanor, disciplined execution, and spotless cleanup (`R0001`, `R0003`, `R0040`). | `R0099`, `R0161` (delayed arrival, unprofessional conduct, lack of accountability). | **High (Dominant Positive Signal)** ($n=15$ core cohort; backed by 54 reviews) | Reflects customer sensitivity to interpersonal behavior; does not prove that behavioral variance causes platform churn. |
| **PAT-08: Repeat-Booking Preference & Partner Reassignment Friction** | `E009`, `E010`, `E018` | Repeat customers develop trust in specific high-performing professionals and express anxiety/frustration when the platform arbitrarily reassigns unfamiliar partners without notification (`R0017`, `R0068`, `R0179`). | `R0013` (books across multiple categories seamlessly without individual professional preference). | **Medium (Low $n=7$, High Textual Fidelity)** | Documents customer desire for relationship continuity; internal allocation rules and preferred-pro feature status unknown (`GAP-004`). |
| **PAT-09: Decoupled Evaluation of Gig Partner vs. Corporate Platform** | `E010`, `E019` | Customers bifurcate their evaluation: praising the gig worker for courtesy and hard work while docking ratings or criticizing Urban Company for corporate platform fees, forced ratings, and lack of support (`R0074`, `R0091`, `R0092`). | `R0136`, `R0144` (conflate worker and company into a single negative judgment: "looters/cheaters"). | **Medium (Prevalence $n=7$) / High (Textual Clarity)** (14.6% of 4-star cohort) | Concentrated primarily in 4-star reviews; reveals that customer trust resides with the human partner rather than the corporate entity. |
| **PAT-10: Local & Competitor Substitution as Churn Workaround** | `E004`, `E014`, `R0070`, `R0113`, `R0145`, `R0163` | When faced with fee inflation, cancellation cascades, or support deflection, customers revert to offline domestic help, local neighborhood mechanics, or competitors like Snabbit (`R0070`, `R0113`, `R0145`, `R0163`). | `R0063` (Urban Company explicitly preferred over unorganized local alternatives). | **Medium (Low $n=4$, Qualitative Significance)** | Indicates low switching barriers in urban domestic services; requires Phase 2 market and competitive triangulation. |

---

## 5. Observation vs. Interpretation

To enforce strict PM analytical discipline, this section separates **what the data literally shows** from **what the PM infers it might mean**. The top five patterns were selected based on evidence strength, severity of impact, and diverse thematic representation across the investigation:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                            EVIDENCE RIGOR HIERARCHY                         │
│                                                                             │
│  OBSERVATION      Directly verifiable text, explicit counts, verbatim quotes │
│       ↓                                                                     │
│    PATTERN        Recurring qualitative co-occurrence across reviews        │
│       ↓                                                                     │
│  INTERPRETATION   Plausible causal mechanism (HYPOTHESIS — NOT PROVEN)      │
│       ↓                                                                     │
│   LIMITATION      Why public review data cannot establish population truth   │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

### Pattern 1 — AI Chatbot Deflection Wall & Inaccessible Human Support
* **Observation:** Multiple reviewers explicitly describe being unable to contact a human agent, finding no telephone customer care number, and receiving repetitive, canned chatbot responses when attempting to dispute charges, cancellations, or damages (`R0071`, `R0108`, `R0116`, `R0117`, `R0170`).
* **Pattern:** Post-service dispute resolution channels exhibit acute customer-perceived accessibility barriers, characterized by automated loops that fail to resolve non-standard inquiries.
* **Interpretation:** Urban Company may have aggressively automated its tier-1 customer support to compress operational overhead, successfully deflecting routine tracking requests but creating severe customer rage on complex, high-stakes edge cases where human judgment is required.
* **Confidence:** **High (Mechanistic Verification) / Negative-Skew Caveat** — Confirmed by 11 independent reviews with identical verbatim descriptions; 9 reviews stem from the unrated Sheet 3 extraction bug which over-indexes on negative recent sentiment.
* **Limitation:** Public reviews do not reveal Urban Company's internal customer support ticketing data, bot deflection success rates, or median resolution times (`GAP-002`).
* **Relevant Evidence:** `E006`, `E011`, `PAT-01`.

---

### Pattern 2 — Post-Booking Cost Inflation & Fee Stacking
* **Observation:** Reviewers document specific checkout and post-booking price additions, including a ₹166 platform fee and ₹34 GST added to a ₹1,055 bill (`R0092`), default weekend surge charges of ₹150–₹200 (`R0058`, `R0165`), on-site charges of ₹350 for a 2-minute fix (`R0090`), and extra payment requests on prepaid packages (`R0073`).
* **Pattern:** Transparent baseline service prices advertised upfront are undermined by cumulative fee-stacking at checkout and variable add-on pricing on-site.
* **Interpretation:** The platform may be utilizing ancillary fees (convenience fees, platform charges, demand-based surge) as margin-expansion levers, which conflicts with customer expectations of transparent, all-inclusive pricing and triggers perceptions of price gouging.
* **Confidence:** **High** — Substantiated by explicit, corroborated monetary figures across 13 independent reviews.
* **Limitation:** Public reviews reflect vocal price-sensitive customers; they cannot measure platform-wide take-rates, average order values, or overall conversion elasticity.
* **Relevant Evidence:** `E004`, `E014`, `PAT-04`.

---

### Pattern 3 — Insta Help Supply Fragility & Cancellation Cascades
* **Observation:** In the Insta Help on-demand vertical, 11 out of 26 reviews report cancellation and partner no-show failures: assigned maids failing to arrive (`R0126`), helpers visiting and refusing appointed tasks (`R0136`), bookings confirmed and repeatedly cancelled (`R0108`), and users reporting 4–5 consecutive cancellations (`R0176`).
* **Pattern:** On-demand domestic chores experience chronic dispatch failure, worker non-arrival, and automated booking cancellation loops.
* **Interpretation:** Instant on-demand dispatch for low-ticket domestic chores (cleaning, vessel washing) suffers from partner supply-side resistance. Gig partners likely prioritize scheduled, high-ticket services or private offline employment over low-margin on-demand tasks with high transit friction.
* **Confidence:** **High (Within Vertical Concentration: 42.3%) / Negative-Skew Caveat** — Extremely concentrated in Insta Help ($n=11/26$), but heavily drawn from unrated Sheet 3 ($n=8/11$).
* **Limitation:** Confined to the Insta Help vertical; does not represent fulfillment reliability in scheduled appliance, cleaning, or salon categories.
* **Relevant Evidence:** `E005`, `E013`, `PAT-03`.

---

### Pattern 4 — In-Home Privacy Breaches & Domestic Execution Trust
* **Observation:** Sampled reviews document severe personal boundary violations inside the home: service partners using the customer's private washroom without permission (`R0143`), technicians conducting remote video calls that capture the home interior without clear consent (`R0109`), socio-religious/communal discomfort (`R0164`, `R0179`), and installation of used parts billed as new (`R0160`).
* **Pattern:** While overall trust-themed review volume is low ($7.8\%$), negative trust incidents represent acute domestic sanctuary violations that create intense safety anxiety.
* **Interpretation:** Under the hypothesized **Two-Stage Trust Model** (reformulated `H4`), trust operates across two distinct thresholds: while platform brand badges and digital verification are hypothesized to establish initial pre-booking reassurance, the post-booking stage may be important to customer retention, particularly where in-home domestic-safety or service-execution problems occur. A single privacy breach inside the home destroys customer trust permanently.
* **Confidence:** **Medium (Prevalence $n=4/179$) / High (Phenomenon Existence & Verbatim Traceability)** — Low absolute frequency, but verified against concrete primary text detailing acute domestic risk.
* **Limitation:** Low review count ($n=4$) indicates this is a severe negative tail risk rather than a median user experience. Review data cannot measure pre-booking drop-off among non-bookers.
* **Relevant Evidence:** `E008`, `E015`, `PAT-05`.

---

### Pattern 5 — Repeat-Booking Preference & Partner Reassignment Friction
* **Observation:** Repeat customers describe developing confidence in individual service professionals through multi-booking history (`R0017`, `R0033`, `R0059`), but report frustration when Urban Company arbitrarily reassigns different, unfamiliar personnel without notice or customer control (`R0068`, `R0179`).
* **Pattern:** High customer satisfaction is anchored in the individual gig worker; when users attempt to rebook, platform dispatch friction disrupts relationship continuity.
* **Interpretation:** Urban Company's dispatch architecture appears optimized for **marketplace liquidity** (dispatching the nearest available worker to minimize wait times) rather than **relationship continuity** (re-dispatching a preferred professional). This liquidity-continuity trade-off frustrates repeat bookers who view the partner, not the app, as their loyalty anchor.
* **Confidence:** **Medium** — Low absolute sample size ($n=7$, 3.9% of sample), but delivers clear qualitative articulation of repeat customer preferences.
* **Limitation:** Public reviews do not reveal whether Urban Company already offers a preferred-professional feature, how discoverable it is, or what percentage of repeat bookings request specific partners (`GAP-004`).
* **Relevant Evidence:** `E009`, `E010`, `E018`, `E019`, `PAT-08`, `PAT-09`.

---

## 6. Contradictory Evidence Signals

A hallmark of rigorous user research is identifying and preserving dialectical tensions in user data rather than forcing an artificial consensus. The review sample exhibits four major unresolved contradictions:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    FOUR CORE EVIDENCE DIALECTICAL TENSIONS                  │
│                                                                             │
│  CON-001: Background Vetting Praise  ◄──[UNRESOLVED]──►  Domestic Sanctuary│
│           (Safe, certified workers)                      Violations (Video, │
│                                                          Washroom usage)    │
│                                                                             │
│  CON-002: Multi-Year Repeat Loyalty ◄──[UNRESOLVED]──►  Arbitrary Partner   │
│           (Zero disappointment)                          Reassignment       │
│                                                          Friction           │
│                                                                             │
│  CON-003: Transparent Upfront Rates ◄──[UNRESOLVED]──►  Checkout Fee       │
│           (Reasonable, fair cost)                        Stacking & Surcharge│
│                                                                             │
│  CON-004: Prompt Customer Care       ◄──[UNRESOLVED]──►  AI Chatbot         │
│           (Helpful call confirmations)                   Deflection Loops   │
└─────────────────────────────────────────────────────────────────────────────┘
```

### Contradiction 1: Safety & Vetting Praise vs. Acute Domestic Sanctuary Breaches (`CON-001`)
* **Positive Signal:** Multiple 5-star reviews praise Urban Company's strict background verification, professional training, identity badges, and express complete comfort welcoming cleaners and technicians into their private residences (`R0036`, `R0052`, `R0056`).
* **Negative Signal:** Independent reviews document alarming domestic privacy breaches: unannounced washroom usage (`R0143`), invasive remote video surveillance into the home (`R0109`), and theft accusations (`R0136`).
* **Underlying Tension:** Baseline platform verification satisfies general identity and safety expectations, but on-site behavioral etiquette and technician remote audit practices occasionally collapse during private in-home service delivery.
* **Current Analytical Boundary:** Cannot conclude whether Urban Company's vetting is failing or whether complaints represent rare partner conduct outliers. Official safety protocols must be evaluated in Phase 2.
* **Evidence Tracing:** `E008`, `E015`, `E017`, `CON-001`.

### Contradiction 2: Multi-Year Repeat Loyalty vs. Partner Reassignment Friction (`CON-002`)
* **Positive Signal:** Long-term repeat customers report seamless, multi-year satisfaction with zero disappointments across regular salon and cleaning bookings (`R0017`, `R0033`, `R0059`).
* **Negative Signal:** Customers report that Urban Company arbitrarily reassigns unfamiliar personnel without customer consent (`R0179`) and prepaid service packages fail on subsequent bookings (`R0073`).
* **Underlying Tension:** Repeat booking works smoothly when the customer desires generic service delivery, but creates intense anxiety when the customer develops a personal preference for a specific trusted professional.
* **Current Analytical Boundary:** Cannot conclude whether Urban Company completely lacks a preferred-pro feature or whether customers simply cannot discover it in the UI (`GAP-004`). Product walkthrough required in Task 6.
* **Evidence Tracing:** `E009`, `E010`, `E018`, `CON-002`.

### Contradiction 3: Transparent Pricing Praise vs. Hidden Fee Stacking (`CON-003`)
* **Positive Signal:** Users praise transparent pricing, reasonable standardized rate cards, and fair billing with zero unexpected demands (`R0001`, `R0008`, `R0033`, `R0035`).
* **Negative Signal:** Users express intense frustration over ₹166 platform fees, ₹200 weekend surge pricing, and ₹50 cancellation fines on unfulfilled bookings (`R0058`, `R0092`, `R0115`, `R0145`).
* **Underlying Tension:** Baseline menu rates appear competitive and transparent, but post-selection fee additions at checkout create perceived bait-and-switch friction.
* **Current Analytical Boundary:** Cannot determine whether fee stacking has depressed platform-wide repeat booking or increased churn without internal billing data.
* **Evidence Tracing:** `E004`, `E012`, `E014`, `CON-003`.

### Contradiction 4: Prompt Customer Care vs. Rigid AI Chatbot Deflection (`CON-004`)
* **Positive Signal:** 5-star reviews note prompt customer care resolution and proactive pre-arrival confirmation calls (`R0010`, `R0085`).
* **Negative Signal:** Users report being trapped in circular AI chatbot loops that offer unhelpful canned responses and completely block access to human escalation (`R0071`, `R0116`, `R0170`).
* **Underlying Tension:** Pre-service operational communication runs smoothly, but post-service dispute resolution channels are heavily automated to contain operational costs, stranding users who experience service defects.
* **Current Analytical Boundary:** Cannot determine platform-wide chatbot containment rates or human escalation availability without internal support logs (`GAP-002`).
* **Evidence Tracing:** `E006`, `E011`, `CON-004`.

---

## 7. Hypothesis-Relevant Findings

Connecting the review-mining evidence to the five hypotheses defined in [`08_problem_discovery.md`](01_problem_discovery_review_mining.md) (lines 32–156), using calibrated, non-overclaimed language:

| Hypothesis | Description | Evidence Direction in Review Sample | What Current Reviews Support | What Review Data Cannot Establish |
|---|---|---|---|---|
| **H1** | **Repeat-Booking UX Friction:** Repeat customers face friction discovering, rebooking, or retaining preferred professionals in the app. | **Partially Supported (Qualitative Signal)** | Documents customer desire to retain known professionals (`E018`, $n=7$) and confirms partner reassignment causes dissatisfaction. | Low absolute sample frequency ($3.4\%$ in `E009`) challenges the premise that rebooking UX friction is the primary driver of customer churn relative to pricing or support. |
| **H2** | **Service Quality Inconsistency:** Variance in workmanship across professionals reduces trust and repeat-booking retention. | **Directionally Supported (Premise & Salience Supported; Retention Impact Indirect)** | Workmanship quality and partner demeanor are highly salient ($28.5\%$ and $30.2\%$). Severe quality defects and collateral damage occur (`E016`, $n=6$). | Review data cannot measure aggregate repeat-booking retention curves or prove that quality variance causes macro customer churn. |
| **H3** | **Platform Allocation Constraints:** Marketplace dispatch rules prioritize city-wide liquidity over relationship continuity. | **Partially Supported (Symptom-side Only)** | Confirms customer-facing symptoms: partner reassignments (`E018`), acute on-demand cancellation cascades (`E013`, $42.3\%$), and cancellation fines (`E012`). | Reviews capture customer perception only; internal dispatch algorithms, partner acceptance rates, and platform liquidity rules remain unobserved supply-side mechanisms. |
| **H4** | **Two-Stage Trust Model:** Pre-Booking Platform Trust vs. Post-Booking Domestic Sanctuary Trust. | **Reformulated / Partially Supported (Post-Booking Component)** | Supports the post-booking domestic execution trust component: acute domestic breaches occur inside the home (`E008` negative trust $n=8/51$, `E015` in-home privacy breaches $n=4/14$, `E016` collateral damage $n=6/51$). | Review data contains only transacting users; it cannot measure pre-booking drop-off among prospective users who never booked. Pre-booking trust is unassessed, not disproven. |
| **H5** | **Supply-Side Trade-offs:** Professional retention and scheduling continuity create operational friction for service partners. | **Unassessed via Customer Reviews** | Customer reviews provide zero visibility into gig worker incentives, partner earnings stability, or operational trade-offs. | Cannot be evaluated using customer review data; requires Phase 2 secondary labor reporting and partner-side research. |

---

## 8. What This Research Can and Cannot Answer

To prevent overclaiming in portfolio reviews and interview defense, the research boundaries of public review mining are explicitly codified:

### What Review Mining CAN Answer:
1. **Recurring User Frustrations:** Identifies verbatim pain points, friction mechanisms, and specific failure modes reported by active customers (e.g., ₹50 cancellation fines, repetitive chatbot loops).
2. **Category-Specific Operational Vulnerabilities:** Exposes extreme vertical concentrations, such as supply-matching breakdowns in on-demand Insta Help ($42.3\%$) and secondary collateral damage in Appliance Repair ($61.0\%$).
3. **Interpersonal Loyalty Anchors:** Uncovers that customer satisfaction and 5-star ratings are overwhelmingly anchored in individual partner demeanor, punctuality, and politeness ($44.1\%$ of positive reviews).
4. **Dialectical Marketplace Tensions:** Captures real customer trade-offs between pricing transparency and fee stacking, and between generic service speed and personal relationship continuity.
5. **Candidate Problem Hypotheses:** Generates grounded qualitative problem directions to guide structured investigation in Phase 2.

### What Review Mining CANNOT Answer:
1. **Platform-Wide Prevalence:** Cannot determine what percentage of Urban Company's millions of monthly bookings experience cancellations, fee disputes, or quality failures.
2. **Actual Churn & Retention Metrics:** Cannot establish customer lifetime value (LTV), cohort retention rates, or the quantitative impact of service defects on repeat booking.
3. **Internal Support Performance:** Cannot measure first-contact resolution rates, chatbot containment success, or average dispute settlement payouts.
4. **Internal Cancellation Attribution:** Cannot observe whether a cancelled booking was initiated by the customer, partner transit delay, or automated platform timeout.
5. **Production Product UX Status:** Cannot verify whether Urban Company already has a preferred-professional rebooking feature in the production app or how it functions.
6. **Supply-Side Partner Perspective:** Cannot observe gig worker earnings, commission structures, dispatch algorithms, or partner churn.
7. **Prospective Non-User Behavior:** Cannot analyze prospective customers who visited Urban Company's website or app but dropped off before booking due to price or distrust.

---

## 9. Research Gaps & Phase 2 Roadmap

The boundaries of the review-mining dataset directly define six knowledge gaps that must be investigated in Phase 2 research:

| Gap ID | Knowledge Gap Description | Why Public Review Mining Cannot Answer It | Next Research Stream Needed (Phase 2) |
|---|---|---|---|
| **GAP-001** | **True Repeat-Booking & Churn Rates** across service categories | Public reviews lack denominator transaction data and cohort tracking. | Secondary financial analysis of Urban Company filings, investor decks, and industry benchmarks in Task 7. |
| **GAP-002** | **Customer Support Deflection & Resolution Rates** | Support ticketing logs, bot escalation percentages, and resolution times are internal proprietary data. | In-app product walkthrough of the live support ticketing flow in Task 6; secondary business press analysis in Task 7. |
| **GAP-003** | **Cancellation Attribution & Partner Penalty Rules** | Review text reports customer frustration, but cannot observe server-side dispatch logic or partner terms. | Deep-dive review of Urban Company partner terms of service, labor reporting, and regulatory filings in Task 7. |
| **GAP-004** | **Production Feature Status of Preferred-Professional Rebooking** | Customer reviews indicate reassignment friction, but cannot confirm if a "book again" feature exists in the current app. | Hands-on product teardown and UI walkthrough of the live Urban Company Android/iOS app in Task 6. |
| **GAP-005** | **Insta Help Unit Economics & Supply Incentives** | Customer reviews show partner no-shows, but cannot explain why gig workers reject instant domestic chore bookings. | Secondary labor and gig economy market analysis on on-demand chores in Task 7. |
| **GAP-006** | **Pre-Booking Trust Barriers for Prospective Non-Bookers** | App store reviews reflect only transacting customers who already overcame initial trust hurdles to book. | Optional primary user interviews with home service consumers in Task 8. |

---

## 10. Evidence Integrity & Compliance Statement

This document serves as the **canonical user research synthesis** for PM-01 and adheres to the highest standards of evidence integrity:

1. **Strict Provenance:** Every factual statement and qualitative pattern is linked to an explicit Evidence ID (`E001`–`E037`) registered in [`05_evidence_matrix.md`](data/evidence_matrix.md) and traced to source artifacts (`S001`–`S006`).
2. **Dual-Confidence Calibration:** Confidence ratings follow the approved methodology, decoupling phenomenon existence (High) from sample prevalence (Medium) where sample sizes are small ($n \le 7$). Level 1 firsthand product observations are classified as `FACT`.
3. **No Phantom Metrics:** No percentages or metrics are cited without explicit numerators and denominators.
4. **Anti-Confirmation Bias:** Contradictory evidence (`CON-001`–`CON-004`) is explicitly preserved, and the initial project hypothesis (H1: Repeat-Booking UX) is candidly recognized as challenged by low sample prevalence ($3.4\%$) relative to pricing ($25.7\%$) and quality ($28.5\%$).
5. **No Solution Prematurity:** This document does not propose product solutions, PRDs, or strategic pivots; it establishes the empirical foundation for strategic decision-making in Task 5 and Phase 2 research.

---

## 11. Human Product Walkthrough — Task 6

### Walkthrough Context & Source Characterization
* **Source Type:** Human product observation / firsthand product walkthrough (Level 1 — direct product observation).
* **Source Documents:** 
  * `S005`: `Urban Company Booking.pdf` (28 pages, 28 screenshots)
  * `S006`: `Urban Comapny Cancellation and Support.pdf` (6 pages, 6 screenshots)
* **Execution Date:** 18 Sep 2026
* **Platform & Client:** iOS Application
* **Location Context:** Mumbai Central, Mumbai, Maharashtra
* **Account State & Limitation:** New account with zero historical bookings. Because there were no historical bookings, the actual post-booking order-history and rebooking experience could not be observed. Rebooking was not observable because the test account had no historical bookings (`E037`). This does NOT infer or establish that Urban Company lacks a rebooking feature.
* **Methodological Distinction:** This walkthrough represents direct product surface observation (UI/UX flow audit), NOT customer interview research, usability testing, or behavioral tracking. It documents what is observable on the screens, not how representative users interpret, feel, or behave across diverse contexts.

---

### A. Direct Observations (FACTS)

#### 1. Pre-Payment / Booking-Stage Transparency
* **Service Catalogue & Cart Displayed Price (`E020`):** In the AC service catalogue, service detail screen, and cart, the Foam-jet service for 2 ACs was displayed at ₹1,098, alongside a crossed-out prior price of ₹1,198 and a "₹100 saved" discount badge.
* **Cart & Slot Selection:** The cart displayed the service amount as ₹1,098. A post-booking voucher promotion ("₹500 Women's Salon voucher redeemable after booking") was present. Slot selected: Friday, Sep 18 at 06:30 PM (no surge pricing indicator on slot tile).
* **Checkout Screen (`E020`, `E023`):** After address and slot selection, the checkout screen displayed the service amount as ₹1,098. The checkout screen included legal reference text stating: *"By proceeding, you agree to our T&C, Privacy and Cancellation Policy"*.
* **Payment Screen Displayed Amount (`E021`):** The subsequent payment method selection screen displayed the header subtitle: *"Amount to pay: ₹1,197"*.
* **Displayed Price Difference Across Stages (`E022`):** The walkthrough observed a ₹99 difference between the service/cart amount (₹1,098) shown earlier in the flow and the subsequent payment-screen amount (₹1,197). The captured screens do not establish the cause or composition of the difference.

#### 2. Post-Booking / On-Site Price Mechanics
* **Service Detail Guidance on Quote Verification (`E024`):** The service detail FAQ explicitly includes the question: *"How can I verify the quote shared?"*.
* **Service Detail Guidance on Extra Charges (`E025`):** The service detail FAQ explicitly includes the question: *"What if I am being charged extra?"*.
* **AC Gas-Refill Quoting & Approval Policy (`E026`):** Step 4 of the 5-step service process walkthrough states: *"Gas refilling (if required): We'll provide a quote and only refill after your approval"*.

#### 3. Cancellation Policy
* **Assignment-Based Fee Trigger (`E027`):** The in-cart cancellation policy modal states that professionals block time for jobs, that cancellations can result in lost revenue for professionals, and that cancellation fees apply once a professional has been assigned.
* **Fee-Free Grace Period (`E028`):** The policy states that customers have some time after placing a request to cancel without incurring a fee. The modal does not specify the exact fee amount or the duration of the fee-free time window.

#### 4. Post-Service Recovery / Warranty
* **UC Warranty Covered Categories (`E033`):** Warranty documentation observed in the walkthrough states coverage for appliance repairs (AC, RO, washing machine repairs, etc.), pest control services, and painting services.
* **UC Warranty Explicit Exclusions (`E034`):** The policy explicitly states that warranty does NOT cover a new issue occurring post-service, nor any item or service not mentioned on the invoice.

#### 5. Account Architecture & Observability Boundaries
* **Help & Support Access (`E029`):** The user profile contains a prominent top-level navigation entry for "Help & support".
* **Help Center Information Architecture (`E030`):** The Help Center landing page organizes self-serve support into six main categories: *Account*, *Getting started with UC*, *Payment & UC Credits*, *UC Plus Membership*, *UC Safety*, and *Claim Warranty*.
* **Safety Disclosures (`E031`, `E032`):** Safety articles state that Urban Company conducts background verification on all service professionals and that an in-app SOS button is available for critical emergency support.
* **Account History & Rebooking (`E035`, `E036`, `E037`):** The profile features a "My Bookings" entry. Opening "My Bookings" displayed an empty state ("No bookings yet"). Rebooking was not observable because the test account had no historical bookings (`E037`).

---

### B. Product Implications (For Investigation Track D004)

1. **Pre-Payment / Booking-Stage Price Transparency:**
   * The presence of a ₹99 difference between checkout (₹1,098) and payment (₹1,197) without an itemized explanation visible on the captured payment screen suggests that price changes can occur immediately prior to payment authorization. For customers expecting to pay the cart price, this may create uncertainty or surprise if line items (such as platform fees or taxes) are not clearly broken down at the point of charge. Direct post-booking price revision was not observed in the walkthrough. Post-booking/on-site pricing mechanics were observed only through the documented quote-and-approval policy for variable work such as gas refilling.
2. **Post-Booking / On-Site Pricing Mechanics:**
   * The product includes dedicated FAQ entries covering quote verification and extra charges. The service description states that gas refilling, if required, requires a quote and customer approval.
3. **Cancellation Rule Ambiguity:**
   * While the economic rationale for cancellation fees (partner time-blocking) is clearly stated, the lack of quantified fee amounts or explicit grace period minutes in the captured modal means customers cannot predict the exact financial consequence of cancellation prior to booking.
4. **Post-Service Recovery & Warranty Boundaries:**
   * The walkthrough observed that any item or service not mentioned on the invoice is excluded from the stated warranty coverage. This may create a recovery boundary for work performed or charges incurred without being reflected on the platform invoice.
5. **Support Discoverability vs. Escalation Depth:**
   * Help topics are readily accessible from the profile, but the walkthrough only observed static help articles; the actual experience of disputing an extra charge or escaping automated deflection could not be observed on an account with no active jobs.

---

### C. Unknowns & Research Limitations

1. **Composition of the ₹99 Price Delta:** It is completely unknown whether the ₹99 represents a platform fee, taxes (GST), convenience fee, or surge pricing. The captured screens do not provide an itemized breakdown.
2. **Dynamic Fee Thresholds:** It is unknown whether the ₹99 fee is a flat fee, a percentage fee, or category/city-dependent.
3. **Cancellation Fee Schedule:** The exact monetary amount of cancellation fees, the fee escalation ladder, and the fee-free cancellation window duration are unobserved in the walkthrough.
4. **On-Site Quoting Compliance:** It cannot be established whether technicians actually provide quotes in-app before refilling gas or whether quotes are recorded on the platform invoice in practice.
5. **Live Dispute Escalation:** It is unknown how easy or difficult it is to reach a human support representative when reporting extra charges or claiming warranty, as no active dispute could be initiated.
6. **Production Rebooking Interface:** Because the test account had zero prior bookings, the rebooking UI, "Book Again" flows, and preferred-pro selection (if any) remain completely unobserved.

---

### D. Cross-Check Against Existing Review-Mining Evidence

Comparing direct product observations (`S005`, `S006`) against review-mining evidence (`E004`, `E012`, `E014`, `E008`, `E016`) reveals critical alignments, tensions, and unaddressed areas:

| Evidence Theme | Walkthrough Observations (`FACT`) | What the Walkthrough SUPPORTS | What the Walkthrough CONTRADICTS | What the Walkthrough DOES NOT ADDRESS |
|---|---|---|---|---|
| **E004 / E014: Pricing & Post-Booking Surcharges** | Service displayed at ₹1,098 (`E020`); Payment amount is ₹1,197 (`E021`); ₹99 difference between stages without visible breakdown (`E022`). FAQs address quote verification (`E024`) and extra charges (`E025`). | Supports the premise that displayed price amounts can change across booking and payment stages, and that extra charges are a recognized area of customer inquiry. | Contradicts any assertion that the app gives zero warning about on-site quotes; the service description explicitly states quotes and approval are required for gas refilling (`E026`). | Does not establish the cause of the ₹99 difference; does not observe actual post-booking price changes; does not measure review claims of checkout platform fees (e.g. ₹166 in `R0092`) or default weekend surge (₹200 in `R0058`). |
| **E012: Cancellation Penalties** | Policy explains assignment-based fees (`E027`) and mentions a fee-free period (`E028`). Checkout references policy (`E023`). | Supports the existence of platform cancellation fees and confirms they trigger upon professional assignment. | Contradicts any assertion that Urban Company charges cancellation fees instantly with zero grace period; policy explicitly cites a free cancellation window (`E028`). | Does not establish the exact fee amount (e.g. ₹50 fine reported in `R0145`); does not observe whether fees are levied when a partner fails to arrive or cancels unilaterally. |
| **E008: Customer Trust** | Safety help article cites background verification (`E031`) and in-app SOS button (`E032`). Profile has dedicated Help & Support (`E029`). | Supports the finding that Urban Company communicates pre-booking trust anchors and domestic safety measures in the product copy. | Contradicts any claim that the app lacks safety disclosures or support contact entry points. | Does not address acute in-home trust breaches (e.g. domestic discretion violations in `E015`) or customer perception during actual service delivery. |
| **E016: Appliance Repair / Secondary Damage** | Warranty documentation observed in the walkthrough states coverage for appliance repairs, pest control services, and painting services (`E033`), but excludes new post-service issues and uninvoiced items (`E034`). | Explains potential friction observed in reviews where post-service damage claims are rejected because the issue is classified as "new" or uninvoiced. | Contradicts any claim that Urban Company provides no warranty on appliance repairs; warranty documentation observed in the walkthrough states coverage for appliance repairs, pest control services, and painting services. | Does not observe warranty claim adjudication in practice, claim rejection rates, or technician dispute handling (`GAP-002`). |

*Critical Methodological Guardrails:*
- A policy existing in the UI does not prove customers experience it correctly.
- A visible FAQ does not prove customers understand it.
- A displayed price discrepancy does not prove overcharging.
- A cancellation policy does not prove fairness.
- A warranty policy does not prove successful recovery.

---

### E. D004-Specific Analysis (Investigation Focus Assessment)

The primary strategic focus selected in `D004` is **Post-Booking Price Predictability and Transparency** (under Option 4: Pricing Transparency / Cancellation Fairness). Below is an objective evaluation of the walkthrough evidence against the 10 core investigation questions:

1. **Can a customer reasonably understand the price before payment?**
   * **Verdict:** `PARTIALLY SUPPORTED`
   * *Evidence:* The base service price (₹1,098) is clearly communicated across catalogue, detail, cart, and initial checkout screens (`E020`). However, on the payment screen, the total changes to ₹1,197 without an itemized line-by-line explanation visible on the captured screen (`E021`, `E022`).
2. **Does the displayed service/cart amount remain consistent through payment?**
   * **Verdict:** `NOT ESTABLISHED` (Negative finding: Price was NOT consistent)
   * *Evidence:* Directly observed inconsistency: ₹1,098 displayed in cart and checkout vs. ₹1,197 displayed on payment screen (`E020`, `E021`, `E022`).
3. **If the amount changes, is the reason visibly explained?**
   * **Verdict:** `NOT ESTABLISHED`
   * *Evidence:* The captured payment screens (pages 24 and 26) show "Amount to pay: ₹1,197" but show no itemized explanation or breakdown of the ₹99 addition.
4. **Are additional charges identifiable before payment?**
   * **Verdict:** `PARTIALLY SUPPORTED`
   * *Evidence:* The user sees the final aggregate amount (₹1,197) before authorizing payment, but the specific components comprising the additional ₹99 are not identified on the captured screens.
5. **Are cancellation consequences presented before commitment?**
   * **Verdict:** `PARTIALLY SUPPORTED`
   * *Evidence:* The checkout screen references the Cancellation Policy before proceeding (`E023`), and the cart allows viewing the policy modal explaining that assignment triggers fees (`E027`). However, the specific fee amount is not presented on the checkout card itself.
6. **Is the cancellation policy sufficiently specific in the observed UI?**
   * **Verdict:** `NOT ESTABLISHED`
   * *Evidence:* The policy modal explains the economic rationale (partner time-blocking) and trigger condition (partner assigned), but omits the exact fee amount and exact duration of the fee-free period (`E027`, `E028`).
7. **Can a customer understand how to verify a quote?**
   * **Verdict:** `SUPPORTED BY WALKTHROUGH`
   * *Evidence:* The service detail FAQ explicitly provides answers to "How can I verify the quote shared?" and outlines that gas refilling requires prior quote approval (`E024`, `E026`).
8. **Is there a visible support path for payment/cancellation/warranty issues?**
   * **Verdict:** `SUPPORTED BY WALKTHROUGH`
   * *Evidence:* "Help & support" is prominently featured in the profile, containing dedicated categories for "Payment & UC Credits", "UC Safety", and "Claim Warranty" (`E029`, `E030`).
9. **Does the walkthrough provide direct evidence of a product-surface issue relevant to price predictability?**
   * **Verdict:** `SUPPORTED BY WALKTHROUGH`
   * *Evidence:* The unexplained ₹99 price difference between checkout (₹1,098) and payment screen (₹1,197) provides direct Level 1 visual evidence of a displayed price difference across booking stages without an itemized line-item explanation on the captured payment screen (`E022`). Direct post-booking price revision was not observed in the walkthrough.
10. **Does any part of the walkthrough suggest the problem may instead be policy/operations rather than interface design?**
    * **Verdict:** `PARTIALLY SUPPORTED`
    * *Evidence:* The UI contains explicit policies requiring quotes for gas refilling (`E026`) and excluding uninvoiced work from warranty (`E034`). This suggests that customer review complaints regarding unexpected on-site charges may stem from on-site operational non-compliance or informal quoting rather than a complete absence of UI policy disclosures.

---

### F. Explicit Research Limitations

To maintain absolute evidence integrity, the following 12 research boundaries are strictly preserved:
1. **Single Account:** Only one test account was utilized for the walkthrough.
2. **Single Session:** Only one end-to-end booking session was conducted.
3. **No Behavioral Measurement:** The walkthrough does not measure real customer behavior, attention, or drop-off rates.
4. **No Transaction Volume Data:** The walkthrough does not measure transaction frequencies or aggregate booking volume.
5. **No Actual Pricing Error Rate:** The walkthrough cannot determine whether the ₹99 difference represents a system calculation error or a scheduled platform fee.
6. **Unexplained Price Difference:** The ₹99 difference is unexplained by the captured screens; its exact composition remains unverified.
7. **No Completed Booking:** No actual financial payment was processed and no service was completed.
8. **Rebooking Unobservable:** Rebooking and historical order management could not be tested due to zero prior bookings (`E037`).
9. **No Live Support Escalation:** Post-booking support ticket submission and AI deflection cannot be tested without an active order.
10. **No Cancellation Execution:** The actual operational cancellation flow, fee deduction, and refund timeline were not executed.
11. **No Refund Behavior Observed:** Platform refund speed and wallet vs. bank account return behavior were not observable.
12. **No Supply-Side Visibility:** Zero partner-side workflows, partner app screens, or dispatch algorithms were observed.

---

### G. Impact on D004

The walkthrough strengthens the investigation because it adds Level 1 product evidence in two adjacent areas:

1. **Booking/payment-stage price transparency:**  
   A ₹99 difference was directly observed between the earlier displayed amount and the payment-screen amount, with no visible itemized explanation in the captured payment screen.

2. **Post-booking/on-site pricing mechanics:**  
   The product explicitly documents quote verification, extra-charge questions, and customer approval before gas refilling.

However, the walkthrough does not establish the cause of the ₹99 difference, does not establish actual post-booking price changes, and does not establish customer harm, overcharging, or causal impact on retention.

*Investigation Status:* D004 remains the selected working investigation direction. Problem definition remains open pending remaining research, and no product solution has been selected.

---

*Document Status: CANONICAL USER RESEARCH & PRODUCT WALKTHROUGH COMPLETE (Task 3 & Task 6).*  
*Next Up: Task 7 — Secondary Market & Financial Research (Urban Company Business teardown).*

---

## 11. Task 8 Primary Research Feasibility & Omission Rationale

### Primary Research Consideration & Omission
Primary research (live user interviews) was initially considered as an optional method to investigate post-booking pricing predictability and validate assumptions regarding prospective non-bookers. 

However, **no interviews were conducted**.

### Rationale for Omission
* **Hard Feasibility Constraint:** The project owner established a hard constraint against conducting live interviews for this project.
* **Geographic/Availability Limitation:** The current operating environment and location do not provide a reliable way to recruit and verify real Urban Company users.
* **Evidence Integrity Enforcement:** To maintain strict evidence governance, no synthetic participants, hypothetical responses, simulated interviews, or fabricated quotes were generated to fill this gap.

### Impact on Evidence
This omission creates a genuine evidence limitation. We lack direct qualitative validation of user mental models surrounding post-booking pricing, cancellation reactions, and alternative-provider switching behavior from a controlled interview setting. All user-side qualitative evidence remains restricted to the asynchronous public review mining (Tasks 1-4).

### Appendix: Unexecuted Interview Guide
*(Note: The following neutral interview guide was drafted but strictly **NOT EXECUTED**. It does not constitute evidence and is retained only for methodological reference.)*

1. "Walk me through the last time you booked a home service."
2. "How did you know what you would eventually have to pay?"
3. "Did the amount you expected to pay change at any point? What happened?"
4. "How was the additional cost or any change in price communicated to you?"
5. "How did you decide whether to continue with the service or not?"
6. "Tell me about a time you cancelled a booking. What did you understand the cancellation consequences to be?"
7. "Tell me about the last time a professional suggested additional work during a service."
8. "What did you do after experiencing an unexpected charge or a service problem?"
9. "Have you ever gone back to a local provider or a different marketplace after such an experience?"
10. "Looking back at your recent bookings, how do you generally decide who to blame when something goes wrong with a service?"
