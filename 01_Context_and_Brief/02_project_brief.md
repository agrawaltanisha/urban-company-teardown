# PM-01 — Urban Company: Post-Booking Experience in a Two-Sided Marketplace
## 01 — Project Brief

**Stage:** SCOPING (Phase 1 Closure → Entry to Phase 2: RESEARCH)  
**Status:** Redirected under D004 (Active Working Focus: Post-Booking Price Predictability & Transparency)  
**Last updated:** 2026-09-18  

---

## 1. Project Identity

| Field | Value |
|-------|-------|
| Project ID | PM-01 |
| Product | Urban Company |
| Category | Consumer — Two-Sided Home Services Marketplace (India) |
| Selected investigation direction | Pricing transparency / cancellation fairness (Initial working focus: post-booking price predictability and transparency) |
| Historical investigation area | Trust and repeat booking (Original scoping domain at initialization under D001; redirected under D004) |
| Type | Teardown → UX Redesign → PRD (all downstream) |
| Current stage | Stage 1: SCOPING (Phase 1 Closure → Entry to Stage 2: RESEARCH) |
| Folder | `PM/projects/PM-01_Urban_Company/` |

---

## 2. Project Objective

> Determine whether there is a meaningful, evidence-supported user/problem opportunity within Urban Company's post-booking price predictability and cancellation experience, understand its underlying causes and affected user segments, and identify a product opportunity worth taking into UX/PRD development.

**This is a discovery objective — not a solution objective.**

No solution has been selected. No feature has been defined. The objective is to investigate the selected working problem area and arrive at a validated, evidence-backed problem statement. Everything downstream (UX, PRD) depends on what this stage and subsequent research produce.

---

## 3. What This Project Will Eventually Produce

When all stages are complete, this project will produce three artifacts:

1. **Product Teardown** — Analysis of Urban Company's existing product experience, with attention to pricing disclosure, post-booking confirmation, add-on handling, and cancellation mechanics
2. **UX Redesign** — A redesign of a specific flow, grounded in the validated problem
3. **PRD** — A Product Requirements Document for a specific feature or improvement

> **These are downstream outputs.** They cannot be created until the problem is validated through research.

---

## 4. Investigation Area — Important Distinctions & Redirection

| Term | Status | Meaning |
|---|---|---|
| "Trust and repeat booking" | HISTORICAL AREA | Original initialization domain (D001). Re-evaluated and redirected under D004 following review-mining evidence. |
| "Pricing transparency / cancellation fairness" | SELECTED INVESTIGATION DIRECTION | The active domain approved under D004 for Phase 2 research. Not a validated problem statement. |
| "Post-booking price predictability and transparency" | WORKING PROBLEM AREA | Initial narrowed focus for Phase 2 investigation to be validated through remaining research. |
| The validated problem statement | NOT YET EXISTS | Must emerge from remaining research (Phase 2) and synthesis (Phase 3). |
| The recommended solution | NOT YET EXISTS | Cannot be selected before the problem is validated. |

### Redirection Rationale (D004)
The project originally began with "trust and repeat booking" as its approved exploration area (`D001`). However, systematic quantitative and qualitative review mining across 179 customer reviews revealed that explicit repeat-booking friction accounted for only $3.4\%$ of all reviews (`E009`), whereas pricing transparency and unexpected surcharges (`E004`, $25.7\%$ overall, $37.3\%$ of negative reviews) and cancellation friction (`E005`, $14.5\%$ overall, $37.3\%$ of negative reviews) were co-dominant drivers of customer dissatisfaction. 

Within pricing, $28.3\%$ of pricing-themed reviews cited concrete post-booking mechanisms (`E014`), including unexpected surge fees added after slot selection, platform convenience charges, and on-site technician add-on demands, alongside asymmetric ₹50 cancellation penalties (`E012`). Stated switching comparisons to local mechanics were observed (`PAT-10`), while multiple 5-star reviews praised clear upfront pricing (`R0001`, `R0008`, `R0033`, `R0035`), proving that the customer issue is predictability and expectation setting rather than baseline price levels.

Under human decision `D004`, the core investigation was formally redirected to **Pricing Transparency / Cancellation Fairness**, with an initial working emphasis on **post-booking price predictability and transparency**.

### Working Investigation Frame
> *"Investigate whether customers lose confidence when post-booking prices or cancellation consequences differ materially from what they reasonably expected at booking."*

*(Important: This is an active working investigation frame to guide discovery, NOT yet a final validated problem statement and NOT yet a solution).*

**ASSUMPTION & BOUNDARY — explicitly labelled:**  
It is currently assumed that post-booking price predictability is a *meaningful working investigation area*. Whether it is the *primary driver* of customer churn, whether fee structures impact retention or LTV, or whether this friction is addressable at the product/UX level without harming marketplace unit economics — none of these are established. They remain research questions to be validated through remaining research (Tasks 6–8).

---

## 5. Scope Boundaries

### In Scope — Stage 1 / Phase 2 Research
- Understanding Urban Company's product and business model (public sources)
- Understanding the customer experience across booking disclosure, fee presentation, surge application, add-on authorization, and cancellation policies
- Understanding the professional (supply-side) experience regarding add-on services, parts billing, and cancellation penalties as far as public evidence allows
- Identifying user pain points related to fee predictability, surge mechanics, and cancellation fairness through public evidence and product walkthroughs
- Forming and refining testable hypotheses against the redirected working frame
- Building an auditable evidence log

### Out of Scope — Stage 1 / Phase 2 Research
- Solution design of any kind (no fee waivers, fee removals, price locks, or cancellation policy rewrites)
- UX flows or redesign work
- PRD writing
- Final feature specification
- Metrics framework finalization
- MVP definition
- Competitor deep-dive (this comes later, after the core problem is defined)

### Out of Scope — Entire Project
- Internal Urban Company data (unavailable)
- Real-time booking volumes or conversion rates (not publicly available)
- Professional-side earnings data (not publicly available)
- Internal unit economics, take-rates, or EBITDA fee contribution (unverified; tracked as explicit research gaps)

---

## 6. Evidence Constraints

Per EVIDENCE_POLICY.md and RESEARCH_PROTOCOL.md:

- No fabricated user quotes
- No invented metrics
- No AI-generated statistics presented as research findings
- All claims must be labelled per the classification system (FACT / ASSUMPTION / HYPOTHESIS / RESEARCH FINDING / ESTIMATE)
- Public community evidence (Tier C) may be used for qualitative signals — must be labelled and bias acknowledged

---

## 7. Two-Sided Marketplace Reminder

Urban Company is not a consumer app. It is a two-sided marketplace. This project must consistently consider:

- **Customer side:** The person booking and paying for a service
- **Professional/supply side:** The trained service professional (gig worker / platform partner)
- **Platform layer:** How Urban Company mediates, incentivizes, and controls quality between the two sides

> Any product decision that improves the customer experience may have second-order effects on the professional or platform. This must be considered before any recommendation is made.

---

## 8. Stage 1 Exit Criteria

Stage 1 (SCOPING) is complete when:
- [x] This project brief is reviewed, confirmed, and updated (`01_project_brief.md`, redirected under D004)
- [x] Research plan is finalized (`03_research_plan.md`)
- [x] Initial hypotheses are logged and updated (`08_problem_discovery.md`)
- [x] Evidence system is initialized and audited (`04_source_log.md`, `05_evidence_matrix.md`, `06_assumption_log.md`)
- [x] PROJECT_INDEX.md is updated
- [x] First research phase completed and audited (Tasks 1–5 completed, D004 finalized)

---

## 9. Downstream Stage Overview

| Stage | What happens |
|---|---|
| Stage 2: RESEARCH | Execute remaining research (Walkthrough, External Triangulation, Primary Research); log all sources |
| Stage 3: ANALYSIS | Segment users; analyze evidence; map patterns against redirected focus |
| Stage 4: SYNTHESIS | Arrive at validated problem statement |
| Stage 5: SOLUTION | Define product direction (Teardown + UX + PRD) |
| Stage 6: VALIDATION | Red-team review |
| Stage 7: DOCUMENTATION | Final artifacts |
| Stage 8: REVIEW | Quality scoring ≥ 8/10 |

---

## 10. Skill Coverage This Project Targets

| PM Skill | Coverage |
|---|---|
| Product sense | ✓ Teardown |
| User empathy | ✓ Evidence-based user research |
| Problem discovery | ✓ Core Stage 1–4 activity |
| Research | ✓ Systematic evidence collection |
| Marketplace thinking | ✓ Two-sided dynamics |
| Prioritization | ✓ Stage 4–5 |
| UX thinking | ✓ UX Redesign |
| PRD writing | ✓ PRD artifact |
| Metrics | ✓ Metrics framework (Stage 5+) |

---

*This brief governs the project until superseded by a later version.*  
*Stage: SCOPING (Phase 1 Closure → Entry to Stage 2: RESEARCH) | Redirected under D004: 2026-09-18*
