# FI Set 5 — Supply Chain Risk Mapping

## Part 1: AI-Mapped Risk Zones — Pilot Partner Corridor

The pilot partner's primary route is **Rustenburg → Harare (Zimbabwe)**. This is a cross-border corridor that passes through the North West Province, crosses into Botswana (transit to Zimbabwe), and terminates in Harare. Below is the risk mapping specific to this route.

**Zone 1 — Rustenburg N4 Corridor (Origin: Rustenburg to Skilpadshek / Botswana Border)**

The route originates in Rustenburg, the heart of South Africa's platinum mining belt, on the N4 Platinum Highway. The N4 between Rustenburg and the Botswana border (Skilpadshek) is a high-risk zone for depot-based overnight siphoning. Fleets operating in Rustenburg run through a concentration of heavy commercial vehicles, contractor fleets, and mining support vehicles — creating a crowded operating environment where unauthorized stops are common. The area has documented fuel theft hotspots at industrial zones, unsecured yards, and along the R104 alternative route that bypasses N4 toll gates. A single commercial truck losing 50 litres/week in this zone = R65,000/year at current diesel prices. The North West Province has identified fuel theft as a growing operational risk across fleet operators serving the mining sector.

**Zone 2 — Botswana Transit Corridor (Skilpadshek to Plumtree Border)**

Many Rustenburg-to-Harare routes transit through Botswana rather than taking the direct Beitbridge route through South Africa and Zimbabwe. While Botswana transit bypasses some SA-border risks, it introduces a different set of vulnerabilities: fuel stop opportunities at truck depots and unmanned fuel facilities along the transit corridor, driver collusion risk (a truck refueling in Botswana with South African fuel cards), and reduced telematics visibility when crossing between South African and regional GSM networks. The 900km-plus route across Botswana has limited cellular coverage in sections. Fuel theft along this corridor is typically lower in frequency but involves larger volumes per event. Criminal networks are known to operate along this transit route, with vehicles occasionally detoured to off-route depots for siphoning.

**Zone 3 — Plumtree / Beitbridge Border Crossing (Zimbabwe Entry)**

Both entry points into Zimbabwe — Plumtree (via Botswana) and Beitbridge (direct from SA) — represent the highest-severity risk points on this corridor. Trucks routinely wait 24–72 hours at Beitbridge. During this waiting period, vehicles are parked in large open areas with limited security, making them vulnerable to organized siphoning. Operators on SA-Zimbabwe routes report single-event losses of up to 600 litres at border crossings. Zimbabwe is a preferred destination for smuggled fuel due to high local prices and currency constraints — creating organized demand for stolen diesel. Inside Zimbabwe, fleet vehicles are at further risk of fuel being siphoned at destination depots or while awaiting customs clearance in Harare.

**Supporting Data:**
- SA commercial fleet sector loses R1.5 billion annually to fuel theft (DigitFMS, 2026)
- Beitbridge is one of Africa's most congested border posts — documented 2–3 day wait times
- Mozambique customs now escorts tankers in armed convoys from Port of Maputo to border due to organized siphoning en route — same dynamic applies at Beitbridge
- SA-to-Zimbabwe fuel smuggling is well-documented; Zimbabwe Revenue Authority seized vehicles and fuel at Beitbridge repeatedly between 2017–2020
- Botswana transit routes have documented fuel card fraud patterns — drivers siphon at depots along the corridor

---

## Part 2: Logistics Manager Pain Points (Pilot Partner Interviews)

*The following captures operational pain points from the pilot partner and logistics managers operating on the Rustenburg-to-Harare and similar cross-border routes.*

**Manager Interview Synthesis:**

The core pain is not detection — it's proof. One fleet manager operating on cross-border routes described it as: "We get the alert. Fuel dropped while the truck was parked at the border. That's all we know. We can't report it, we can't act on it, and we definitely can't use it in a disciplinary hearing. The driver says nothing happened. We're left guessing." This manager noted that on the Rustenburg-to-Harare run specifically, the extended journey time (800km+) means fuel consumption baselines are harder to model without physics-grounded validation — and that existing systems routinely flag "anomalies" that turn out to be nothing.

A second manager highlighted the dual-tank issue on the N4: "Our trucks run dual tanks through Rustenburg and up the N4. When they park on any kind of incline — and there are plenty on that route — the fuel shifts between tanks and sets off every theft alert we have. We get 30–50 false alerts a week just from that. After a while, the team stops looking at the alerts entirely. That's when real theft slips through."

Both managers cited the month-end reconciliation workflow as the sharpest pain: "Finance wants a number. The number keeps being 5–8% higher than it should be. We report 'theft and variance' and that's where the conversation ends. Nobody can explain it. We need a document we can hand to someone and say 'this is what happened.'"

---

## Part 3: Risk Zone Prioritization for PhyLo's Detection Engine

Cross-referencing the AI-mapped zones with the pilot partner's specific corridor (Rustenburg → Harare) and manager pain points, the following is prioritized for PhyLo's detection engine:

**Priority 1 — Dual-Tank Grade Attribution (Engine Foundation Model)**
The manager pain is immediate and acute: 30–50 false alerts per week from dual-tank fuel shift on parked inclines along the N4. This is the highest-frequency false positive source on the pilot partner's route and the fastest path to demonstrating PhyLo's advantage over rule-based systems. Build the dual-tank, parked-on-grade physics model first. If PhyLo eliminates these false alerts while maintaining theft detection, the ops team will adopt it within the first week of the pilot. This is also the clearest illustration of what "physics-informed" means in practice.

**Priority 2 — Cross-Border Stationary Attribution (Zone 3)**
Rustenburg-to-Harare involves extended stationary periods at the border (Plumtree or Beitbridge). Single events here cause up to 600 litres of loss — R17,000+ per incident. PhyLo's engine should be calibrated to: (a) flag fuel drops during extended stationary periods with high confidence, (b) attribute drops that occur outside geofenced safe zones, and (c) account for thermal tank contraction during overnight stops in varying temperatures. The Botswana transit leg should be treated as a medium-confidence zone where engine state data (CAN bus, odometer) substitutes for GPS when cellular coverage drops.

**Priority 3 — Route-Level Consumption Validation (Full Corridor)**
The 800km+ Rustenburg-to-Harare run requires physics-based fuel burn modeling against GPS-verified route distance, load profile, and terrain. Existing systems treat this as threshold alerts — if consumption exceeds X litres per 100km, flag it. PhyLo replaces the threshold with a model: expected consumption = f(grade profile, distance, load, temperature). Deviations from model are classified, not just flagged. The monthly audit report — the winning product from Ideaster testing — is the output of this model. Finance directors on this route are the primary buyer.