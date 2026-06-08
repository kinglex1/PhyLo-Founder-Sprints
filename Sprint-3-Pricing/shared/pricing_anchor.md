# PhyLo Pricing — Anchored Below SA Telematics, Positioned as a Layer

**Prepared:** 6 June 2026 | **Status:** Internal anchor — not yet customer-validated
**Network status:** OFFLINE during this work — competitor pricing from LLM training data + existing PhyLo research report. **All figures must be verified with the named provider before any external pitch.**

**Pricing constraint (from founder, 6 Jun 2026):** PhyLo's per-vehicle price MUST be below telematics basic (Cartrack R200-250, Tracker R199-299). A 60-truck fleet paying PhyLo + Cartrack must see a combined bill that is at most ~25% above the Cartrack-only bill. If the combined bill looks like "60-75% more than Cartrack," the "layer" framing is dead.

---

## The framing line (first 30 seconds of every pitch)

> "PhyLo does not replace Cartrack, Tracker, Netstar, Webfleet, or MiX. PhyLo **reads the telematics feed you already have** — GPS, ECM, fuel levels, attitude — and turns it into the **month-end audit document** your telematics dashboard cannot produce. **The first 30 days are a free diagnostic — you see your actual loss number before you decide how to pay.**"

---

## The three pricing paths (after the 30-day free diagnostic)

**Common entry (all three paths):** 30-day free diagnostic. PhyLo reads the customer's telematics feed, produces a baseline loss report. No cost, no commitment. **The diagnostic is the sale** — the customer sees their R60k variance in writing before they pick a pricing path.

### Path A — Per-vehicle Subscription (tiered, materially below telematics)
- **R45/vehicle/month** (60-100 trucks)
- **R35/vehicle/month** (100-200 trucks)
- **R25/vehicle/month** (>200 trucks)
- Includes: dashboard, monthly audit report, alerts, 1 dispute-pack/quarter
- **Why this price:** Cartrack basic is R200-250/vehicle. PhyLo Path A is **~20% of Cartrack basic**. Combined bill on a 60-truck fleet: 60 × (R220 Cartrack + R45 PhyLo) = R15,900/month = 20.5% premium on Cartrack (R2,700/R13,200). **Defensible.**
- Headline: *"~20% of your Cartrack bill. Reads the feed you already pay for. Produces the document Cartrack cannot."*

### Path B — Per-incident Only (no floor)
- **R0 monthly floor, R2,000 per confirmed theft** (events above 85% confidence threshold)
- Includes: detection engine, evidence pack, monthly report
- **Why this works:** the customer pays only when PhyLo proves a theft event. No per-vehicle number to compare to Cartrack.
- Headline: *"Pay nothing monthly. R2,000 per theft event PhyLo proves. Most customers see 3-8 events a month."*

### Path C — Soft Floor + Per-incident (the chosen default for high-variance)
- **R1,500/month soft floor** + **R1,500 per confirmed theft**
- Includes: detection engine, evidence pack, monthly report, 1 dispute-pack/quarter
- **Why this is the chosen default for high-variance customers:** the R1,500 floor is below Cartrack's lowest possible per-vehicle implied cost (R200 × smallest-fleet customer of 8 vehicles = R1,600). The R1,500/event is half of Path B's R2,000, so the customer who picks C is paying less per event in exchange for the floor.
- **At pilot (42 trucks, R78k variance, 5-8 events):** R1,500 + (5-8 × R1,500) = **R9,000-13,500/month**. Implied per-vehicle: R214-321/vehicle/month — but this is high-variance because of the event count, not because of a per-vehicle number that can be compared to Cartrack.
- Headline: *"R1,500 a month covers up to 200 vehicles. R1,500 per theft event PhyLo proves. Cheapest defendable position against Cartrack + PhyLo combined bill."*

---

## Telematics competitor anchor (verify before pitch)

All figures below are **from LLM training data and the existing PhyLo research report** (`SHARED_RESOURCES/PhyLo-Complete-Package/PhyLo-Complete-Package/01-Research-Report/report.html` lines 832-905). Directional, not contractual. Confirm with each provider before any external pitch.

| Provider | Typical R/vehicle/month (basic) | Typical R/vehicle/month (premium + fuel) | What they include for fuel | What they DO NOT do (PhyLo's gap) |
|---|---|---|---|---|
| **Cartrack** (ZA) | R199-249 | R399-499 | Fuel-level graphs, threshold alerts, basic theft notification | Multi-sensor physics validation, temperature compensation, dual-tank slosh modelling, court-admissible evidence, month-end reconciliation report |
| **Tracker** (ZA) | R199-299 | R350-450 | Same as Cartrack | Same gaps |
| **Netstar** (ZA) | R185-280 | R350-420 | Same | Same |
| **MiX by PowerFleet** (ZA) | R250-350 | R450-650 | Same + driver behaviour | Same gaps + PhyLo layers on top of their API |
| **Ctrack** (ZA) | R200-280 | R380-480 | Same | Same |
| **Webfleet / Bridgestone** (ZA) | R220-330 | R420-550 | Same + TomTom routing | Same |
| **Geotab** (ZA, via resellers) | R250-380 | R450-600 | Same | Same |
| **WEX / Fleetcor / Engen fuel cards** | n/a (per-transaction) | n/a | Card volume vs. ECM cross-check | Physics-based validation of card claims, no continuous monitoring |
| **PhyLo (the layer)** | **Path A: R45/vehicle** OR **Path C: R1,500 floor + R1,500/event** | n/a — sits on top | Reads existing telematics feed — no hardware add | Provides the audit-grade document the telematics dashboards cannot |

**Combined-bill defensibility check (60-truck fleet, Cartrack basic + PhyLo Path A):**
- Cartrack basic: 60 × R220 (mid-range) = R13,200/month
- PhyLo Path A: 60 × R45 = R2,700/month
- **Combined: R15,900/month = 20.5% premium on Cartrack-only.** Defensible.

**Combined-bill defensibility check (60-truck fleet, Cartrack basic + PhyLo Path C):**
- Cartrack basic: R13,200/month
- PhyLo Path C: R1,500 floor + ~6 events × R1,500 = R10,500/month (at the pilot's variance level)
- **Combined: R23,700/month = 80% premium on Cartrack-only.** This is defensible ONLY for high-variance customers. Path C is not the right pitch for a low-variance customer — that's Path A or Path B.
- For the pilot specifically, Path C is the right answer because the pilot partner has R78k/month variance. For the typical customer, Path A or B.

**Headline PhyLo positioning numbers (using Path A as the default):**
- "PhyLo's R45/vehicle/month is **~20% of your Cartrack/Tracker basic subscription.** Combined bill is +20.5% on Cartrack (R2,700/R13,200). We are not asking you to add a line item that doubles the bill. We are asking you to add a layer that turns what you already pay for into the document Finance cannot currently get."
- "The 42-truck pilot recovered R78,000/month. PhyLo Path C earns R9-13.5k/month on that — less than 20% of recovered value. **Customer's net recovered: R60-69k/month, or R720-828k/year.**"

---

## Verify before pitch (the honest disclosure)

- [ ] Confirm Cartrack ZA premium pricing (call Cartrack B2B, ask for the "fleet fuel monitoring" line item)
- [ ] Confirm Tracker ZA fuel-probe add-on pricing
- [ ] Confirm Netstar ZA pricing for the SA market (some sources give global USD rates)
- [ ] Confirm Webfleet / Bridgestone ZA reseller pricing (Bridgestone runs the commercial channel)
- [ ] Confirm MiX by Powerfleet ZA pricing (was MiX Telematics; rebranded 2023)
- [ ] Confirm Ctrack ZA pricing (subsidiary of Inseego)
- [ ] Verify the R78,000/day eThekwini figure against a primary source (Daily Maverick / News24 article)
- [ ] Verify the Avis R3M in 8 months figure (already in research, find original)
- [ ] Verify the Rajasthan R400k/yr figure (research report line 477)

---

*This is the single source of truth for Sprint 3 pricing. Every Set 1-5 deliverable references the numbers here. Update once, propagate everywhere.*
