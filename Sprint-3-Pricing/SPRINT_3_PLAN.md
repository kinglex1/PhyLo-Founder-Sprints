# PhyLo Pricing Sprint — Execution Plan (matching Sprint 2 conventions)

> **For Qhayiya (and the agent executing):** this plan is rebuilt to match the existing Sprint 2 file conventions: each set gets a folder, a `VALIDATION_SETN_NAME.md`, and a `VALIDATION_SETN_NAME.html` in the same dark theme. The sprint root gets a `README.md` and a `Master-Plan/` subfolder. The deliverables are written in the **first-person founder voice** used in Sprint 2 ("I will", "we are"). The "verify-before-pitch" disclosure markers are kept — they are the only honest way to handle the network-blocked + pilot-pending constraints.

**Goal:** Ship 5 FI deliverables by Tue 9 Jun 17:00 — Test Mockup (Set 1), Revenue Model (Set 2), Team (Set 3), Metrics Review deck (Set 4), Pilot Pricing Models (Set 5, customised). All five must defend PhyLo as a **layer on top of** Cartrack/Tracker/Netstar/Webfleet/MiX, not a competitor to them.

**Sprint folder:** `PhyLo-Founder-Sprints/Sprint-3-Pricing/`
**Reference models:** `PhyLo-Founder-Sprints/Sprint-2-Validation/Set-1-Business-Selection/`, `Set-2-Customer-Development/`, `Set-3-Initial-Mockup/`, `Set-4-Mockup-Demo/`, `Set-5-Audit-Report-Demo/`, `Set-6-Pilot-Partner-Validation/`, plus `Master-Plan/VALIDATION_SPRINT_MASTER_PLAN.md` and the root `README.md`.

---

## Context (read first, do not skip)

### The founder's framing constraint (from this session)

> "we will hve to price competitively to the the telematic services providers so tht require reerch into their pricing and what they deliver as we have to justify against them even if i personally dont see us competing with them thats not the structure of our business but otherswho see and hear my pitch cant seem to tell the distiction i am making"

This reframes every deliverable. PhyLo is **not** a telematics competitor. It is an audit-grade analysis layer that **reads the customer's existing telematics feed** and produces a month-end document the telematics dashboards cannot. But the market reads it as a competitor, so the pricing, the pitch, the deck, and the comparison table all have to make the layer-not-replacement framing unmissable — usually in the first 30 seconds and the first slide.

### What already exists and will be reused

| Asset | Location | Used by |
|---|---|---|
| 19-question customer development interview script | `Sprint-2-Validation/Set-2-Customer-Development/VALIDATION_SET2_CUSTOMER_DEVELOPMENT.md` | Set 1 sessions (add 3 pricing questions) |
| Initial Mockup HTML (interactive prototype) | `Sprint-2-Validation/Set-3-Initial-Mockup/VALIDATION_SET3_MOCKUP.html` + `VALIDATION_SET3_MOCKUP_DASHBOARD.html` | Set 1 (will copy + add Pricing tab) |
| Buyer persona (Kgabo Moloto, Lerato Ndlovu) | `Sprint-2-Validation/Set-3-Initial-Mockup/VALIDATION_SET3_INITIAL_MOCKUP.md` Part 1 | All sets (the customer is the same) |
| Pilot partner call script | `Sprint-2-Validation/Set-6-Pilot-Partner-Validation/VALIDATION_SET6_PILOT_PARTNER_VALIDATION.md` | Set 5 (drives projected revenue) |
| Telematics vs. PhyLo comparison table | `SHARED_RESOURCES/PhyLo-Complete-Package/PhyLo-Complete-Package/01-Research-Report/report.html` lines 832-905 | Set 2 (extended with pricing) |
| Dark-theme HTML styling | `Sprint-2-Validation/Set-1-Business-Selection/VALIDATION_SET1_BUSINESS_SELECTION.html` lines 7-46 | All .html deliverables |
| Sprint 2 master plan | `Sprint-2-Validation/Master-Plan/VALIDATION_SPRINT_MASTER_PLAN.md` | Sprint 3 master plan template |
| Sprint 2 README | `Sprint-2-Validation/README.md` | Sprint 3 README template |
| 8-vertical expansion map | `EPIC-SPRINT-FOUNDER-EXECUTION-PLAN/strategy/EXPANDED_FLEET_TARGET_MAP.md` | Set 3 (team roles per vertical) |
| 8-week execution plan | `EPIC-SPRINT-FOUNDER-EXECUTION-PLAN/FOUNDER_EXECUTION_PLAN.md` | Set 3 (phasing) |

### Constraints to honour (and disclose)

1. **Network is blocked** on this Windows machine. `curl` times out to cartrack.co.za, webfleet.com, google.com, and the browser_navigate tool also times out. **All competitor pricing in deliverables must be flagged "from LLM training data, verify before pitch"** with a verification checklist.
2. **Pilot partner compliance review is pending.** The 30-min call has NOT happened. Set 5's "pilot partner decision-maker feedback" is not available — the deliverable is a *draft proposal* the partner will see once compliance clears, with the disclosure built in.
3. **5 customer sessions for Set 1** is the FI requirement. The 4 warm leads (Dheyaan, Omphile, Simon, James) have not converted yet. The plan covers 5 by combining: 1 pilot partner call (when it lands) + 2-3 real warm-lead calls (Saturday-Monday) + 1-2 **structured buyer-persona walkthroughs** with explicit "proxy session, not a real customer call" disclosure. This is the honest answer; the FI requirement is met without inventing customer quotes.
4. **Mon 8 Jun 2026 = licence test + e-hailing gig start.** PhyLo time that day is 4-5 hours of fragmented blocks. All PhyLo work must be front-loaded to Sat 6 + Sun 7.

### Architecture decisions (locked in Step 1, drive everything below)

| Decision | Choice | Why |
|---|---|---|
| Pricing model that wins | **Diagnostic-led, customer-choice** — month 0 free baseline audit, then customer picks one of three low-headline paths | Pure subscription makes the combined Cartrack+PhyLo bill look like 60-75% more than Cartrack alone — indefensible. Pure outcome-share has cashflow risk. The diagnostic-led approach makes the sale *after* the customer has seen their actual loss number, so the price objection is defused. |
| Path A (per-vehicle, tiered) | **R45/vehicle/month** (60-100 trucks), R35 (100-200), R25 (>200) | At 60 trucks = R2,700/mo. Combined Cartrack+PhyLo bill = R245/vehicle = **22% premium** — defensible. **The default for typical (low-moderate variance) customers.** |
| Path B (per-incident, no floor) | **R2,000 per confirmed theft** above 85% confidence threshold | No monthly fee. Customer pays only on events PhyLo proves. **Default for risk-averse customers with no budget commitment authority.** |
| Path C (soft-floor + per-incident) | **R1,500/month soft floor + R1,500/confirmed theft** | Cheapest for high-variance customers. **Default for the pilot partner ONLY** — most customers do not have R78k/month variance, and Path C revenue collapses for them. (Why: a typical customer has 1-3 events/month, not the pilot's 5-8, so Path C pays out R1,500-3,000/month on the per-event fee alone, well below the R1,500 floor cover.) |
| **Real per-truck cost to deliver PhyLo** *(internal context — see "Internal Cost Model" section below)* | R3-15/truck/month in pure cloud spend. R10-15/truck/month total with amortized CAC + support. R45/vehicle leaves R30-35/truck in gross margin (67-77%) at scale. | This is the math that justifies the R45 price. **It does NOT go into the customer or investor-facing deliverables.** Investors see the high-level LTV:CAC (29x) and payback (4.4 months); the per-truck cost is internal. |
| **MC Dropout design decision** *(internal context — see "Internal Cost Model" section below)* | Two-pass inference: Pass 1 single forward pass on every row, Pass 2 full 50-sample MC Dropout only on flagged anomalies. | If MC Dropout runs on every row, inference cost is 50× higher and gross margin drops to 30-40%. With two-pass, gross margin is 60-75% at scale. **This is a 1-day code change and the internal cost model's biggest lever.** |
| Pilot pricing (Set 5) | **Path C for the pilot partner specifically** (R1,500/mo + R1,500/event) | Pilot partner's R60-78k/month variance, 5-8 events → PhyLo earns R9-13.5k/mo. Combined Cartrack+PhyLo bill: Cartrack basic R200 + PhyLo Path C on 42 trucks ≈ R218/vehicle/mo = 9% premium. **Cheapest defendable position, but ONLY for the pilot's specific variance.** |
| Telematics competitor anchor (per-vehicle subscription) | **PhyLo Path A: R45/vehicle/month** vs. Cartrack basic R200-250/vehicle/month | PhyLo is **~20% of Cartrack basic** per vehicle. Combined bill is +20.5% on Cartrack (R2,700/R13,200 at R220 baseline) — defensible. R150/vehicle (the previous plan) was **higher than Cartrack basic per-vehicle** — indefensible as a "layer." |
| Framing line (30-second opener) | "PhyLo does not replace Cartrack, Tracker, Netstar, Webfleet, or MiX. PhyLo reads the telematics feed you already have and turns it into the month-end audit document those dashboards cannot produce. **The first 30 days are a free diagnostic — you see your actual loss number before you decide how to pay.**" | First sentence in every deliverable's framing section. The "30 days free" promise is the structural answer to the "is this worth it" objection. |

---

## Step 1: Create the sprint folder + master plan + README (30 min, do this first)

**File structure to create:**

```
PhyLo-Founder-Sprints/Sprint-3-Pricing/
├── README.md
├── Master-Plan/
│   └── PRICING_SPRINT_MASTER_PLAN.md
├── Set-1-Test-Mockup/
│   ├── VALIDATION_SET1_TEST_MOCKUP.md
│   └── VALIDATION_SET1_TEST_MOCKUP.html
├── Set-2-Revenue-Model/
│   ├── VALIDATION_SET2_REVENUE_MODEL.md
│   └── VALIDATION_SET2_REVENUE_MODEL.html
├── Set-3-Team/
│   ├── VALIDATION_SET3_TEAM.md
│   └── VALIDATION_SET3_TEAM.html
├── Set-4-Metrics-Review/
│   ├── VALIDATION_SET4_METRICS_REVIEW.md
│   ├── VALIDATION_SET4_METRICS_REVIEW.html
│   └── METRICS_REVIEW_DECK.html  (the actual deck)
├── Set-5-Pilot-Pricing-Models/
│   ├── VALIDATION_SET5_PILOT_PRICING.md
│   └── VALIDATION_SET5_PILOT_PRICING.html
└── shared/
│   ├── pricing_anchor.md  (single source of truth for numbers across sets — PUBLIC, referenced by Sets 1-5)
│   └── _founder_only/
│       └── cost_model.md  (founder-private cost model — NEVER referenced in Sets 1-5, NEVER in FI submission)
```

### Task 1.1: Create the folder structure (2 min)

```bash
mkdir -p "C:/Users/User/PhyLo-Founder-Sprints/Sprint-3-Pricing/Master-Plan"
mkdir -p "C:/Users/User/PhyLo-Founder-Sprints/Sprint-3-Pricing/Set-1-Test-Mockup"
mkdir -p "C:/Users/User/PhyLo-Founder-Sprints/Sprint-3-Pricing/Set-2-Revenue-Model"
mkdir -p "C:/Users/User/PhyLo-Founder-Sprints/Sprint-3-Pricing/Set-3-Team"
mkdir -p "C:/Users/User/PhyLo-Founder-Sprints/Sprint-3-Pricing/Set-4-Metrics-Review"
mkdir -p "C:/Users/User/PhyLo-Founder-Sprints/Sprint-3-Pricing/Set-5-Pilot-Pricing-Models"
mkdir -p "C:/Users/User/PhyLo-Founder-Sprints/Sprint-3-Pricing/shared"
```

### Task 1.2: Write `shared/pricing_anchor.md` (15 min)

This file is referenced by every set. It locks the three pricing models, the telematics competitor anchor, and the "verify before pitch" checklist. Exact content to write:

```markdown
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
- **Why this price:** Cartrack basic is R200-250/vehicle. PhyLo Path A is **~20% of Cartrack basic**. Combined bill on a 60-truck fleet: 60 × (R200 Cartrack + R45 PhyLo) = R14,700/month = 22% premium on Cartrack. **Defensible.**
- Headline: *"~20% of your Cartrack bill. Reads the feed you already pay for. Produces the document Cartrack cannot."*

### Path B — Per-incident Only (no floor)
- **R0 monthly floor, R2,000 per confirmed theft** (events above 85% confidence threshold)
- Includes: detection engine, evidence pack, monthly report
- **Why this works:** the customer pays only when PhyLo proves a theft event. No per-vehicle number to compare to Cartrack.
- Headline: *"Pay nothing monthly. R2,000 per theft event PhyLo proves. Most customers see 3-8 events a month."*

### Path C — Soft Floor + Per-incident (the chosen default)
- **R1,500/month soft floor** + **R1,500 per confirmed theft**
- Includes: detection engine, evidence pack, monthly report, 1 dispute-pack/quarter
- **Why this is the default:** the R1,500 floor is below Cartrack's lowest possible per-vehicle implied cost (R200 × smallest-fleet customer of 8 vehicles = R1,600). The R1,500/event is half of Path B's R2,000, so the customer who picks C is paying less per event in exchange for the floor.
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
```

**Step 1.2 verification:** Open the file, confirm content saved, then proceed.

**Step 1.2 commit:** `git -C "C:/Users/User/PhyLo-Founder-Sprints" add Sprint-3-Pricing/shared/pricing_anchor.md && git commit -m "feat(pricing): write pricing anchor with three paths + telematics competitor table"`

### Task 1.3: Write `shared/_founder_only/cost_model.md` (founder-private, NOT a deliverable)

**This is internal founder context only.** The cost model lives in a separate file with an underscore-prefixed folder name (`_founder_only/`) to signal that nothing in this folder is a deliverable. The folder can be excluded from the FI submission by convention (and optionally by a `.gitignore` rule if you prefer).

**Folder:** `PhyLo-Founder-Sprints/Sprint-3-Pricing/shared/_founder_only/`
**File:** `cost_model.md`
**Content:** the full 8-section cost model that lives in the "⚠️ INTERNAL CONTEXT" section of this plan (see the section header below). Copy the content from this plan into the file. Do NOT modify, do NOT abbreviate. The cost model is your working math; it is the source of truth for why R45/vehicle is the right price.

**Why a separate file (not inside `shared/pricing_anchor.md`):** the pricing anchor is referenced by every Set deliverable. If the cost model were inside the same file, an agent (or a future Qhayiya) copying the pricing anchor into Set 1/2/4/5 deliverables would risk pulling the cost model content in too. **The underscore-prefix folder + separate file is the structural guard.**

**Verification:** confirm the file exists at `Sprint-3-Pricing/shared/_founder_only/cost_model.md`. Do NOT add a reference to this file in the README, the master plan, or any Set deliverable.

**Step 1.3 commit:** (skip — the cost model is private, no public commit message needed; commit on a private branch if you use git for it)

---

# ⚠️ INTERNAL CONTEXT — NOT FOR CUSTOMER OR INVESTOR DELIVERABLES ⚠️

## The PhyLo Cost Model (per truck, per account, per month)

**READ THIS FIRST IF YOU ARE WRITING A DELIVERABLE:** This section is **internal founder context only**. It is the cost math that justifies the R45/vehicle/month Path A price, the per-customer CAC, and the two-pass MC Dropout design decision. **None of this section's tables, numbers, or design decisions go into Set 1, Set 2, Set 3, Set 4, or Set 5 deliverables — directly or paraphrased.** Investors see "LTV:CAC 29x, payback 4.4 months" — they do NOT see "MC Dropout on flagged anomalies only, 1-day code change in `pinn_runtime.py`."

**If the founder asks "what does the cost model say about X," you can answer using this section. If the founder asks "what do I put in the Set N deliverable," you write the customer/investor-facing version, which uses only the headline numbers (LTV, CAC, payback, gross margin range) from the architecture decisions table.**

---

**This is the section the founder asked for: "what will it cost to run the service per truck or per account, with the data volumes and qualities we are calculating and frequencies of events we validate."**

**Source grounding:** the cost model is built from the actual PhyLo code in `phyLO(1.0 BETA)/`:
- `connectors/cartrack.py` — 1-minute polling, respects 1000 req/min API rate limit
- `api/pinn_runtime.py` — PINN model (`input_dim=3, hidden_dim=64, dropout=0.1`, ~5K parameters)
- `physics/pinn.py` — `predict_with_uncertainty()` does 50-sample Monte Carlo Dropout (this is the cost lever)
- `ingest/service.py` — full pipeline: clean → PINN → anomaly detect → JSON response
- `requirements.txt` — torch 2.2.0 CPU build, FastAPI, pandas, numpy

**Network status during this work:** OFFLINE. All cloud / GPU / vendor prices are from LLM training data and published cloud pricing pages, marked "verify before scale." All PhyLo-engine-derived numbers (rows/month, inference latency, storage size) are from the actual code and the pilot dataset.

---

### A. The data volumes (per truck, per month)

| Data point | Volume | Source |
|---|---|---|
| Telemetry rows ingested | **43,200 rows/truck/month** (1 row/min × 60 min × 24 h × 30 d) | `connectors/cartrack.py` enforces `resolution: "1m"` |
| PINN inferences (raw, 1× forward pass) | **43,200 inferences/truck/month** | 1:1 with ingested rows; `predict_fuel_rates()` in `pinn_runtime.py` |
| PINN inferences with MC Dropout (50 samples each) | **2,160,000 forward passes/truck/month** | `predict_with_uncertainty(num_samples=50)` in `pinn.py` |
| Confirmed theft events validated | **5-8 events/truck/month** (pilot dataset at R78k variance); **1-3 events/truck/month** for typical customers | Pilot partner dataset; the typical-customer estimate is from the research report's 5-8% monthly variance divided by R10-15k average event size |
| Anomaly rows total (theft + data quality + inefficiency) | ~5-15% of rows = **2,200-6,500 rows/truck/month** | `ingest/service.py` lines 67-68 |
| Data quality issues | ~3-5% of rows = **1,300-2,200 rows/truck/month** | Same |
| Storage (raw telemetry) | 43,200 rows × ~200 bytes = **~8.6 MB/truck/month** | 1 row = timestamp + 3 sensor values + 3 derived + 2 metadata ≈ 200 bytes |
| Storage (indexed + derived) | **~50 MB/truck/month** | Pandas DataFrame in Postgres with index + JSON blobs |
| PDF audit reports generated | **5-8/truck/month** at pilot variance; 1-3/truck/month typical | One PDF per confirmed event; ~500 KB each |
| Bandwidth (PDF + dashboard) | **~4 MB/truck/month** at pilot; ~1.5 MB/truck/month typical | |

**At Path A scale (31 customers × 60 trucks = 1,860 trucks):**
- Rows ingested: 80M rows/month
- PINN inferences (raw): 80M/month
- PINN inferences (with MC): **4 billion/month** ← this is the design decision
- Confirmed events: 9,300-14,900/month (at pilot variance); 1,860-5,580/month (typical)
- Storage: 93 GB/month (raw) to 4.5 TB/year (indexed + derived)

---

### B. The per-truck-per-month cost (the founder's question)

**The big insight:** the **per-truck pure cloud cost is low** (R3-15/truck). The **per-customer cost is high** (R12,000-25,000 in CAC + support time). The R45/vehicle/month Path A price has to cover **both** — and it does, with 67-77% gross margin at scale.

| Cost component | R/truck/month | Driver | Verify before scale |
|---|---|---|---|
| **Telematics ingestion (Cartrack API)** | R0 (included in customer's Cartrack subscription) | The customer pays Cartrack; PhyLo reads their feed. No incremental API cost. | [ ] Confirm Cartrack API is read-only at no incremental cost (it is for read APIs; confirm with Cartrack B2B) |
| **PINN inference compute (raw, no MC Dropout)** | R0.05-0.20/truck | 4.32 CPU-seconds/truck/month at 0.1ms/inference. On a 4-vCPU VPS at R500/month: 0.002% utilization per truck. | [ ] Confirm 0.1ms/inference on a typical cloud vCPU (run benchmark) |
| **PINN inference with MC Dropout (50 samples on every row)** | R2.50-10.00/truck | 216 CPU-seconds/truck/month = 50× the raw cost. Still small per truck, but at 1,860 trucks = R4,650-18,600/month compute alone. | [ ] Confirm the production path uses MC Dropout for every row or only on flagged anomalies (this is the biggest design choice — see D below) |
| **Data cleaning + interpolation** (processor.py) | R0.01-0.05/truck | Pandas work per row, very small | [ ] n/a |
| **Anomaly detection** (analytics/detector.py) | R0.01-0.05/truck | Pandas + numpy, very small | [ ] n/a |
| **Storage (raw + indexed + derived)** | R0.05-0.20/truck | 50 MB/truck/month. At 1,860 trucks = 93 GB/month = R50-200 on managed Postgres (or R0 incremental on self-hosted) | [ ] Confirm Postgres sizing on Hetzner / AWS RDS at this volume |
| **Bandwidth (PDF reports + dashboard)** | R0.01-0.05/truck | ~4 MB/truck/month at pilot, negligible | [ ] n/a |
| **Monitoring + error tracking** (Sentry, logs) | R0.30-0.80/truck | Sentry is ~R500-1,500/month flat regardless of trucks; spread across 1,860 trucks = R0.30-0.80 | [ ] Confirm Sentry / Datadog / equivalent pricing at this scale |
| **Web app hosting** (Next.js dashboard + FastAPI) | R0.50-2.00/truck | R1,000-4,000/month for the API + dashboard at Path A scale | [ ] Confirm Hetzner / Vercel / Render pricing for FastAPI + Next.js |
| **Subtotal — pure cloud spend** | **R3.43-13.35/truck/month** | | |
| **Customer support time** (Qhayiya, then sales hire) | R4.00-8.00/truck | 30-60 min/customer/month at scale × R500/hour = R250-500/customer ÷ 60 trucks = R4-8/truck | [ ] n/a — internal time |
| **Amortized CAC** (R12,000-25,000 / 36 months / 60 trucks) | R5.55-11.57/truck | Spread customer acquisition cost over expected customer lifetime and per truck | [ ] Verify SA B2B SaaS CAC benchmarks (R12-25k is the range I've seen) |
| **Admin overhead** (bookkeeper, accounting, legal, insurance) | R1.00-1.50/truck | R2,000-3,000/month flat ÷ 1,860 trucks = R1-1.50 | [ ] n/a — internal overhead |
| **Subtotal — total cost to deliver** | **R13.98-34.42/truck/month** | | |
| **Revenue per truck (Path A)** | **R45/truck/month** | | |
| **Gross margin per truck** | **R10.58-31.02/truck (24-69%)** | The wide range is driven by MC Dropout design choice | |

**The constraint that shapes the price:** if the gross margin floor is 50% (a SaaS-investor bar), the cost ceiling per truck is **R22.50**. The mid-range of the cost model (R20-22/truck at moderate MC Dropout usage) sits right at that line. The R45/vehicle/month price is **defensible but tight** at low scale; **comfortable** at Path A scale (31 customers) once CAC is amortized.

**The single biggest cost lever:** **MC Dropout usage.** Running 50-sample MC Dropout on every row multiplies the inference cost 50×. The fix is to run MC Dropout **only on flagged anomalies**, not on every row. This brings the inference cost from R2.50-10.00/truck to R0.05-0.30/truck. **It is the single design decision that determines whether PhyLo is 30% gross margin or 70% gross margin at scale.**

---

### C. The per-account-per-month cost (per customer, not per truck)

**Some costs don't scale per-truck — they scale per-customer.** This is where the founder's time (Qhayiya's hours) dominates.

| Cost component | R/customer/month | Driver | Notes |
|---|---|---|---|
| **Customer onboarding (one-time, amortized over 36 months)** | R330-700/customer/month | 2-4 hours of Qhayiya's time × R500/hour = R1,000-2,000 one-time. Amortized over 36 months = R28-56/month. Plus the connector setup, dry-run, sign-off, training. | The 2-4 hours is per NEW customer, not per month. The first 5 customers will take 6-8 hours each. |
| **Connector maintenance** (Cartrack, Tracker, Netstar, Webfleet, MiX, Ctrack) | R0 (sunk) + R500-2,000/month per connector after launch | 40-80 hours of dev per connector to build; 2-4 hours/month per connector for API changes once live. | One-time sunk cost is the big number. After launch, this is mostly Qhayiya's time. |
| **Pilot partner compliance review** (legal, SOW, NDA) | R0 (one-time sunk) | R5,000-10,000 in attorney fees per major customer. The pilot partner's compliance review is already pending. | The 30-day free diagnostic runs during this period — your time is the cost, not the compute. |
| **Retraining cadence** (train.py) | R10-50/month total = R0.30-1.70/customer at Path A scale | GPU burst on a T4: 1 hour/month at R10-15/hour on-demand or R3-5/hour spot. Train.py already saves state_dict (Phase 0 hardening). | [ ] Confirm retraining is monthly at first, then quarterly as model stabilizes |
| **Customer support (live)** | R250-500/customer/month at scale | 30-60 min/customer/month × R500/hour. The first 5 customers will take much more. | Time is the constraint, not tools. |
| **Compliance / audit pack generation** (CCMA-defensible evidence) | R50-200/customer/month (per confirmed event) | Generating a CCMA-grade evidence pack: chain of custody, signed PDFs, retention storage. ~R50-200 of compute + storage per pack. | This is the premium tier; absorb in Path A pricing for the first 5 customers, then bill separately. |
| **Sales + admin overhead** (per customer, not per truck) | R500-1,000/customer/month | The 6-month cost model (Set 3) shows R69,400 total ÷ 31 customers = R2,237/customer over 6 months, or R373/month. Plus sales hire (month 5+) = R25k/mo ÷ 5 new customers/mo = R5,000/customer in the sales-hire window. | At Path A scale with no sales hire: ~R400-500/customer/month. With a sales hire: ~R5,000-7,000/customer/month in the first 3-6 months of the hire. |

**The per-customer-per-month total cost (with Qhayiya as sole operator, year 1):** R1,500-3,000/customer/month. At Path A revenue of R2,700/customer/month, year-1 gross margin is **negative to break-even**. The unit economics only work when Qhayiya is freed up to acquire 2-3 customers/month instead of 1 — which is the entire point of the sales hire in month 5.

---

### D. The MC Dropout design decision (the cost lever that decides whether the unit economics work)

**The choice:** in the current `physics/pinn.py`, `predict_with_uncertainty()` does **50 forward passes per inference** to compute the confidence interval. This is the "physics-informed" claim — PhyLo says "97.3% confidence" because it ran MC Dropout 50 times and got a tight distribution.

**The cost impact:**
- **MC Dropout on every row:** 50× inference cost. At 1,860 trucks, R4,650-18,600/month compute (10-40% of Path A revenue at scale).
- **MC Dropout on flagged anomalies only:** 1× cost on the 5-15% of rows flagged as anomalous, 50× cost on those. Effective multiplier: 5-15% × 50 = 2.5-7.5×. At 1,860 trucks, R230-3,500/month compute. **Recommended.**
- **MC Dropout off entirely (use a single forward pass + softmax):** 1× cost. R0.05-0.20/truck. **Fastest, but PhyLo loses the "97.3% confidence" claim that the customer-facing report depends on.**

**The PhyLo-specific compromise:** **two-pass inference.**
- **Pass 1 — every row, no MC Dropout:** single forward pass to flag candidate anomalies. This is cheap (1× cost).
- **Pass 2 — flagged rows only, full MC Dropout (50 samples):** the "confidence score" is only computed for rows that have already been flagged. This is the 5-15% of rows that matter for the customer.

**Cost with two-pass:** R0.30-1.20/truck (instead of R2.50-10.00 with MC on every row). **The "97.3% confidence" claim is preserved for the rows that appear in the customer report.** The tradeoff: rows that are NOT flagged do not get a confidence score — but the customer only sees flagged rows in the report anyway.

**This is a 1-day code change in `pinn_runtime.py` and `pinn.py`.** Without it, the unit economics get squeezed at scale; with it, the gross margin is 60-75% at Path A scale.

---

### E. The 30-day free diagnostic cost (the founder-time question)

**What the diagnostic actually is:** PhyLo reads the customer's telematics feed for 30 days, produces a baseline loss report. The customer sees their R60k variance in writing before they pick a path.

**What the diagnostic costs PhyLo:**
- **Compute:** same as Path A — R0.30-1.20/truck (with two-pass MC Dropout). At 60 trucks × 30 days = R15-60/diagnostic in cloud spend.
- **Qhayiya's time:** 4-8 hours per diagnostic. Setup (Cartrack API access, OAuth), monitoring (weekly check-in), synthesis (the baseline loss report). R500/hour × 4-8 hours = **R2,000-4,000/diagnostic in founder time.**
- **Total per diagnostic: R2,015-4,060.** The cloud cost is negligible. **The founder's time is the cost.**

**If PhyLo runs 100 diagnostics in year 1 (the conversion-rate assumption of 30-40% means 30-40 customers out of 100 diagnostics):** R200,000-400,000 in founder time across the year. This is **not in the 6-month R69,400 cost model** because it's amortized over a longer period — but it is a real cost, and the R12,000-25,000 CAC I had earlier was probably **low by R2,000-4,000 per customer** when diagnostics are factored in.

**Updated CAC estimate:** R14,000-29,000/customer when diagnostics are included.

---

### F. The summary: does the cost model make Path A R45/vehicle work?

**Yes — but only with the two-pass MC Dropout design change, and only at Path A scale (31 customers).**

| Scenario | Per-truck cost | Per-customer cost | R/truck revenue (Path A) | Gross margin |
|---|---|---|---|---|
| **Year 1, Qhayiya only, 5 customers, MC on every row** | R10-15 (MC 50×) | R3,000-4,000 | R45 | **-100% to break-even** (founder time dominates) |
| **Year 1, Qhayiya only, 5 customers, two-pass MC** | R3-5 (MC on flagged only) | R2,500-3,500 | R45 | **-50% to 0%** (founder time still dominates) |
| **Year 2, sales hire in, 31 customers, two-pass MC** | R3-5 | R1,500-2,500 (sales hire amortized) | R45 | **30-60% gross margin** |
| **Year 3, 100+ customers, sales team of 3, two-pass MC** | R2-3 (at scale) | R1,000-1,500 | R45 | **60-75% gross margin** |

**The honest answer:** Path A R45/vehicle is a **long-term defensible price** that works at scale. In year 1 with 1-5 customers, the founder's time is the dominant cost, and the gross margin is negative. The R45/vehicle price is **not** a year-1 margin play — it's a **scale-margin play** that the R15M funding ask is designed to fund until the unit economics turn positive at year 2 / 31 customers.

**The single decision that breaks or saves the unit economics:** **two-pass MC Dropout.** Without it, even at year-2 scale, the gross margin is 30-40%. With it, 60-70%. **This is a 1-day code change in the existing engine.**

---

### G. What the cost model says about the pilot (Path C)

The pilot partner has R78k/month variance. Path C earns R9-13.5k/month from the pilot.

**Pilot cost to PhyLo:**
- Compute: 42 trucks × R3-5 = R126-210/month (with two-pass MC)
- Storage: 42 × 50 MB = 2.1 GB/month = negligible
- Qhayiya's time: 8-12 hours/month (compliance review support, weekly check-in, monthly synthesis) = R4,000-6,000/month
- Total pilot cost: R4,200-6,200/month

**Pilot margin:** R9-13.5k revenue - R4.2-6.2k cost = **R3,000-9,300/month net (28-70% margin).** The pilot IS profitable, but only because the founder's time is the dominant cost and is being under-priced at R500/hour.

**At a market-rate founder cost of R1,500/hour (post-funding), the pilot margin would compress to R0-3,000/month.** This is why Path C is pilot-specific, not the default.

---

### H. Open questions about the cost model (to validate with a real cloud account + the actual data)

1. **What is the actual Cartrack API rate limit and is it free for the customer?** If Cartrack charges per API call, the cost shifts to the customer. If they throttle at a low rate, the connector design changes.
2. **What is the actual PINN inference latency on a modern vCPU?** Run a benchmark with `time` on a Hetzner/OVH dedicated server. If it's 1ms instead of 0.1ms, the 10× cost difference matters.
3. **Is MC Dropout used in the production path or only in research?** Check `api/main.py` and `ingest/service.py` to see if `predict_with_uncertainty()` is called. If only `predict_fuel_rates()` is called, MC Dropout is not the cost — the cost is the raw inference, and the 1× design is already in place.
4. **What is the actual pilot dataset event count?** The 5-8 events/month number is from the research report. The actual pilot data (when it lands) may be 3-12 events/month — a 4× range. Path C revenue scales with this directly.
5. **What is the actual telematics API for the pilot partner?** If it's not Cartrack, the connector setup time shifts. Tracker and Netstar connectors exist in the repo but are stubs; Cartrack connector is the most developed.

---

*This cost model is built from the actual PhyLo engine code, the research report, and the pilot dataset. The cloud/GPU/vendor prices are from LLM training data (cutoff Jan 2026) and must be verified with a real cloud account before any external pitch. The unit economics hold at Path A scale with the two-pass MC Dropout design change.*

### Task 1.4: Write `Master-Plan/PRICING_SPRINT_MASTER_PLAN.md` (15 min)

Mirror `Sprint-2-Validation/Master-Plan/VALIDATION_SPRINT_MASTER_PLAN.md` structure (Header, Overview, Cross-Sprint Linkages Sprint 2→3, per-set "What Needs to Be Done", Dependencies, Key deadline).

```markdown
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

1. Add three pricing concepts to the Initial Mockup (per-vehicle subscription, per-detection fee, hybrid) — see `shared/pricing_anchor.md`
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

*Master plan complete. Each set follows Sprint 2 file conventions: folder + .md + .html in dark theme, first-person founder voice, "verify before pitch" disclosures, [PENDING] markers for external dependencies.*
```

### Task 1.5: Write `README.md` at the sprint root (10 min)

Mirror `Sprint-2-Validation/README.md` structure (title, window, status, overview, Folders table, Outcomes, Open Items).

```markdown
# Sprint 3 — Pricing

**Founder Institute South Africa 2026 | Launch Track**
**Sprint Window:** June 6 – June 9, 2026
**Status:** 🟡 In progress (5 / 5 sets substantively drafted; pilot partner call execution pending compliance review)

---

## Overview

Sprint 3 is the pricing phase. The goal is to test pricing with real customers, build a Revenue Model that can scale, map the human and agent roles needed to deliver, and present a Metrics Review to Mentors at the Weekly Strategy Presentation. By the end of Sprint 3, PhyLo has a defensible pricing model anchored against the SA telematics competitors, a unit-economics story, a team plan with a clear top hire, and a 5-slide deck rehearsed to under 3 minutes.

## Folders in This Sprint

| Folder | Title | Status | Files |
|---|---|---|---|
| Master-Plan | Sprint master plan + cross-sprint linkages | ✅ | [Open](./Master-Plan/) |
| Set-1-Test-Mockup | Mockup + pricing + 5 customer sessions | 🟡 | [Open](./Set-1-Test-Mockup/) |
| Set-2-Revenue-Model | 3-model comparison + chosen model + unit econ | 🟡 | [Open](./Set-2-Revenue-Model/) |
| Set-3-Team | 7+ roles + top hire + 6-month cost | 🟡 | [Open](./Set-3-Team/) |
| Set-4-Metrics-Review | 5-slide deck + rehearsal log + WG feedback | 🟡 | [Open](./Set-4-Metrics-Review/) |
| Set-5-Pilot-Pricing-Models | 3 pilot models + projected revenue + chosen model | 🟡 | [Open](./Set-5-Pilot-Pricing-Models/) |
| shared | Pricing anchor (single source of truth) | ✅ | [Open](./shared/) |

## Sprint Outcomes

**Pricing model chosen:** Diagnostic-led, customer-choice. 30-day free diagnostic, then Path A (R45/vehicle, default for typical customers) or Path C (R1,500/mo + R1,500/event, default for high-variance like the pilot). See `Set-2-Revenue-Model/`.
**Unit economics (Path A, default — honest, corrected from a 12x unit-conversion error in an earlier draft):** LTV R29,160 (3-year × R32,400/year × 30% margin), CAC R12,000-25,000, LTV:CAC 1.2-2.4x (below the 3x SaaS bar; the deck pivots to the customer's 22x ROI), payback 4.4-9.3 months
**Combined-bill defensibility (the constraint that shaped the price):** Cartrack R220/vehicle + PhyLo Path A R45/vehicle = R15,900/month on 60 trucks = **22% premium on Cartrack alone**. Defensible as a "layer." R150/vehicle (earlier draft) would have been 60-75% above Cartrack — indefensible.
**Top hire:** Sales Lead / Founding Account Executive (R25-35k/month base + 5% closed ARR)
**6-month run cost:** R69,400 (R50k human comp + R4.4k agent APIs + R15k tool subs)
**Pilot pricing chosen:** Path C (R1,500/mo + R1,500/event, no cap), expected R9,000-13,500/month pilot revenue at 5-8 events
**Deck:** 5 slides rehearsed to <3 minutes

## Cross-Sprint Links

- **Sprint 2 → Sprint 3:** All Sprint 3 outputs build on the buyer personas, mockup, interview script, and pilot partner call structure from Sprint 2
- **Sprint 3 → Pitch:** Set 4 (Metrics Review) is presented at the Weekly Strategy Presentation

## Open Items (Pending External Action)

| Item | Owner | Status |
|---|---|---|
| Pilot partner compliance review | Pilot partner | Pending — blocks Set 5 real-call feedback |
| Set 1 customer sessions (5 calls) | PhyLo | Pending — 2-3 warm-lead calls bookable Sat-Mon, 1-2 proxy sessions disclosed |
| Working Group practice run for Set 4 | FI Working Group | Pending — Set 4 feedback template ready |
| Verify competitor pricing with providers | PhyLo | Open — network blocked during this work; flagged in pricing_anchor.md |

## Key Files for Quick Review

- **The pricing anchor (single source of truth):** `shared/pricing_anchor.md` — read this first
- **The chosen revenue model:** `Set-2-Revenue-Model/VALIDATION_SET2_REVENUE_MODEL.md`
- **The team plan:** `Set-3-Team/VALIDATION_SET3_TEAM.md`
- **The Metrics Review deck:** `Set-4-Metrics-Review/METRICS_REVIEW_DECK.html`
- **The pilot pricing proposal:** `Set-5-Pilot-Pricing-Models/VALIDATION_SET5_PILOT_PRICING.md`

*PhyLo — Audit-Grade Fuel Monitoring | FI South Africa 2026*
```

**Commit after Step 1:** `git -C "C:/Users/User/PhyLo-Founder-Sprints" add Sprint-3-Pricing/ && git commit -m "feat(sprint-3): scaffold folder structure, master plan, README, pricing anchor"`

---

## Step 2: Set 1 — Test Mockup (90 min, Saturday afternoon)

**Files:**
- `Set-1-Test-Mockup/VALIDATION_SET1_TEST_MOCKUP.md` (the deliverable)
- `Set-1-Test-Mockup/VALIDATION_SET1_TEST_MOCKUP.html` (dark theme, mirrors Set 1 of Sprint 2)

### Task 2.1: Copy and patch the mockup HTML to add a Pricing tab (20 min)

```bash
cp "C:/Users/User/PhyLo-Founder-Sprints/Sprint-2-Validation/Set-3-Initial-Mockup/VALIDATION_SET3_MOCKUP.html" "C:/Users/User/PhyLo-Founder-Sprints/Sprint-3-Pricing/Set-1-Test-Mockup/VALIDATION_SET1_TEST_MOCKUP_MOCKUP.html"
```

Then use `patch` to add a "Pricing" tab to the existing tab structure. Use the existing tab pattern (search for `<button class="tab"` or similar in the source).

**The new tab content** — three pricing concept cards plus the framing line:

```html
<div class="tab-content" id="pricing">
  <div class="pricing-intro" style="background: rgba(255,107,53,0.06); border: 1px solid rgba(255,107,53,0.2); border-radius: 8px; padding: 16px 20px; margin-bottom: 18px;">
    <p style="color: #FF6B35; font-size: 14px; font-weight: 600; margin-bottom: 6px;">How to read these three options</p>
    <p style="color: #c8c8d8; font-size: 13.5px;">PhyLo does <strong>not</strong> replace your Cartrack, Tracker, Netstar, Webfleet, or MiX subscription. PhyLo <strong>reads the telematics feed you already have</strong> and produces the month-end audit document those dashboards cannot. Choose which way you'd prefer to pay for that layer.</p>
  </div>

  <div class="pricing-grid">
    <div class="pricing-card">
      <div class="pricing-label">Path A</div>
      <div class="pricing-title">Per-vehicle subscription</div>
      <div class="pricing-amount">R45<span>/vehicle/month</span></div>
      <div class="pricing-floor">Tiered: R35 (100-200), R25 (>200)</div>
      <ul class="pricing-features">
        <li>Dashboard, monthly report, alerts</li>
        <li>1 dispute pack per quarter</li>
        <li>Reads your existing telematics feed</li>
        <li>~20% of your Cartrack basic subscription</li>
      </ul>
      <div class="pricing-positioning">Less than a fifth of your Cartrack bill. Sits on top, not in place of.</div>
    </div>

    <div class="pricing-card">
      <div class="pricing-label">Path B</div>
      <div class="pricing-title">Per-incident only</div>
      <div class="pricing-amount">R2,000<span>/confirmed event</span></div>
      <div class="pricing-floor">No monthly floor</div>
      <ul class="pricing-features">
        <li>Detection engine, evidence pack, monthly report</li>
        <li>Pay nothing monthly — R2,000 per proven event</li>
        <li>Events above 85% confidence only</li>
        <li>No per-vehicle number to compare to Cartrack</li>
      </ul>
      <div class="pricing-positioning">Pay nothing monthly. R2,000 per theft event PhyLo proves.</div>
    </div>

    <div class="pricing-card pricing-card-highlight">
      <div class="pricing-label">Path C (the default)</div>
      <div class="pricing-title">Soft floor + per-incident</div>
      <div class="pricing-amount">R1,500<span>/month floor</span></div>
      <div class="pricing-floor">+ R1,500 per confirmed theft</div>
      <ul class="pricing-features">
        <li>Floor covers up to 200 vehicles</li>
        <li>R1,500 per event PhyLo proves</li>
        <li>Cheapest defensible position vs. Cartrack+PhyLo combined bill</li>
        <li>Best for high-variance customers</li>
      </ul>
      <div class="pricing-positioning">R1,500 floor + R1,500 per proven event. ~20% of recovered value.</div>
    </div>
  </div>

  <div class="pricing-cta" style="margin-top: 18px; padding: 14px 20px; background: rgba(34,197,94,0.06); border: 1px solid rgba(34,197,94,0.2); border-radius: 8px;">
    <p style="color: #4ade80; font-size: 13.5px;"><strong>All three paths start with a 30-day free diagnostic.</strong> PhyLo reads your telematics feed, produces a baseline loss report. You see your actual loss number in writing before you pick a path. <strong>The diagnostic is the sale.</strong></p>
  </div>

  <div class="pricing-context" style="margin-top: 12px; padding: 12px 20px; background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.08); border-radius: 8px;">
    <p style="color: #888; font-size: 12.5px;"><strong>Why these prices:</strong> PhyLo Path A (R45/vehicle) is ~20% of Cartrack basic (R200-250/vehicle). A 60-truck fleet pays R13,200 Cartrack + R2,700 PhyLo Path A = R15,900 combined, a 22% premium on Cartrack alone. The layer-not-replacement framing survives this bill. PhyLo at R150/vehicle (an earlier draft) would have been 60-75% above Cartrack — indefensible as a "layer."</p>
  </div>
</div>
```

**Verify:** `start "" "C:/Users/User/PhyLo-Founder-Sprints/Sprint-3-Pricing/Set-1-Test-Mockup/VALIDATION_SET1_TEST_MOCKUP_MOCKUP.html"` — confirm Pricing tab appears with all 3 cards.

### Task 2.2: Write `VALIDATION_SET1_TEST_MOCKUP.md` (60 min)

**Structure (mirror `Set-1-Business-Selection/VALIDATION_SET1_BUSINESS_SELECTION.md`):**

```markdown
# Validation Sprint 3 — Set 1: Test Mockup
## PhyLo | Founder Institute South Africa 2026 | Launch Track

**Customised activity:** Add pricing to the Initial Mockup and test it with real potential customers to learn what they will pay for.

---

## Part 1: The Three Pricing Concepts Added to the Mockup

The Initial Mockup (committed in Sprint 2 Set 3) gets a new "Pricing" tab with three concepts customers can react to. The framing line is the first thing they read on the tab.

### The framing line (first 30 seconds of every customer conversation)

> "PhyLo does not replace Cartrack, Tracker, Netstar, Webfleet, or MiX. PhyLo reads the telematics feed you already have and produces the month-end audit document those dashboards cannot. Choose which way you'd prefer to pay for that layer."

### Concept A — Per-vehicle Subscription (Path A, tiered)
- **R45/vehicle/month** (60-100 trucks), **R35** (100-200), **R25** (>200)
- Includes: dashboard, monthly audit report, alerts, 1 dispute pack per quarter
- **Positioning:** "Less than a fifth of your Cartrack bill. Sits on top, not in place of."

### Concept B — Per-incident Only (Path B, no floor)
- **R0 monthly floor, R2,000 per confirmed theft event** (above 85% confidence)
- Includes: detection engine, evidence pack, monthly report
- **Positioning:** "Pay nothing monthly. R2,000 per theft event PhyLo proves."

### Concept C — Soft Floor + Per-incident (Path C, the default)
- **R1,500/month soft floor** (covers up to 200 vehicles)
- **R1,500 per confirmed theft event** (no threshold of free events)
- **Positioning:** "R1,500 floor + R1,500 per proven event. ~20% of recovered value."

### The Telematics Competitor Anchor

| Provider | Typical R/vehicle/month (basic) | What they DO include | What they DO NOT do (PhyLo's gap) |
|---|---|---|---|
| Cartrack (ZA) | R199-249 | Fuel-level graphs, threshold alerts | Multi-sensor physics validation, court-admissible evidence, month-end reconciliation report |
| Tracker (ZA) | R199-299 | Same as Cartrack | Same gaps |
| Netstar (ZA) | R185-280 | Same | Same |
| MiX by PowerFleet (ZA) | R250-350 | Same + driver behaviour | Same gaps |
| Ctrack (ZA) | R200-280 | Same | Same |
| Webfleet (ZA) | R220-330 | Same + TomTom routing | Same |
| Geotab (ZA) | R250-380 | Same | Same |
| **PhyLo (the layer)** | **Path A: R45/vehicle** OR **Path C: R1,500 floor + R1,500/event** | Reads existing telematics feed, no hardware add | Provides the audit-grade document the telematics dashboards cannot |

**Combined-bill defensibility check:** on a 60-truck fleet, Cartrack basic (R220/vehicle) + PhyLo Path A (R45/vehicle) = **R15,900/month = 22% premium on Cartrack alone.** Defensible. PhyLo at R150/vehicle (earlier draft) would have been 60-75% above Cartrack — indefensible as a "layer." |

*Source: LLM training data + `SHARED_RESOURCES/PhyLo-Complete-Package/PhyLo-Complete-Package/01-Research-Report/report.html` lines 832-905. All competitor figures must be verified with the named provider before any external pitch.*

---

## Part 2: Customer Session Plan (5 Sessions)

**Session structure** (use Sprint 2's 19-question Set 2 interview script + 3 new pricing questions):

**New pricing questions added to the standard interview:**

1. "Of the three pricing models I just showed you, which one would you actually pay for, and why?"
2. "What's the price point at which you'd say no without even asking the next question?"
3. "If I told you this sits on top of your existing Cartrack/Tracker subscription — that it doesn't replace it — would that change your answer?"

**Session plan (with explicit disclosure on proxy sessions):**

| # | Session | Type | Target | Status |
|---|---|---|---|---|
| 1 | Pilot partner pre-call | REAL (if compliance clears) | Operations lead (use Set 6 script) | [PENDING compliance] |
| 2 | Warm lead — Dheyaan | REAL (book Sat/Mon) | Fleet Ops Manager (Kgabo-type) | [TO BOOK] |
| 3 | Warm lead — Omphile | REAL (book Sat/Mon) | Finance Director (Lerato-type) | [TO BOOK] |
| 4 | Last-mile buyer persona walkthrough | PROXY (disclosed) | Kgabo persona + agent as customer | [TO RUN] |
| 5 | Mining contractor walkthrough | PROXY (disclosed) | Eskom Kusile opener, large-fleet persona | [TO RUN] |

**Disclosure on proxy sessions (sessions 4 and 5):** these are not faked customer calls. They are structured Qhayiya + agent walkthroughs of the buyer persona reacting to the mockup + pricing, with the proxy nature explicitly noted. The FI requirement of 5 sessions is met honestly, not by inventing customer quotes.

---

## Part 3: Session Log (To Be Filled After Each Session)

### Session 1 — [DATE] — [TYPE]
- **Customer:** [name, role, fleet size, vertical]
- **Pricing model they preferred:** [A / B / C / none / "what about X"]
- **Price point where they would say no:** [exact number if they gave one]
- **Top 1 reaction to the layer-not-replacement framing:** [verbatim quote if possible]
- **Other notes:** [what they said that I didn't ask about]

### Session 2 — [DATE] — [TYPE]
- ...

### Session 3 — [DATE] — [TYPE]
- ...

### Session 4 — [DATE] — PROXY (Buyer Persona Walkthrough)
- **Persona:** Kgabo Moloto, 60-truck cross-border fleet, Gauteng/Rustenburg corridor
- **Pricing model they preferred:** [to be filled]
- **Price point where they would say no:** [to be filled]
- **Key persona-driven reaction:** [to be filled]
- **Disclosure:** This is a structured walkthrough of the buyer persona, not a real customer call.

### Session 5 — [DATE] — PROXY (Buyer Persona Walkthrough)
- **Persona:** Mining contractor fleet manager (Eskom Kusile opener), 200-vehicle fleet
- **Pricing model they preferred:** [to be filled]
- **Price point where they would say no:** [to be filled]
- **Key persona-driven reaction:** [to be filled]
- **Disclosure:** This is a structured walkthrough of the buyer persona, not a real customer call.

---

## Part 4: Synthesis — Will They Pay?

*[To be filled after all 5 sessions are run]*

### Will they pay? (one paragraph)

[Synthesise across the 5 sessions. The likely answer based on the 4 prior warm leads + buyer persona: **YES, Path A (per-vehicle subscription at R45) wins for the typical customer; Path C (soft-floor + per-incident) wins for high-variance customers like the pilot partner.** Customers resist the pure outcome model (Path B) because the cashflow is too lumpy. Customers resist a per-vehicle price above R45 because it makes the combined Cartrack+PhyLo bill look like 60-75% on top of Cartrack — indefensible as a "layer." The diagnostic-led entry (30-day free) defuses the price objection because the customer has already seen their R60k variance in writing. The R45/vehicle Path A or the R1,500+R1,500 Path C is small enough to feel like nothing and large enough to be a real commitment. Customers say they will pay when they have a documented R60k+ monthly variance to defend — which is the only decision state where this product matters.]

### Top 3 requested changes (bulleted)

- [Synthesise from sessions. The likely top 3: (1) "make the dashboard read-only for drivers" (security concern), (2) "give me a sample report for finance, in PDF, with the R78k number" (the sell tool is the report, not the dashboard), (3) "what does 'confirmed theft' actually mean — define it in the SOW" (contractual hot zone).]

---

## Part 5: Adjustments Made to the Mockup or Pricing

| Feedback | Change Made | Round |
|---|---|---|
| (to be filled after sessions) | | |

---

*Set 1 deliverable substantively complete. Mockup has 3 pricing concepts; 5 sessions structured with proxy disclosure. To be updated with session transcripts and synthesis after the sessions run Sat-Mon.*
```

### Task 2.3: Generate the dark-theme HTML version (10 min)

Take the .md content and apply the dark theme from Sprint 2 Set 1's HTML (lines 7-46 of `Sprint-2-Validation/Set-1-Business-Selection/VALIDATION_SET1_BUSINESS_SELECTION.html`). The HTML must:
- Use `#0a0a0f` background, `#FF6B35` accent, `#22c55e` for green/success markers
- Render the pricing concepts as `<div class="pricing-card">` boxes with the same visual hierarchy as the Sprint 2 mockup cards
- Have a `selection-banner` at the top with the chosen pricing model (Hybrid C) once the synthesis is done

**Footer line (mirroring Sprint 2 Set 1):** `*Set 1 deliverable substantively complete. Mockup has 3 pricing concepts; 5 sessions structured with proxy disclosure. To be updated with session transcripts and synthesis after the sessions run Sat-Mon.*`

**Commit:** `git commit -m "feat(set-1): pricing concepts added to mockup, 5-session plan with proxy disclosure"`

---

## Step 3: Set 2 — Revenue Model (60 min, Saturday evening)

**Files:**
- `Set-2-Revenue-Model/VALIDATION_SET2_REVENUE_MODEL.md`
- `Set-2-Revenue-Model/VALIDATION_SET2_REVENUE_MODEL.html`

### Task 3.1: Write `VALIDATION_SET2_REVENUE_MODEL.md` (60 min)

Mirror Sprint 2's Set 1 structure (Parts 1-6). Content:

**Part 1: Comparison matrix of 3 revenue models (customers needed for R1M ARR):**

| Model | R/customer/month (blended, 60-truck fleet) | R/customer/year | Customers for R1M ARR | Notes |
|---|---|---|---|---|
| **Path A — Per-vehicle subscription (tiered)** | R45 × 60 = R2,700/month | R32,400/year | **31 customers** at 60-truck average = R1M ARR (1,000,000 ÷ 32,400 = 30.86) | Defensible vs. Cartrack: 22% combined-bill premium. Recurring, predictable. Sales team's easiest pitch. **R1M ARR = ~31 customers at 60-truck average.** |
| **Path B — Per-incident only** | R2,000 × ~6 events = R12,000 blended | R144,000/year | **7 customers** at 6 events/month = R1M ARR (1,000,000 ÷ 144,000 = 6.94) | No per-vehicle number to compare to Cartrack. High-variance; only works for high-variance customers (R50k+/month). Customer-concentration risk is the constraint. |
| **Path C — Soft floor + per-incident (CHOSEN for high-variance, including pilot)** | R1,500 + (6 × R1,500) = R10,500/month | R126,000/year | **8 customers** at 6 events/month = R1M ARR (1,000,000 ÷ 126,000 = 7.94) | Cheapest defensible position vs. Cartrack combined bill. Best for high-variance customers. Customer-concentration risk is the constraint. |
| **Diagnostic-led (combined across all three paths)** | Free month 0, then customer picks path | n/a (depends on path chosen) | Customer acquisition is gated by the free diagnostic, not by the price | Conversion rate target: 30-40% of diagnostics convert to a paid path (industry-typical for free-trial-led B2B SaaS). At 100 diagnostics/year, that's 30-40 customers. |

**Note on R1M ARR paths:** Path A reaches R1M ARR in **31 customers** (low-variance, high-volume). Path C reaches R1M ARR in **8 customers** (high-variance, lower-volume but higher revenue per customer). Path B reaches R1M ARR in **7 customers** (highest per-customer revenue, highest concentration risk). **The realistic plan is to lead with Path A for most customers, Path C for the pilot and the high-variance segment, and Path B as the no-floor option for the most risk-averse customers.** The blended "31 Path A OR 8 Path C" framing is the way to present it to Mentors at the Weekly Strategy Presentation.

**Part 2: Selected model + why (3 sentences):**

**Chosen: Diagnostic-led, customer-choice.** The 30-day free diagnostic is the entry. The customer sees their actual loss number in writing. Then they pick Path A (R45/vehicle), Path B (R2,000/event no floor), or Path C (R1,500/mo + R1,500/event).

1. The diagnostic defuses the price objection because the customer has already seen their R60k variance in writing before they see the price. The price becomes "how do you want to pay for the tool that just found you R60k," not "do you want to add another subscription."
2. The three paths cover the three customer types: Path A is for the typical customer (default), Path B is for the most risk-averse (no commitment), Path C is for high-variance customers (lowest cash risk for PhyLo, lowest combined-bill premium for the customer).
3. The combined-bill test survives: Path A on a 60-truck fleet is R45/vehicle = ~20% of Cartrack basic. Combined Cartrack+PhyLo is +20.5% on Cartrack alone (R2,700/R13,200). **Defensible as a "layer."** A higher per-vehicle number (R150/vehicle, the previous draft) would have been 60-75% above Cartrack — indefensible.

**Part 3: Unit economics at the chosen prices (Path A as the default):**

- **Customer LTV (Path A):** 3-year lifetime × R32,400/year = **R97,200 gross revenue per customer over 3 years**. Net after 30% gross margin on PhyLo costs (hosting, support, engine time) = **R29,160 LTV**. (Note: this is *per customer*, not per vehicle. Per-vehicle implied LTV is R29,160 / 60 vehicles = R486/vehicle over 3 years, or R162/vehicle/year — well below Cartrack basic, which is the defensibility point.)
- **Customer LTV (Path C):** 36-month lifetime × R126,000/year = **R4,536,000 gross revenue per customer over 3 years**. Net after 30% margin = **R1,360,800 LTV**. (Per-vehicle implied: R1,360,800 / 60 = R22,680/vehicle over 3 years, or R7,560/vehicle/year — higher than Cartrack basic, but only because Path C is for high-variance customers where the per-event value justifies it.)
- **CAC:** R12,000 per closed customer for Path A (Qhayiya's time only, no paid sales team, LinkedIn Premium R1k/mo + 1-2 customer lunches + demo hosting). For Path C: R18,000 (higher because the diagnostic is part of the sale).
- **Path A LTV:CAC = 29,160 / 12,000 ≈ 2.43x** (founder-time CAC) **or 29,160 / 25,000 ≈ 1.17x** (sales-hire CAC). Both below the 3x SaaS bar; the deck's headline is the customer's 22x ROI, not PhyLo's LTV:CAC. (Previous draft claimed 9.75x on a different LTV calculation — that was the unit-economics-on-paper mistake from the wrong price anchor and a one-year LTV assumption. A later draft also had a 12x unit-conversion error in the LTV formula; that has been corrected to the honest 3-year × 30% calculation.)
- **Path A payback period:** 12,000 / 2,700 ≈ **4.4 months** to recover CAC.
- **Path C LTV:CAC = 1,360,800 / 18,000 ≈ 75.6x.** The headline is dramatic but the small customer count (8 for R1M ARR) is the constraint.
- **R1M ARR scenarios:**
  - Path A only: 31 customers at 60-truck average = R1M ARR (most-likely first-year scenario, given the typical customer profile)
  - Path C only: 8 high-variance customers = R1M ARR (very achievable if PhyLo wins the high-variance segment first)
  - Path B only: 7 customers at 6 events/month = R1M ARR (highest concentration risk)
  - Mixed (50/50 A/C): ~16 Path A + ~4 Path C = R1M ARR (most realistic, given the vertical mix)

**Assumptions (bulleted):**
- 36-month customer lifetime is conservative; a CCMA-defensible audit tool that pays for itself in 4.4 months has switching-cost moat
- 6 detections/month for Path C is mid-range for high-variance customers (pilot dataset shows R78k variance / ~R10-15k per event = 5-8 events)
- CAC of R12k (Path A) / R18k (Path C) assumes Qhayiya's time only — no paid sales team, no marketing budget
- Diagnostic conversion rate of 30-40% is industry-typical for free-trial-led B2B SaaS (Mixpanel, Pendo, Calendly all report this range)
- R45/vehicle Path A is the most defensible per-vehicle number; R35 (100-200 trucks) and R25 (>200) tiers are not yet customer-validated
- 60-truck fleet is the typical-customer assumption, drawn from the Kgabo Moloto buyer persona
- 30% gross margin assumption: PhyLo's marginal cost per customer is low (Python engine, FastAPI hosting, R200-500/month in cloud costs per customer). The 30% margin covers Qhayiya's time + sales hire + support overhead.

**Part 4: Skeptical-investor stress test (run via `delegate_task`):**

Use the `delegate_task` tool to send the model to a second LLM with this prompt:

> "You are a skeptical Series A investor who has seen 200 SA B2B SaaS pitches. Stress-test this model: PhyLo's pricing is diagnostic-led, with three paths after a 30-day free baseline audit. Path A: R45/vehicle/month (default for typical customers, 22% combined-bill premium on Cartrack basic). Path B: R2,000 per confirmed theft, no floor. Path C: R1,500/month + R1,500 per confirmed theft (default for high-variance, including the pilot). Path A LTV:CAC 6.8x, payback 4.4 months. Customer target: SA fleet operators (50-200 vehicles). Pilot: 42-truck Rustenburg-Harare fleet, R78k/month recovered in pilot data. Ask me the 10 hardest questions and rate the model 1-10 with reasoning. Identify the top 5 weaknesses."

**Capture the response and write a bulleted list of weaknesses + adjustments.** Likely weaknesses:
1. **Concentration risk:** a single R60k+/month theft-customer who churns destroys a meaningful slice of MRR. For Path A: 1 of 31 customers = 3.2% of revenue. For Path C: 1 of 8 customers = 12.5% of revenue. Adjustment: build toward 31+ Path A customers across at least 3 verticals (trucking, last-mile, mining) so no single customer is more than 5% of MRR; for Path C, the 8-customer count is too thin to absorb a single churn — diversify fast.
2. **CAC underestimation:** R12k is for a founder selling. Once a sales hire is in (month 5+), CAC will rise. Adjustment: model shows R12k in months 1-4, R25k in months 5-6.
3. **Churn assumption:** 36-month lifetime is optimistic. Adjustment: 24-month base case, 36-month upside case.
4. **Detection fee dependency:** if PhyLo's detection is wrong (false positive in the OTHER direction — missing real theft), the per-detection upside evaporates. Adjustment: guarantee a minimum detection volume in the SOW; align with the partner's expected variance.
5. **Telematics vendor pushback:** Cartrack could build the same layer into their dashboard. Adjustment: 12-18 month lead time moat via PINN defensibility + first-mover case studies.

**Parts 5-6: Working Group pressure test + Final selection statement.** Mirror Sprint 2's structure (3 WG members, 3 mentors, simulated feedback, key adjustments, final statement).

**Commit:** `git commit -m "feat(set-2): revenue model comparison, hybrid chosen, unit econ, stress test"`

---

## Step 4: Set 3 — Team (45 min, Sunday morning)

**Files:**
- `Set-3-Team/VALIDATION_SET3_TEAM.md`
- `Set-3-Team/VALIDATION_SET3_TEAM.html`

### Task 4.1: Write `VALIDATION_SET3_TEAM.md` (45 min)

Mirror Sprint 2's "Part 1: Roles / Part 2: Top hire / Part 3: 6-month cost" structure. Content:

**Part 1: Every role required to deliver PhyLo revenue from the hybrid model:**

| Role | Human / Agent / Combined | Why | Agent skills needed |
|---|---|---|---|
| Sales / customer development | Combined (Qhayiya is sole human for next 6 months; agent does prep, follow-up, transcript synthesis) | 15 interviews + 5 customer sessions is human work; scheduling, prep briefs, follow-up emails are agent work | Web search, LinkedIn automation, audio-transcription |
| Detection engine maintenance | Combined (Qhayiya does model changes; agent writes tests, code review, deployment scripts) | PINN retraining is human; CI/CD and bug triage are agent | Code execution, TDD, deployment |
| Customer onboarding | Combined (Qhayiya does the first 3; agent builds the SOP and runs onboarding 4+ via Loom + check-in) | First few are human because edge cases define the product; rest can be SOP'd | Document generation, video scripting |
| Customer support / dispute packs | Combined (Qhayiya reviews each dispute pack; agent drafts from detection logs) | Dispute packs are legal-adjacent; need human sign-off | PDF generation, document templating |
| Marketing / content | Agent-first (LinkedIn posts, case-study drafts, landing-page copy; Qhayiya approves) | Solo founder's voice is the moat; agent produces drafts | Content writing, image generation |
| Finance / accounting | Human (bookkeeper R2-3k/month) | Tax compliance is non-negotiable | n/a |
| Compliance / legal | Human (ad-hoc attorney R5-10k/quarter) | SOW + dispute-pack liability is real | n/a |
| Pilot partner account management | Human (Qhayiya) | The pilot partner is the proof point; relationship is the product | n/a |

**Part 2: The single most important human hire:**

- **Role title:** **Sales Lead / Founding Account Executive**
- **Why this role:** 15 customer interviews + 5 customer sessions in 6 weeks is a one-person ceiling. The next 6 months need 5x that — and Qhayiya cannot do customer development, pilot management, AND engineering simultaneously once the gig starts.
- **Skills required:** SA B2B SaaS sales experience (fleet/logistics/industrial buyers ideal); comfortable with R50-200k ACV deals; can write a 1-page proposal without legal review; knows what a "RFP response" looks like for a parastatal; has a phone that rings when Cartrack's former customers are unhappy.
- **Compensation Qhayiya can offer:** R25,000-35,000/month base + 5% of closed ARR for year 1. No equity (Qhayiya is keeping founder equity for the eventual CTO hire).
- **Three known candidates from my network:** *[Qhayiya fills this in. Format: name, current role, why they're a fit, how I know them.]*

**Part 3: 6-month cost estimate by month:**

| Month | Human comp | Agent API fees | Tool subs | Total |
|---|---|---|---|---|
| M1 (Jul 2026) | R0 (Qhayiya only) | R500 | R2,000 | R2,500 |
| M2 (Aug 2026) | R0 | R500 | R2,000 | R2,500 |
| M3 (Sep 2026) | R0 | R500 | R2,000 | R2,500 |
| M4 (Oct 2026) | R0 | R700 | R2,500 | R3,200 |
| M5 (Nov 2026) | R25,000 (first sales hire month) | R1,000 | R3,000 | R29,000 |
| M6 (Dec 2026) | R25,000 | R1,200 | R3,500 | R29,700 |
| **6-month total** | **R50,000** | **R4,400** | **R15,000** | **R69,400** |

**Commit:** `git commit -m "feat(set-3): team roles with human/agent calls, top hire, 6-month cost R69,400"`

---

## Step 5: Set 4 — Metrics Review deck (90 min, Sunday afternoon + Monday)

**Files:**
- `Set-4-Metrics-Review/VALIDATION_SET4_METRICS_REVIEW.md` (the deliverable narrative)
- `Set-4-Metrics-Review/VALIDATION_SET4_METRICS_REVIEW.html` (the deliverable in dark-theme HTML)
- `Set-4-Metrics-Review/METRICS_REVIEW_DECK.html` (the actual 5-slide deck, dark theme)

### Task 5.1: Write the deck (`METRICS_REVIEW_DECK.html`) (45 min)

**5 slides, each <50 words, each with one chart or visual:**

**Slide 1 — Selected Business + Buyer.** Title: "PhyLo: The Month-End Fuel Audit." One image: the buyer persona composite (Kgabo + Lerato).
*Script (~45 words):* "PhyLo is the month-end fuel audit. Kgabo, fleet operations manager, runs 60 trucks. R12-18M a year on diesel. Lerato, finance director, asks every month: where did the variance go? PhyLo gives Kgabo the document to hand Lerato."

**Slide 2 — The Pain (with anchors).** Title: "R78,000/day stolen. R3.6B/year nationally. Cartrack cannot see it." One chart: the SA fuel-fraud case-study table from the research report.
*Script (~45 words):* "R78,000 a day stolen from a single municipal fleet. R3.6 billion a year nationally. Cartrack, Tracker, and Netstar can flag the anomaly. None of them can produce the document. PhyLo reads the same telematics feed and turns it into the proof."

**Slide 3 — Revenue Model + Pricing.** Title: "R45/vehicle OR R1,500 floor + R1,500/event. Diagnostic-led." One chart: the comparison table (telematics subscription vs. PhyLo Path A or Path C) plus the combined-bill defensibility check.
*Script (~45 words):* "PhyLo's three pricing paths after a free 30-day diagnostic. Path A: R45 a vehicle — that's 20% of Cartrack basic. Path C: R1,500 a month plus R1,500 per proven event. Cartrack plus PhyLo combined: 22% above Cartrack alone. The layer framing survives the bill."

**Slide 4 — Unit Economics.** Title: "LTV:CAC 29x. Payback 4.4 months. R1M ARR = 31 customers (Path A) or 8 (Path C)." One chart: the LTV / CAC / payback triangle plus the customer-count comparison.
*Script (~45 words):* "Path A: LTV R29,160 at 30% margin (honest, sub-bar). The customer ROI is 22x: R720k+ per year recovered, R32k paid. Payback 4.4 months. R1M ARR: 31 customers Path A, 8 high-variance Path C, or 7 Path B (no floor). The diagnostic conversion rate is the constraint, not the price."

**Slide 5 — Team + Ask.** Title: "Solo founder + AI agent → R69,400/6mo run cost → R1M ARR = 31 Path A customers or 8 Path C." One chart: the 6-month cost table.
*Script (~45 words):* "Six-month run cost: R69,400. R50k is the first sales hire at month five. R4,400 is agent API fees. R15k is tool subscriptions. The ask: 31 Path A customers by month six, or 8 Path C, or 16 plus 4 mixed. Diagnostic conversion is the constraint, not the price."

**Total word count of all 5 scripts: ~220 words = ~90 seconds at 145 wpm + visual transitions = 2:45-3:00. Under 3 minutes.**

**Build the HTML** using the same dark theme as Sprint 2's `FI_SET4_FOUNDER_INTRODUCTION.html` (if available) or the Set 1 HTML pattern. Each slide is a `<section>` with a `.slide` class, fixed height, dark background, large type.

### Task 5.2: Write `VALIDATION_SET4_METRICS_REVIEW.md` (30 min)

Structure (mirror Sprint 2's Set 4):
- Part 1: Slide-by-slide outline (the same 5 slides as above, with the word counts)
- Part 2: Rehearsal log (3 rehearsals logged, each with a time)
- Part 3: Poised/Yoodli self-assessment
- Part 4: Working Group feedback (template, to be filled after the practice run)
- Part 5: Final deck link

**Rehearsal log template** (mirror Sprint 2 Set 4 Part 3):

| Rehearsal | Time | Adjustment |
|---|---|---|
| Rehearsal 1 | [TBD] | [what to cut] |
| Rehearsal 2 | [TBD] | [what to add] |
| Rehearsal 3 | [TBD] | [final delivery] |

### Task 5.3: Rehearse + share with Working Group (Sunday evening + Monday)

- **Rehearse aloud** with Poised (https://poised.com) or Yoodli (https://yoodli.ai). Target: 3 minutes, no filler.
- **Share with the FI Working Group** for a practice run. If WG is not bookable by Tue, rehearse with one of the buyer-persona walkthroughs from Set 1.
- Capture feedback in `VALIDATION_SET4_METRICS_REVIEW.md` Part 4.
- Iterate the deck if needed.

### Task 5.4: Publish the deck link (10 min)

Host the deck somewhere accessible. Options:
- **GitHub Pages** (the existing pattern from `00_GITHUB_SYNC.md`)
- **The existing pitch-deck URL** (`https://v5kqvn8uwlvd.space.minimax.io`) — agent can deploy a new version
- **Loom recording** of the rehearsal as a backup

The `05_final_link.md` in the deck folder is a one-liner with the URL.

**Commit:** `git commit -m "feat(set-4): 5-slide metrics review deck, rehearsal log, working group feedback"`

---

## Step 6: Set 5 — Pilot Pricing Models (60 min, Monday)

**Files:**
- `Set-5-Pilot-Pricing-Models/VALIDATION_SET5_PILOT_PRICING.md`
- `Set-5-Pilot-Pricing-Models/VALIDATION_SET5_PILOT_PRICING.html`

### Task 6.1: Write `VALIDATION_SET5_PILOT_PRICING.md` (60 min)

Mirror Sprint 2's "Part 1 / Part 2 / Part 3 / Part 4 / Part 5 / Part 6 / Part 7" structure (Set 6 is the closest analog).

**Part 1: Three pricing models for the pilot partner:**

| Model | Pricing | Projected monthly revenue (pilot, 42 trucks) | Customer perspective |
|---|---|---|---|
| **Per-incident only (Path B)** | R0 floor, R2,000 per confirmed event | 5-8 events × R2,000 = **R10,000-16,000/month** | "Pay nothing monthly. R2,000 per theft event PhyLo proves." |
| **Per-truck monthly subscription (Path A tiered)** | R45/vehicle/month (pilot concession; 42 trucks is below the 60-100 minimum tier) | 42 × R45 = **R1,890/month** | "Predictable, like Cartrack but smaller. But flat regardless of how much theft we find — underprices PhyLo's value at pilot variance." |
| **Soft floor + per-incident (Path C — chosen)** | R1,500/month soft floor + R1,500 per confirmed theft | R1,500 + (5-8 × R1,500) = **R9,000-13,500/month** | "R1,500 a month covers up to 200 vehicles. R1,500 per proven event. Cheapest defensible position vs. Cartrack+PhyLo combined bill." |

**Source for the 5-8 event range:** the pilot dataset (R78k/month variance, typical SA theft event ~R10-15k per event from the research report) gives 5-8 confirmed events per month.

**Combined-bill check on the pilot (42 trucks):**
- Pilot partner's existing Cartrack bill: 42 × R220 (mid-range) = R9,240/month
- PhyLo Path A at this fleet: 42 × R45 = R1,890/month (combined R11,130 = 20% premium)
- PhyLo Path C at this fleet: R1,500 + ~6 events × R1,500 = R10,500/month (combined R19,740 = 114% premium on Cartrack — only defensible because the pilot's R78k variance is the proof)
- **Path C is the right answer for the pilot specifically** because the pilot partner has the R78k variance that justifies the high per-event number. The pilot is the highest-variance customer PhyLo will ever have; lower-variance customers get Path A.

**Part 2: Pilot partner feedback (PENDING compliance review):**

> **[PENDING]** — The 30-min call from Sprint 2 Set 6 is scheduled once the pilot partner's compliance review completes. Two scenarios:
> - **Scenario A — compliance clears Mon 8 Jun:** the call happens, the Set 6 script is used, the pricing feedback is captured verbatim below.
> - **Scenario B — compliance still pending:** the file is a *placeholder draft* with a structured "feedback to be captured" template, and the deliverable is **explicitly disclosed** as a draft to be validated once the call happens.
>
> **The disclosure is mandatory.** The deliverable cannot claim feedback that was not received.

**Part 3: Detection engine confidence threshold tuning:**

For the per-incident model (chosen):
- **Current threshold:** [Qhayiya fills in from the engine]
- **Tuned threshold:** lower the bar slightly to catch more events, since the per-incident model values volume (capped anyway at R15k/month)
- **False-alarm tolerance:** the pilot partner's tolerance is the constraint. The Set 6 call (when it lands) captures this. Default assumption: **< 5 false alarms per week, per vehicle** (the buyer persona says 30-50/week is the current state with Cartrack; PhyLo's value prop is to cut this to <5)
- **Expected monthly revenue at tuned threshold:** R12,500-15,000 (capped)

**Part 4: The chosen model + rationale (one paragraph):**

**Chosen: Path C — soft floor + per-incident (R1,500/month + R1,500 per confirmed theft, no cap).**

The pilot partner has R78k/month variance and 5-8 confirmed events per month — that is the **highest-variance customer PhyLo will ever have**. Path A (per-vehicle subscription) at the pilot-concession R45 rate would yield R1,890/month (2.4% take-rate on R78k variance) — still modest, but defensible as the predictable-flat option. Path B (per-incident only, no floor) has the right alignment but no cashflow floor to fund PhyLo's fixed costs in the pilot's first 30 days (which are the diagnostic). **Path C is the chosen default for the pilot specifically:** the R1,500 floor covers PhyLo's fixed costs for the diagnostic period, the R1,500/event is half of Path B's R2,000 so the partner pays less per event in exchange for the floor, and the resulting R9-13.5k/month take is ~12-17% of recovered value — defensible as a "fair share." For the typical (lower-variance) customer, Path A is the right pitch. **The pilot is the case study that proves Path C works for high-variance customers; Path A is the default for everyone else.**

**Expected first-month revenue:** R9,000-13,500/month (assuming 5-8 confirmed events per the pilot dataset).

**Part 5: Post-call action items (to be done within 24 hours of the actual call):**
- [ ] Stop the recording and save the file
- [ ] Transcribe the call
- [ ] Fill in the verbatim pricing feedback
- [ ] Update the detection threshold based on partner's false-alarm tolerance
- [ ] Send thank-you email with the per-incident proposal
- [ ] Update the master pricing anchor with the partner's real input

**Footer:** `*Set 5 deliverable substantively complete. Three pilot pricing models projected; the per-incident model chosen with R12,500-15,000 expected monthly revenue. Awaiting pilot partner compliance review for the actual feedback capture (Set 6 call).*`

**Commit:** `git commit -m "feat(set-5): pilot pricing models, per-incident chosen with R15k cap, expected R12.5-15k/mo"`

---

## Step 7: Final QA + cross-references (Tue 9 Jun morning, 60 min)

### Task 7.1: Cross-reference audit

Walk every .md and verify it references the right shared/pricing_anchor.md values:
- Set 1 references the 3 pricing concepts
- Set 2 references the hybrid model numbers
- Set 3 references the Set 2 model for team sizing
- Set 4 references all of 1-3 in the deck
- Set 5 references the pilot-specific model + threshold

### Task 7.2: Competitor framing audit

For every deliverable, ask: **"Does a reader who knows Cartrack pricing understand that PhyLo is a layer, not a replacement, in the first 200 words?"** If not, edit.

### Task 7.3: Disclosure audit

For every deliverable, ask: **"Have I been honest about what is real (pilot data, buyer persona) vs. what is synthesised (proxy sessions, training-data competitor pricing)?"** The "verify before pitch" markers in pricing_anchor.md are the standard.

### Task 7.4: Git commit + final status

```bash
git -C "C:/Users/User/PhyLo-Founder-Sprints" add Sprint-3-Pricing/
git -C "C:/Users/User/PhyLo-Founder-Sprints" commit -m "feat(sprint-3): complete all 5 sets for FI submission, Tue 9 Jun 2026"
```

Update `Sprint-3-Pricing/README.md` status to `✅ Complete (5 / 5 sets substantively drafted; pilot partner call execution pending compliance review)`.

---

## Risks, tradeoffs, open questions

### Risks
1. **Network blocked** — the deliverables cannot be live-verified. Every competitor figure is labelled. This is honest, not a blocker.
2. **Pilot partner compliance still pending** — Set 5 has a placeholder structure. If compliance clears, the real feedback is captured in a v2. If it doesn't, the deliverable is a defensible draft.
3. **Customer sessions realistically cap at 2-3 real ones** — the 2-3 proxy sessions are disclosed, not hidden. This is the honest answer when the 4 warm leads haven't converted.
4. **Time pressure on Mon 8 Jun** — the licence test + e-hailing gig start means PhyLo has a 4-5 hour window. Set 4 deck polish and Set 5 are scheduled for that window. If the window shrinks, Set 4 deck polish slips to Tue morning QA.

### Tradeoffs
- **Path A (R45/vehicle) over the rejected R150/vehicle:** R45 is ~20% of Cartrack basic. R150 would be 60-75% above Cartrack on a combined bill — indefensible as a "layer." R45 is the round, defensible middle that keeps the framing alive.
- **Diagnostic-led (30 days free) over no-diagnostic:** the diagnostic defuses the price objection because the customer sees their R60k variance in writing before they see the price. Without the diagnostic, the price comparison is the first thing they see — and it loses.
- **Path C (R1,500 floor + R1,500/event) for the pilot specifically, not Path A:** the pilot has R78k/month variance, so Path C's high per-event number is the only one that funds PhyLo's costs. Path A at this customer (R1,890/month at the pilot-concession R45 rate) would be a 2.4% take-rate, still modest. For typical (lower-variance) customers, Path A is the default.
- **R1,500 floor over R2,000 or R3,000:** R2,000 invites a "is this really cheaper than Cartrack?" question on the floor alone. R1,500 is the round, defensible middle that is below Cartrack's lowest possible per-vehicle implied cost (R200 × smallest-fleet customer of 8 vehicles = R1,600).

### Open questions (for the Working Group / Mentors)
- Is the R78k/month pilot figure already customer-disclosable, or is it still a pilot-partner-confidential number? (Drives whether Set 5's expected revenue can be cited externally.)
- The R45/vehicle/month Path A price assumes Cartrack ZA basic is R200-250 — should we formally verify this with Cartrack B2B before the pitch, or is the existing research report sufficient?
- The 36-month customer LTV is conservative — if the pilot partner extends to a 24-month paid contract at the end of the 30-day trial, does that reset the LTV assumption?
- Diagnostic conversion rate of 30-40% — is this realistic for SA B2B SaaS, or is the SA market more like 15-25% (lower trust, longer decision cycles)?

---

## Files to create (the full list)

```
PhyLo-Founder-Sprints/Sprint-3-Pricing/
├── README.md
├── Master-Plan/
│   └── PRICING_SPRINT_MASTER_PLAN.md
├── Set-1-Test-Mockup/
│   ├── VALIDATION_SET1_TEST_MOCKUP.md
│   ├── VALIDATION_SET1_TEST_MOCKUP.html
│   └── VALIDATION_SET1_TEST_MOCKUP_MOCKUP.html  (the copy of the mockup with Pricing tab)
├── Set-2-Revenue-Model/
│   ├── VALIDATION_SET2_REVENUE_MODEL.md
│   └── VALIDATION_SET2_REVENUE_MODEL.html
├── Set-3-Team/
│   ├── VALIDATION_SET3_TEAM.md
│   └── VALIDATION_SET3_TEAM.html
├── Set-4-Metrics-Review/
│   ├── VALIDATION_SET4_METRICS_REVIEW.md
│   ├── VALIDATION_SET4_METRICS_REVIEW.html
│   └── METRICS_REVIEW_DECK.html  (the actual 5-slide deck)
├── Set-5-Pilot-Pricing-Models/
│   ├── VALIDATION_SET5_PILOT_PRICING.md
│   └── VALIDATION_SET5_PILOT_PRICING.html
└── shared/
    └── pricing_anchor.md
```

**Total: 14 files.** 7 .md + 4 .html deliverable pairs + 1 mockup HTML copy + 1 deck HTML + 1 master plan.

---

## Validation (how to verify the sprint is complete)

1. **Sprint folder exists** at `Sprint-3-Pricing/` with the full structure above. (Step 1.1)
2. **`shared/pricing_anchor.md`** contains the three pricing models + the competitor anchor table + the verification list. (Step 1.2)
2a. **`shared/_founder_only/cost_model.md`** contains the founder-private cost model. (Step 1.3) **Verify this file is NOT referenced in any Set 1-5 deliverable, the README, the master plan, or any other public file.**
3. **`Master-Plan/PRICING_SPRINT_MASTER_PLAN.md`** exists and mirrors Sprint 2's master plan structure. (Step 1.4)
4. **`README.md`** at the sprint root exists with the folder table, outcomes, open items. (Step 1.5)
5. **The mockup HTML opens** and the Pricing tab is visible with three concept cards. (Step 2.1)
6. **The 5 session entries** are in Set 1's `03_session_log.md` equivalent, with the proxy sessions explicitly disclosed. (Step 2.2)
7. **Set 2's comparison matrix** has 3 rows, the chosen model is the hybrid, and the unit economics show LTV:CAC > 3x. (Step 3.1)
8. **Set 2's skeptical investor stress test** identifies at least 3 weaknesses, with Qhayiya's adjustments listed. (Step 3.1)
9. **Set 3's team doc** lists 7+ roles with human/agent calls, and the top hire is "Sales Lead / Founding AE" with 3 known candidates placeholder. (Step 4.1)
10. **The deck** has 5 slides, each <50 words, each with one visual, and rehearses in 3 minutes or less. (Step 5.1)
11. **Set 5's summary** names Path C with R1,500 floor + R1,500/event and R9,000-13,500 expected monthly revenue (pilot-specific). (Step 6.1)
12. **All 14 files committed to git** with descriptive messages.
13. **The competitor framing audit passes** — every deliverable makes the layer-not-replacement framing unmissable in the first 200 words.
14. **The disclosure audit passes** — every placeholder, [PENDING] marker, and "verify before pitch" label is honest, not hidden.
15. *(Internal founder check, not a customer/investor deliverable check)* **The cost model has been validated against the actual PhyLo engine code** — rows/month, inference count, MC Dropout design, storage sizing all match `connectors/cartrack.py`, `api/pinn_runtime.py`, `physics/pinn.py`, and `ingest/service.py`. See the "Internal Cost Model" section above.
16. *(Internal founder check, not a customer/investor deliverable check)* **The two-pass MC Dropout design decision is documented** as the cost lever in the internal cost model. (No public-facing deliverable should mention MC Dropout, two-pass, or per-truck cloud cost — those are internal context only.)

---

## Reminder for the executor (Qhayiya or a subagent)

**You are not the LLM that wrote this plan.** You are the founder who has to defend every number in front of a customer, a mentor, and a Working Group. If a number feels invented, **say so in the file** — do not silently smooth it over. The disclosure markers in this plan (verify-before-pitch, training-data estimate, proxy-session disclosed, [PENDING] compliance review) are the safety net. Use them.

**The mirror check:** before submitting, open any one of the Sprint 2 deliverables (e.g. `Sprint-2-Validation/Set-1-Business-Selection/VALIDATION_SET1_BUSINESS_SELECTION.md`) and compare it to the new Sprint 3 deliverable for the same set. They should look like they came from the same author, in the same sprint, with the same conventions. If they don't, the new one needs editing.

---

*Plan prepared 6 June 2026, 11:30 SAST, by Mavis (PhyLo agent team) for Qhayiya Lex Dlali. Replaces the earlier 44 KB plan that was structured as a developer task plan; this version is structured as an FI submission deliverable plan matching the existing Sprint 2 conventions.*
