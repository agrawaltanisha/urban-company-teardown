# PM-01 — Urban Company
## 04 — Source Log

**Stage:** RESEARCH  
**Purpose:** Record every source used in this project, with full metadata, so that all claims are traceable.  
**Last updated:** 2026-09-17  

> **Rule:** Log every source at the moment it is used. Do not reconstruct sources after the fact. Do not use a source that is not logged here. Every claim in project artifacts must trace back to a Source ID registered in this log.

| **GAP-005** | Post-Diagnosis Abandonment Rate | Unknown | 2026-09-18 | Statistical frequency of transaction abandonment after diagnostic visitation fee is quoted. D004 magnitude remains unquantifiable without this. |
| **GAP-006** | True Net-Net Earnings Margin | Unknown | 2026-09-18 | Actual median gig worker wage after accounting for operational capital expenditures (data, vehicles, uniforms, idle time). |
| **GAP-007** | Off-Platform Leakage (Disintermediation) | Unknown | 2026-09-18 | Rate at which consumers and professionals take transactions off-app to bypass the 20-25% commission. |
---

## Source Log Format

Each entry follows this structure:

| Field | Description |
|-------|-------------|
| Source ID | Unique ID — format: S001, S002, S003... |
| Source name | Full title of article, report, dataset, or artifact |
| URL / path | Direct URL or local workspace file path |
| Source type | Tier A / B / C / D (per `RESEARCH_PROTOCOL.md`) or Internal Artifact |
| Evidence level | Level 1 to Level 5 (per `EVIDENCE_POLICY.md`) |
| Publication date | When the source was originally published / review date span |
| Date accessed | When the source was extracted or accessed |
| Geography | Country/region the data covers |
| Claim supported | What project claim(s) this source supports |
| Reliability | Assessed reliability — methodology, peer review, or verification status |
| Limitations | Biases, selection effects, scope constraints, unrepresentativeness |
| Notes | Role in project and boundary conditions |

---

## Source Registry

| Source ID | Source Name | URL / Path | Source Type | Evidence Level | Pub Date | Date Accessed | Geography | Claim Supported | Reliability | Limitations |
|-----------|-------------|------------|-------------|----------------|----------|---------------|-----------|-----------------|-------------|-------------|
| **S001** | Urban Company Google Play Store Review-Mining Dataset | [`PM01_Urban_Company_Cleaned.xlsx`](data/Urban_Company_Cleaned_Dataset.xlsx) | Tier C: Community / user evidence | Level 4: Public Community / User Evidence | 2019-06-12 to 2026-09-15 | 2026-09-16 | India | User sentiment, qualitative friction, support/cancellation/pricing signals, and repeat-booking preference | Useful for qualitative pattern discovery; zero numerical ratings fabricated | Self-selection bias, public review bias, skewed rating slice, 40 unrecoverable ratings; not representative of all UC users |
| **S002** | Review-Mining Dataset Audit & Data Quality Pipeline Report | [`DATA_QUALITY_ANALYSIS.md`](data/data_quality_analysis.md) | Internal Project Artifact (Audit) | Internal Verification | 2026-09-16 | 2026-09-16 | India / Internal | Dataset audit trail, schema profiling, missing rating resolution (`[RATING UNAVAILABLE]`), taxonomy mapping | High (fully audited via programmatic pipeline & scripts) | Internal audit only; supports dataset hygiene, not external market/user facts |
| **S003** | Sample Descriptive Analysis & Cross-Tabulation Report | [`DESCRIPTIVE_ANALYSIS.md`](data/descriptive_analysis.md) | Internal Project Artifact (Analysis) | Internal Descriptive Finding | 2026-09-16 | 2026-09-16 | India / Internal | Sample-level descriptive statistics, category breakdowns, topic distributions, rating cross-tabs | High internal mathematical validity for the N=179 sample | Sample-only statistics; strictly non-causal and non-generalizable to platform-wide base |
| **S004** | Qualitative Pattern Analysis & Candidate Synthesis Report | [`QUALITATIVE_PATTERN_ANALYSIS.md`](data/qualitative_pattern_analysis.md) | Internal Project Artifact (Synthesis) | Internal Candidate Synthesis | 2026-09-16 | 2026-09-16 | India / Internal | 10 candidate behavioral patterns (AI deflection, cancellation penalties, supply fragility, cost inflation, etc.) | Grounded with direct Review IDs and explicit contradicting reviews | Candidate pattern synthesis only; requires triangulation before declaring validated problems |
| **S005** | Urban Company iOS App Firsthand Walkthrough — Booking Flow | [`Urban_Company_Booking_Teardown.pdf`](../04_presentation_and_assets/Urban_Company_Booking_Teardown.pdf) | Firsthand Product Observation | Level 1: Direct Product Observation | 2026-09-18 | 2026-09-18 | Mumbai Central, India | Direct UI flow observations: Home, search, AC category hub, service detail, FAQs, cart, slot selection, checkout, payment screen (₹1,098 vs ₹1,197), and empty booking history | High (direct photographic screenshots from live production iOS app) | Single account, zero historical bookings, rebooking unobserved, payment breakdown unitemized in captured screens |
| **S006** | Urban Company iOS App Firsthand Walkthrough — Cancellation & Support | [`Urban_Company_Cancellation_Support.pdf`](../04_presentation_and_assets/Urban_Company_Cancellation_Support.pdf) | Firsthand Product Observation | Level 1: Direct Product Observation | 2026-09-18 | 2026-09-18 | Mumbai Central, India | Direct UI flow observations: In-cart cancellation policy modal, profile help navigation, Help center topics, UC safety article, and warranty coverage/exclusions | High (direct photographic screenshots from live production iOS app) | Static text inspection only; operational enforcement, fee amounts, and live dispute escalation unobserved |

---

## Detailed Source Records

### [S001] Urban Company Google Play Store Review-Mining Dataset
* **Source Name:** Urban Company Google Play Store Review-Mining Dataset (Raw + Normalized Cleaned)
* **File Locations:**
  * Cleaned & Normalized: [`PM01_Urban_Company_Cleaned.xlsx`](data/Urban_Company_Cleaned_Dataset.xlsx)
  * Raw (Preserved Unchanged): [`Urban_Company_Cleaned_Dataset.xlsx`](data/Urban_Company_Cleaned_Dataset.xlsx)
* **Source Type:** Tier C — Community / User Evidence (`RESEARCH_PROTOCOL.md`)
* **Evidence Classification:** Level 4 — Public Community / User Evidence (`EVIDENCE_POLICY.md`)
* **Publication Date Range:** 2019-06-12 to 2026-09-15
* **Extraction / Access Date:** 2026-09-16
* **Geography:** India (Urban Company Android Application)
* **Sampling Architecture:**
  * Total reviews: N = 179
  * Slice 1: `Most Relevant 5 Star` (n = 57)
  * Slice 2: `Most Relevant 4 Star` (n = 47)
  * Slice 3: `Newest` (n = 75)
* **Claims Supported:**
  * Real user perceptions of service quality, professional behavior, punctuality, and domestic discretion.
  * Direct user accounts of post-booking pricing inflation, inspection fees, and asymmetric cancellation charges.
  * Direct user friction regarding AI chatbot loops and lack of reachable human support.
  * Signals of customer desire to rebook specific professionals and frustration with platform-enforced reassignment.
* **Reliability Assessment:**
  * High qualitative integrity for uncovering user mental models, emotional triggers, and friction points.
  * Strict anti-fabrication rules enforced: zero ratings inferred from sentiment; 40 parsing-error rows in the `Newest` sheet audited and designated as `[RATING UNAVAILABLE]` (`Rating Status = NOT RECOVERABLE FROM REVIEW TEXT`).
* **Critical Limitations & Boundary Conditions:**
  * **Not representative of Urban Company's total user base:** Public app store reviewers represent a self-selected cohort biased toward extreme satisfaction or intense dissatisfaction.
  * **Sample skew:** Slices were chosen across 5-star, 4-star, and newest reviews, not random sampling across all historical transactions.
  * **Sample-Only Scope:** Must NEVER be cited as proof of platform-wide metrics (e.g., claiming "Urban Company has a 10.6% cancellation rate" is invalid; the valid statement is "10.6% of reviews in this sampled dataset mentioned cancellations").

---

### [S002] Review-Mining Dataset Audit & Data Quality Pipeline Report
* **Source Name:** PM-01 Review-Mining Dataset: Audit, Data Quality Pipeline & Taxonomy Analysis
* **File Location:** [`DATA_QUALITY_ANALYSIS.md`](data/data_quality_analysis.md)
* **Source Type:** Internal Project Artifact (Audit)
* **Evidence Classification:** Internal Verification
* **Creation Date:** 2026-09-16
* **Geography:** Internal
* **Claims Supported:**
  * Verification of the 179-row review dataset integrity and completeness.
  * Complete audit trail of the 40 missing-rating records in the `Newest` slice (100% verified unrecoverable, zero fabrication).
  * Programmatic taxonomy normalization from 102 fragmented raw categories into 6 core Service Verticals: *Platform/App*, *Appliance*, *Insta Help*, *Home Cleaning*, *Home Maintenance*, *Beauty/Salon*.
  * Generation of the correction queue and schema validation rules.
* **Reliability Assessment:** High. Generated via automated Python scripts (`generate_cleaned.py`) and verified against original spreadsheets.
* **Limitations:** Internal artifact only. Validates internal research hygiene and reproducibility; does not represent external market facts.

---

### [S003] Sample Descriptive Analysis & Cross-Tabulation Report
* **Source Name:** PM-01 Urban Company Review-Mining Dataset: Descriptive Analysis & Thematic Cross-Tabulations
* **File Location:** [`DESCRIPTIVE_ANALYSIS.md`](data/descriptive_analysis.md)
* **Source Type:** Internal Project Artifact (Analysis)
* **Evidence Classification:** Internal Descriptive Finding
* **Creation Date:** 2026-09-16
* **Geography:** Internal
* **Claims Supported:**
  * Sample composition: 179 total reviews, 139 valid ratings (mean = 4.41 among valid ratings), 40 unavailable ratings.
  * Sample topic frequencies: Quality (49.7%), Professional Behavior (45.3%), Pricing (15.6%), App/UX (15.1%), Cancellations (10.6%), Trust (5.0%), Rebooking (3.4%), Consistency (1.7%).
  * Cross-tabulations between service verticals, rating tiers, and negative/positive thematic tags.
* **Reliability Assessment:** High internal mathematical accuracy for the sampled N=179 dataset.
* **Limitations:** Purely descriptive. All statistics apply strictly to the sample (N=179). Does not infer causality or platform-level operational KPIs.

---

### [S004] Qualitative Pattern Analysis & Candidate Synthesis Report
* **Source Name:** PM-01 Urban Company Review Dataset: Qualitative Pattern Analysis & Behavioral Synthesis
* **File Location:** [`QUALITATIVE_PATTERN_ANALYSIS.md`](data/qualitative_pattern_analysis.md)
* **Source Type:** Internal Project Artifact (Synthesis)
* **Evidence Classification:** Internal Candidate Synthesis
* **Creation Date:** 2026-09-16
* **Geography:** Internal
* **Claims Supported:**
  * Identification of 10 candidate behavioral patterns:
    * `PAT-01`: Support deflection loop (AI chatbot barrier to human escalation).
    * `PAT-02`: Asymmetric cancellation penalty structure.
    * `PAT-03`: Supply fragility & cancellation cascades in Insta Help / on-demand services.
    * `PAT-04`: Post-booking scope/cost inflation and hidden fees.
    * `PAT-05`: Domestic intimacy and in-home privacy trust breaches.
    * `PAT-06`: Defective repair work and secondary appliance damage.
    * `PAT-07`: Partner demeanor, punctuality, and etiquette as the primary anchor of repeat loyalty.
    * `PAT-08`: Customer demand for professional continuity vs platform-enforced random reassignment.
    * `PAT-09`: Decoupled evaluation of gig partner vs corporate platform.
    * `PAT-10`: Silent churn following failed service recovery.
* **Reliability Assessment:** High qualitative grounding. Every pattern is tied to specific review IDs, counter-evidence, rating distributions, and alternative explanations.
* **Limitations:** Represents candidate patterns, not yet validated problem definitions. Requires triangulation with product walkthroughs and marketplace dynamics.

---

### [S005] Urban Company iOS App Firsthand Walkthrough — Booking Flow
* **Source Name:** Urban Company iOS App Firsthand Walkthrough — Discovery, Catalogue, Cart, Checkout, and Payment Flow
* **File Location:** [`Urban_Company_Booking_Teardown.pdf`](../04_presentation_and_assets/Urban_Company_Booking_Teardown.pdf)
* **Source Type:** Firsthand Product Observation (`RESEARCH_PROTOCOL.md`)
* **Evidence Classification:** Level 1 — Direct Product Observation (`EVIDENCE_POLICY.md`)
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** Mumbai Central, Mumbai, Maharashtra, India (Urban Company iOS Application)
* **Sampling & Inspection Scope:**
  * 28 sequential screenshot pages covering:
    - Homepage discovery & service categories (Pages 1–3)
    - AC Category Hub & service catalogue (Pages 4–7)
    - Service detail page, process steps, warranty terms, Co-Pilot free gas check, and FAQs (Pages 8–16)
    - Cart interaction & annual plan upsell (Pages 17–20)
    - Address and time-slot scheduling modal (Pages 21–22)
    - Checkout review & legal policy links (Page 23)
    - Payment selection screens (Pages 24–26)
    - Profile hub and empty My Bookings history (Pages 27–28)
* **Claims Supported:**
  * Direct observation of displayed service pricing (₹1,098 in cart and checkout vs. ₹1,197 on payment screen; ₹99 difference).
  * Direct observation of service inclusions, pre-service inspection rules, and gas refill quote authorization policy.
  * Direct observation of FAQ guidance on quote verification and extra charges.
  * Direct observation of checkout policy links (T&C, Privacy, Cancellation Policy).
  * Direct observation of empty state in My Bookings for an account with zero prior transactions.
* **Reliability Assessment:** High. Primary photographic evidence captured directly from a live production iOS client.
* **Critical Limitations & Boundary Conditions:**
  * Single test account with no prior bookings; longitudinal rebooking could not be observed.
  * The captured payment screens display the total amount to pay (₹1,197) without an itemized breakdown explaining the ₹99 difference.
  * No completed financial transaction was processed.

---

### [S006] Urban Company iOS App Firsthand Walkthrough — Cancellation & Support
* **Source Name:** Urban Company iOS App Firsthand Walkthrough — Cancellation Policy Modal, Help Center, Safety, and Warranty Information Architecture
* **File Location:** [`Urban_Company_Cancellation_Support.pdf`](../04_presentation_and_assets/Urban_Company_Cancellation_Support.pdf)
* **Source Type:** Firsthand Product Observation (`RESEARCH_PROTOCOL.md`)
* **Evidence Classification:** Level 1 — Direct Product Observation (`EVIDENCE_POLICY.md`)
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** Mumbai Central, Mumbai, Maharashtra, India (Urban Company iOS Application)
* **Sampling & Inspection Scope:**
  * 6 sequential screenshot pages covering:
    - In-cart Cancellation Policy modal (Page 1)
    - User profile support entry point (Page 2)
    - Help Center top-level topic directory (Page 3)
    - UC Safety precautionary measures article (Page 4)
    - Warranty FAQ list and coverage/exclusion article (Pages 5–6)
* **Claims Supported:**
  * Direct text of the in-app Cancellation Policy: rationale (technician time blocking), trigger condition (professional assigned), and grace period statement.
  * Direct information architecture of Help & Support (6 primary categories: Account, Getting started, Payment & UC Credits, UC Plus, Safety, Warranty).
  * Direct text of UC Safety commitments: mandatory background verification and in-app SOS emergency button.
  * Direct text of UC Warranty scope (Appliance repair, pest control, painting) and explicit exclusions (new issues post-service, uninvoiced items).
* **Reliability Assessment:** High. Primary photographic evidence captured directly from a live production iOS client.
* **Critical Limitations & Boundary Conditions:**
  * Static UI content inspection only; does not observe operational fulfillment, fee enforcement thresholds, or live customer dispute resolution.
  * Does not establish numerical cancellation fee amounts (e.g., ₹50) or exact fee-free time windows.

---


---

### [S007] Urban Company FY2024 Annual Business Summary
* **Source Name:** Urban Company FY2024 Annual Business Summary
* **File Location:** investor.urbancompany.com
* **Source Type:** OFFICIAL / PRIMARY (Corporate Disclosure)
* **Evidence Classification:** Level 2 — Official Corporate Claims
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** India
* **Claims Supported:** FY24 consolidated revenue, PBT losses, partner earnings (top 20%).
* **Reliability Assessment:** High for stated official metrics; low for extrapolating median reality.
* **Critical Limitations & Boundary Conditions:** Does not disclose granular category-level unit economics or dispute resolution costs.

---

### [S008] Urban Company 12-Point Partner Welfare Program
* **Source Name:** Urban Company 12-Point Partner Welfare Program PR Blog
* **File Location:** urbancompany.com/blog
* **Source Type:** OFFICIAL / PRIMARY (Company PR)
* **Evidence Classification:** Level 2 — Official Corporate Claims
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** India
* **Claims Supported:** 100% cancellation fee pass-through, commission slab reduction (30% to 25%), algorithmic block removals.
* **Reliability Assessment:** High for stated policy change at the time of announcement.
* **Critical Limitations & Boundary Conditions:** Stated corporate policy change (historical 2021-2024 context); actual current enforcement and algorithmic weighting variables remain unverified.

---

### [S009] Urban Company AC Service Pricing Rate Card
* **Source Name:** Urban Company AC Service & Installation Charges Rate Card
* **File Location:** urbancompany.com
* **Source Type:** OFFICIAL / PRIMARY (Official Policy)
* **Evidence Classification:** Level 2 — Official Corporate Policy
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** India
* **Claims Supported:** Granular upfront parts pricing, visitation fee mechanisms.
* **Reliability Assessment:** High (Official terms).
* **Critical Limitations & Boundary Conditions:** Does not account for unanticipated, non-catalogued bespoke parts.

---

### [S010] Urban Company Painting Services Terms
* **Source Name:** Urban Company Painting Services Terms & Pricing
* **File Location:** urbancompany.com
* **Source Type:** OFFICIAL / PRIMARY (Official Policy)
* **Evidence Classification:** Level 2 — Official Corporate Policy
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** India
* **Claims Supported:** Phased escrow for macro-projects (at-home consultation, exact quoting, 35% upfront).
* **Reliability Assessment:** High (Official terms).
* **Critical Limitations & Boundary Conditions:** Applies only to specific macro-project categories.

---

### [S011] Urban Company Extended Warranty Terms
* **Source Name:** Urban Company Extended Warranty Terms & Conditions
* **File Location:** urbancompany.com
* **Source Type:** OFFICIAL / PRIMARY (Official Policy)
* **Evidence Classification:** Level 2 — Official Corporate Policy
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** India
* **Claims Supported:** Standard warranty duration, damage protection cap, extended warranty exclusions.
* **Reliability Assessment:** High (Official terms).
* **Critical Limitations & Boundary Conditions:** Legal T&Cs; does not track specific claim rejection rates.

---

### [S012] Urban Company General Cancellation Policy
* **Source Name:** Urban Company General Cancellation Policy
* **File Location:** urbancompany.com
* **Source Type:** OFFICIAL / PRIMARY (Official Policy)
* **Evidence Classification:** Level 2 — Official Corporate Policy
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** India
* **Claims Supported:** India cancellation penalties by time & vertical.
* **Reliability Assessment:** High (Official terms).
* **Critical Limitations & Boundary Conditions:** Exact penalty caps may vary by geography and time remaining.

---

### [S013] Urban Company Singapore Cleaning Services Page
* **Source Name:** Urban Company Singapore Cleaning Services Page
* **File Location:** urbancompany.com/sg
* **Source Type:** OFFICIAL / PRIMARY (Official Policy)
* **Evidence Classification:** Level 2 — Official Corporate Policy
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** Singapore
* **Claims Supported:** Singapore cancellation penalties.
* **Reliability Assessment:** High (Official terms).
* **Critical Limitations & Boundary Conditions:** Specific to Singapore market.

---

### [S014] Fairwork India Ratings
* **Source Name:** Fairwork India Ratings (2019 & 2024)
* **File Location:** fair.work
* **Source Type:** INDEPENDENT (Institutional Watchdog)
* **Evidence Classification:** Level 2 — Independent Audit
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** India
* **Claims Supported:** Labor conditions scores, fair representation.
* **Reliability Assessment:** High (Institutional academic rating).
* **Critical Limitations & Boundary Conditions:** High-level platform score does not parse individual transaction-level pricing disputes.

---

### [S015] TaskRabbit Trust & Support Fee Policy
* **Source Name:** TaskRabbit Trust & Support Fee Policy
* **File Location:** taskrabbit.com
* **Source Type:** OFFICIAL / PRIMARY (Competitor Policy)
* **Evidence Classification:** Level 2 — Official Corporate Policy
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** USA / Global
* **Claims Supported:** Dynamic percentage-based fee structure.
* **Reliability Assessment:** High (Official terms).
* **Critical Limitations & Boundary Conditions:** Different geography and labor market.

---

### [S016] TaskRabbit Expense Policy
* **Source Name:** TaskRabbit Expense Policy
* **File Location:** taskrabbit.com
* **Source Type:** OFFICIAL / PRIMARY (Competitor Policy)
* **Evidence Classification:** Level 2 — Official Corporate Policy
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** USA / Global
* **Claims Supported:** Material expense reimbursements caps ($100-$150).
* **Reliability Assessment:** High (Official terms).
* **Critical Limitations & Boundary Conditions:** Applies to TaskRabbit only.

---

### [S017] TaskRabbit Cancellation Policy
* **Source Name:** TaskRabbit Cancellation Policy
* **File Location:** taskrabbit.com
* **Source Type:** OFFICIAL / PRIMARY (Competitor Policy)
* **Evidence Classification:** Level 2 — Official Corporate Policy
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** USA / Global
* **Claims Supported:** TaskRabbit cancellation terms.
* **Reliability Assessment:** High (Official terms).
* **Critical Limitations & Boundary Conditions:** Applies to TaskRabbit only.

---

### [S018] Thumbtack Terms of Use
* **Source Name:** Thumbtack Terms of Use
* **File Location:** thumbtack.com
* **Source Type:** OFFICIAL / PRIMARY (Competitor Policy)
* **Evidence Classification:** Level 2 — Official Corporate Policy
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** USA / Global
* **Claims Supported:** Decentralized lead-gen platform architecture.
* **Reliability Assessment:** High (Official terms).
* **Critical Limitations & Boundary Conditions:** Different geographic market and platform architecture.

---

### [S019] TaskRabbit Reddit Community Discussions
* **Source Name:** TaskRabbit Reddit Threads (Two specific threads)
* **File Location:** reddit.com/r/TaskRabbit
* **Source Type:** COMMUNITY (Community Evidence)
* **Evidence Classification:** Level 4 — Public Community Evidence
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** USA / Global
* **Claims Supported:** Consumer hostility to Trust & Support Fees (alleged 30-40% markup).
* **Reliability Assessment:** Low (Downgraded due to expressive/reactionary bias; exact percentage lacks statistical rigor).
* **Critical Limitations & Boundary Conditions:** Unverified anecdotal claims; used for subjective community perception only.

---

### [S020] NITI Aayog Gig Economy Report
* **Source Name:** NITI Aayog Gig Economy Report
* **File Location:** niti.gov.in
* **Source Type:** INDEPENDENT (Macro Data)
* **Evidence Classification:** Level 1 — Institutional Data
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** India
* **Claims Supported:** 7.7M gig workforce baseline (2020-21).
* **Reliability Assessment:** High (Institutional macro projections).
* **Critical Limitations & Boundary Conditions:** Macro estimates; no platform-specific insight.

---

### [S021] Economic Survey 2023-2024
* **Source Name:** Economic Survey 2023-2024
* **File Location:** indiabudget.gov.in
* **Source Type:** INDEPENDENT (Macro Data)
* **Evidence Classification:** Level 1 — Institutional Data
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** India
* **Claims Supported:** 23.5M gig workforce projection by 2030.
* **Reliability Assessment:** High (Institutional macro projections).
* **Critical Limitations & Boundary Conditions:** Macro estimates; no platform-specific insight.

---

### [S022] Gemini Triangulation Research Corpus
* **Source Name:** Gemini Triangulation Research PDF / Synthesis Corpus
* **File Location:** Urban Company Triangulation Research - Google Docs.pdf
* **Source Type:** SYNTHESIS (Aggregated Corpus)
* **Evidence Classification:** Level 5 — Synthesized Research
* **Observation Date:** 2026-09-18
* **Extraction / Inspection Date:** 2026-09-18
* **Geography:** Global / India
* **Claims Supported:** General context. **NOT PRIMARY EVIDENCE. NOT CITABLE AS ORIGINAL SOURCE. USED ONLY AS RESEARCH/SEARCH-DISCOVERY ARTIFACT.**
* **Reliability Assessment:** Medium.
* **Critical Limitations & Boundary Conditions:** Triangulation report serving as corpus; all facts must map to primary S007-S021.


## Source Count by Type

| Type | Tier / Classification | Count | Sources Included |
|------|-----------------------|-------|------------------|
| **Tier A** | Primary Sources (Filings, Investor Presentations, Official ToS) | 8 | S007, S008, S009, S010, S011, S012, S013, S015, S016, S017, S018 |
| **Tier B** | Firsthand Product Observation (App Walkthrough Screenshots) | 2 | S005, S006 |
| **Tier C** | Community / User Evidence (App Store Reviews, Reddit, Forums) | 2 | S001, S019 |
| **Tier D** | Model & Estimate Sources | 0 | Pending Phase 3/4 Modeling |
| **Internal** | Internal Project Audit & Analysis Artifacts | 3 | S002, S003, S004 |
| **Independent** | Institutional Watchdog / Macro Data | 3 | S014, S020, S021 |
| **Synthesis** | Synthesis Corpus (Not Primary Evidence) | 1 | S022 |
| **Total Registered Sources** | | **19** | S001 – S022 |

---

## Evidence Gap Log

Record searches that returned no useful results or data points that cannot be resolved through current sources.

| Gap ID | Topic / Query | Target Domain | Date Logged | Status / Impact |
|--------|--------------|---------------|-------------|-----------------|
| **GAP-001** | Platform-wide repeat booking rate by vertical | Internal UC Operational Data | 2026-09-17 | Cannot be proven via public app reviews; must remain an explicit estimate or hypothesis in later modeling. |
| **GAP-002** | Customer support ticket resolution rate & deflection metrics | Internal UC Support Operations | 2026-09-17 | Review text signals strong AI deflection friction; S006 reveals top-level Help directory, but internal resolution and bot containment rates remain unknown. |
| **GAP-003** | Partner-side cancellation incentives & penalty mechanics | Supply-Side Economics / Partner App | 2026-09-17 | Requires external secondary research on UC partner policies and worker reports in Phase 2 (Task 7). |
| **GAP-004** | Current native UX flow for "Rebook Same Professional" | App Walkthrough / Product Inspection | 2026-09-17 | Partially inspected in Task 6 (S005 Page 27–28). "My bookings" exists, but rebooking flow was unobservable due to test account having zero prior bookings. Remains an active knowledge gap. |

---

*Stage: RESEARCH — S001–S006 registered and verified.*  
*Last updated: 2026-09-18 (Task 6 Walkthrough Sources Registered)*
