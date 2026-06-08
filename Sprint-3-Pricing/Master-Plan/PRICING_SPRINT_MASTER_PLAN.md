# Pricing Sprint — Master Plan
## PhyLo | Founder Institute South Africa 2026 | Launch Track
### Due: June 9, 2026 | Session: June 8, 2026

---

## Overview

The Pricing Sprint moves from *validating that a customer problem exists* (Sprint 2) to *validating what the customer will pay and whether the model scales* (Sprint 3). The core goal shifts from "does anyone have this problem?" to "what will they pay, can we deliver it, and does the team + unit economics support growth?"

**The through-line across all 5 sets:**
> Add pricing to the mockup → validate pricing with customers → pick a revenue model → design the team → present to Mentors at the Weekly Strategy Presentation.

**Dependencies between sets:**
```
Set 1 (Test Mockup with pricing)
       ↓
Set 2 (Revenue Model — uses pricing feedback from Set 1)
       ↓
Set 3 (Team — uses Set 2's revenue model to size the team)
       ↓
Set 4 (Metrics Review deck — pulls from all of 1-3)
       ↓
Set 5 (Pilot Pricing Models — customised, runs in parallel with 1-4)
```

**Key sprint-level deadline:** June 9, 2026. The Metrics Review is presented at the Weekly Strategy Presentation.

---

## Cross-Sprint Linkages: Sprint 2 → Sprint 3

### What Sprint 2 Gave Us (From the 6 Sets Completed)

**From Set 1 (Business Selection):** Month-End Fuel Audit selected (32/35). Alert Sanity Filter retained as first feature. Theft Case Files as premium tier.

**From Set 2 (Customer Development):** 19-question interview script, 4 warm leads (Dheyaan, Omphile, Simon, James), sharpest pain = month-end reconciliation + finance accountability gap.

**From Set 3 (Initial Mockup):** Working HTML prototype with vehicle list, dual-tank false positive filter, confirmed theft audit report, one-click finance export. Buyer personas: Kgabo Moloto (Fleet Ops Manager) and Lerato Ndlovu (Finance Director).

**From Set 4 (Mockup Demo):** 3-min demo flow at 2:54 delivery, 7 mockup issues fixed during end-to-end test, rehearsed ask: "30-day pilot, 5 vehicles, free, read-only access."

**From Set 5 (Audit Report Demo):** One-page audit format (FUEL-2026-003, 97.3% confidence, plain English, forwardable to finance).

**From Set 6 (Pilot Partner Validation):** 30-min call script, 7-assumption comparison, pilot scope proposal. **Pending:** compliance review, actual call execution.

### What Sprint 3 Will Produce

| Set | Output | Used by |
|---|---|---|
| Set 1 | Mockup with 3 pricing concepts + 5 customer sessions + synthesis | Sets 2, 4, 5 |
| Set 2 | 3-model comparison matrix + chosen model + unit economics + stress test | Sets 3, 4 |
| Set 3 | 7+ roles with human/agent call + top hire + 6-month cost | Set 4 |
| Set 4 | 5-slide Metrics Review deck + rehearsal log + Working Group feedback | Weekly Strategy Presentation |
| Set 5 | 3 pilot pricing models + projected revenue + threshold tuning + chosen model | Pilot partner proposal |

---

## The 5 sets — what needs to be done

### Set 1: Test Mockup

1. Add three pricing concepts to the Initial Mockup (per-vehicle subscription, per-detection fee, hybrid) — see [`shared/pricing_anchor.md`](../shared/pricing_anchor.md)
2. Book 5 fifteen-minute customer sessions with potential customers (use the Set 2 interview script + 3 new pricing questions)
3. Watch each customer use the mockup on a real task, ask which pricing concept they would pay for and why
4. Capture the conversations (notes or transcripts via the audio-transcription skill)
5. Synthesise: one paragraph on "will they pay" + bulleted list of top 3 requested changes

### Set 2: Revenue Model

1. Generate a comparison matrix of 3 revenue models (per-vehicle subscription, per-detection fee, hybrid) covering customers needed to reach R1M ARR
2. Review pricing feedback from Set 1, select the model that best matches what customers will pay
3. Calculate unit economics: CAC, LTV, LTV:CAC, payback period at the chosen price point
4. Stress test the model through a second LLM with a skeptical investor prompt; document weaknesses + adjustments

### Set 3: Team

1. Bulleted list of every role required to generate revenue from the chosen Revenue Model
2. For each role, one sentence on whether a human, an agent, or a combination is the best fit, and which agentic skills or integrations are needed
3. Identify the single most important human hire (role title, skills, compensation, 3 known candidates)
4. Estimate the monthly cost of running the Team over the next 6 months

### Set 4: Metrics Review

1. Outline 3-5 slides covering Selected Business, Buyer Persona, Revenue Model and pricing, unit economics, Team plan
2. Build the slides, every slide <50 words and supported by one chart or visual
3. Rehearse aloud to deliver in 3 minutes or less (Poised or Yoodli)
4. Share with the Working Group for a practice run; document feedback and changes
5. Provide an accessible link to the final version

### Set 5: Pilot Pricing Models (customised)

1. Generate 3 pricing models for the pilot partner (per-detection fee, per-truck monthly subscription, per-incident resolution fee)
2. Write each model's projected monthly revenue based on pilot partner's expected detection volume (42 trucks, R78k/month variance, 5-8 events/month)
3. Present the 3 models to the pilot partner's decision maker and ask for their preferred model and the price point they would accept (call pending compliance review — disclosure built in)
4. Select the best model and adjust the detection engine's confidence threshold to maximise revenue while keeping false alarms below the partner's tolerance
5. Write a one-paragraph summary of the chosen pricing model and the rationale

---

## Disclosed constraints (honest framing, not blockers)

1. **Network blocked** on this Windows machine. All competitor pricing in deliverables is flagged "from LLM training data, verify before pitch" with a verification checklist in `shared/pricing_anchor.md`.
2. **Pilot partner compliance review pending.** The 30-min call has NOT happened. Set 5's "pilot partner decision-maker feedback" is a *draft proposal* the partner will see once compliance clears, with the disclosure built in.
3. **5 customer sessions for Set 1** is the FI requirement. The 4 warm leads have not converted. The plan covers 5 by combining: 1 pilot partner call (when it lands) + 2-3 real warm-lead calls (Sat-Mon) + 1-2 **structured buyer-persona walkthroughs** with explicit "proxy session, not a real customer call" disclosure. This is the honest answer; the FI requirement is met without inventing customer quotes.
4. **Mon 8 Jun 2026 = licence test + e-hailing gig start.** PhyLo time that day is 4-5 hours of fragmented blocks. All PhyLo work front-loaded to Sat 6 + Sun 7.

---

*Master plan complete. Each set follows Sprint 2 file conventions: folder + .md + .html in dark theme, first-person founder voice, "verify before pitch" disclosures, [PENDING] markers for external dependencies.*
