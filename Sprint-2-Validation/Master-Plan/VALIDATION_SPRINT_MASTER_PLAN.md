# Validation Sprint — Master Plan
## PhyLo | Founder Institute South Africa 2026 | Launch Track
### Due: June 1, 2026 | Session: May 25, 2026, 6pm SAST

---

## Overview

The Validation Sprint moves from *exploring ideas* (Sprint 1) to *selecting and validating a single business* (Sprint 2). The core goal shifts from "what should we build?" to "what should we build, is anyone willing to pay for it, and can we demonstrate it works?"

**The through-line across all 6 sets:**
> Select one business → understand the customer deeply → build a mockup that solves one real workflow → demonstrate it clearly → confirm it solves a real pain point for the pilot partner.

**Dependencies between sets:**
```
Set 1 (Business Selection)
       ↓
Set 2 (Customer Development — uses selected business from Set 1)
       ↓
Set 3 (Initial Mockup — uses customer dev data from Set 2)
       ↓
Set 4 (Mockup Demo — uses mockup from Set 3)
       ↓
Sets 5 + 6 (Audit Demo + Pilot Validation — can run in parallel after Set 4)
```

**Key sprint-level deadline:** June 1, 2026. Session is May 25, 2026. The demo is presented at the Weekly Strategy Presentation.

---

## Cross-Sprint Linkages: Sprint 1 → Sprint 2

### What Sprint 1 Gave Us (From the 7 Sets Completed)

**From Set 1 (Ideation):**
- 10 initial ideas, narrowed to 4 landing pages tested via Ideaster
- Market evidence: R1.5B/yr SA fleet theft, R250k/month for 80-truck Gauteng fleet, R3M saved in 8 months by Avis 89-vehicle fleet
- Why now: PINNs accessible, April 2026 diesel price shock (+32.5%), alert fatigue gap, USD 230M market, 15–18% CAGR
- Winning wedge: Month-End Fuel Audit

**From Set 2 (Customer Problems):**
- 5 synthesized customer problems with evidence
- Warm lead contacts: Dheyaan, Omphile, Simon, James
- Ideaster result: only Month-End Fuel Audit converted (1 of 5 visits)
- Sharpest pain: finance reconciliation, accountability gap, cross-border risk

**From Set 3 (Purpose):**
- Personal purpose: "I want to make fuel monitoring actually tell fleets what happened — not just alert them that something might be wrong"
- The accountability gap drives everything

**From Set 4 (Pitch Madlibs):**
- 3 ideas pitched: Month-End Fuel Audit, Alert Sanity Filter, Theft Case File Reports
- Selected: Month-End Fuel Audit for Weekly Strategy Presentation

**From Set 5 (Supply Chain Risk Mapping):**
- Pilot partner primary route: Rustenburg → Harare (Zimbabwe)
- 3 risk zones mapped: N4/Rustenburg, Botswana transit, Plumtree/Beitbridge border
- Engine prioritization: dual-tank false positive elimination first, then cross-border attribution, then full corridor model

**From Set 6 (AI Proficiency):**
- Landing page hub built and pushed to GitHub
- AI proficiency demonstrated across the sprint outputs

**From Set 7 (Audit Report Design):**
- 3 audit report templates generated (Timestamp, Location, Confidence formats)
- Compliance team feedback simulated (pending actual pilot partner review)
- Final consolidated template: 97.3% confidence, GRADE A evidence, tested with synthetic theft scenario
- Fields: incident ID, timestamp, GPS, speed anomaly, dwell time, confidence score, narrative summary

---

## Set 1: Business Selection

### What Needs to Be Done

1. **Review feedback for each of the three Sprint 1 businesses** — use customer problems (Set 2), working group feedback (TBD), mentor feedback (TBD)
2. **Write bulleted list of strongest signals and concerns** for each business
3. **Estimate revenue potential** — market size, willingness to pay, rough path to R1M annual revenue (~$55k USD)
4. **Score each business 1–5** (no 3s) on real customer problems and real revenue potential
5. **Write selection rationale** (2–3 sentences)
6. **Share with Working Group and at least one Mentor** — pressure test and record feedback
7. **Document final adjustments** based on that pressure test

### The Three Businesses to Evaluate

Based on Sprint 1 outputs, PhyLo has three plausible businesses from the pitch madlibs (Set 4):

**Business A — Month-End Fuel Audit** (highest signal)
- What it is: Automated monthly report showing vehicle-by-vehicle fuel accountability — route-verified consumption, anomalies classified with confidence scores, loss values in Rands
- Evidence: Only Ideaster conversion, explicitly named by pilot partner as pain point, finance-ready output matches what ops managers cannot produce today
- Revenue potential: R250k/month for 80-truck fleet → R3M/year. SA commercial fleet market ~45,000 vehicles → TAM ~R1.35B/yr at R30k/truck/year. SOM (year 1, SA focus): R180k–R540k ARR
- Concerns: Requires integration into existing telematics; requires finance director buyer, not just ops manager

**Business B — Alert Sanity Filter (Dual-Tank False Positive Elimination)**
- What it is: Physics-informed filter that eliminates dual-tank false positive alerts on parked inclines — turns 30–50 false alerts/week into zero
- Evidence: Directly reported by pilot partner as the fastest path to trust restoration
- Revenue potential: Dual-tank SA long-haul fleet ~8,000–12,000 vehicles. R12k–R24k/truck/year for a focused filter tool → TAM R96M–R288M. Lower per-vehicle but faster to implement
- Concerns: May be seen as a feature, not a business. Operators want the full system, not just the filter. Needs clear standalone value proposition

**Business C — Theft Case File Reports**
- What it is: On-demand report that converts a theft alert into an evidence package suitable for disciplinary hearings, CCMA arbitration, or legal proceedings
- Evidence: Legal/proof framing appealed to ops managers in Ideaster testing (0 conversions — too far from daily workflow)
- Revenue potential: Lower volume, higher price per report. R500–R1,500 per report × 12 reports/year per fleet × 100 fleets = R600k–R1.8M ARR. Niche.
- Concerns: Infrequent purchase — not a recurring revenue business unless bundled. Legal framing didn't convert in landing page testing. Market may want prevention more than prosecution.

### Scoring Framework

| Dimension | Month-End Audit | Alert Sanity Filter | Theft Case Files |
|---|---|---|---|
| Customer problem severity | 5 | 4 | 3 |
| Customer problem frequency | 5 | 5 | 2 |
| Willingness to pay evidence | 4 | 3 | 2 |
| Market size (TAM) | 5 | 4 | 2 |
| Path to R1M ARR | 4 | 3 | 3 |
| Technical defensibility (PINN) | 4 | 5 | 4 |
| Recurring revenue potential | 5 | 4 | 2 |
| **Total** | **32** | **28** | **18** |

### Key Decisions Needed in Set 1

- Which business to select (Month-End Fuel Audit has highest composite score)
- Whether to bundle Alert Sanity Filter as a feature of the Audit business or keep it as a separate product
- Whether Theft Case Files becomes part of the audit output or a separate premium tier
- Who is the primary buyer — fleet ops manager or finance director (this affects the entire go-to-market)
- What the minimum viable customer profile (MICP) is for the first 6 months

---

## Set 2: Customer Development

### What Needs to Be Done

1. **Write customer development script** — open-ended questions uncovering pain points, current solutions, willingness to pay, decision-making process
2. **Rehearse the script** — use AI speaking tools (Poised, Yoodli, or AI-assisted practice)
3. **Recruit at least 15 potential customers** — use warm leads (Dheyaan, Omphile, Simon, James), working group connections, LinkedIn, industry associations
4. **Schedule calls, send reminders, track status** — use a spreadsheet or simple CRM
5. **Conduct 15 interviews** — capture via transcription
6. **Synthesize patterns** — bulleted list of: strongest validations, most concerning signals, new problems uncovered

### Customer Development Script Structure

Based on Sprint 1 customer problems work, the script should cover:

**Block 1 — Context (5 min)**
- Fleet operation overview: vehicles, routes, fuel management tools
- Current fuel monitoring stack: sensors, GPS, telematics, fuel cards, manual processes
- Month-end reconciliation process: who does it, what they produce, what finance asks for

**Block 2 — Problem Exploration (10 min)**
- "Walk me through the last time you had to explain a fuel loss to finance. What happened?"
- "When you get a fuel theft alert — what actually happens next?"
- "Have you ever not taken action on a fuel anomaly because you couldn't prove it? What was that like?"
- "What does the false positive situation look like in your operation?"

**Block 3 — Current Solutions and Spending (5 min)**
- "What are you currently paying for fuel monitoring? What are you unhappy with?"
- "What would you pay for a solution that solved [their described problem]?"
- "Who would write the cheque — you, finance, the owner?"

**Block 4 — Decision Process (5 min)**
- "If I showed you a system that produced a month-end report with vehicle-by-vehicle fuel accountability — confidence scores, alternative hypotheses eliminated, loss values in Rands — what would you need to see to buy it?"
- "Have you ever bought a SaaS product for your fleet operation? What was the process?"
- "What's the biggest reason you'd hesitate to buy something like this?"

**Block 5 — Referrals (3 min)**
- "Who else in your network is managing a similar fleet operation and might want to have this conversation?"
- "Any industry events, WhatsApp groups, or associations where fleet operators connect?"

### Recruitment Plan

| Source | Target | Notes |
|---|---|---|
| Warm leads (Dheyaan, Omphile, Simon, James) | 4 contacts → 4 interviews | Personal outreach, highest conversion likelihood |
| Working Group | 3–5 contacts | FI community, shared context |
| LinkedIn — Gauteng/Rustenburg fleet operators | 5–8 contacts | Specific to N1/N4/Border corridor operators |
| Industry associations (RFA, SATCC) | 3–5 contacts | Road Freight Association, SA Transport Chamber |
| Referrals from warm leads | 2–3 contacts | Warm introductions highest conversion |

---

## Set 3: Initial Mockup

### What Needs to Be Done

1. **Generate Buyer Persona** from customer development data (from Set 2)
2. **Identify single most valuable workflow** — scope it as a buildable mockup that solves that one workflow end-to-end
3. **Build the mockup** — use AI builder (Lovable, Replit Design Mode, or similar)
4. **Iterate on AI output** — don't specify every feature; let the tool show you what's possible
5. **Share an accessible link**

### Buyer Persona (Draft — to be refined with Set 2 data)

> **Name:** Kgabo Moloto | **Role:** Fleet Operations Manager
> **Demographics:** Male, 35–50, Gauteng/Rustenburg-based, managing 30–80 vehicle commercial fleet, R800k–R2M annual fuel budget, 8–12 years transport/logistics experience
> **Goals:** Produce a clean monthly fuel reconciliation for finance, reduce unexplained fuel variance, identify and act on real theft events without false positive noise
> **Challenges:** Existing telematics flags anomalies but provides no accountability document; monthly variance of 5–8% unexplained; inability to act on theft alerts due to lack of proof; cross-border routes where telematics drops offline
> **Buying process:** Will evaluate based on whether the output replaces the manual month-end process and whether the evidence is credible enough to use in disciplinary action. Will not buy without a pilot trial. Price point: R500–R2,000/month depending on fleet size.

### The One Workflow to Mock Up

**The Month-End Fuel Audit Workflow:**

1. Ops manager selects the month (e.g., May 2026)
2. System shows: vehicle list, route-verified expected consumption, actual consumption, variance (L and Rands), anomaly flags
3. Ops manager clicks on flagged vehicle → sees the audit report (timestamp, location, confidence score, alternative hypothesis elimination, narrative summary)
4. Ops manager clicks "Export for Finance" → generates PDF with all vehicles, total variance, total loss value
5. Ops manager shares PDF with finance director — reconciliation complete in 10 minutes instead of 3 hours

**This is the one workflow.** Everything else (real-time alerts, cross-border monitoring, driver exoneration) is downstream. The month-end reconciliation document is the wedge.

---

## Set 4: Mockup Demo

### What Needs to Be Done

1. **Outline the demo flow** — Selected Business, Buyer Persona, core workflow, pricing feedback
2. **Test the mockup end-to-end** — confirm it runs reliably for a 3-minute walkthrough
3. **Fix any issues** — document fixes made
4. **Rehearse the demo aloud** — at least 3 times, use Poised/Yoodli to refine pacing
5. **Share with Working Group** — practice run, record feedback
6. **Document WG feedback and changes**
7. **Provide accessible link to mockup**

### Demo Flow (Draft)

**Total: 3 minutes**

1. **Who am I / what is the problem** (30 sec)
   - "PhyLo helps fleet operators prove where their fuel went — instead of guessing"
   - Problem: 5–8% monthly fuel variance unexplained, no audit document, no accountability

2. **Who is the buyer** (15 sec)
   - Kgabo, Fleet Ops Manager — "He manages 60 vehicles, spends R1.2M/month on diesel, and every month he has to explain R60k of unexplained loss to finance with nothing to show for it"

3. **The workflow** (1 min 30 sec)
   - "Every month-end, Kgabo opens PhyLo and sees all 60 vehicles. Green means on-track. Red means anomaly. He clicks on any anomaly and sees the full audit report — where, when, how much, confidence score, and in plain English: this is what happened."
   - Walk through: month selection → vehicle list → anomaly flag → audit report → finance export

4. **The evidence** (30 sec)
   - "Every report shows confidence score, alternative hypotheses eliminated, chain of custody verified. This is the document Kgabo hands to finance — and if he needs it, to HR or law enforcement"

5. **The ask** (15 sec)
   - "We're running a pilot with a 42-vehicle cross-border fleet. If you manage a fleet and this pain resonates, I'd love to talk"

---

## Set 5: Audit Report Demo (Customized)

### What Needs to Be Done

1. **Design a one-page audit report format** with fields: incident ID, timestamp, GPS coordinates, speed anomaly, dwell time, confidence score, narrative summary
2. **Generate a sample report** for a confirmed theft scenario using tuned model on pilot data — narrative in plain English
3. **Share with pilot partner** — write bulleted feedback on clarity, usefulness, missing fields

### Connection to Sprint 1

Set 7 from Sprint 1 (Audit Report Design) already built the full 3-template system. Set 5 of Validation Sprint is essentially the *product-facing demo version* of that — simplified to one page, optimized for the buyer persona (fleet ops manager), and tested with the pilot partner's actual response.

**Key difference:** Sprint 1 Set 7 was a comprehensive legal/audit document. Validation Sprint Set 5 is the *operational decision-support* version — what the ops manager sees when they click on a flagged vehicle in the mockup.

### One-Page Format (Draft)

```
╔══════════════════════════════════════════════════════╗
║  PHyLO FUEL INCIDENT REPORT         [ID: FUEL-2026-003]║
╠══════════════════════════════════════════════════════╣
║                                                      ║
║  VEHICLE: ZAN 123 GP  |  FLEET: Pilot Partner Fleet   ║
║  ROUTE: Rustenburg → Harare |  DATE: 2026-05-15       ║
║                                                      ║
║  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  ║
║                                                      ║
║  TIMELINE                                            ║
║  02:31 — Vehicle stationary, Plumtree Transit Zone   ║
║  04:43 — Fuel dropped 100.1L while engine OFF        ║
║  Loss rate: 106.3 L/hr (siphon rate, not gauge error) ║
║                                                      ║
║  LOCATION                                            ║
║  −21.9873°S, 27.5432°E | Plumtree Border, Botswana   ║
║  12km from Zimbabwe border | Outside safe-zone fence ║
║                                                      ║
║  CONFIDENCE SCORE                                     ║
║  ████████████████ 97.3% — CONFIRMED THEFT            ║
║                                                      ║
║  ALTERNATIVE HYPOTHESES ELIMINATED:                   ║
║  ✓ Sensor malfunction     — dual sensors confirmed    ║
║  ✓ Thermal contraction    — corrected, still 99.3L   ║
║  ✓ Dual-tank fuel shift  — flat ground confirmed    ║
║  ✓ Engine burn during idle — CAN confirms engine OFF ║
║                                                      ║
║  NARRATIVE SUMMARY                                    ║
║  "Between 02:31 and 04:43 on May 15, 2026, vehicle   ║
║  ZAN 123 GP lost 100.1 litres of diesel while        ║
║  stationary at Plumtree Border Transit Zone. The     ║
║  engine was confirmed OFF via CAN bus. The loss rate ║
║  of 106.3 L/hr is consistent with deliberate         ║
║  siphoning, not natural evaporation. The vehicle was ║
║  outside any safe-zone geo-fence. Estimated value:   ║
║  R 778. Confidence: 97.3%. Proceed to disciplinary." ║
║                                                      ║
║  COST: R 778 | DRIVER: Thabo Mkhize | STATUS: CONFIRMED║
╚══════════════════════════════════════════════════════╝
```

---

## Set 6: Pilot Partner Validation

### What Needs to Be Done

1. **Schedule 30-minute call** with pilot partner's operations lead
2. **Ask three open-ended questions:**
   - "What is your current method for detecting fuel theft, and how confident are you in it?"
   - "What is the cost to your operation of false alarms — in time, money, and trust?"
   - "What would you be willing to pay for a solution that gave you proof you could act on?"
3. **Record verbatim responses**
4. **Compare answers to Key Assumptions** — which are confirmed, which need revision
5. **Write a one-sentence pitch** tailored to this partner's language and pain points

### Key Assumptions to Compare Against

From Sprint 1 customer problems work:

| Assumption | Source | Needs Confirmation |
|---|---|---|
| "We have sensors. We have telematics. Nothing changes." | Pilot partner (Sprint 1 Set 3) | Confirm whether the accountability gap is the core pain |
| 5–8% monthly fuel variance is the norm | Pilot partner (Sprint 1 Set 3) | Confirm the variance figure and frequency |
| Cross-border routes are the highest-risk zone | Sprint 1 Set 5 | Confirm whether Plumtree/Beitbridge is their primary risk |
| Dual-tank false positives are 30–50/week | Pilot partner (Sprint 1 Set 3) | Confirm whether the false positive rate is as high as described |
| Willingness to pay exists | Ideaster conversion (1) | Confirm WTP with direct question |
| Month-End Fuel Audit is the sharpest product | Sprint 1 Set 2 | Confirm whether monthly reconciliation is the buying trigger |

### One-Sentence Pitch (Draft — to refine with call response)

Based on pilot partner language from Sprint 1: "We give you the document you need to tell finance where every litre went — and the proof you need to actually do something about it."

---

## Timeline Recommendation

| Week | Focus |
|---|---|
| Week 1 (May 25–31) | Set 1 (Business Selection) + Set 2 script + begin recruitment |
| Week 2 (Jun 1–7) | Conduct interviews (Sets 2) + Set 3 (Mockup) + Set 5 (Audit Report) |
| Week 3 (Jun 8–14) | Set 4 (Demo rehearsal) + Set 6 (Pilot Partner call) |
| June 1 submission | Everything due to FI editor |

**Note:** Sets 5 and 6 can run in parallel once the audit format is locked. Set 4 is dependent on Set 3 (the mockup must exist). Set 2 is dependent on Set 1 (the business must be selected before writing the script). Plan accordingly.

---

## Sprint 1 → Sprint 2 Summary

| From Sprint 1 | Used In |
|---|---|
| Set 1: Month-End Fuel Audit (only Ideaster conversion) | Set 1 scoring, Set 3 mockup, Set 5 audit |
| Set 2: 5 customer problems, warm leads | Set 2 interviews, Set 3 buyer persona |
| Set 3: Accountability gap insight | Set 1 scoring, Set 4 pitch, Set 6 validation |
| Set 5: Rustenburg → Harare route, border risk zones | Set 6 pilot partner validation |
| Set 7: 3 audit report templates, compliance feedback | Set 5 audit report demo (simplified version) |
| All sets: evidence base for scoring | Set 1 business selection scoring |

*This plan document serves as the master reference for the Validation Sprint. Individual sets will be built as deliverables in sequence.*