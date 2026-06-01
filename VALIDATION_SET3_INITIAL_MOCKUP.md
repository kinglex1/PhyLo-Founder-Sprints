# Validation Sprint — Set 3: Initial Mockup
## PhyLo | Founder Institute South Africa 2026 | Launch Track

**Selected Business:** Month-End Fuel Audit
**The Mockup:** `VALIDATION_SET3_MOCKUP.html` — interactive prototype of the Month-End Fuel Audit workflow

---

## Part 1: Buyer Persona

*Note: This persona is drafted from Sprint 1 customer problems work (Sprint 1 Set 2) and the pilot partner conversation (Sprint 1 Set 3). It will be refined as the Set 2 customer development interviews are conducted and a sample size of 15 fleet operators provides more granular data.*

### Primary Buyer Persona

**Name:** Kgabo Moloto
**Role:** Fleet Operations Manager
**Location:** Gauteng/Rustenburg corridor, South Africa
**Fleet:** 60 commercial vehicles — mostly heavy-duty trucks (Isuzu FVZ, Mercedes Actros, Volvo FH) running cross-border routes to Zimbabwe, Botswana, and Mozambique
**Annual fuel spend:** R12–R18 million (R1M–R1.5M/month at current SA diesel prices)
**Reporting to:** Operations Director (in mid-size operators) or Owner (in smaller operators)
**Buys from:** CEO/Owner or Finance Director signs the cheque; Kgabo evaluates and advocates

**Demographics:**
- 38–50 years old
- Male (industry skew)
- 10–15 years in transport/logistics
- Started as a driver or dispatcher, worked up
- High school education, often a tertiary diploma in logistics or supply chain
- English-speaking (some Afrikaans, some Zulu in smaller operations)
- Tech-comfortable but not a power user — uses email, WhatsApp, and dashboards; doesn't write code

**Goals:**
- Produce a clean monthly fuel reconciliation for finance — the document that explains what happened to every litre
- Reduce the 5–8% monthly fuel variance that nobody can explain
- Identify real theft events and act on them — disciplinary process, insurance claim, or criminal charge
- Restore trust in the fuel monitoring system (the team has stopped trusting false-positive alerts)
- Stop the cycle of finance meetings where Kgabo has nothing to show for unexplained losses
- Get home on time — month-end reconciliation currently eats 2–3 evenings per month

**Challenges:**
- Existing telematics flags anomalies but provides no accountability document
- Manual reconciliation takes 8–12 hours per month at month-end
- False positive alerts (30–50/week from dual-tank vehicles) cause alert fatigue — the team has stopped looking
- Cross-border routes drop telematics offline at borders — gaps in the data
- The finance director/owner doesn't trust the variance number because Kgabo can't explain it
- Theft events are reported but no action is taken because there's no proof
- His job security depends on this number — every month that ends in "we don't know" weakens his position
- He's not sure if the issue is theft, inefficiency, or just unexplained mechanical/operational variance

**Buying Process:**
- **Trigger:** Last finance meeting where he had to say "we don't know where R60k went" — the look on the finance director's face
- **Evaluation criteria:** Will this produce a document I can hand to finance? Will it survive a CCMA hearing if I have to discipline a driver? Will it work on my cross-border routes?
- **Decision timeline:** 4–8 weeks from first conversation to purchase
- **Risk factors:** Integration with existing telematics is the biggest concern. He doesn't want to rip out the current system. He wants this to add to it.
- **Budget authority:** Can recommend, can't approve. Approval sits with the finance director or owner.
- **What closes the deal:** A finance-ready number in Rands (R78,000 saved per month, etc.), a shareable PDF report, and evidence that the system will work on his routes (cross-border, dual-tank, hilly terrain)
- **What kills the deal:** Too long a pilot, no demonstrated ROI, vague claims about "AI accuracy" without numbers, integration requirements that are too complex

**Quote (representative of how he talks):**
> "I don't need another dashboard. I need a document. I need to be able to show finance — here's what we bought, here's what we used, here's what we lost, and here's why. If I can give them that, the rest of my job gets easier."

---

### Secondary Persona: The Finance Director (Co-buyer)

**Name:** Lerato Ndlovu
**Role:** Finance Director (CFO in mid-size, Head of Finance in smaller operators)
**Reports to:** CEO/Owner
**Tenure:** Often newer to the business than the operations team

**Goals:**
- Get clean monthly numbers for board reporting
- Reduce variance that doesn't have a justification
- Catch fraud before it becomes a CCMA or criminal case
- Build a culture of accountability

**Buying trigger:**
- Failed audit, tax dispute, or insurance claim
- Personal liability concern (she's signing off on numbers she can't fully explain)
- Director/owner pressure to "tighten up the numbers"

**Decision process:**
- Wants ROI calculator with payback period
- Will not sign a SaaS contract without a trial period
- Asks the ops manager to evaluate first; relies on ops manager's assessment

**Quote:**
> "If you can show me a number that's defensible in a board meeting, and a report I can attach to a file, I can justify the spend. Don't give me dashboards — give me documents."

---

## Part 2: The Single Most Valuable Workflow

**The Month-End Fuel Audit workflow.**

Every month, on the last business day, Kgabo opens PhyLo, selects the month, and gets a complete picture of fleet fuel performance. The system shows him which vehicles are clean, which have anomalies, and exactly what happened on each anomaly. He clicks on a flag, sees the full audit report, and either accepts it or notes an alternative explanation. He clicks "Export for Finance" and gets a one-click PDF. He emails it to Lerato. The reconciliation that used to take 8–12 hours takes 10 minutes.

**Why this workflow:**
1. **It's the sharpest pain** (Sprint 1 Set 2, only Ideaster conversion, pilot partner explicit pain)
2. **It's the strongest buyer signal** (Lerato needs it, not just Kgabo)
3. **It demonstrates PhyLo's full value chain** (dual-tank false positive elimination, cross-border edge cases, anomaly classification, audit-grade reporting)
4. **It's the wedge for recurring revenue** (monthly subscription, monthly pain)
5. **It produces a shareable artifact** (PDF) that becomes the primary demo and acquisition tool

**What's NOT in the mockup (deliberately):**
- Real-time alerts (downstream feature, not the wedge)
- Driver exoneration console (downstream feature)
- Cross-border live tracking (downstream feature)
- Mobile driver app (downstream feature)
- Insurance claim submission (downstream feature)

The mockup does one thing, end-to-end. Everything else is built on top of the trust this workflow creates.

---

## Part 3: The Mockup

**File:** `VALIDATION_SET3_MOCKUP.html`
**Type:** Interactive HTML prototype (single file, no backend)
**Data:** Synthetic — based on the pilot partner's fleet profile (Rustenburg → Harare route) with sample month data

### What the Mockup Demonstrates

**Screen 1 — Vehicle List (Month-End Dashboard)**
- Month selector (e.g., "May 2026")
- Vehicle list with: registration, route, expected consumption, actual consumption, variance (litres + Rands), anomaly status (green/yellow/red)
- Total variance at the top (R78,400 this month, vs. R60,000 average)
- "Export for Finance" button in the top right
- Sample data: 60 vehicles, 3 with anomalies, 1 with confirmed theft (the pilot partner Rustenburg → Harare incident)

**Screen 2 — Anomaly Detail (Clicking on Red Flag)**
- Vehicle header: ZAN 123 GP, route, driver
- Timeline of the event: 02:31 stationary → 04:43 fuel drop → 05:12 stable
- GPS coordinates and zone classification
- Confidence score (97.3%)
- Alternative hypotheses eliminated (5 of 5)
- Narrative summary in plain English
- Cost in Rands (R 778)
- "Export this report" button

**Screen 3 — Finance Export (PDF-style view)**
- Company header
- Executive summary
- Vehicle-by-vehicle table
- Total variance and loss value
- Audit trail
- "Download as PDF" button (simulated)

### How to Use the Mockup

1. Open `VALIDATION_SET3_MOCKUP.html` in any browser
2. Click on the red-flagged vehicle (ZAN 123 GP) to see the audit report
3. Click "Back to fleet" to return to the dashboard
4. Click "Export for Finance" to see the PDF view
5. Click "Download as PDF" (simulated — generates a print preview)

### Mockup Limitations (Honest)

- This is a prototype with synthetic data — it does not connect to a real database
- The "Download as PDF" button is a print preview, not a real PDF generation
- The confidence scores are pre-computed (based on the Sprint 1 Set 7 audit report work)
- The alternative hypothesis elimination is illustrative, not interactive
- The vehicle data, fuel loss event, and confidence calculations are all based on the synthetic Plumtree border theft scenario from Sprint 1 Set 7

### What This Mockup Is For

**Primary:** Demo to Working Group and at the Weekly Strategy Presentation (Set 4)
**Secondary:** Shareable artifact for finance directors and fleet operators to evaluate the output
**Tertiary:** Foundation for the audit report demo in Set 5

### What This Mockup Is NOT For

- Live customer use (requires backend, real data integration, calibration)
- Pilot deployment (requires the full PhyLo engine with sensor integration)
- Real-time monitoring (out of scope — the wedge is month-end, not real-time)

---

## Part 4: Building the Mockup — Process Notes

**AI Builder Tool:** Lovable (recommended in Set 3 guidelines) — used for rapid HTML prototype generation. The mockup was generated from a structured prompt and iterated based on the user persona and workflow requirements.

**Prompt given to AI builder:**

> "Build a single-page HTML prototype for a fleet fuel monitoring platform called PhyLo. The buyer is a Fleet Operations Manager named Kgabo who manages 60 vehicles, mostly cross-border to Zimbabwe. The product is a Month-End Fuel Audit tool that produces a vehicle-by-vehicle reconciliation report. Show a month-end dashboard with vehicle list, expected vs actual consumption, variance in Rands, and anomaly flags. One vehicle should have a red flag — clicking it shows a full audit report with timestamp, GPS, confidence score, alternative hypotheses eliminated, narrative summary, and cost. The whole thing should look like a real B2B SaaS product — clean, professional, finance-ready. Include an 'Export for Finance' button that shows a PDF-style view."

**Iterations made:**
- **Round 1:** Initial design — too generic, looked like a generic dashboard. Asked for fleet-specific visual design.
- **Round 2:** Added route badges, vehicle registration plates (SA style), fuel level visualizations, and the Rands-cost emphasis. Looked better but the anomaly detail needed more credibility.
- **Round 3:** Added the alternative hypothesis elimination section, the 97.3% confidence score with breakdown, and the chain of custody hash. This is what the audit report needs to look like for finance to trust it.

**Decisions made during iteration:**
- Used the Plumtree border theft scenario from Sprint 1 Set 7 as the sample anomaly — it's the most representative incident for the pilot partner's actual route
- Added a "dual-tank false positive" example as a yellow-flag vehicle — this is the feature that builds trust in the system
- Used a South African Rand (R) currency symbol throughout, not generic dollar signs
- Kept the color palette restrained — dark navy/charcoal for ops manager dashboard, green/yellow/red for status, with no playful gradients
- The "Export for Finance" PDF view is designed to look like something Lerato would forward to the board

**What was deliberately NOT specified upfront:**
- Real-time alerts (out of scope)
- Driver app (out of scope)
- Mobile responsive (the buyer is at a desk)
- Multi-tenant (single fleet view only)

The mockup demonstrates the wedge. Everything else is downstream.

---

## Part 5: Access and Sharing

**Mockup location:** `VALIDATION_SET3_MOCKUP.html` in the same directory as this file
**Accessibility:** Single HTML file, no external dependencies, opens in any browser
**Sharing:** Can be:
1. Hosted on a static site (Netlify drop, Vercel, GitHub Pages)
2. Attached to email as a downloadable file
3. Linked from a landing page
4. Presented live in a screen-share demo

**Next steps for production:**
1. Replace synthetic data with real PhyLo engine output
2. Add authentication, multi-tenant support, and database integration
3. Generate real PDF reports (using a library like jsPDF or Puppeteer)
4. Add data export to Excel/CSV for finance teams
5. Build a real-time anomaly detection layer behind the month-end summary

---

*Mockup complete. The artifact in `VALIDATION_SET3_MOCKUP.html` is the working prototype. Set 4 (Mockup Demo) builds the 3-minute presentation script around this mockup, and Set 5 (Audit Report Demo) uses the anomaly detail screen as the one-page audit report format.*