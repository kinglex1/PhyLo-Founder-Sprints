# Validation Sprint 3 — Set 5: Pilot Pricing Models
## PhyLo | Founder Institute South Africa 2026 | Launch Track

**Customised activity:** Test three pricing models with the pilot partner using real detection data. The pilot partner is a 42-truck Rustenburg-Harare fleet with R78,000/month variance and 5-8 confirmed events per month (per the pilot dataset).

---

## Part 1: Three Pricing Models for the Pilot Partner

| Model | Pricing | Projected monthly revenue (pilot, 42 trucks) | Customer perspective |
|---|---|---|---|
| **Per-incident only (Path B)** | R0 floor, R2,000 per confirmed event | 5-8 events × R2,000 = **R10,000-16,000/month** | "Pay nothing monthly. R2,000 per theft event PhyLo proves." |
| **Per-truck monthly subscription (Path A tiered)** | R45/vehicle/month (pilot gets the smallest-tier rate as a pilot concession, even though 42 trucks is below the 60-100 minimum) | 42 × R45 = **R1,890/month** | "Predictable, like Cartrack but smaller. But flat regardless of how much theft we find — underprices PhyLo's value at pilot variance." |
| **Soft floor + per-incident (Path C — CHOSEN)** | R1,500/month soft floor + R1,500 per confirmed theft | R1,500 + (5-8 × R1,500) = **R9,000-13,500/month** | "R1,500 a month covers up to 200 vehicles. R1,500 per proven event. Cheapest defensible position vs. Cartrack+PhyLo combined bill." |

**Source for the 5-8 event range:** the pilot dataset (R78k/month variance, typical SA theft event ~R10-15k per event from the research report) gives 5-8 confirmed events per month.

### Combined-bill check on the pilot (42 trucks)

- Pilot partner's existing Cartrack bill: 42 × R220 (mid-range) = **R9,240/month**
- PhyLo Path A at this fleet: 42 × R45 = **R1,890/month** (combined R11,130 = 20% premium)
- PhyLo Path C at this fleet: R1,500 + ~6 events × R1,500 = **R10,500/month** (combined R19,740 = 114% premium on Cartrack — only defensible because the pilot's R78k variance is the proof)
- **Path C is the right answer for the pilot specifically** because the pilot partner has the R78k variance that justifies the high per-event number. The pilot is the highest-variance customer PhyLo will ever have; lower-variance customers get Path A.

---

## Part 2: Pilot Partner Feedback

> **[PENDING]** — The 30-min call from Sprint 2 Set 6 is scheduled once the pilot partner's compliance review completes. Two scenarios:
>
> - **Scenario A — compliance clears Mon 8 Jun:** the call happens, the Set 6 script is used, the pricing feedback is captured verbatim below.
> - **Scenario B — compliance still pending:** the file is a *placeholder draft* with a structured "feedback to be captured" template, and the deliverable is **explicitly disclosed** as a draft to be validated once the call happens.
>
> **The disclosure is mandatory.** The deliverable cannot claim feedback that was not received.

### Feedback capture template (to be filled after the call)

**Decision maker:** [name, role, fleet size — to be filled]
**Preferred model (Path A / Path B / Path C / "what about X"):** [to be filled]
**Price point they would accept:** [exact number — to be filled]
**Objection (verbatim if possible):** [to be filled]
**Top concern about PhyLo's value prop:** [to be filled]
**Top concern about the pilot scope:** [to be filled]
**Next step they want from us:** [to be filled]

---

## Part 3: Detection Engine Confidence Threshold Tuning

For the per-incident model (chosen: Path C):

- **Current threshold (production):** 85% confidence (per `physics/pinn.py` and the PhyLo research report)
- **Tuned threshold for pilot:** **lower to 80%** to catch more events, since the per-incident model values volume (Path C earns R1,500 per event, capped at pilot's actual event count)
- **Trade-off:** the lower threshold will surface more candidates, of which a higher fraction will be false positives. The pilot partner's tolerance for false alarms is the constraint.
- **False-alarm tolerance:** [to be captured from the pilot partner call]. Default assumption: **< 5 false alarms per week, per vehicle** (the buyer persona says 30-50/week is the current state with Cartrack; PhyLo's value prop is to cut this to <5)
- **Expected monthly revenue at tuned threshold:** **R12,500-13,500** (7-8 confirmed events, within the disclosed 5-8 range; the tuned threshold surfaces events at the upper edge of the base range)

**Honest disclosure:** the threshold tuning number (R12,500-13,500) is a **forecast** based on the pilot dataset and the research report's 5-8 events/month range, with the tuned threshold expected to surface events at the upper edge (7-8 events). The actual revenue will depend on:
- The partner's actual false-alarm tolerance (set in the SOW)
- The real pilot data (compliance-blocked, pending)
- The PhyLo engine's performance on Cartrack's actual feed (vs. the research report's synthetic dataset)

---

## Part 4: The Chosen Model + Rationale

**Chosen: Path C — soft floor + per-incident (R1,500/month + R1,500 per confirmed theft, no cap).**

The pilot partner has R78k/month variance and 5-8 confirmed events per month — that is the **highest-variance customer PhyLo will ever have**. Path A (per-vehicle subscription) would underprice PhyLo at this variance: R1,890/month (pilot concession R45 rate × 42 trucks) on a customer who is losing R78k/month is a 2.4% take-rate, still low to fund PhyLo's fixed costs in steady state but defensible as the predictable-flat option. Path B (per-incident only, no floor) has the right alignment but no cashflow floor to fund PhyLo's fixed costs in the pilot's first 30 days (which are the diagnostic). **Path C is the chosen default for the pilot specifically:** the R1,500 floor covers PhyLo's fixed costs for the diagnostic period, the R1,500/event is half of Path B's R2,000 so the partner pays less per event in exchange for the floor, and the resulting R9-13.5k/month take is ~12-17% of recovered value — defensible as a "fair share." For the typical (lower-variance) customer, Path A is the right pitch. **The pilot is the case study that proves Path C works for high-variance customers; Path A is the default for everyone else.**

**Expected first-month revenue:** R9,000-13,500/month (assuming 5-8 confirmed events per the pilot dataset).

---

## Part 5: Post-Call Action Items (to be done within 24 hours of the actual call)

- [ ] Stop the recording and save the file
- [ ] Transcribe the call
- [ ] Fill in the verbatim pricing feedback (Part 2 template)
- [ ] Update the detection threshold based on partner's false-alarm tolerance (Part 3)
- [ ] Send thank-you email with the per-incident proposal
- [ ] Update the master pricing anchor (`shared/pricing_anchor.md`) with the partner's real input
- [ ] File a v2 of this deliverable with the captured feedback

---

*Set 5 deliverable substantively complete. Three pilot pricing models projected; the per-incident model (Path C) chosen with R9,000-13,500 expected monthly revenue. Awaiting pilot partner compliance review for the actual feedback capture (Set 6 call from Sprint 2).*
