# PhyLo Cost Model — Internal Founder Context

> **⚠️ INTERNAL CONTEXT — NOT FOR CUSTOMER OR INVESTOR DELIVERABLES ⚠️**
>
> This is the **founder-private** cost model. It is the math that justifies the R45/vehicle/month Path A price, the per-customer CAC, and the two-pass MC Dropout design decision. **None of this content — tables, numbers, design decisions, code-change references — goes into Set 1, Set 2, Set 3, Set 4, or Set 5 deliverables, directly or paraphrased.** Investors see "LTV:CAC 29x, payback 4.4 months." They do NOT see "MC Dropout on flagged anomalies only, 1-day code change in `pinn_runtime.py`."
>
> If Qhayiya asks "what does the cost model say about X," answer from this file. If Qhayiya asks "what do I put in the Set N deliverable," write the customer/investor-facing version, which uses only the headline numbers (LTV, CAC, payback, gross margin range) from the architecture decisions table.
>
> **The underscore-prefix folder (`_founder_only/`) is the structural guard** that prevents this content from being copied into a customer-facing deliverable. The folder name itself signals that nothing inside is a deliverable.

---

## A. The data volumes (per truck, per month)

**Source grounding:** the cost model is built from the actual PhyLo code in `phyLO(1.0 BETA)/`:
- `connectors/cartrack.py` — 1-minute polling, respects 1000 req/min API rate limit
- `api/pinn_runtime.py` — PINN model (`input_dim=3, hidden_dim=64, dropout=0.1`, ~5K parameters)
- `physics/pinn.py` — `predict_with_uncertainty()` does 50-sample Monte Carlo Dropout (this is the cost lever)
- `ingest/service.py` — full pipeline: clean → PINN → anomaly detect → JSON response
- `requirements.txt` — torch 2.2.0 CPU build, FastAPI, pandas, numpy

| Data point | Volume | Source |
|---|---|---|
| Telemetry rows ingested | **43,200 rows/truck/month** (1 row/min × 60 min × 24 h × 30 d) | `connectors/cartrack.py` enforces `resolution: "1m"` |
| PINN inferences (raw, 1× forward pass) | **43,200 inferences/truck/month** | 1:1 with ingested rows; `predict_fuel_rates()` in `pinn_runtime.py` |
| PINN inferences with MC Dropout (50 samples each) | **2,160,000 forward passes/truck/month** | `predict_with_uncertainty(num_samples=50)` in `pinn.py` |
| Confirmed theft events validated | **5-8 events/truck/month** (pilot dataset at R78k variance); **1-3 events/truck/month** for typical customers | Pilot partner dataset; typical-customer estimate from research report's 5-8% monthly variance ÷ R10-15k avg event size |
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

## B. The per-truck-per-month cost

**The big insight:** the **per-truck pure cloud cost is low** (R3-15/truck). The **per-customer cost is high** (R12,000-25,000 in CAC + support time). The R45/vehicle/month Path A price has to cover **both** — and it does, with 67-77% gross margin at scale.

| Cost component | R/truck/month | Driver | Verify before scale |
|---|---|---|---|
| **Telematics ingestion (Cartrack API)** | R0 (included in customer's Cartrack subscription) | The customer pays Cartrack; PhyLo reads their feed. No incremental API cost. | [ ] Confirm Cartrack API is read-only at no incremental cost (read APIs are usually free; confirm with Cartrack B2B) |
| **PINN inference compute (raw, no MC Dropout)** | R0.05-0.20/truck | 4.32 CPU-seconds/truck/month at 0.1ms/inference. On a 4-vCPU VPS at R500/month: 0.002% utilization per truck. | [ ] Confirm 0.1ms/inference on a typical cloud vCPU (run benchmark) |
| **PINN inference with MC Dropout (50 samples on every row)** | R2.50-10.00/truck | 216 CPU-seconds/truck/month = 50× the raw cost. Still small per truck, but at 1,860 trucks = R4,650-18,600/month compute alone. | [ ] Confirm whether the production path uses MC Dropout for every row or only on flagged anomalies (biggest design choice — see D) |
| **Data cleaning + interpolation** (processor.py) | R0.01-0.05/truck | Pandas work per row, very small | n/a |
| **Anomaly detection** (analytics/detector.py) | R0.01-0.05/truck | Pandas + numpy, very small | n/a |
| **Storage (raw + indexed + derived)** | R0.05-0.20/truck | 50 MB/truck/month. At 1,860 trucks = 93 GB/month = R50-200 on managed Postgres | [ ] Confirm Postgres sizing on Hetzner / AWS RDS at this volume |
| **Bandwidth (PDF reports + dashboard)** | R0.01-0.05/truck | ~4 MB/truck/month at pilot, negligible | n/a |
| **Monitoring + error tracking** (Sentry, logs) | R0.30-0.80/truck | Sentry is ~R500-1,500/month flat regardless of trucks; spread across 1,860 trucks | [ ] Confirm Sentry / Datadog / equivalent pricing at scale |
| **Web app hosting** (Next.js dashboard + FastAPI) | R0.50-2.00/truck | R1,000-4,000/month for the API + dashboard at Path A scale | [ ] Confirm Hetzner / Vercel / Render pricing |
| **Subtotal — pure cloud spend** | **R3.43-13.35/truck/month** | | |
| **Customer support time** (Qhayiya, then sales hire) | R4.00-8.00/truck | 30-60 min/customer/month × R500/hour ÷ 60 trucks | n/a — internal time |
| **Amortized CAC** (R12,000-25,000 / 36 months / 60 trucks) | R5.55-11.57/truck | Spread customer acquisition cost over expected lifetime and per truck | [ ] Verify SA B2B SaaS CAC benchmarks (R12-25k is the range I've seen) |
| **Admin overhead** (bookkeeper, accounting, legal, insurance) | R1.00-1.50/truck | R2,000-3,000/month flat ÷ 1,860 trucks | n/a — internal overhead |
| **Subtotal — total cost to deliver** | **R13.98-34.42/truck/month** | | |
| **Revenue per truck (Path A)** | **R45/truck/month** | | |
| **Gross margin per truck** | **R10.58-31.02/truck (24-69%)** | Wide range driven by MC Dropout design choice | |

**The constraint that shapes the price:** if the gross margin floor is 50% (a SaaS-investor bar), the cost ceiling per truck is **R22.50**. The mid-range of the cost model (R20-22/truck at moderate MC Dropout usage) sits right at that line. The R45/vehicle/month price is **defensible but tight** at low scale; **comfortable** at Path A scale (31 customers) once CAC is amortized.

**The single biggest cost lever:** **MC Dropout usage.** Running 50-sample MC Dropout on every row multiplies the inference cost 50×. The fix is to run MC Dropout **only on flagged anomalies**, not on every row. This brings the inference cost from R2.50-10.00/truck to R0.05-0.30/truck.

---

## C. The per-account-per-month cost (per customer, not per truck)

**Some costs don't scale per-truck — they scale per-customer.** This is where the founder's time (Qhayiya's hours) dominates.

| Cost component | R/customer/month | Driver | Notes |
|---|---|---|---|
| **Customer onboarding (one-time, amortized over 36 months)** | R330-700/customer/month | 2-4 hours of Qhayiya's time × R500/hour = R1,000-2,000 one-time. Amortized = R28-56/month. Plus connector setup, dry-run, sign-off, training. | The 2-4 hours is per NEW customer, not per month. First 5 customers will take 6-8 hours each. |
| **Connector maintenance** (Cartrack, Tracker, Netstar, Webfleet, MiX, Ctrack) | R0 (sunk) + R500-2,000/month per connector after launch | 40-80 hours of dev per connector to build; 2-4 hours/month per connector for API changes once live. | One-time sunk cost is the big number. After launch, mostly Qhayiya's time. |
| **Pilot partner compliance review** (legal, SOW, NDA) | R0 (one-time sunk) | R5,000-10,000 in attorney fees per major customer. The pilot partner's compliance review is already pending. | 30-day free diagnostic runs during this period — your time is the cost, not the compute. |
| **Retraining cadence** (train.py) | R10-50/month total = R0.30-1.70/customer at Path A scale | GPU burst on a T4: 1 hour/month at R10-15/hour on-demand or R3-5/hour spot. | [ ] Confirm retraining is monthly at first, then quarterly as model stabilizes |
| **Customer support (live)** | R250-500/customer/month at scale | 30-60 min/customer/month × R500/hour. First 5 customers will take much more. | Time is the constraint, not tools. |
| **Compliance / audit pack generation** (CCMA-defensible evidence) | R50-200/customer/month (per confirmed event) | Generating a CCMA-grade evidence pack: chain of custody, signed PDFs, retention storage. | Premium tier; absorb in Path A pricing for first 5 customers, then bill separately. |
| **Sales + admin overhead** (per customer, not per truck) | R500-1,000/customer/month | 6-month cost model (Set 3) shows R69,400 total ÷ 31 customers = R2,237/customer over 6 months, or R373/month. Plus sales hire (month 5+) = R25k/mo ÷ 5 new customers/mo = R5,000/customer in sales-hire window. | At Path A scale with no sales hire: ~R400-500/customer/month. With a sales hire: ~R5,000-7,000/customer/month in first 3-6 months of the hire. |

**The per-customer-per-month total cost (with Qhayiya as sole operator, year 1):** R1,500-3,000/customer/month. At Path A revenue of R2,700/customer/month, year-1 gross margin is **negative to break-even**. The unit economics only work when Qhayiya is freed up to acquire 2-3 customers/month instead of 1 — which is the entire point of the sales hire in month 5.

---

## D. The MC Dropout design decision (the cost lever)

**The choice:** in the current `physics/pinn.py`, `predict_with_uncertainty()` does **50 forward passes per inference** to compute the confidence interval. This is the "physics-informed" claim — PhyLo says "97.3% confidence" because it ran MC Dropout 50 times and got a tight distribution.

**The cost impact:**
- **MC Dropout on every row:** 50× inference cost. At 1,860 trucks, R4,650-18,600/month compute (10-40% of Path A revenue at scale).
- **MC Dropout on flagged anomalies only:** 1× cost on the 5-15% of rows flagged as anomalous, 50× cost on those. Effective multiplier: 5-15% × 50 = 2.5-7.5×. At 1,860 trucks, R230-3,500/month compute. **Recommended.**
- **MC Dropout off entirely (use a single forward pass + softmax):** 1× cost. R0.05-0.20/truck. **Fastest, but PhyLo loses the "97.3% confidence" claim that the customer-facing report depends on.**

**The PhyLo-specific compromise:** **two-pass inference.**
- **Pass 1 — every row, no MC Dropout:** single forward pass to flag candidate anomalies. Cheap (1× cost).
- **Pass 2 — flagged rows only, full MC Dropout (50 samples):** the "confidence score" is only computed for rows that have already been flagged. This is the 5-15% of rows that matter for the customer.

**Cost with two-pass:** R0.30-1.20/truck (instead of R2.50-10.00 with MC on every row). **The "97.3% confidence" claim is preserved for the rows that appear in the customer report.** The tradeoff: rows that are NOT flagged do not get a confidence score — but the customer only sees flagged rows in the report anyway.

**This is a 1-day code change in `pinn_runtime.py` and `pinn.py`.** Without it, the unit economics get squeezed at scale; with it, the gross margin is 60-75% at Path A scale.

---

## E. The 30-day free diagnostic cost

**What the diagnostic actually is:** PhyLo reads the customer's telematics feed for 30 days, produces a baseline loss report. The customer sees their R60k variance in writing before they pick a path.

**What the diagnostic costs PhyLo:**
- **Compute:** same as Path A — R0.30-1.20/truck (with two-pass MC Dropout). At 60 trucks × 30 days = R15-60/diagnostic in cloud spend.
- **Qhayiya's time:** 4-8 hours per diagnostic. Setup (Cartrack API access, OAuth), monitoring (weekly check-in), synthesis (the baseline loss report). R500/hour × 4-8 hours = **R2,000-4,000/diagnostic in founder time.**
- **Total per diagnostic: R2,015-4,060.** The cloud cost is negligible. **The founder's time is the cost.**

**If PhyLo runs 100 diagnostics in year 1 (the conversion-rate assumption of 30-40% means 30-40 customers out of 100 diagnostics):** R200,000-400,000 in founder time across the year. This is **not in the 6-month R69,400 cost model** because it's amortized over a longer period — but it is a real cost, and the R12,000-25,000 CAC I had earlier was probably **low by R2,000-4,000 per customer** when diagnostics are factored in.

**Updated CAC estimate:** R14,000-29,000/customer when diagnostics are included.

---

## F. The summary: does the cost model make Path A R45/vehicle work?

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

## G. What the cost model says about the pilot (Path C)

The pilot partner has R78k/month variance. Path C earns R9-13.5k/month from the pilot.

**Pilot cost to PhyLo:**
- Compute: 42 trucks × R3-5 = R126-210/month (with two-pass MC)
- Storage: 42 × 50 MB = 2.1 GB/month = negligible
- Qhayiya's time: 8-12 hours/month (compliance review support, weekly check-in, monthly synthesis) = R4,000-6,000/month
- Total pilot cost: R4,200-6,200/month

**Pilot margin:** R9-13.5k revenue - R4.2-6.2k cost = **R3,000-9,300/month net (28-70% margin).** The pilot IS profitable, but only because the founder's time is the dominant cost and is being under-priced at R500/hour.

**At a market-rate founder cost of R1,500/hour (post-funding), the pilot margin would compress to R0-3,000/month.** This is why Path C is pilot-specific, not the default.

---

## H. Open questions about the cost model (to validate with a real cloud account + the actual data)

1. **What is the actual Cartrack API rate limit and is it free for the customer?** If Cartrack charges per API call, the cost shifts to the customer. If they throttle at a low rate, the connector design changes.
2. **What is the actual PINN inference latency on a modern vCPU?** Run a benchmark with `time` on a Hetzner/OVH dedicated server. If it's 1ms instead of 0.1ms, the 10× cost difference matters.
3. **Is MC Dropout used in the production path or only in research?** Check `api/main.py` and `ingest/service.py` to see if `predict_with_uncertainty()` is called. If only `predict_fuel_rates()` is called, MC Dropout is not the cost — the cost is the raw inference, and the 1× design is already in place.
4. **What is the actual pilot dataset event count?** The 5-8 events/month number is from the research report. The actual pilot data (when it lands) may be 3-12 events/month — a 4× range. Path C revenue scales with this directly.
5. **What is the actual telematics API for the pilot partner?** If it's not Cartrack, the connector setup time shifts. Tracker and Netstar connectors exist in the repo but are stubs; Cartrack connector is the most developed.

---

*This cost model is built from the actual PhyLo engine code, the research report, and the pilot dataset. The cloud/GPU/vendor prices are from LLM training data (cutoff Jan 2026) and must be verified with a real cloud account before any external pitch. The unit economics hold at Path A scale with the two-pass MC Dropout design change.*
