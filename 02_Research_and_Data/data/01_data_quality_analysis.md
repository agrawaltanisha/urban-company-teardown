# PM-01 — Urban Company: Trust & Repeat-Booking in a Two-Sided Marketplace
# Review-Mining Dataset: Audit, Data Quality Pipeline & Taxonomy Analysis

**Document Type:** Research Dataset Audit & Quality Analysis  
**Project:** PM-01 (Urban Company)  
**Author:** Research / Data Analyst  
**Date:** 2026-09-16  
**Status:** COMPLETE — AUDIT VERIFIED  
**Raw Source File:** [`Urban_Company_Cleaned_Dataset.xlsx`](Urban_Company_Cleaned_Dataset.xlsx) *(Preserved 100% Unchanged)*  
**Cleaned Dataset:** [`PM01_Urban_Company_Cleaned.xlsx`](Urban_Company_Cleaned_Dataset.xlsx) *(Generated Separately)*  
**Primary Backup:** `scratch/PM01_Urban_Company_backup.xlsx`

---

## 1. Executive Overview

This document synthesizes the complete investigative, auditing, and data quality pipeline performed on the Google Play Store review-mining dataset for **PM-01 Urban Company**.

The review mining was collected as Assignment 1 across three operational slices:
1. `Most Relevant 5 Star` (57 reviews)
2. `Most Relevant 4 Star` (47 reviews)
3. `Newest` (75 reviews)
Total records: **179 reviews**.

The data quality pipeline was carried out in two distinct phases:
1. **The Star-Rating Missing Field Audit & Repair:** Resolving parsing/extraction failures in the `Rating` field under strict zero-fabrication rules.
2. **The Automated Data Quality & Taxonomy Pipeline:** End-to-end schema profiling, deduplication, format normalization, sentiment/rating contradiction checks, category taxonomy consolidation, and generation of a structured correction queue.

In strict compliance with `/Users/testuser/Documents/Learning OS/00_Portfolio/EVIDENCE_POLICY.md` and `/Users/testuser/Documents/Learning OS/00_Portfolio/AGENTS.md`:
* **Zero numerical ratings were invented, guessed, or inferred from sentiment.**
* **Zero ambiguous ratings were silently modified.**
* **The raw dataset was preserved untouched; all transformations exist in a distinct cleaned workbook.**

---

## 2. Phase 1: Star-Rating Missing Field Audit & Repair

### 2.1 The Problem Statement
During review collection from the Google Play Store, an extraction/parsing bug failed to capture the numerical star rating for 40 rows in the `Newest` sheet, resulting in `'Not provided'`. Sheets 1 and 2 had valid numeric ratings (5.0 and 4.0 respectively).

### 2.2 Core Mandate & Anti-Fabrication Constraints
* **Hard Rule:** Sentiment is NOT the same as a star rating. An author writing a scathing complaint cannot be assigned a `1.0` unless "1 star" is explicitly stated in the text. An author writing "great service" cannot be assigned a `5.0`.
* **Standard Placeholder:** Unrecoverable star ratings must be labeled exactly `[RATING UNAVAILABLE]`.
* **Provenance Field:** Every row must record a `Rating Status`:
  * `ORIGINAL`
  * `RECOVERED FROM REVIEW TEXT`
  * `NOT RECOVERABLE FROM REVIEW TEXT`
  * `NO RATING FIELD`

### 2.3 Full-Text Inspection Results
Every single review text among the 40 missing entries was audited for explicit star declarations (e.g., "1 star", "rated 2/5", "giving 3 stars").
* **Total rows examined:** 40
* **Explicit ratings found in review text:** **0**
* **Total ratings recovered:** **0**
* **Total ratings marked `[RATING UNAVAILABLE]`:** **40**

### 2.4 Deep-Dive into Ambiguous Cases
Several reviews contained numbers or sentiment keywords requiring rigorous scrutiny to prevent false-positive recoveries:

1. **`R0158` ("bohot ghatiya app hai... support k naam pe 0"):**
   * *Number detected:* "0"
   * *Analysis:* Colloquial Hindi expression meaning *"zero in the name of support"* (critique of customer care absence). Google Play Store enforces a strict 1–5 star scale; a 0-star rating does not exist on the platform.
   * *Resolution:* Retained as `[RATING UNAVAILABLE]`, `NOT RECOVERABLE FROM REVIEW TEXT`. Note: *"Review text mentions 'support k naam pe 0' (colloquial expression for non-existent support); not a numerical star rating (Play Store scale is 1-5)."*
2. **`R0176` ("...This has happened to me 4–5 times."):**
   * *Numbers detected:* "4–5"
   * *Analysis:* The context explicitly defines frequency: *"This has happened to me 4–5 times"* regarding booking cancellations. It is not a rating.
   * *Resolution:* Retained as `[RATING UNAVAILABLE]`, `NOT RECOVERABLE FROM REVIEW TEXT`. Note: *"Review text mentions '4–5 times' referring to cancellation frequency, not a star rating."*
3. **`R0129` ("great service"):**
   * *Sentiment:* Unambiguously Positive.
   * *Analysis:* Contains no star rating or score. Guessing 5 stars would violate the core research integrity policy.
   * *Resolution:* Retained as `[RATING UNAVAILABLE]`, `NOT RECOVERABLE FROM REVIEW TEXT`. Note: *"Review text has positive sentiment ('great service') but contains no explicit numerical star rating; rating cannot be inferred from sentiment."*
4. **Monetary Charges (`R0115`, `R0145`, `R0163`, `R0165`):**
   * Mentions `₹50` cancellation fees, `500` / `200` rupees paid to mechanics, `extra 200` weekend surge fees. None represent ratings.
5. **Durations & Dates (`R0116`, `R0125`, `R0166`, `R0167`, `R0177`):**
   * Mentions `~10 hours`, `24 August`, `2 week`, `24 hours`, `15 days`, `6, 8, 14 September`, `after 2p` (2 PM). None represent ratings.

### 2.5 Audit Log of All 40 Repaired Rows (Sheet: `Newest`)

| # | Review ID | Sheet Row | Service Category | Sentiment | Review Quote (Excerpt) | Rating Status | Audit Note |
| :---: | :---: | :---: | :--- | :---: | :--- | :---: | :--- |
| 1 | `R0106` | 3 | General/expansion request | Neutral | *"expand your services to telangana towns like..."* | `NOT RECOVERABLE` | Review is an expansion request; contains no numerical star rating. |
| 2 | `R0108` | 5 | Insta Help | Negative | *"Even after your booking is confirmed they kee..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 3 | `R0109` | 6 | General/privacy | Negative | *"someone was watching my home via a video call..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 4 | `R0110` | 7 | General/pricing | Negative | *"fraud company not mention properly charge ext..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 5 | `R0111` | 8 | AC service | Negative | *"Buy a new AC from the market and—courtesy ..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 6 | `R0112` | 9 | Mixer grinder repair | Negative | *"bakwas tumre pass mixer grinder repair ka ..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 7 | `R0113` | 10 | Window AC cleaning | Negative | *"for windows ac cleaning they clean only fr..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 8 | `R0114` | 11 | General | Negative | *"not good"* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 9 | `R0115` | 12 | App booking/cancellation | Negative | *"an order was booked by mistake... forced m..."* | `NOT RECOVERABLE` | Review mentions monetary fee (₹50 cancellation fee), not a star rating. |
| 10 | `R0116` | 13 | Insta Help/customer support | Negative | *"finally after ~10 hours it's connected to ..."* | `NOT RECOVERABLE` | Review mentions wait time (~10 hours), not a star rating. |
| 11 | `R0117` | 14 | Customer support | Negative | *"Their service has started degrading by the..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 12 | `R0118` | 15 | AC cleaning | Negative | *"After AC cleaning, whole AC got Complaint ..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 13 | `R0125` | 22 | Insta Help/maid | Negative | *"24 August ko book kiya wi aaj tak na koi h..."* | `NOT RECOVERABLE` | Review mentions booking date (24 August) and duration (2 weeks), not a star rating. |
| 14 | `R0126` | 23 | Insta Help | Negative | *"On both occasions, I booked Insta Help, bu..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 15 | `R0127` | 24 | Cleaning/parlour | Negative | *"my fan switch stopped working and taps are..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 16 | `R0129` | 26 | General | Positive | *"great service"* | `NOT RECOVERABLE` | Review text has positive sentiment ('great service') but contains no explicit numerical star rating; rating cannot be inferred from sentiment. |
| 17 | `R0133` | 30 | General/transparency | Negative | *"they have stopped being transparent. servi..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 18 | `R0134` | 31 | Time slot | Negative | *"Urban keeps changing our required time slo..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 19 | `R0136` | 33 | Insta Help/AC cooler | Negative | *"Instant helper visits and denies the work ..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 20 | `R0138` | 35 | Native water purifier | Negative | *"Native water purifier is worst product sin..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 21 | `R0139` | 36 | General | Negative | *"Service cancelled by your company. Disappo..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 22 | `R0143` | 40 | Professional conduct | Negative | *"I have had instances of them using my home..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 23 | `R0144` | 41 | General | Negative | *"worst company to deal with . cheaters"* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 24 | `R0145` | 42 | Insta Help/app support | Negative | *"I made a booking and the insta help said s..."* | `NOT RECOVERABLE` | Review mentions cancellation charge (₹50), not a star rating. |
| 25 | `R0148` | 45 | Pricing | Negative | *"beware of their pricing. They add addition..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 26 | `R0149` | 46 | App performance | Negative | *"app is too slow"* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 27 | `R0154` | 51 | Pricing | Negative | *"charges to much high i am never use this a..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 28 | `R0158` | 55 | General/AI support | Negative | *"bohot ghatiya app hai... support k naam pe..."* | `NOT RECOVERABLE` | Review text mentions 'support k naam pe 0' (colloquial expression for non-existent support); not a numerical star rating (Play Store scale is 1-5). |
| 29 | `R0160` | 57 | Spare part/after-sales | Negative | *"I paid for a new spare part, but an old/us..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 30 | `R0161` | 58 | General | Negative | *"Very unprofessional service.There are no o..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 31 | `R0163` | 60 | Mechanic service | Negative | *"I paid 500 and he did nothing. Called anot..."* | `NOT RECOVERABLE` | Review mentions service amounts paid (₹500 / ₹200), not a star rating. |
| 32 | `R0164` | 61 | Workforce | Negative | *"Workforce discrimination by their religiou..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 33 | `R0165` | 62 | Booking/pricing | Negative | *"booking a slot always end up on weekend wi..."* | `NOT RECOVERABLE` | Review mentions weekend slot charge (extra ₹200), not a star rating. |
| 34 | `R0166` | 63 | Geyser service | Negative | *"water will be dripping for next 24 hours (..."* | `NOT RECOVERABLE` | Review mentions duration periods (24 hours, 15 days), not a star rating. |
| 35 | `R0167` | 64 | RO installation | Negative | *"6 सितंबर को RO की डिलीवरी हुई थी और 8 सितं..."* | `NOT RECOVERABLE` | Review mentions calendar dates (6, 8, 14 September), not a star rating. |
| 36 | `R0170` | 67 | Offer/customer support | Negative | *"I am searching for any helpline number or ..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 37 | `R0174` | 71 | Bathroom cleaning | Negative | *"recently in bathroom cleaning urban compan..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |
| 38 | `R0176` | 73 | Insta Help | Negative | *"They seem to use bot profiles to accept bo..."* | `NOT RECOVERABLE` | Review text mentions '4–5 times' referring to cancellation frequency, not a star rating. |
| 39 | `R0177` | 74 | General | Negative | *"useless app any time they will sey sry .. ..."* | `NOT RECOVERABLE` | Review mentions arrival time ('after 2p'); contains no numerical star rating. |
| 40 | `R0179` | 76 | Insta Help | Mixed | *"insta help now a days they are taking musl..."* | `NOT RECOVERABLE` | Review text contains qualitative feedback but no explicit numerical rating or star score. |

---

## 3. Phase 2: Automated Data Quality Pipeline Findings

### 3.1 Schema & Field Completeness Profiling

| Field Name | Type | Completeness | Required Field Status | Data Quality Finding |
| :--- | :--- | :---: | :---: | :--- |
| `Review ID` | String | 179 / 179 (100%) | Mandatory Key | Unique. Contains zero-padding format drift. |
| `Date` | Date/Timestamp | 179 / 179 (100%) | Mandatory Metadata | 100% valid. Span: 2019-06-12 to 2026-09-15. |
| `Rating` | Float / String | 179 / 179 (100%) | Mandatory Metric | 139 valid numeric ratings, 40 audit placeholders. |
| `Service category` | String | 179 / 179 (100%) | Mandatory Dimension | 102 distinct labels; un-normalized taxonomy. |
| `Sentiment` | String | 179 / 179 (100%) | Categorical | 4 values (`Positive`, `Negative`, `Mixed`, `Neutral`). |
| `Topics` | String | 179 / 179 (100%) | Tag List | Semicolon delimited. High semantic fragmentation. |
| `Relevant quote` | String | 179 / 179 (100%) | User Evidence | Preserved verbatim. Zero corrupted strings. |
| `Observation` | String | 179 / 179 (100%) | Synthesis Log | 100% present. Succinct factual descriptions. |
| `Rating Status` | String | 179 / 179 (100%) | Provenance Tag | `ORIGINAL` (139) or `NOT RECOVERABLE` (40). |
| `Notes` | String | 40 / 179 (22.3%) | Explanatory Audit | Detailed audit rationale for all 40 repaired rows. |

### 3.2 Deduplication Audit
* **Review ID Duplicates:** **0**. Zero primary key collisions.
* **Exact Duplicate Quotes:** Exactly **1** single-word quote (`"good"`) occurs 6 times across separate rows in the `Newest` sheet (`R0123`, `R0124`, `R0146`, `R0151`, `R0173`, `R0175`). Inspection confirmed these represent independent short user submissions on 2026-09-14.
* **Near-Duplicate / Paraphrased Quotes:** **0** instances found (SequenceMatcher ratio > 0.80).

### 3.3 Formatting & Structural Anomalies
* **Zero-Padding Drift in Review IDs:**
  * Sheet 1 (`Most Relevant 5 Star`): Uses 3 digits (`R001` through `R057`).
  * Sheet 2 (`Most Relevant 4 Star`): Switches to 4 digits (`R0058` through `R0104`).
  * Sheet 3 (`Newest`): Continues with 4 digits (`R0105` through `R0179`).
  * *Correction applied in cleaned file:* Standardized all IDs to canonical 4-digit zero padding (`R0001` to `R0179`) to ensure correct alpha-numeric sorting in spreadsheets and SQL databases.
* **Topic Formatting:** Delimiters are 100% clean semicolons (`;`); zero instances of double semicolons or dangling delimiters.

---

## 4. Taxonomy & Semantic Analysis

### 4.1 Topic Folksonomy vs. Controlled Vocabulary
The dataset contains **571 total topic instances** mapping to **475 unique strings**. This indicates free-form, ad-hoc tagging without a controlled vocabulary.

Key synonym clusters identified:
* **Punctuality:** `punctual` (8), `on time` (5), `punctuality` (4), `arrival on time` (1), `punctual service` (1), `delayed` (1).
* **Professionalism:** `professional` (11), `professionalism` (8), `professional service` (1), `professional conduct` (1), `polite behavior` (1), `courteous` (3).
* **Quality of Work:** `good` (9), `good service` (5), `service good` (4), `quality` (5), `neat work` (2), `proper work` (2).
* **Support & Resolution:** `no customer care` (3), `support k naam pe 0` (1), `support access` (1), `complaint response` (1), `unhelpful support` (1).

### 4.2 Service Category Consolidation & Standardized Verticals
The raw dataset contains **102 unique service category strings** across 179 rows. Three primary flaws were identified:
1. **Professional Personal Name entered as Category:** `R043` is tagged with `Technician Shabir`.
2. **Plurality / Redundancy Inconsistency:** `General services` (15 rows) and `General service` (3 rows) alongside `General` (36 rows).
3. **Problem Dimensions Tagged as Categories:** 31 reviews used operational problem dimensions (`App UX`, `Pricing`, `Booking/pricing`, `Time slot`, `Workforce`, `Worker welfare`, `Professional conduct`, `General/privacy`) instead of service categories.

To resolve this without losing raw data, a two-tier hierarchy was established:

```
Urban Company Marketplace
├── 1. Platform, App & Support (85 reviews, 47.5%)
│      [Cross-service policies, app performance, surge pricing, cancellations, customer care]
├── 2. Appliance Repair & Servicing (42 reviews, 23.5%)
│      [AC, Water Purifier / RO, Geyser, Washing Machine, Refrigerator, Microwave]
├── 3. Insta Help & Daily Services (26 reviews, 14.5%)
│      [On-demand maids, cooks, helpers, utensil cleaning]
├── 4. Home Cleaning & Pest Control (16 reviews, 8.9%)
│      [Bathroom cleaning, Deep home cleaning, Sofa cleaning, Housekeeping]
├── 5. Home Maintenance & Repairs (7 reviews, 3.9%)
│      [Electrician, Plumber, Carpenter, Furniture assembly]
└── 6. Beauty, Salon & Spa (3 reviews, 1.7%)
       [Haircut, Massage, Parlour services]
```

### 4.3 Sentiment & Rating Dissonance Audit

#### A. Rating Contradiction Flagged (`R009`)
* **Review ID:** `R009`
* **Sheet:** `Most Relevant 5 Star` | **Rating:** `5.0`
* **Raw Sentiment:** `Negative`
* **Quote:** *"If the service cannot provide help within a reasonable time, why is it marketed as 'Insta Help'?"*
* **Observation:** *Insta Help availability does not match promise.*
* **Audit Finding:** The review contains zero positive attributes. This could either be a sarcastic 5-star rating submitted by the user on Play Store to gain visibility, or an extraction misplacement. In accordance with Rule 7, **this was not silently overwritten**; it is flagged in the dataset as `AMBIGUOUS_RATING_CONTRADICTION`.

#### B. Sentiment Conflicts (Tagged `Positive` but Text is `Mixed` / Critical)
Six reviews in `Most Relevant 4 Star` were tagged `Positive`, but express serious friction, app bugs, or ethical violations. In the cleaned dataset, these have been marked as proposed corrections to `Mixed`:

1. **`R0060` (App Payment Bug):** *"The payment amount shown while confirming invoice and final payment is different... fix this bug"*.
2. **`R0069` (Missing Service Gap):** Expresses disappointment that no specific chemical or option is available for mosaic tile floors.
3. **`R0091` (Ethical Violation Allegation):** *"customers should not be asked to give a 5-star rating before the work is completed. It is unethical."*
4. **`R0092` (Excessive Platform Fees):** Complaints that app platform fee (₹166) and GST (₹34) inflated a ₹1,055 service.
5. **`R0093` (Service Deficiency):** Author states they deliberately deducted a star (gave 4 instead of 5) because parlour services were unsatisfactory.
6. **`R0095` (Worker Safety / Welfare):** Author flags neglect of injured workers by the company as a critical failure.

---

## 5. Complete Correction Queue

The correction queue captures all **83 identified items**, categorized by severity and confidence. All items are logged in the `Correction Queue` sheet of [`PM01_Urban_Company_Cleaned.xlsx`](Urban_Company_Cleaned_Dataset.xlsx).

### Priority Queue: Semantic & Tagging Conflicts (8 Items)

| Review ID | Standardized ID | Field | Issue Type | Raw Value | Cleaned Value | Reason / Justification | Confidence | Status |
| :---: | :---: | :--- | :--- | :--- | :--- | :--- | :---: | :---: |
| `R009` | `R0009` | `Rating` | Contradictory Rating vs Text | `5.0` | `5.0 (FLAGGED)` | Review in 5-star sheet is 100% negative critique of Insta Help. Ambiguous (possible ironic 5-star or scraper misplacement). Rating preserved; flagged for user review. | **MEDIUM** | `FLAGGED_UNRESOLVED` |
| `R043` | `R0043` | `Service category` | Personal Name in Category | `Technician Shabir` | `General service` | Technician personal name mistakenly entered into category column. Quote: *"Excellent service by Urban Company technician Shabir"*. | **HIGH** | `CLEANED` |
| `R0060` | `R0060` | `Sentiment` | Sentiment Tagging Conflict | `Positive` | `Mixed` | Review reports a financial app bug (*"payment amount shown while confirming invoice and final payment is different"*). Inappropriate `Positive` label. | **HIGH** | `PROPOSED_CLEANED` |
| `R0069` | `R0069` | `Sentiment` | Sentiment Tagging Conflict | `Positive` | `Mixed` | Review expresses dissatisfaction over missing mosaic cleaning options. | **HIGH** | `PROPOSED_CLEANED` |
| `R0091` | `R0091` | `Sentiment` | Sentiment Tagging Conflict | `Positive` | `Mixed` | Review calls UC's practice of demanding 5-star ratings prior to completion *"unethical"*. | **HIGH** | `PROPOSED_CLEANED` |
| `R0092` | `R0092` | `Sentiment` | Sentiment Tagging Conflict | `Positive` | `Mixed` | Review complains about high platform fees (₹166 app fee on ₹1,055 bill). | **HIGH** | `PROPOSED_CLEANED` |
| `R0093` | `R0093` | `Sentiment` | Sentiment Tagging Conflict | `Positive` | `Mixed` | Review states rating was docked from 5 to 4 specifically due to poor parlour service. | **HIGH** | `PROPOSED_CLEANED` |
| `R0095` | `R0095` | `Sentiment` | Sentiment Tagging Conflict | `Positive` | `Mixed` | Review highlights neglect of injured workers as a serious concern. | **HIGH** | `PROPOSED_CLEANED` |

### Taxonomy Normalization Queue (18 Items)

| Review IDs | Field | Raw Value | Cleaned Value | Reason | Confidence | Status |
| :--- | :--- | :--- | :--- | :--- | :---: | :---: |
| `R008`, `R010`, `R022`, `R028`, `R029`, `R032`, `R033`, `R034`, `R035`, `R037`, `R038`, `R039`, `R040`, `R045`, `R046` (15 rows) | `Service category` | `General services` | `General` | Label variant of canonical category `General` | **HIGH** | `CLEANED` |
| `R013`, `R025`, `R047` (3 rows) | `Service category` | `General service` | `General` | Label variant of canonical category `General` | **HIGH** | `CLEANED` |

### ID Format Normalization Queue (57 Items)

| Review IDs | Field | Raw Range | Cleaned Range | Reason | Confidence | Status |
| :--- | :--- | :--- | :--- | :--- | :---: | :---: |
| `R001` through `R057` (57 rows) | `Review ID` | `R001` – `R057` | `R0001` – `R0057` | Standardized to canonical 4-digit zero-padding to match `R0058`–`R0179` | **HIGH** | `CLEANED` |

---

## 6. Comprehensive Summary Statistics

### 6.1 Record Distribution by Sheet Slice

| Sheet Name | Row Count | Percentage Share | Valid Star Ratings | Ratings Unavailable |
| :--- | :---: | :---: | :---: | :---: |
| `Most Relevant 5 Star` | 57 | 31.8% | 57 (5.0 stars) | 0 |
| `Most Relevant 4 Star` | 47 | 26.3% | 47 (4.0 stars) | 0 |
| `Newest` | 75 | 41.9% | 35 (34x 5.0, 1x 4.0) | 40 (`[RATING UNAVAILABLE]`) |
| **Total Across Sheets** | **179** | **100.0%** | **139 (77.7%)** | **40 (22.3%)** |

### 6.2 Rating Distribution & Data Status

| Rating Category | Review Count | Share of Total | Data Status / Provenance |
| :--- | :---: | :---: | :--- |
| `5.0 Stars` | 91 | 50.8% | `ORIGINAL` (Google Play Store extraction) |
| `4.0 Stars` | 48 | 26.8% | `ORIGINAL` (Google Play Store extraction) |
| `[RATING UNAVAILABLE]` | 40 | 22.3% | `NOT RECOVERABLE FROM REVIEW TEXT` (Audit placeholder) |
| **Total** | **179** | **100.0%** | — |

### 6.3 Sentiment Distribution: Raw vs. Proposed Cleaned

| Sentiment Class | Raw Count | Raw Share | Proposed Cleaned Count | Proposed Cleaned Share | Net Change |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Positive** | 99 | 55.3% | 93 | 52.0% | -6 |
| **Mixed** | 24 | 13.4% | 30 | 16.8% | +6 |
| **Negative** | 51 | 28.5% | 51 | 28.5% | 0 |
| **Neutral** | 5 | 2.8% | 5 | 2.8% | 0 |
| **Total** | **179** | **100.0%** | **179** | **100.0%** | 0 |

### 6.4 Service Verticals vs. Sentiment Cross-Tabulation

| Normalized Service Vertical | Total Reviews | Positive | Mixed | Negative | Neutral | % of Total Dataset |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Platform, App & Support** | 85 | 42 | 14 | 25 | 4 | 47.5% |
| **Appliance Repair & Servicing** | 42 | 26 | 5 | 11 | 0 | 23.5% |
| **Insta Help & Daily Services** | 26 | 5 | 7 | 14 | 0 | 14.5% |
| **Home Cleaning & Pest Control** | 16 | 11 | 3 | 1 | 1 | 8.9% |
| **Home Maintenance & Repairs** | 7 | 6 | 1 | 0 | 0 | 3.9% |
| **Beauty, Salon & Spa** | 3 | 3 | 0 | 0 | 0 | 1.7% |
| **Total** | **179** | **93** | **30** | **51** | **5** | **100.0%** |

---

## 7. Cleaned Dataset Specification

The cleaned workbook [`PM01_Urban_Company_Cleaned.xlsx`](Urban_Company_Cleaned_Dataset.xlsx) was built using openpyxl with professional styling, auto-adjusted column widths, and frozen header panes.

### Worksheet Structure
1. **`All Reviews Consolidated` (180 rows, 16 cols):**
   Master database uniting all 179 reviews across the 3 slices into a single filterable table. Contains:
   * `Sheet`, `Review ID (Raw)`, `Review ID (Cleaned)`
   * `Date`, `Rating`, `Rating Status`
   * `Service Category (Raw)`, `Service Category (Cleaned)`, `Service Vertical`
   * `Sentiment (Raw)`, `Sentiment (Cleaned)`
   * `Topics`, `Relevant Quote`, `Observation`, `Notes`
   * `Data Quality Flags` (e.g., `VALID`, `STANDARDIZED_ID_PADDING`, `CATEGORY_STANDARDIZED`, `SENTIMENT_CORRECTED`, `AMBIGUOUS_RATING_CONTRADICTION`, `RATING_UNAVAILABLE`)
2. **`Most Relevant 5 Star` (58 rows, 16 cols):** Sheet 1 with standardized fields and quality flags.
3. **`Most Relevant 4 Star` (48 rows, 16 cols):** Sheet 2 with standardized fields and quality flags.
4. **`Newest` (76 rows, 16 cols):** Sheet 3 with standardized fields and audit placeholders.
5. **`Correction Queue` (84 rows, 10 cols):** Full log of all 83 modifications and proposed corrections.
6. **`Summary Statistics` (45 rows, 6 cols):** Formatted tables matching Section 6 of this report.

---

## 8. Research Integrity Checklist

- [x] **Raw Dataset Preserved:** [`Urban_Company_Cleaned_Dataset.xlsx`](Urban_Company_Cleaned_Dataset.xlsx) is unmodified and matches the pre-audit backup byte-for-byte.
- [x] **Zero Synthetic Ratings:** Not a single missing rating was inferred from sentiment.
- [x] **Zero Row Loss / Reordering:** All 179 rows maintain their original relative order.
- [x] **Ambiguous Cases Documented:** `R009` flagged; no silent alteration.
- [x] **Selection Bias Acknowledged:** In downstream Stage 2 research, review data must be treated as `RESEARCH FINDING (community)` with explicit note of user self-selection bias.
- [x] **No Premature Product Conclusions:** Data quality analysis complete without downstream hypothesis testing or feature ideation.

---
*Document generated as part of PM-01 Urban Company Evidence & Data Quality Pipeline.*  
*Reference: `00_Portfolio/PM/projects/PM-01_Urban_Company/`*
