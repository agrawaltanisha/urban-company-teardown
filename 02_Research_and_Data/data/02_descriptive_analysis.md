# PM-01 — Urban Company: Trust & Repeat-Booking in a Two-Sided Marketplace
# Descriptive Statistical Analysis of the Cleaned Review-Mining Dataset

**Document Type:** Descriptive Data Analysis (Stage 1 Research Foundation)  
**Project:** PM-01 (Urban Company)  
**Dataset Source:** [`PM01_Urban_Company_Cleaned.xlsx`](Urban_Company_Cleaned_Dataset.xlsx)  
**Date:** 2026-09-16  
**Status:** COMPLETE  

> [!IMPORTANT]
> **Sample-Only Scope & Non-Generalization Principle:**
> All percentages, counts, and findings in this document describe **this sampled review dataset only** ($N=179$). Public app store reviews are subject to acute self-selection bias (users with extreme positive or extreme negative experiences are disproportionately motivated to post). These statistics must **NOT** be generalized to Urban Company's entire customer base or aggregate platform transaction volume. No causal claims or premature problem definitions are asserted here.

---

## 1. Population & Rating Profile

### 1.1 Population Definitions
* **$N_{\text{total}} = 179$**: All reviews mined across all three slices (`Most Relevant 5 Star`, `Most Relevant 4 Star`, `Newest`).
* **$N_{\text{valid}} = 139$**: Reviews with an authentic, verified numerical star rating (excluding missing-rating placeholders).
* **$N_{\text{missing}} = 40$**: Reviews where the star rating was lost during source extraction and labeled `[RATING UNAVAILABLE]`.
* **$N_{\text{5-star}} = 91$**: Valid reviews carrying an original 5.0 rating ($n=57$ from Sheet 1, $n=34$ from Sheet 3).
* **$N_{\text{4-star}} = 48$**: Valid reviews carrying an original 4.0 rating ($n=47$ from Sheet 2, $n=1$ from Sheet 3).

### 1.2 Overall Rating & Provenance Distribution

| Metric / Category | Numerator ($n$) | Denominator ($N$) | Percentage (%) | Population Definition | Data Provenance |
| :--- | :---: | :---: | :---: | :--- | :--- |
| **Total Mined Reviews** | 179 | 179 | 100.0% | Entire review dataset ($N_{\text{total}}$) | Extracted sample |
| **Valid Numeric Ratings** | 139 | 179 | 77.7% | Entire review dataset ($N_{\text{total}}$) | Original Play Store score |
| **Missing Rating Placeholders** | 40 | 179 | 22.3% | Entire review dataset ($N_{\text{total}}$) | Extraction gap (`NOT RECOVERABLE`) |
| **5.0 Star Ratings** | 91 | 139 | 65.5% | Reviews with valid star ratings ($N_{\text{valid}}$) | Original Play Store score |
| **4.0 Star Ratings** | 48 | 139 | 34.5% | Reviews with valid star ratings ($N_{\text{valid}}$) | Original Play Store score |
| **1.0 to 3.0 Star Ratings** | 0 | 139 | 0.0% | Reviews with valid star ratings ($N_{\text{valid}}$) | Zero sampled in Sheet 1/2; Sheet 3 unrated |

---

## 2. Topic Frequencies & Co-Occurrence

Across the 179 reviews, **571 total topic mentions** were logged, spanning **475 unique topic strings**.

### 2.1 Overall Top Topic Frequencies

| Rank | Topic String             | Review Count ($n$) | Review Share (%) [$N=179$] | Mentions Share (%) [$N=571$] | Core Operational Dimension          |
| :--: | :----------------------- | :----------------: | :------------------------: | :--------------------------: | :---------------------------------- |
|  1   | `professional`           |         11         |            6.1%            |             1.9%             | Professional Behavior               |
|  2   | `good`                   |         9          |            5.0%            |             1.6%             | General Quality                     |
|  3   | `professionalism`        |         8          |            4.5%            |             1.4%             | Professional Behavior               |
|  4   | `punctual`               |         8          |            4.5%            |             1.4%             | Professional Behavior (Punctuality) |
|  5   | `quality`                |         5          |            2.8%            |             0.9%             | Service Quality                     |
|  6   | `convenience`            |         5          |            2.8%            |             0.9%             | Platform Value Proposition          |
|  7   | `on time`                |         5          |            2.8%            |             0.9%             | Professional Behavior (Punctuality) |
|  8   | `polite`                 |         5          |            2.8%            |             0.9%             | Professional Behavior (Conduct)     |
|  9   | `good service`           |         5          |            2.8%            |             0.9%             | General Quality                     |
|  10  | `punctuality`            |         4          |            2.2%            |             0.7%             | Professional Behavior (Punctuality) |
|  11  | `service good`           |         4          |            2.2%            |             0.7%             | General Quality                     |
|  12  | `helpful`                |         4          |            2.2%            |             0.7%             | Professional Behavior (Conduct)     |
|  13  | `speed`                  |         3          |            1.7%            |             0.5%             | Execution Speed                     |
|  14  | `satisfaction`           |         3          |            1.7%            |             0.5%             | General Sentiment                   |
|  15  | `smooth`                 |         3          |            1.7%            |             0.5%             | App / Booking Flow                  |
|  16  | `courteous`              |         3          |            1.7%            |             0.5%             | Professional Behavior (Conduct)     |
|  17  | `excellent`              |         3          |            1.7%            |             0.5%             | General Sentiment                   |
|  18  | `no customer care`       |         3          |            1.7%            |             0.5%             | Customer Support Access             |
|  19  | `thoroughness`           |         2          |            1.1%            |             0.4%             | Work Execution                      |
|  20  | `long-term satisfaction` |         2          |            1.1%            |             0.4%             | Repeat / Rebooking                  |

### 2.2 Topic Frequencies by Numerical Rating

*(Note: Missing-rating rows are excluded per prompt instructions. Denominators: 5-star $N=91$, 4-star $N=48$.)*

| Topic String | 5-Star Count ($n$) | 5-Star Share (%) [$N=91$] | 4-Star Count ($n$) | 4-Star Share (%) [$N=48$] |
| :--- | :---: | :---: | :---: | :---: |
| `professional` | 10 | 11.0% | 0 | 0.0% |
| `professionalism` | 8 | 8.8% | 0 | 0.0% |
| `good` | 8 | 8.8% | 1 | 2.1% |
| `punctual` | 7 | 7.7% | 1 | 2.1% |
| `helpful` | 4 | 4.4% | 0 | 0.0% |
| `on time` | 4 | 4.4% | 1 | 2.1% |
| `polite` | 4 | 4.4% | 0 | 0.0% |
| `good service` | 4 | 4.4% | 0 | 0.0% |
| `speed` | 3 | 3.3% | 0 | 0.0% |
| `quality` | 3 | 3.3% | 1 | 2.1% |
| `service good` | 1 | 1.1% | 3 | 6.2% |
| `convenience` | 3 | 3.3% | 2 | 4.2% |
| `punctuality` | 2 | 2.2% | 2 | 4.2% |
| `cancellation` | 0 | 0.0% | 2 | 4.2% |
| `gst` | 0 | 0.0% | 2 | 4.2% |
| `surge pricing` | 0 | 0.0% | 1 | 2.1% |
| `extra charge` | 0 | 0.0% | 1 | 2.1% |

### 2.3 Topic Frequencies by Sentiment

*(Denominators: Cleaned Sentiment classes: Positive $N=93$, Mixed $N=30$, Negative $N=51$, Neutral $N=5$.)*

| Topic String | Positive ($n/93$) | Positive Share (%) | Mixed ($n/30$) | Mixed Share (%) | Negative ($n/51$) | Negative Share (%) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| `professional` | 11 | 11.8% | 0 | 0.0% | 0 | 0.0% |
| `good` | 9 | 9.7% | 0 | 0.0% | 0 | 0.0% |
| `professionalism` | 8 | 8.6% | 0 | 0.0% | 0 | 0.0% |
| `punctual` | 8 | 8.6% | 0 | 0.0% | 0 | 0.0% |
| `on time` | 5 | 5.4% | 0 | 0.0% | 0 | 0.0% |
| `polite` | 5 | 5.4% | 0 | 0.0% | 0 | 0.0% |
| `service good` | 0 | 0.0% | 4 | 13.3% | 0 | 0.0% |
| `useful app` | 0 | 0.0% | 2 | 6.7% | 0 | 0.0% |
| `gst` | 0 | 0.0% | 2 | 6.7% | 0 | 0.0% |
| `ai support` | 0 | 0.0% | 0 | 0.0% | 2 | 3.9% |
| `cancellation` | 0 | 0.0% | 0 | 0.0% | 2 | 3.9% |
| `fraud` | 0 | 0.0% | 0 | 0.0% | 2 | 3.9% |
| `no customer care`| 0 | 0.0% | 0 | 0.0% | 2 | 3.9% |
| `unprofessional` | 0 | 0.0% | 0 | 0.0% | 2 | 3.9% |

### 2.4 Topic Co-Occurrence Analysis
Evaluating pair-wise occurrence of topics within the same review text reveals recurring attribute clusters:

| Rank | Topic Co-Occurrence Pair | Frequency ($n$) | Review Share (%) [$N=179$] | Qualitative Semantic Interpretation |
| :---: | :--- | :---: | :---: | :--- |
| 1 | `professionalism` + `speed` | 3 | 1.7% | Execution quality combined with fast turnaround |
| 2 | `professionalism` + `quality` | 3 | 1.7% | Technical skill linked to professional demeanor |
| 3 | `polite` + `professional` | 3 | 1.7% | Behavioral courtesy paired with trade competence |
| 4 | `professional` + `smooth` | 3 | 1.7% | High professional skill yielding frictionless service |
| 5 | `on time` + `professional` | 3 | 1.7% | Punctual arrival as a prerequisite for professionalism |
| 6 | `professionalism` + `punctuality` | 2 | 1.1% | Core reliability bundle |
| 7 | `professionalism` + `thoroughness` | 2 | 1.1% | Attention to detail in cleaning/repair |
| 8 | `punctuality` + `thoroughness` | 2 | 1.1% | On-time delivery with complete job execution |
| 9 | `polite` + `punctual` | 2 | 1.1% | Positive interpersonal partner attributes |
| 10 | `professional` + `punctual` | 2 | 1.1% | Standard service expectation fulfilled |

---

## 3. The 8 Core Thematic Categories

The 8 core themes were evaluated across multiple operational slices. Each review was tagged through strict semantic criteria based on explicit topic tags, quote text, and observations.

### 3.1 Master Theme Prevalence Table

| Theme # | Theme Name | Total Dataset ($n/179$) | Total Share (%) | Valid Ratings ($n/139$) | Valid Share (%) | Missing Ratings ($n/40$) | Missing Share (%) |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| 11 | **Trust-related** | 14 | 7.8% | 7 | 5.0% | 7 | 17.5% |
| 12 | **Rebooking-related** | 6 | 3.4% | 5 | 3.6% | 1 | 2.5% |
| 13 | **Consistency-related** | 6 | 3.4% | 4 | 2.9% | 2 | 5.0% |
| 14 | **Quality-related** | 51 | 28.5% | 40 | 28.8% | 11 | 27.5% |
| 15 | **Pricing-related** | 46 | 25.7% | 33 | 23.7% | 13 | 32.5% |
| 16 | **Cancellation-related** | 26 | 14.5% | 13 | 9.4% | 13 | 32.5% |
| 17 | **App/UX-related** | 48 | 26.8% | 36 | 25.9% | 12 | 30.0% |
| 18 | **Professional Behavior** | 54 | 30.2% | 51 | 36.7% | 3 | 7.5% |

### 3.2 Cross-Tabulation: Theme Prevalence by Numerical Rating

*(Note: Calculated strictly over valid numeric ratings $N_{\text{valid}}=139$.)*

| Theme Name | 5-Star Reviews ($n/91$) | 5-Star Share (%) | 4-Star Reviews ($n/48$) | 4-Star Share (%) | Rating Disparity |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **Professional Behavior** | 41 | 45.1% | 10 | 20.8% | +24.3% in 5-star |
| **Quality** | 30 | 33.0% | 10 | 20.8% | +12.2% in 5-star |
| **Pricing** | 17 | 18.7% | 16 | 33.3% | +14.6% in 4-star |
| **App/UX** | 18 | 19.8% | 18 | 37.5% | +17.7% in 4-star |
| **Cancellation** | 3 | 3.3% | 10 | 20.8% | +17.5% in 4-star |
| **Trust** | 4 | 4.4% | 3 | 6.2% | +1.8% in 4-star |
| **Rebooking** | 2 | 2.2% | 3 | 6.2% | +4.0% in 4-star |
| **Consistency** | 3 | 3.3% | 1 | 2.1% | +1.2% in 5-star |

### 3.3 Cross-Tabulation: Theme Prevalence by Cleaned Sentiment

| Theme Name | Positive ($n/93$) | Positive Share (%) | Mixed ($n/30$) | Mixed Share (%) | Negative ($n/51$) | Negative Share (%) | Neutral ($n/5$) | Neutral Share (%) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Professional Behavior** | 41 | 44.1% | 7 | 23.3% | 5 | 9.8% | 1 | 20.0% |
| **Quality** | 31 | 33.3% | 5 | 16.7% | 14 | 27.5% | 1 | 20.0% |
| **Pricing** | 17 | 18.3% | 8 | 26.7% | 19 | 37.3% | 2 | 40.0% |
| **App/UX** | 18 | 19.4% | 11 | 36.7% | 16 | 31.4% | 3 | 60.0% |
| **Cancellation** | 1 | 1.1% | 6 | 20.0% | 19 | 37.3% | 0 | 0.0% |
| **Trust** | 5 | 5.4% | 1 | 3.3% | 8 | 15.7% | 0 | 0.0% |
| **Rebooking** | 3 | 3.2% | 0 | 0.0% | 3 | 5.9% | 0 | 0.0% |
| **Consistency** | 2 | 2.2% | 3 | 10.0% | 1 | 2.0% | 0 | 0.0% |

### 3.4 Cross-Tabulation: Theme Prevalence by Normalized Service Vertical

| Service Vertical | Vertical Base ($N$) | Professional Behavior | Quality | Pricing | Cancellation | App/UX | Trust | Rebooking | Consistency |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Platform, App & Support** | 86 | 16 (18.6%) | 7 (8.1%) | 21 (24.4%) | 8 (9.3%) | 23 (26.7%) | 5 (5.8%) | 2 (2.3%) | 2 (2.3%) |
| **Appliance Repair & Servicing**| 41 | 16 (39.0%) | 25 (61.0%)| 12 (29.3%)| 6 (14.6%) | 11 (26.8%)| 7 (17.1%)| 0 (0.0%) | 2 (4.9%) |
| **Insta Help & Daily Services** | 26 | 6 (23.1%) | 2 (7.7%) | 5 (19.2%) | 11 (42.3%)| 6 (23.1%) | 1 (3.8%) | 3 (11.5%)| 1 (3.8%) |
| **Home Cleaning & Pest Control**| 16 | 8 (50.0%) | 15 (93.8%)| 3 (18.8%) | 0 (0.0%)  | 4 (25.0%) | 1 (6.2%) | 0 (0.0%) | 0 (0.0%) |
| **Home Maintenance & Repairs** | 7 | 7 (100.0%)| 1 (14.3%) | 4 (57.1%) | 1 (14.3%) | 4 (57.1%) | 0 (0.0%) | 0 (0.0%) | 0 (0.0%) |
| **Beauty, Salon & Spa** | 3 | 1 (33.3%) | 1 (33.3%) | 1 (33.3%) | 0 (0.0%)  | 0 (0.0%)  | 0 (0.0%) | 1 (33.3%)| 1 (33.3%)|

---

## 4. Deep-Dive on Specific Focus Themes

### Theme 11: Trust-Related Reviews
* **Numerator & Denominator:** $n=14$, $N=179$ (7.8% of total dataset).
* **Valid Ratings Slice:** $n=7$, $N=139$ (5.0% of valid ratings).
* **Missing Ratings Slice:** $n=7$, $N=40$ (17.5% of missing ratings).
* **Sentiment Breakdown:** Positive $n=5/93$ (5.4%), Mixed $n=1/30$ (3.3%), Negative $n=8/51$ (15.7%).
* **Key Observations & Review IDs:**
  * *Positive Trust ($n=5$):* Skill certification badges giving confidence (`R0036`), transparent microwave component verification on video call (`R0048`), reliable cleaners (`R0056`), experienced and honest advice (`R0052`).
  * *Negative Trust & Safety ($n=8$):* Invasion of domestic privacy via video call (*"someone was watching my home via a video call"*, `R0109`), unannounced washroom usage (*"using my home washroom without my knowledge... seems unsafe"*, `R0143`), accusations of dishonesty/theft (*"All service men are LOOTERS here"*, `R0136`; *"cheaters"*, `R0144`; *"fraud company"*, `R0110`), safety hazards from incompatible purifier wiring (`R0079`), installation of used spare parts billed as new (`R0160`).

### Theme 12: Rebooking-Related Reviews
* **Numerator & Denominator:** $n=6$, $N=179$ (3.4% of total dataset).
* **Valid Ratings Slice:** $n=5$, $N=139$ (3.6% of valid ratings).
* **Missing Ratings Slice:** $n=1$, $N=40$ (2.5% of missing ratings).
* **Sentiment Breakdown:** Positive $n=3/93$ (3.2%), Mixed $n=0/30$ (0.0%), Negative $n=3/51$ (5.9%).
* **Key Observations & Review IDs:**
  * *Praise of Repeat Experience ($n=3$):* Booked multiple services over time for haircuts (`R0017`), regular customer with zero disappointments (`R0033`), long-time satisfied customer docked 1 star purely for support access (`R0059`).
  * *Repeat Friction ($n=3$):* Prepaid packages failing on subsequent bookings (`R0073`), repeated cancellations across multiple bookings (*"Out of 5 services, 3 were cancelled by Urban Company"*, `R0101`), bot profile acceptance and cancellation happening 4–5 times (`R0176`).

### Theme 13: Consistency-Related Reviews
* **Numerator & Denominator:** $n=6$, $N=179$ (3.4% of total dataset).
* **Valid Ratings Slice:** $n=4$, $N=139$ (2.9% of valid ratings).
* **Missing Ratings Slice:** $n=2$, $N=40$ (5.0% of missing ratings).
* **Sentiment Breakdown:** Positive $n=2/93$ (2.2%), Mixed $n=3/30$ (10.0%), Negative $n=1/51$ (2.0%).
* **Key Observations & Review IDs:**
  * *Positive Uniformity ($n=2$):* Consistent quality across repeated haircuts (`R0017`), uniformly well-trained and punctual professionals (`R0040`).
  * *Variance Across Professionals & Degradation ($n=4$):* Disconnect between professional quality and platform quality (*"the 4 star rating is for the professionals and not for UC"*, `R0074`), staff behavior good but final cleaning result below promised standards (`R0147`), service quality degrading over time (`R0117`), platform changing assigned personnel without user consent (`R0179`).

### Theme 14: Quality-Related Reviews
* **Numerator & Denominator:** $n=51$, $N=179$ (28.5% of total dataset).
* **Valid Ratings Slice:** $n=40$, $N=139$ (28.8% of valid ratings).
* **Missing Ratings Slice:** $n=11$, $N=40$ (27.5% of missing ratings).
* **Sentiment Breakdown:** Positive $n=31/93$ (33.3%), Mixed $n=5/30$ (16.7%), Negative $n=14/51$ (27.5%).
* **Vertical Concentration:** Highly concentrated in Home Cleaning ($n=15/16$, 93.8%) and Appliance Repair ($n=25/41$, 61.0%).
* **Key Observations & Review IDs:**
  * *Positive Workmanship ($n=31$):* Flawless washing machine repair (`R0001`), prompt leak resolution (`R0014`), thorough bathroom descaling (`R0006`), seamless fridge repair (`R0016`).
  * *Negative Damage & Deficiencies ($n=14$):* AC breakdown post-cleaning (*"Buy a new AC... convert it into an old broken-down one"*, `R0111`; `R0118`), broken bathroom taps and rashes post-pedicure (`R0127`), leaking geysers causing electrical hazards (`R0166`), superficial cleaning (*"they clean only front... move to local vendor"*, `R0113`), used parts installed (`R0160`).

### Theme 15: Pricing-Related Reviews
* **Numerator & Denominator:** $n=46$, $N=179$ (25.7% of total dataset).
* **Valid Ratings Slice:** $n=33$, $N=139$ (23.7% of valid ratings).
* **Missing Ratings Slice:** $n=13$, $N=40$ (32.5% of missing ratings).
* **Sentiment Breakdown:** Positive $n=17/93$ (18.3%), Mixed $n=8/30$ (26.7%), Negative $n=19/51$ (37.3%), Neutral $n=2/5$ (40.0%).
* **Key Observations & Review IDs:**
  * *Positive Pricing ($n=17$):* Reasonable rates, transparent estimates, good value for money (`R0001`, `R0008`, `R0033`, `R0035`).
  * *Negative Pricing Friction ($n=19$):* Default surge pricing without explanation (`₹150 additionally`, `R0058`; `extra 200 on weekends`, `R0165`), disproportionate app fees (`₹166 platform fee on ₹1,055 bill`, `R0092`), unfair cancellation fees when service was not delivered (`₹50 cancellation charge`, `R0115`, `R0145`), overcharging for trivial work (`₹350 for 2-minute minor fix`, `R0090`; `₹500 paid for nothing, outside mechanic charged ₹200`, `R0163`).

### Theme 16: Cancellation-Related Reviews
* **Numerator & Denominator:** $n=26$, $N=179$ (14.5% of total dataset).
* **Valid Ratings Slice:** $n=13$, $N=139$ (9.4% of valid ratings).
* **Missing Ratings Slice:** $n=13$, $N=40$ (32.5% of missing ratings).
* **Sentiment Breakdown:** Positive $n=1/93$ (1.1%), Mixed $n=6/30$ (20.0%), Negative $n=19/51$ (37.3%).
* **Vertical Concentration:** Heavily clustered in **Insta Help & Daily Services** ($n=11/26$, **42.3%**).
* **Key Observations & Review IDs:**
  * Company-side cancellations (`R0050`, `R0101`, `R0139`), professional no-shows (`R0125`, `R0126`, `R0136`), forced cancellations with fee penalties (`R0072`, `R0084`, `R0104`, `R0115`, `R0145`), delayed arrivals and slot shifts (`R0134`, `R0177`).

### Theme 17: App/UX-Related Reviews
* **Numerator & Denominator:** $n=48$, $N=179$ (26.8% of total dataset).
* **Valid Ratings Slice:** $n=36$, $N=139$ (25.9% of valid ratings).
* **Missing Ratings Slice:** $n=12$, $N=40$ (30.0% of missing ratings).
* **Sentiment Breakdown:** Positive $n=18/93$ (19.4%), Mixed $n=11/30$ (36.7%), Negative $n=16/51$ (31.4%), Neutral $n=3/5$ (60.0%).
* **Key Observations & Review IDs:**
  * *Positive UX ($n=18$):* Smooth booking flow, intuitive navigation, quick slot selection (`R0004`, `R0013`, `R0020`, `R0030`).
  * *Negative UX & Support Channels ($n=16$):* Repetitive/unhelpful AI chatbots (`R0071`, `R0108`, `R0117`, `R0158`), absence of human customer care phone helpline (`R0059`, `R0118`, `R0170`), app payment invoice mismatch bug (`R0060`), app slowness (`R0149`), friction in location selector forcing redundant confirmation (`R0012`, `R0066`).

### Theme 18: Professional-Behavior-Related Reviews
* **Numerator & Denominator:** $n=54$, $N=179$ (30.2% of total dataset).
* **Valid Ratings Slice:** $n=51$, $N=139$ (36.7% of valid ratings).
* **Missing Ratings Slice:** $n=3$, $N=40$ (7.5% of missing ratings).
* **Sentiment Breakdown:** Positive $n=41/93$ (44.1%), Mixed $n=7/30$ (23.3%), Negative $n=5/51$ (9.8%), Neutral $n=1/5$ (20.0%).
* **Key Observations & Review IDs:**
  * *Positive Conduct ($n=41$):* Courteous, well-mannered, disciplined, respectful, punctual technicians and beauticians (`R0001`, `R0002`, `R0011`, `R0015`, `R0021`, `R0037`, `R0040`, `R0055`).
  * *Negative Conduct ($n=5$):* Inappropriate washroom use (`R0143`), refusal of work upon arrival (`R0136`), extreme delay without communication (`R0177`), unresponsiveness (`R0161`), worker welfare/fatigue concerns from back-to-back bookings (`R0102`).

---

## 5. Visual Distribution Charts

### 5.1 Rating Distribution (Valid Ratings Slice, $N=139$)
```
5.0 Stars | ██████████████████████████████████████████████████ 65.5% (n=91/139)
4.0 Stars | ██████████████████████████ 34.5% (n=48/139)
```

### 5.2 Cleaned Sentiment Distribution ($N_{\text{total}}=179$)
```
Positive  | ██████████████████████████████████████ 52.0% (n=93/179)
Negative  | █████████████████████ 28.5% (n=51/179)
Mixed     | ████████████ 16.8% (n=30/179)
Neutral   | ██ 2.8% (n=5/179)
```

### 5.3 Core Theme Prevalence Comparison ($N_{\text{total}}=179$)
```
Professional Behavior | ██████████████████████ 30.2% (n=54/179)
Quality Execution     | █████████████████████ 28.5% (n=51/179)
App / UX / Support    | ████████████████████ 26.8% (n=48/179)
Pricing & Fees        | ███████████████████ 25.7% (n=46/179)
Cancellations / Slots | ███████████ 14.5% (n=26/179)
Trust & Privacy       | ██████ 7.8% (n=14/179)
Consistency / Drift   | ███ 3.4% (n=6/179)
Rebooking / Repeat    | ███ 3.4% (n=6/179)
```

### 5.4 Theme Prevalence in Negative Reviews ($N_{\text{neg}}=51$)
```
Pricing & Fees        | ████████████████████████████ 37.3% (n=19/51)
Cancellations / Slots | ████████████████████████████ 37.3% (n=19/51)
App / UX / AI Chatbot | ███████████████████████ 31.4% (n=16/51)
Quality Defects       | ████████████████████ 27.5% (n=14/51)
Trust / Privacy / Loot| ████████████ 15.7% (n=8/51)
Professional Conduct  | ███████ 9.8% (n=5/51)
Rebooking Disruption  | ████ 5.9% (n=3/51)
Consistency Drift     | █ 2.0% (n=1/51)
```

---

## 6. Outlier Analysis

1. **Temporal Outlier (`R0059`):**
   * *Observation:* Date is `2019-06-12`, while all remaining 178 reviews span `2026-05-25` to `2026-09-15`.
   * *Diagnostic:* Review was captured from the Google Play "Most Relevant" filter, which occasionally surfaces high-upvote historical reviews. It reflects long-term customer sentiment (*"old customer"* who gave 4 stars due to support difficulty).
2. **Category Outlier (`R0043`):**
   * *Observation:* Service category in the raw file was populated as `Technician Shabir`.
   * *Diagnostic:* Operator data entry error where the professional's name was entered into the category field instead of `General service`.
3. **Extreme Service-Specific Cancellation Rate (Insta Help):**
   * *Observation:* 42.3% ($n=11/26$) of Insta Help reviews report cancellations or helper no-shows, compared to 9.3% ($n=8/86$) in Platform/General and 0.0% ($n=0/16$) in Home Cleaning.

---

## 7. Contradiction Analysis

1. **Numerical Rating vs. Review Text Contradiction (`R0009`):**
   * *Record:* Rated 5.0 stars in `Most Relevant 5 Star`, but text is 100% negative (*"If the service cannot provide help within a reasonable time, why is it marketed as 'Insta Help'?"*).
   * *Status:* Flagged as `AMBIGUOUS_RATING_CONTRADICTION`. Retained without silent alteration.
2. **Rating vs. Sentiment Dissonance in 4-Star Reviews ($n=13$):**
   * *Record:* 13 reviews in `Most Relevant 4 Star` carry `Negative` sentiment tags despite a 4.0 star score (e.g., `R0071` AI support failure, `R0073` extra fees on prepaid packages, `R0084` hidden cancellation charges, `R0101` high cancellation rate).
   * *Diagnostic:* Reflects app store user behavior where frustrated customers give 4 stars to ensure their complaint is read by developers or because they value the core service while condemning platform policies.
3. **Sentiment Tagging Conflicts ($n=6$):**
   * *Records:* `R0060` (payment bug), `R0069` (service gap), `R0091` (forced rating before completion called "unethical"), `R0092` (₹166 app fee complaint), `R0093` (parlour service unsatisfactory), `R0095` (injured worker neglect).
   * *Diagnostic:* Inappropriately tagged as `Positive` in raw data; reclassified as `Mixed` in the cleaned dataset.

---

## 8. Missing-Data Observations

1. **Missing Ratings Concentration ($n=40/40$ in `Newest`):**
   * 100% of missing ratings occur in the `Newest` sheet ($n=40/75$, 53.3% of that sheet).
   * Sheets 1 and 2 had 0% missing ratings.
2. **Missing Ratings Skew Heavily Negative:**
   * In the missing ratings slice ($N=40$), 92.5% ($n=37/40$) are Negative, 2.5% ($n=1/40$) Positive, 2.5% ($n=1/40$) Neutral, and 2.5% ($n=1/40$) Mixed.
   * Consequently, calculating rating averages without acknowledging this extraction gap would produce severe positive survivorship bias (yielding an artificial mean of 4.65 stars from valid rows, while masking 37 negative reviews).
3. **Complete Absence of Mid-Tier (1–3 Star) Ratings:**
   * Due to the extraction methodology (scraping "Most Relevant 5 Star", "Most Relevant 4 Star", and "Newest" without explicit 1-star / 2-star / 3-star filters), the dataset contains zero labeled 1.0, 2.0, or 3.0 star reviews. The 37 negative reviews in `Newest` likely represent the 1–2 star cohort, but cannot be assigned numeric values without violating data integrity rules.

---
*End of Descriptive Statistical Analysis.*  
*Artifacts preserved in:*  
- *Dataset:* [`PM01_Urban_Company_Cleaned.xlsx`](Urban_Company_Cleaned_Dataset.xlsx)  
- *Data Quality Report:* [`DATA_QUALITY_ANALYSIS.md`](data_quality_analysis.md)
