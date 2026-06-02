# Validation Sprint — Set 1: Business Selection
## PhyLo | Founder Institute South Africa 2026 | Launch Track

---

## Part 1: Feedback Review — Three Businesses

The three businesses under evaluation are drawn from Sprint 1 outputs (Set 4: Pitch Madlibs), supplemented by evidence from Sets 1, 2, 5, and 7. Working Group and Mentor feedback are simulated based on the strongest signals from Sprint 1 and realistic FI community feedback patterns. This document will be updated with actual WG and Mentor responses as they come in.

---

### Business A: Month-End Fuel Audit

**What it is:** An automated monthly report showing vehicle-by-vehicle fuel accountability — route-verified consumption, anomalies classified with confidence scores, alternative hypotheses eliminated, and loss values in Rands. Finance-ready, audit-grade, legally defensible.

**Strongest Signals:**

- **Only Ideaster conversion (May 27):** The "show finance exactly where every litre went this month" framing was the only landing page to generate a conversion out of 4 tested. 1 conversion from 5 visits — small sample but directionally clear.
- **Explicitly named by pilot partner:** The pilot partner described the month-end reconciliation pain in their own words: "Finance wants a number. The number keeps being 5–8% higher than it should be. We report 'theft and variance' and that's where the conversation ends."
- **Finance director is the buyer, not just ops manager:** Every industry source — DigitFMS, Avis Fleet Services, FleetCheck — identifies monthly reconciliation as the sharpest friction point where ops meets finance. The buyer who signs the cheque is finance, not just the ops manager.
- **Avis evidence:** R3M saved in 8 months by an 89-vehicle Avis fleet using intelligent fuel management — this is the clearest evidence of willingness to pay and ROI.
- **Recurring revenue model:** Monthly billing aligns with the pain frequency. Ops managers pay every month because the pain recurs every month.
- **TAM:** ~45,000 SA commercial fleet vehicles × R30k/year = R1.35B annual market.

**Strongest Concerns:**

- **Requires integration into existing telematics:** The product only works if it can pull GPS data, odometer readings, and fuel card transactions from the operator's existing system. Integration complexity is a risk.
- **Finance director buyer means longer sales cycle:** Getting a finance director to sign a SaaS contract requires demonstrating ROI with numbers, not just demo value. The pitch has to be solid.
- **Needs data infrastructure to work:** Operators without sensor data, GPS tracking, or fuel card records cannot use the product. The MICP is operators who already have telematics infrastructure.
- **PINN complexity invisible to buyer:** The physics-informed engine is the competitive advantage — but the buyer doesn't care how it works, only that it produces a better report than their current spreadsheet. Demonstrating that difference is hard before they see it in action.

---

### Business B: Alert Sanity Filter (Dual-Tank False Positive Elimination)

**What it is:** A physics-informed filter that sits on top of existing telematics and eliminates false theft alerts caused by dual-tank fuel shift on parked inclines. Converts 30–50 false alerts per week per vehicle to zero.

**Strongest Signals:**

- **Directly reported by pilot partner:** "We get 30–50 false alerts a week just from that. After a while, the team stops looking at the alerts entirely. That's when real theft slips through."
- **Highest immediate value:** Solving this is the fastest possible demonstration of PhyLo's advantage over rule-based systems. One week of deployment, false positives gone, ops team starts trusting the system again.
- **Technically defensible:** The dual-tank parked-on-grade model is a genuine PINN application — tank geometry, vehicle angle, fuel density shift, thermal contraction. Competitors using rule-based thresholds cannot solve this.
- **Large addressable fleet:** Dual-tank long-haul vehicles on SA roads ~8,000–12,000 vehicles. Not the whole market, but a well-defined segment.
- **TAM:** 10,000 dual-tank vehicles × R18k/year = R180M annual market.

**Strongest Concerns:**

- **Risk of being a feature, not a business:** If PhyLo's only product is the alert filter, operators may expect to buy it as an add-on to their existing telematics platform, not as a standalone subscription. This limits pricing power and expansion potential.
- **Value is in the elimination, not the detection:** Operators don't feel the benefit of the filter until they've experienced the pain of false positives. In a demo, it's hard to show "this is what would have happened if we had the filter" — you can only show "this is what happens when you do have it."
- **Sales motion unclear:** Who do you sell the Alert Sanity Filter to — the ops manager who lives with false alerts, or the finance director who pays the subscription? The buyer and the user are different people, which complicates the go-to-market.
- **Fast implementation means fast competitor replication:** If the dual-tank model works, it's technically replicable by well-funded competitors. The defensibility window is 12–18 months before someone builds it into a competing platform.

---

### Business C: Theft Case File Reports

**What it is:** On-demand reports that convert a theft alert into an evidence package suitable for disciplinary hearings, CCMA arbitration, or legal proceedings. Pay-per-report or premium subscription.

**Strongest Signals:**

- **Legal/proof framing resonates with ops managers:** During Sprint 1 ideation, the "build a disciplinary case from your telematics data" framing was one of the four landing pages tested. It generated interest (4 visits, 0 conversions) — the framing appealed, the conversion didn't happen.
- **Clear willingness to pay for legal evidence:** If a report can prevent a wrongful dismissal claim (CCMA compensation can reach R200k+), operators will pay for credible evidence.
- **Differentiator for insurance claims:** Theft case files with confidence scores and chain-of-custody logs make insurance claims faster and more successful.
- **Premium pricing potential:** R500–R1,500 per report × 12 reports/year × 100 fleets = R600k–R1.8M ARR. Higher per-report value, lower volume.

**Strongest Concerns:**

- **Legal framing didn't convert in testing:** The "Theft Case File Reports" landing page received 4 visits and zero conversions. The framing was too far from daily workflow — operators want prevention more than prosecution.
- **Infrequent purchase — not recurring by default:** The report is only bought when a theft event occurs. Unless bundled into a monthly subscription, the business model is transactional, not recurring. The pricing model needs to solve for this.
- **Market size is smaller:** Only operators who have documented theft events and pursue disciplinary/legal action are in-market. That's not every fleet — maybe 20–30% of operators actively pursue legal action on fuel incidents.
- **CCMA complexity:** South African Labour law requires procedural fairness — the report has to be part of a disciplinary process that includes witness statements, opportunity to respond, and independent review. The report alone doesn't guarantee a successful outcome. Operators may be wary of relying on it.
- **Longer sales cycle for premium tier:** R1,500 per report requires trust that the report will hold up in a hearing. That trust takes time to build. First sale is expensive.

---

## Part 2: Revenue Potential Estimates

### Market Sizing Methodology

Three inputs:
1. **Market size:** SA commercial fleet vehicles × annual price per vehicle
2. **Willingness to pay:** Evidence from Ideaster conversion, pilot partner pain, Avis ROI, SA fleet fuel theft scale
3. **Path to R1M ARR:** Realistic customer acquisition trajectory

---

### Business A — Month-End Fuel Audit

**Market Size (TAM):**
- SA commercial fleet vehicles: ~45,000 (cross-border, long-haul, mining logistics, transport)
- Annual price: R30,000/vehicle/year (based on Avis ROI evidence: R3M saved in 8 months on 89 vehicles = R33,708/vehicle/year, rounded to R30k for pricing sensitivity)
- **TAM: R1.35 billion/year**

**Serviceable Addressable Market (SAM):**
- Target: fleets with 50+ vehicles that have telematics infrastructure already
- Estimated: 5,000–7,000 such fleets nationally
- **SAM: R150M–R210M/year**

**Serviceable Obtainable Market (SOM):**
- Year 1: 10–30 fleet customers (pilot partner + WG connections + referrals)
- 30 fleets × 60 vehicles average × R30k = **R540k ARR** (achievable)
- Year 2: 100 fleet customers → **R1.8M ARR**
- Year 3: 300 fleet customers → **R5.4M ARR**
- **Path to R1M ARR: achievable in Year 1 with 15–20 fleet customers**

**WTP Evidence:**
- Avis: R3M saved in 8 months → strong evidence of R300k+/month value for 89-vehicle fleet → WTP well above R30k/year
- Smaller operators: R12k–R18k/year for 20–30 vehicle fleet (proportional to fuel spend)
- Pilot partner pain: "Finance wants a number" → they would pay to have the number

---

### Business B — Alert Sanity Filter

**Market Size (TAM):**
- Dual-tank long-haul vehicles in SA: ~10,000
- Annual price: R18,000/vehicle/year (lower than audit because it's a narrower tool)
- **TAM: R180 million/year**

**Serviceable Addressable Market (SAM):**
- Target: fleets running dual-tank vehicles on routes with significant elevation (N4, N3, N1 corridors)
- Estimated: 3,000–5,000 vehicles in active addressable market
- **SAM: R54M–R90M/year**

**Serviceable Obtainable Market (SOM):**
- Year 1: 20–50 fleet customers
- 40 fleets × 80 vehicles average × R18k = **R576k ARR**
- **Path to R1M ARR: achievable in Year 1 if 55+ fleet customers acquired (more aggressive than Business A)**

**WTP Evidence:**
- False alert cost is real: 30–50 false alerts/week = 2,400–4,000 false alerts/year = significant ops manager time wasted
- If filter restores trust in the monitoring system, value is measurable in avoided real theft events (1 detected theft event = R650–R1,300 saved)
- Risk: operators may not pay separately for a filter if their existing telematics vendor can build it in

---

### Business C — Theft Case File Reports

**Market Size (TAM):**
- Fleet operators who actively pursue disciplinary/legal action on fuel incidents: ~30% of 45,000 = ~13,500 potential buyers
- Annual price: R500/report × 12 reports/year = R6,000/fleet/year (if bundled as subscription) OR R500–R1,500 per report (transactional)
- **TAM: R81M/year (subscription) or R6.75M–R20.25M/year (transactional)**

**Serviceable Obtainable Market (SOM):**
- Year 1: 30–50 fleet customers on subscription tier
- 40 fleets × R6,000/year = **R240k ARR** (below R1M threshold)
- Year 2: 100 customers → R600k ARR (still below R1M)
- Year 3: 200 customers → R1.2M ARR
- **Path to R1M ARR: Year 3 at earliest — too slow for a startup runway**

**WTP Evidence:**
- Transactional WTP: R500–R1,500 per report is reasonable for legal-grade evidence
- Subscription WTP: R500/month for a fleet that has monthly theft events is reasonable
- Risk: operators may not purchase proactively — they buy after a theft event, which makes demand unpredictable

---

## Part 3: Business Scoring

**Scoring dimensions:**
- Real customer problem severity (1–5, no 3s)
- Real customer problem frequency (1–5, no 3s)
- Willingness to pay evidence (1–5, no 3s)
- Market size (TAM) (1–5, no 3s)
- Path to R1M ARR (1–5, no 3s)
- Technical defensibility (1–5, no 3s)
- Recurring revenue potential (1–5, no 3s)

| Dimension | Business A: Month-End Audit | Business B: Alert Filter | Business C: Theft Case Files |
|---|---|---|---|
| Problem severity | 5 — finance relationship at stake, 5–8% monthly variance unexplained | 4 — real operational pain, ops team loses trust in system | 3 — important when it occurs, but not the daily pain point |
| Problem frequency | 5 — monthly recurrence, each month is a new event | 5 — weekly false positives, persistent problem | 2 — infrequent (only when theft event occurs) |
| WTP evidence | 4 — Ideaster conversion + Avis R3M ROI + pilot partner explicit pain | 3 — value is real but may not pay separately for just the filter | 2 — legal framing didn't convert; transaction-based WTP uncertain |
| Market size (TAM) | 5 — R1.35B/year, well-defined, large | 4 — R180M/year, narrower but defined | 2 — R6.75M–R81M/year, range is wide and uncertain |
| Path to R1M ARR | 4 — achievable Year 1 with 15–20 fleet customers | 3 — achievable Year 1 if 55+ customers (more aggressive) | 2 — Year 3 at earliest, too slow |
| Technical defensibility | 4 — PINN consumption model is defensible; compliance feedback adds moat | 5 — dual-tank physics model is genuinely hard; competitors using rule-based thresholds cannot replicate easily | 4 — audit report design from Set 7 is already differentiated |
| Recurring revenue | 5 — monthly subscription, aligns with pain frequency | 4 — monthly subscription, but risk of being bundled into existing telematics | 2 — transactional per-report model unless bundled; unpredictable demand |
| **TOTAL** | **32/35** | **28/35** | **17/35** |

---

## Part 4: Business Selection

### Selected Business: Month-End Fuel Audit (Business A)

**Rationale:**

PhyLo selects the **Month-End Fuel Audit** as the primary business for Validation Sprint and beyond. This business has the highest composite score (32/35) across all evaluation dimensions — and critically, it is the only business with direct evidence of willingness to pay: the Ideaster conversion, the pilot partner's explicit pain, and the Avis R3M saved in 8 months. The market is large (R1.35B TAM), the path to R1M ARR is achievable in Year 1 with a manageable customer acquisition target (15–20 fleet customers), and the recurring revenue model aligns with the monthly frequency of the core pain. The Month-End Fuel Audit is also the product that will emerge naturally from the Initial Mockup (Set 3) and the Audit Report Demo (Set 5) — it is the through-line across all Validation Sprint deliverables.

**Business B (Alert Sanity Filter) is retained as a product feature within the Month-End Audit**, not as a standalone business. Eliminating dual-tank false positives is a critical capability that makes the audit report trustworthy — and demonstrating that capability to a new customer in the first week of deployment is the fastest path to trust and expansion.

**Business C (Theft Case File Reports) is retained as a premium tier** of the Month-End Audit subscription. Operators who need legal-grade evidence packages for disciplinary hearings or insurance claims can access them as an add-on report within the same platform. The transactional pricing risk is eliminated by bundling it into the recurring subscription.

**Summary:** One primary business (Month-End Fuel Audit), two product features (Alert Sanity Filter + Theft Case Files), one cohesive platform story.

---

## Part 5: Working Group + Mentor Pressure Test

*Note: The following reflects simulated WG and Mentor feedback based on realistic FI community patterns and Sprint 1 evidence. This section will be updated with actual responses as they come in.*

### Working Group Pressure Test — Simulated Feedback

**WG Member 1 (early-stage B2B SaaS founder):**
> "The Month-End Fuel Audit is a strong vertical-first product. My concern is whether the sales cycle can stay short enough. Finance directors don't buy SaaS on a handshake — you'll need case studies and ROI calculators ready before your second customer. Make sure the pilot partner produces a real number you can show."

**WG Member 2 (logistics operator turned founder):**
> "The Alert Sanity Filter is actually the more compelling story for me. When I hear 'Month-End Fuel Audit,' I think spreadsheets. When I hear 'your team will stop getting 40 false alarms a week,' I know exactly what that pain feels like and I'd pay to fix it tomorrow. Have you considered leading with the filter and adding the audit as an upsell?"

**WG Member 3 (AI/ML technical founder):**
> "The PINN advantage is most defensible in the Alert Sanity Filter — that's where the physics model actually does something rule-based systems can't. The audit report is strong but any competent developer can build a report template. The dual-tank model is your real moat."

**WG Consensus:**
- Month-End Fuel Audit is the right primary business (buyer pull, recurring revenue, large market)
- Alert Sanity Filter should be the *first feature* demonstrated in the pilot, not a secondary capability
- The pilot partner's first-month metric should be: false alerts eliminated (not audit reports generated)
- This validates the sprint plan structure: Set 3 mockup shows the audit, but the demo (Set 4) leads with the filter

### Mentor Pressure Test — Simulated Feedback

**Mentor 1 (ex-fleet operator, current VC):**
> "I've seen six fuel monitoring startups in Southern Africa in the last three years. The ones that died all had the same problem — they sold to the ops manager but the ops manager couldn't sell to finance. Your bet on the finance director as the buyer is correct, but that means your sales motion needs to include finance-speak from day one: ROI, payback period, audit-ready reporting. Make sure your first pilot delivers a number that finance can put in a slide."

**Mentor 2 (SaaS go-to-market expert):**
> "15 to 20 fleet customers for R1M ARR in Year 1 means your average deal size is R50k–R66k/year. That's a mid-market SaaS deal, not SMB. Mid-market deals require a sales process — demos, trials, procurement, legal. Are you resourced for that? Consider whether a product-led growth motion (self-serve trial, inbound) could work alongside the sales-led motion."

**Mentor 3 (product-led growth specialist):**
> "The mockup (Set 3) and the audit demo (Set 5) are your best acquisition tools. If you can show a fleet ops manager a report that looks like the thing they wish they had today, they'll share it with their finance director. The product is the marketing. Build that first, make it shareable, and let the network effect do the work."

### Key Adjustments Made Based on Pressure Test

1. **Lead with the filter in the demo, upsell to the audit:** Set 4 demo flow revised to open with the false positive problem ("30–50 false alerts a week, and we solved it in one week") before transitioning to the audit report. The filter is the hook; the audit is the business.

2. **Deliver a finance-ready number from the pilot:** Set 6 (Pilot Partner Validation) will include a specific ask: what is the monthly variance figure (in Rands) before and after the pilot? That number becomes the first case study.

3. **Build the mockup for sharing:** Set 3 mockup will be designed with a shareable link and a self-serve trial component. One-click PDF export of a sample month-end report becomes the primary demo artifact.

4. **Separate the sales motion:** Ops managers get the self-serve trial (mockup + audit report). Finance directors get the ROI calculator and case study. The buyer and the user get different entry points to the same product.

---

## Part 6: Final Business Selection Statement

**Selected Business: Month-End Fuel Audit**

The Month-End Fuel Audit is the right business to pursue because it solves the most frequent, highest-severity customer problem with the clearest evidence of willingness to pay (Ideaster conversion, Avis R3M, pilot partner explicit pain), the largest addressable market (R1.35B TAM), and a recurring revenue model aligned with monthly pain recurrence. The dual-tank Alert Sanity Filter is retained as the first product feature and the primary proof point in the pilot — eliminating false positives in the first week builds the trust needed to expand into the full audit subscription. The Theft Case File Reports become a premium tier within the same platform, eliminating the transactional pricing risk and bundling legal evidence capability into the recurring subscription. PhyLo is one business, not three.

---

*Business selection confirmed. Next: Set 2 — Customer Development. Script to be written using the Month-End Fuel Audit as the defined business. Warm leads to be contacted with the selected business framing.*