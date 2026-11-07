# PM-01 — Urban Company
## 02 — Product Context

**Stage:** SCOPING
**Purpose:** Establish what is publicly known about Urban Company as a business and product — before any user research begins.
**Last updated:** 2026-09-16

> **Important:** This file contains only what is verifiable from public sources or explicitly labelled as an assumption. No internal data, no fabricated metrics, no invented quotes.

---

## 1. Company Overview

### What Urban Company is
`FACT — source: Urban Company official website and public statements (to be verified and logged in source log)`

Urban Company (formerly UrbanClap) is an Indian home-services marketplace platform that connects customers with trained, verified service professionals for a range of services including home cleaning, appliance repair, beauty and wellness, plumbing, electrical, painting, carpentry, and more.

The platform operates in India (its primary market) and has international operations in UAE, Saudi Arabia, Singapore, and Australia.

**Business model:** Urban Company takes a commission or margin on services booked through the platform. Professionals are trained and often supplied consumables/tools by the platform.

> **Evidence gap:** Exact commission/take-rate structure is not publicly disclosed. Urban Company's precise unit economics are not available for this analysis.

### Market context
- Home services is a large, fragmented, largely unorganized market in India
- Urban Company competes primarily with the unorganized local market (finding a plumber or electrician through personal referrals, local listings) — not primarily with other platforms
- The platform play is: **organize supply** (train and credential professionals), **aggregate demand** (give customers a reliable booking channel), and **build trust** (through ratings, guarantees, professional vetting)

`ASSUMPTION — label: the primary competitive alternative for most customers is the unorganized local market, not a competing platform. This is plausible given India's market structure but unverified.`

---

## 2. Two-Sided Structure

Urban Company operates with two distinct user populations whose incentives are not always aligned.

### Customer side
- Books services through the Urban Company app or website
- Pays the listed price for the service
- Rates the professional after service completion
- Can request a specific professional for repeat bookings (alleged — to be verified)
- Primary concern: reliable service quality, trustworthy professional, fair price

### Professional/supply side
- Independent professionals trained and verified by Urban Company
- Earn from completed jobs (revenue sharing or commission deducted by platform)
- Rated by customers; ratings affect future job allocation
- Operate under platform rules, pricing, and quality standards
- Primary concern: sufficient jobs, fair earnings, manageable workload

### Platform (Urban Company)
- Controls matching, pricing, and quality enforcement
- Sets the trust infrastructure: background checks, training, ratings system
- Earns on transaction volume and margin
- Faces the fundamental marketplace tension: optimizing for customers may harm professionals, and vice versa

> This three-way dynamic is what makes this project analytically richer than a single-sided consumer app. Any product decision must be assessed across all three layers.

---

## 3. Product Experience (as publicly understood)

`ASSUMPTION — label: the following is based on publicly accessible product walkthroughs, press coverage, and app store descriptions. Actual product behavior may differ.`

**What the current booking flow roughly involves:**
1. Customer opens app → selects service category
2. Selects specific service → receives pricing
3. Books a time slot
4. A professional is assigned (matching happens on platform side)
5. Professional arrives → service completed
6. Customer rates the professional

**What is known about trust/repeat-booking mechanics:**
- Rating system exists (professionals receive star ratings)
- Urban Company has historically marketed a "UC Pro" or premium tier system with higher-rated professionals
- ==The platform has some form of "re-book same professional" feature — exact mechanics, availability, and UX path are **not fully clear from public sources** and must be researched==

`EVIDENCE GAP: Whether repeat booking of the same professional is a prominent, discoverable feature or buried is unknown until product research is conducted.`

---

## 4. What Is Publicly Known vs. Unknown

| Area              | Known (publicly)                                                                 | Unknown                                                                                 |
| ----------------- | -------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Business model    | Commission/margin model on home services                                         | Exact take rate                                                                         |
| Markets           | India (primary), UAE, KSA, SG, AU                                                | Market share in each                                                                    |
| User base         | Claims to have served millions of customers                                      | Actual MAU, DAU, retention rates                                                        |
| Professional base | Claims to have hundreds of thousands of trained professionals                    | Exact supply-side count, churn rate                                                     |
| Financials        | Company has raised significant venture funding; had reported losses as a startup | Current revenue, profitability, unit economics                                          |
| Repeat booking    | Platform claims to enable it                                                     | How prominent it is, what fraction of bookings are repeat, whether it's a growth driver |
| Trust mechanisms  | Ratings, background checks, training                                             | Weight of each factor, failure rates                                                    |
| Churn drivers     | Unknown                                                                          | Unknown — must be inferred from public evidence                                         |

---

## 5. What the Research Must Establish

Before Stage 3 (Analysis) can begin, research must surface evidence about:

1. What actual customers say about their experience on the platform (positive and negative)
2. Whether trust and repeat booking appear as genuine user pain points in public discourse
3. Whether professionals express concerns about their side of the marketplace in public forums
4. What the platform currently does well (to avoid building on a false assumption of failure)
5. Where the experience demonstrably breaks down

---

---

## 7. Task 6 — Human Product Walkthrough (Firsthand iOS App Inspection)

**Execution Date:** 2026-09-18  
**Source Documents:**  
1. `Urban Company Booking.pdf` (`S005` — 28 pages: Discovery, Category Hub, Service Detail, Cart, Scheduling, Checkout, Payment, Profile, My Bookings)  
2. `Urban Comapny Cancellation and Support.pdf` (`S006` — 6 pages: In-cart Cancellation Policy Modal, Help & Support Directory, Safety Measures, Warranty Scope & Exclusions)  
**Platform Inspected:** Apple iOS (Production Native Mobile App)  
**Location Displayed in Client:** Mumbai Central, Mumbai, Maharashtra, India  
**Account Profile & State:** Test user account ("Anshul"), incomplete profile badge, zero prior booking history  
**Methodological Constraints & Limitations:**  
- Conducted as a single-session firsthand visual inspection of the live client.
- Because the test account had zero completed bookings, historical order management and the live rebooking flow could not be populated or observed.
- The inspection captures client-side visual states; server-side dispatch logic, partner-side interfaces, and dynamic pricing algorithms are not directly observable.

---

### A. Discovery & Homepage

* **OBSERVATION:**  
  The homepage (S005, Page 1) displays a top location banner showing *"In 29 minutes / Mumbai Central - Mumbai- Maharashtra- I... v"*. A primary search bar features rotating placeholder text (*"Search for 'Kitchen cleaning'"*). The main viewport highlights seasonal promotions (*"HAPPY Ganesh Chaturthi"* banner with sub-cards: *"Get festive ready (25% off)"*, *"Prep your home"*, *"Instant help"*, *"Decorate home"*). Service verticals are presented in an 8-tile grid: *InstaHelp*, *Women's Salon & Spa*, *Men's Salon & Massage (44 mins)*, *Cleaning & Pest Control*, *Wall Panels by Revamp*, *Painting & Water-proofing*, *AC & Appliance Repair (42 mins)*, and *Electrician, Plumber & Carpenter (29 mins)*. Below the grid is a *"Native Smart Products"* section. A floating bottom pill shows *"1 item in cart / From 1 category"* with a *"View"* CTA.  
  The search screen (Pages 2–3) offers *"Trending searches"* (Professional cleaning, Salon, Electricians, Plumbers, Carpenters) and an *"Ask anything with AI"* module with natural-language prompt chips (*"I'd like to book my previous haircut!"*, *"My fridge is not working, making some noise."*, *"Anything to help me clean my stained sofa?"*).
* **IMPLICATION:**  
  Urban Company's discovery architecture aggressively leads with fulfillment speed/ETA indicators (*"In 29 minutes"*, *"42 mins"*, *"44 mins"*) to signal operational liquidity. The search interface indicates that natural-language AI search is integrated alongside structured category navigation.
* **UNKNOWN:**  
  The underlying algorithm determining displayed lead times, whether ETAs reflect real-time partner supply or static city-level estimates, and whether search ranking is personalized based on past booking history.

---

### B. Service Selection & Category Hub

* **OBSERVATION:**  
  Selecting "AC & Appliance Repair" navigates to the AC Category Hub (S005, Pages 4–7). The header displays category rating and volume (*"★ 4.78 (14.1 M bookings)"*) and earliest available slot (*"Earliest Fri, 11:00 AM"*). A hero banner features *"FREE GAS CHECK / AC diagnosis with Co-pilot / No gas refill without a reading"* with a photo of a technician operating a proprietary digital diagnostic meter. A trust badge highlights *"UC COVER / Upto 30 days warranty on repairs >"*.  
  Services are categorized into four carousels: *Super saver packages (Upto 30% OFF)*, *Service*, *Repair & gas refill*, and *Installation/uninstallation*.  
  Within *Super saver packages*, the *"Foam-jet service (2 ACs)"* package is prominently listed at **₹1,098** with a crossed-out anchor price of **₹1,198** (*"2 hrs"*, *"₹549/AC"*). Bullets state: *"Applicable for both window or split ACs"* and *"Indoor unit deep cleaning with foam & jet spray"*. Primary CTAs are *"View details"* and *"Add"*. Multi-unit packages scale with visible per-unit discounting (3 ACs: ₹1,497 / ₹499 per AC; 4 ACs: ₹1,796 / ₹449 per AC).
* **IMPLICATION:**  
  Catalogue pricing utilizes crossed-out anchoring (₹1,198 → ₹1,098) and transparent per-unit calculations (₹549/AC) to establish high initial price clarity. Diagnostic technology ("Co-pilot") is positioned as an objective arbiter to preempt customer skepticism regarding unnecessary refrigerant charges.
* **UNKNOWN:**  
  The basis of the crossed-out reference price (whether a standard rate or regulatory maximum), whether package discounts vary dynamically by temperature or demand, and what percentage of users book single vs multi-unit packages.

---

### C. Service Detail Page & Process Disclosure

* **OBSERVATION:**  
  The detail page for "Foam-jet AC service" (S005, Pages 8–16) displays:
  - **Service Specifications:** Re-states package price (**₹1,098**, crossed-out ₹1,198, ₹549 per AC, 2 hrs). Lists core highlights: applicable for split & window units, indoor foam-jet cleaning, outdoor jet-spray wash.
  - **Diagnostic & Process Protocol:** Reinforces *"FREE GAS CHECK / Transparent AC diagnosis with Co-Pilot / No gas refills without a reading"* with a *"How it works >"* link. Outlines a mandatory 5-step workflow: (1) Pre-service inspection with free gas check via Co-Pilot machine; (2) Indoor unit cleaning with foam/jet spray and spill protection tray; (3) Outdoor unit cleaning via jet spray; (4) **"Gas refilling (if required): We'll provide a quote and only refill after your approval"**; (5) Final clean-up of surrounding area.
  - **Warranty & Customer Prerequisites:** Card displays *"10-day warranty / With upto ₹10,000 damage cover & more / Know more >"*. Inclusions confirm free inspection, quotation, and post-repair check. Customer is asked to provide: bucket & water, power point, ladder or stool. "Please note" states that warranty excludes spare parts provided by the customer and outer unit cleaning is conditional on safe accessibility.
  - **Technician Credentialing:** Highlights *"Top professionals: Background verified, 300+ hours of training, Certified under Skill India Programme"*.
  - **Frequently Asked Questions (FAQs):** Contains explicit questions: *"Are spare parts covered under warranty?"*, *"What if the same issue occurs again?"*, *"Does UC service centralized/VRV ACs?"*, **"How can I verify the quote shared?"**, **"What if I am being charged extra?"**, *"Will the professional check the AC after the service?"*, *"What happens if the professional finds an issue with my AC during the service?"*.
  - **Social Proof:** Displays 4.75-star rating across 2.9M reviews (2.7M 5-star; 96K 1-star) with filter tabs (*"Most detailed"*, *"In my area"*, *"Frequent users"*).
* **IMPLICATION:**  
  The service detail page proactively addresses customer fear of on-site price gouging by establishing a formal policy: refrigerant refilling requires a quotation and explicit customer consent before execution. The presence of specific FAQs addressing quote verification and extra charges demonstrates that on-site billing discrepancies are recognized customer concerns.
* **UNKNOWN:**  
  The exact verbatim text inside the unexpanded FAQ accordions (*"How can I verify the quote shared?"* and *"What if I am being charged extra?"*), how the digital quote approval flow functions in the customer app during a live service, and partner compliance rates with the pre-approval protocol.

---

### D. Cart Management & Upselling

* **OBSERVATION:**  
  Adding the service opens the cart view (S005, Pages 17–20). The cart shows:
  - Header banner: *"Saving ₹100 on this order"*.
  - Cross-service promotional voucher: *"GIFT VOUCHER / Flat ₹500 off on all Women's Salon / Redeemable after this booking"* with a *"Claim FREE"* button.
  - Line item: *"Foam-jet service (2 ACs)"*, quantity `1`, displayed price **₹1,098** (crossed-out ₹1,198).
  - Optional subscription upsell modal: *"Choose Annual plan to get ₹400 off / Foam-jet service (2 ACs) x 1 / [ ] 2 services Validity of 6 months / ₹1,996 (₹998/visit)"* with an info tooltip.
  - Cross-sell carousel (*"People also take"*: Refrigerator check-up ₹199, Deep chimney service ₹1,249, Fridge cleaning ₹399).
  - Primary bottom button: **"Add address and slot"** (solid purple).
* **IMPLICATION:**  
  The cart maintains the single service package price (₹1,098) while utilizing post-booking rewards (Women's Salon voucher redeemable *after* this service) to drive cross-vertical expansion.
* **UNKNOWN:**  
  Whether platform fees, taxes, or visiting charges are calculated in the background at this stage or deferred until address and slot confirmation.

---

### E. Address Selection & Scheduling Modal

* **OBSERVATION:**  
  Tapping "Add address and slot" triggers a scheduling bottom-sheet modal (S005, Pages 21–22):
  - Heading: *"When should the professional arrive?"*.
  - Instant Delivery Option: *"Instant / In 30 mins / Unavailable at the moment"* (disabled radio button).
  - Scheduled Delivery Option: *"Schedule for later / Select your preferred day & time"* (active radio button).
  - Date carousel: *"Today 18"* (selected), *"Sat 19"*, *"Sun 20"*, *"Mon 21"*.
  - Time slots for Today 18: *"06:30 PM"*, *"06:45 PM"*, *"07:00 PM"*.
  - Selecting *"06:30 PM"* enables the primary CTA: **"Proceed to checkout"**.
* **IMPLICATION:**  
  The scheduling modal enforces slot confirmation before checkout. The selected slot is an evening slot (6:30 PM on a Friday). No surge pricing indicators, peak slot warnings, or convenience fees are displayed on the time slot buttons in this specific view.
* **UNKNOWN:**  
  Whether selecting weekend slots (Saturday/Sunday) or peak morning hours triggers dynamic surge pricing flags in the UI.

---

### F. Checkout Review Screen

* **OBSERVATION:**  
  Upon confirming slot and address, the user lands on the checkout review screen (S005, Page 23):
  - Top header displays *"Your cart"*.
  - Savings banner persists: *"Saving ₹100 on this order"*.
  - Service line item displays: *"Foam-jet service (2 ACs)"*, quantity `1`, displayed price **₹1,098** (crossed-out ₹1,198).
  - Confirmed address card: *"Home - 47, Mumbai Central, Mumbai, Maharash..."* (with edit pencil icon).
  - Confirmed slot card: *"Fri, Sep 18 - 06:30 PM"* (with edit pencil icon).
  - Primary bottom button: **"Proceed to pay"** (solid purple).
  - Mandatory legal policy disclaimer directly under CTA: **"By proceeding, you agree to our T&C, Privacy and Cancellation Policy."** (with hyperlinked blue text).
* **IMPLICATION:**  
  The checkout screen presents the confirmed service, delivery address, and time slot. The only monetary amount visible on the page remains **₹1,098**. The application explicitly binds the user to the Cancellation Policy at the point of tapping "Proceed to pay".
* **UNKNOWN:**  
  Whether a full bill breakdown (itemizing taxes, platform fees, or convenience charges) was accessible via scrolling down the checkout screen (the screenshot captures the bottom CTA anchored above the system bar).

---

### G. Payment Selection & Observed Price Discrepancy

* **OBSERVATION:**  
  Tapping "Proceed to pay" transitions to the "Select payment method" screen (S005, Pages 24, 26):
  - Prominent header subtitle reads: **"Amount to pay: ₹1,197"**.
  - Payment options listed: UPI (*PhonePe*, *Amazon Pay*, *MyAirtel with ₹100 cashback on min ₹300*, *Add UPI ID*), Cards (*Add new card*), Wallet (*Amazon Pay Balance*), Pay with app (*CRED Pay*), Netbanking, and Pay Later (*Pay later online*, *Pay later with cash*).
  - Page 25 captures an intermediate state: animated three dots with *"Please wait / Verifying your payment status"*.
  - **Observed Numerical Discrepancy:** The payable amount on the payment screen is **₹1,197**, compared to **₹1,098** displayed on the cart and checkout screens — an exact difference of **₹99**.
  - **UI Breakdown Visibility:** The captured payment screen does **not** display an itemized invoice, tax breakdown, or fee explanation explaining what the ₹99 represents.
* **IMPLICATION:**  
  A customer proceeding from checkout to payment experiences a ₹99 increase in the total required outlay at the final payment step. Because no itemized breakdown is visible on the captured payment screen, the user is presented with a higher payable figure without an immediate inline explanation.
* **UNKNOWN:**  
  The precise commercial or statutory breakdown of the ₹99 difference (e.g., whether it represents platform convenience fees, goods and services tax / GST, technology fees, or visiting charges). The captured screenshots establish the numerical discrepancy across screens but do not establish its composition.

---

### H. Cancellation Policy Modal

* **OBSERVATION:**  
  Inspecting the in-cart Cancellation Policy modal (S006, Page 1) reveals the following verbatim policy text:
  > *"Cancellation Policy*  
  > *Urban Company has a fair cancellation policy. Our Professionals block time for jobs, and cancellations lead to lost revenue for them. We only charge cancellation fees when a Professional has been assigned to a job (since they no longer get any other jobs for that time). Depending on the service, customers have some time after placing the request to cancel the job without incurring a fees"* [sic].  
  Dismissal CTA: *"Okay, got it"*.
* **IMPLICATION:**  
  The policy grounds cancellation fees in partner revenue protection and opportunity cost. It articulates two governing principles: (1) fees apply only *after* a professional is assigned, and (2) a fee-free grace period exists immediately after booking placement.
* **UNKNOWN:**  
  The exact fee amount (e.g., ₹50 flat vs variable percentage), the exact duration of the grace period (e.g., 5, 10, or 15 minutes), how service-specific variations are applied, and what rules govern situations where the professional arrives late or fails to appear.

---

### I. Help & Support Architecture

* **OBSERVATION:**  
  The user profile screen (S005 Page 27; S006 Page 2) features a dedicated *"Help & support"* tile at the top level alongside *"My bookings"* and *"Native devices"*.  
  Tapping it opens the "Help" directory (S006, Page 3) titled *"All topics"*, which lists six primary categories:
  1. *Account*
  2. *Getting started with UC*
  3. *Payment & UC Credits*
  4. *UC Plus Membership*
  5. *UC Safety*
  6. *Claim Warranty*
* **IMPLICATION:**  
  Help and dispute resolution pathways are surfaced directly in primary profile navigation. Key transactional friction categories (Payment, Warranty, Safety) have structured entry points.
* **UNKNOWN:**  
  Whether live human telephone support or chat escalation is accessible within these topic trees, whether an automated chatbot gate mediates inquiries, and the average response latency.

---

### J. Safety Disclosures

* **OBSERVATION:**  
  The safety support article (S006, Page 4) titled *"Know more about Urban Company's safety measures"* states:
  > *"At Urban Company, the safety of customers and professionals is taken extremely seriously. To ensure this, we have taken the following precautionary measures:*  
  > *• We conduct background verification on all our professionals*  
  > *• In case of any critical support, SOS button is available in app for both our customers and professionals"*  
  Includes a *"Was this article helpful?"* feedback widget.
* **IMPLICATION:**  
  Safety commitments in the product are anchored in pre-service background checks and an in-app emergency SOS mechanism.
* **UNKNOWN:**  
  The operational rigor of background verification (document KYC vs criminal record check), and the physical dispatch and escalation protocols triggered by the SOS button.

---

### K. Warranty Disclosures & Exclusions

* **OBSERVATION:**  
  The Help center warranty article (S006, Pages 5–6) titled *"Which services are covered under UC warranty?"* states:
  > *"UC Warranty covers:*  
  > *1. Appliance repairs like AC, RO, Washing machine repairs etc.*  
  > *2. Pest control services*  
  > *3. Painting services*  
  >  
  > *However, the UC warranty does not cover:*  
  > *1. Any new issue that occurs post the service*  
  > *2. Any item/service that is not mentioned on the invoice"*
* **IMPLICATION:**  
  Warranty coverage is strictly bounded by the official invoice and excludes "new issues". This provides clear contractual protection for the platform, but creates a significant vulnerability for customers who accept undocumented technician add-ons or face secondary appliance failures post-service.
* **UNKNOWN:**  
  The criteria used by customer support to distinguish a "new issue" from a defective repair, warranty dispute resolution rates, and whether damage protection (advertised as ₹10,000 on the AC detail page) is administered through warranty claims or third-party insurance.

---

### L. My Bookings & Rebooking Observability

* **OBSERVATION:**  
  The user profile (S005 Page 27; S006 Page 2) contains a prominent *"My bookings"* tile. Tapping it opens the "My bookings" screen (S005, Page 28), which displays an empty state:
  > *"No bookings yet.*  
  > *Looks like you haven't experienced quality services at home.*  
  > *Explore our services ->"*  
  Top right features a *"Help"* button.
* **IMPLICATION:**  
  A dedicated booking history interface exists within the native app. However, because the test account had no prior completed transactions, no historical order cards, past professional profiles, or repeat booking CTAs were rendered.
* **UNKNOWN:**  
  The actual UI/UX of a populated "My Bookings" screen, whether a "Book Again" or "Rebook Same Professional" button is available on completed orders, how technician availability is surfaced on rebooking, and whether rebooking prices match initial booking rates.

---

*Stage: RESEARCH (Phase 2 Walkthrough Completed).*  
*Last updated: 2026-09-18 (Task 6 Firsthand Inspection Logged)*

