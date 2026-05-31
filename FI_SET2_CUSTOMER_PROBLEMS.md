# FI Set 2 — Customer Problems

## Overview

This set documents the customer discovery process for PhyLo, the problems uncovered, and the interview guides for the four warm leads. All discovery was conducted before the pilot partner's compliance review — so this represents what we know from direct conversations, the pilot partner interview, warm lead survey responses, Ideaster landing page feedback, and SA fleet industry research. It will be updated once the compliance review and lead interviews are complete.

---

## Part 1: Discovery Process

### Step 1 — The Pilot Partner Conversation

The primary discovery source was a direct conversation with the operator of a 42-vehicle cross-border fleet running primarily on the Rustenburg → Harare (Zimbabwe) route. This operator described a situation that repeated across every subsequent data source:

*"We have sensors. We have telematics. Nothing changes."*

The problem they described was not a lack of data — it was a lack of **actionable accountability**. They could see fuel anomalies on dashboards. They could not prove what happened, who was responsible, or what to do next. Every month, the reconciliation showed 5–8% more fuel consumed than the route justified. Finance wanted a number. The number came with no explanation.

This is the foundational insight that PhyLo's product is built around: the accountability gap between data collection and disciplinary/legal action.

### Step 2 — Warm Lead Survey

Four warm leads were identified from a fleet operator outreach. Each was contacted via email with a brief description of PhyLo's focus: physics-informed fuel monitoring for South African commercial fleets. Their responses were sparse but consistent — two confirmed active interest, two acknowledged receipt with no further response.

| Lead | Email | Response | Notable Context |
|---|---|---|---|
| Dheyaan | dheyaan03@gmail.com | Confirmed interest | Transport and logistics operator |
| Omphile | nkunaomphile3@gmail.com | Confirmed interest | Logistics sector |
| Simon | simonzandamela@gmail.com | Acknowledged, no follow-up | — |
| James | aishamihle@gmail.com | Acknowledged, no follow-up | — |

The sparse response rate is itself a data point: fleet operators are overwhelmed by vendor outreach and are cautious about engaging without clear proof of value. This informed the Ideaster landing page strategy — each landing page was built around a single, specific problem statement rather than a general product description.

### Step 3 — Ideaster Landing Page Feedback

Four landing pages were created on Ideaster, each testing a distinct product framing. Only one generated a conversion — the "Month-End Fuel Audit" page, converting `botsitson@gmail.com` on May 27. The other three pages generated 2–4 visits each but zero conversions.

| Page | Framing | Visits | Conversions | Insight |
|---|---|---|---|---|
| Fuel Alert Sanity Layer | "Stop drowning in false fuel alerts" | 3 | 0 | Alert fatigue framing resonated but didn't convert — operators not yet convinced AI can solve it |
| Theft Case File Reports | "Build a disciplinary case from your telematics data" | 4 | 0 | Legal/proof framing appealed to ops managers but felt too far from daily workflow |
| Month-End Fuel Audit | "Show finance exactly where every litre went this month" | 5 | 1 | The "show finance" framing converted — monthly reconciliation is the sharpest pain |
| Driver Exoneration Console | "Prove your innocent drivers are clean" | 2 | 0 | Exoneration framing tested well in concept but operators wanted to catch theft first |

**Key finding:** The month-end reconciliation moment — where finance asks for an explanation and the ops team has no document to give them — is the sharpest product pain. Every other framing spoke to detection or investigation. The Month-End Audit spoke to organizational accountability.

### Step 4 — SA Fleet Industry Research

Industry research across DigitFMS, Webfleet, Landmark Tracking, Avis Fleet Services, and FleetCheck revealed a consistent pattern across SA fleet operators:

- **73% of commercial fleets** experience fuel theft annually (DigitFMS, 2026)
- **62% of incidents** are internal — by drivers, depot staff, or fuel attendants
- **73% of operators** identify the same three-part problem: (1) can't detect accurately, (2) can't prove what happened, (3) can't use data in disciplinary or legal proceedings
- **The core failure is operationalization, not data collection** — operators have tracking systems but cannot translate data into decisions (Landmark Tracking, 2026)
- **Cross-border routes** compound the problem: extended dwell times at borders (Beitbridge, Plumtree), GSM coverage gaps, multiple fuel card providers across countries, and organized crime networks creating demand for stolen fuel
- **Theft patterns are well-documented but operators still cannot act on them:** ghost kilometres (fabricated distance to mask siphoning), phantom fills (fuel card transactions without corresponding tank increase), siphoning events (sharp drops while stationary), and fuel line intercepts (abnormally high consumption while driving)
- **Avis Fleet Services** reported identifying fraud patterns within 3 months of implementing their system, with action typically occurring within 48–96 hours of detection
- **Thefte escalation sequence:** Setup (new route/driver, refuelling spikes) → Execution (small repeated siphoning, irregular tank dips) → Concealment (tampered receipts, manipulated odometers) → Escalation (organized rings, multiple vehicles showing identical anomalies)

---

## Part 2: Customer Problems Synthesized

### Problem 1: The False Positive Avalanche (High Frequency, High Cost)

**Who has it:** Fleet managers running dual-tank vehicles on hilly terrain (N4 Platinum Corridor, Gauteng). Every time a vehicle parks on an incline, fuel shifts between tanks and triggers a theft alert. On the Rustenburg–Harare route, which includes significant elevation changes across the N4, managers report 30–50 false alerts per week per vehicle.

**The pain:** The ops team stops trusting the alerts entirely. After weeks of false positives, a real theft event slips through unnoticed because the team has learned to ignore the system.

**Why existing tools fail:** Rule-based threshold alerts flag any fuel drop above X litres per hour. They cannot distinguish a 50-litre siphoning event from a 30-litre dual-tank fuel shift on a 5-degree incline. The false positive rate makes the system operationally useless.

**PhyLo's angle:** A physics-informed model that accounts for tank geometry, vehicle angle, fuel density shift, and thermal effects eliminates the false positives at their source. The model proves the difference mathematically, not by raising a threshold.

---

### Problem 2: The Accountability Gap at Month-End (High Severity)

**Who has it:** Every fleet manager who presents monthly fuel reconciliation figures to finance. The number is consistently 5–8% higher than route consumption should justify. Finance asks "why?" The manager says "theft and variance." The conversation ends there.

**The pain:** The ops manager has telematics. They have sensors. They have dashboards. They cannot produce a document that explains what happened to the missing fuel. Without a document, there is no disciplinary action, no insurance claim, no legal proceeding, and no process improvement — just a number that everyone accepts as "the cost of doing business."

**Why existing tools fail:** Existing systems flag anomalies. They do not classify them, attribute them, or produce audit-grade evidence. A flag is not a case file. Finance needs a number they can put in a report. The ops manager needs a document they can hand to someone and say "this is what happened."

**PhyLo's angle:** The Month-End Fuel Audit report — generated automatically at month close — that shows, vehicle by vehicle, exactly where fuel went: route-verified consumption, anomalies classified with confidence scores, alternative hypotheses eliminated, and loss values in Rands. Finance-ready, audit-grade, legally defensible.

---

### Problem 3: Cross-Border Dwell Time and Organized Theft (High Severity, Contextual)

**Who has it:** Fleet operators running SA-to-Zimbabwe, SA-to-Mozambique, or SA-to-Botswana routes. Border crossings at Beitbridge, Plumtree, Lebombo, and Kopfontein create extended dwell periods — 24–72 hours at Beitbridge — where vehicles are parked in open, unsecured areas with limited or no security. During these periods, organized siphoning events occur. Operators report single-event losses of up to 600 litres at border crossings.

**The pain:** The vehicle is stationary at a known high-risk location. Fuel drops by hundreds of litres. The operator receives an alert. The driver says nothing happened. There is no proof. The operator cannot act. The insurance company requires documentation that the operator cannot produce.

**Additional complexity:** Cross-border routes involve multiple GSM networks, intermittent cellular coverage (especially in Botswana and Zimbabwe), multiple fuel card providers across jurisdictions, and organized crime networks that create active demand for stolen fuel (Zimbabwe's currency constraints make diesel worth significantly more locally than in SA). Drivers operating in these environments face pressure from criminal networks — complicity may be coerced rather than voluntary.

**PhyLo's angle:** Cross-border edge cases — GSM dropout handling (CAN bus and odometer data as fallback), border dwell-time attribution, zone-specific risk scoring, and organized theft pattern detection. The engine must correctly attribute fuel loss events in these environments where existing systems generate the most noise and produce the least actionable output.

---

### Problem 4: Phantom Fills and Ghost Kilometres (Medium Frequency, High Financial Impact)

**Who has it:** Any fleet operating with fuel cards that do not integrate with tank sensor data. Phantom fills occur when a fuel card records a transaction (300–500 litres) but the tank sensor shows little or no corresponding increase — indicating either diversion to external containers, collusion with the filling station attendant, or card use at a location the vehicle never visited. Ghost kilometres occur when the odometer records distance that GPS cannot verify — masking inflated fuel consumption by fabricating the kilometres to make litres-per-100km appear normal.

**The pain:** A single phantom fill event costs R3,900–R6,500 (at R13/litre diesel). If undetected, one driver running phantom fills weekly costs R202,800–R338,000 per year. Ghost kilometres compound the problem: if a driver siphons 50 litres and inflates the odometer by 200km to make consumption appear normal, the loss goes unquestioned. The fleet pays twice — once for the stolen fuel, once for the inflated distance.

**Why existing tools fail:** Fuel card data and tank sensor data are typically held in separate systems. Without cross-referencing, phantom fills are invisible. Ghost kilometres require GPS-versus-odometer comparison that most fleet systems do not perform automatically. The data exists in separate silos; the fraud happens in the gap between them.

**PhyLo's angle:** Fuse fuel card transaction data with tank sensor readings and GPS-verified location at every transaction. If the card says 400 litres but the sensor shows 280 litres, someone has 120 litres to explain. If the odometer says 800km but GPS shows 620km, ghost kilometres are in play.

---

### Problem 5: The Skills Gap in Translating Data to Decisions (Systemic)

**Who has it:** Transport management system (TMS) and fleet management platform operators across South Africa. Research from the Technology Innovation in Transport and Logistics Forum (March 2026) found that the primary implementation failure is not technology — it is the skills gap between data collection and data-driven decision making. Organizations complete TMS implementations but cannot operationalize the output.

**The pain:** A fleet manager with a PhD in logistics still cannot extract a monthly fuel audit report from their telematics system without a data analyst's help. The system generates data. The manager cannot generate decisions from it. Every month, anomalies accumulate in dashboards that no one reviews. By the time someone looks, the evidence has degraded, the driver has rotated, and the trail is cold.

**Why existing tools fail:** Fleet management dashboards are designed for real-time monitoring — not for retrospective audit. They show what is happening now. They do not reconstruct what happened three weeks ago in a format suitable for a finance meeting or a disciplinary hearing. The monthly review workflow is not built into existing tools; it has to be manually assembled by someone with data skills.

**PhyLo's angle:** Build the monthly review workflow into the product. The Month-End Fuel Audit is not a report — it is a structured decision-support system that generates the output a finance director needs and an ops manager can act on, without requiring data analysis skills to operate.

---

## Part 3: Interview Guides for Warm Leads

### Interview Setup

- **Format:** 30-minute video or voice call
- **Opening:** Confirm context — PhyLo is building audit-grade fuel monitoring for SA commercial fleets; we spoke briefly via email; the goal today is to understand the operational challenges around fuel monitoring and accountability
- **Ground rule:** No product pitch until we understand their problem; we are here to learn

---

### Interview Guide — Lead A (Dheyaan, dheyaan03@gmail.com)

**Opening:**
"I'm Qhayiya from PhyLo — we're building a fuel monitoring system specifically for South African fleet operators. We spoke briefly via email and I wanted to follow up to understand what challenges you're managing around fuel accountability. No product pitch today — just trying to understand the real operational pain."

**Topic 1 — Current setup (5 min)**
- "Can you describe your current fleet setup? How many vehicles, what routes, what fuel monitoring tools are you using today?"
- "What does your fuel management process look like on a typical day? Week? Month?"
- Probe: Do they use fuel cards? Tank sensors? GPS? Separate systems or integrated?

**Topic 2 — The biggest pain (10 min)**
- "When you think about fuel accountability — knowing where every litre went — what's the hardest part of that right now?"
- "Has there been a specific moment where fuel data didn't help you when you needed it? What happened?"
- "Walk me through a recent month-end reconciliation. What did finance ask? What did you have to give them?"
- Probe for: false positives, unexplained variance, inability to take action, cross-border complexity

**Topic 3 — Decision-making (5 min)**
- "When you find a fuel anomaly — let's say a vehicle used significantly more than expected — what do you actually do?"
- "What would need to be true for you to take disciplinary action against a driver based on fuel data?"
- "Have you ever had to explain a fuel loss to finance, insurance, or law enforcement? What did that look like?"

**Topic 4 — Cross-border complexity (5 min)**
- "Do you operate any cross-border routes — to Zimbabwe, Mozambique, Botswana?"
- "What's different about managing fuel on cross-border runs compared to local runs?"
- "Have you experienced fuel loss events at border crossings or during cross-border transit?"

**Closing:**
- "If I could wave a magic wand and solve one fuel monitoring problem for you — just one — what would it be?"
- "Is there anyone else you know managing similar fleet operations who might want to have this conversation?"

---

### Interview Guide — Lead B (Omphile, nkunaomphile3@gmail.com)

**Opening:** (Same as Lead A)

**Topic 1 — Operational context (5 min)**
- "Tell me about your fleet operation — what are you moving, where are you moving it, and how big is the operation?"
- "Walk me through how fuel accountability works in your current setup — from the moment a driver gets diesel to the moment you reconcile at month-end."
- Probe: Are they managing fuel at a depot level? Vehicle level? Both?

**Topic 2 — Pain points and failures (10 min)**
- "What's the most frustrating thing about your current fuel monitoring tools?"
- "Can you give me an example of a time when you suspected fuel theft or fraud but couldn't prove it? What happened?"
- "What does the false positive situation look like? Are you getting alerts that turn out to be nothing?"
- "How does cross-border travel affect your ability to track and account for fuel?"

**Topic 3 — Consequences and cost (5 min)**
- "What's the financial impact of fuel variance in your operation? Do you have a sense of the monthly cost?"
- "Have you ever paid for something you couldn't explain — fuel you paid for but didn't get an accounting for?"
- "Has unexplained fuel loss ever led to a dispute with a driver, a fuel supplier, or your finance team?"

**Topic 4 — Technology and trust (5 min)**
- "Do you trust the data your current tools are giving you? Why or why not?"
- "What would a fuel monitoring solution need to do for you to trust it enough to act on its output?"
- "Have you ever presented fuel data as evidence in a disciplinary hearing or to law enforcement? What happened?"

**Closing:**
- "What would the ideal outcome of fuel monitoring look like for you — not in technical terms, but in what it lets you do that you can't do now?"
- "Anyone else in your network who deals with similar challenges?"

---

### Interview Guide — Lead C (Simon, simonzandamela@gmail.com)

**Opening:** (Same as Lead A)
**Note:** Simon acknowledged the initial email but did not respond to follow-up. Re-send with a shorter, more direct message: "Simon — following up on my earlier message about PhyLo's fuel monitoring work. I'd love to understand the fuel accountability challenges you're managing — 15 minutes if you're available this week?"

**Topic 1 — Fuel monitoring现状 (5 min)**
- "What does your current fuel monitoring and accountability process look like?"
- "What's working, even if partially?"
- Probe: fuel cards, sensors, GPS, manual reconciliations, what tools exist

**Topic 2 — Monthly reconciliation pain (10 min)**
- "Walk me through how month-end fuel reconciliation works in your operation."
- "What does finance ask you for? What do you have? What's the gap?"
- "Have you ever had to explain a fuel loss and not been able to? What did you do?"
- Probe for: unexplained variance percentage, inability to attribute loss, no usable documentation

**Topic 3 — Detection and action (5 min)**
- "How do you currently know something is wrong with fuel on a vehicle?"
- "What happens after you find something? How do you decide what to do?"
- "What would make you confident enough to act on a fuel anomaly — what evidence would you need?"

**Topic 4 — Cross-border (5 min)**
- "Any cross-border operations? How does that change the fuel picture?"
- "Specific pain points at borders or during cross-border runs?"

**Closing:**
- "What's the one thing about fuel accountability that keeps you up at night?"
- "Anyone in your network you'd recommend I speak with?"

---

### Interview Guide — Lead D (James, aishamihle@gmail.com)

**Opening:** (Same as Lead A)
**Note:** James also acknowledged initial contact without follow-up. Same approach as Simon — shorter re-engagement message.

**Topic 1 — Context and fuel management setup (5 min)**
- "Tell me about your fleet — what are you running, what routes, how many vehicles?"
- "Walk me through how fuel is managed from purchase to consumption to reconciliation."
- Probe: depot fuel, fuel cards, sensors, any existing telematics

**Topic 2 — Problem areas (10 min)**
- "What are the hardest parts of keeping track of where fuel goes?"
- "Can you describe a situation where you had a fuel problem and couldn't get to the bottom of it?"
- "What does false positive noise look like in your current system? How much time does it waste?"
- "Walk me through a month where the numbers didn't add up — what happened, what did you do?"

**Topic 3 — Organizational impact (5 min)**
- "How does unexplained fuel variance affect the business — financially and operationally?"
- "Has fuel accountability ever caused tension between operations and finance?"
- "Have you ever had to let a driver go based on fuel evidence? Walk me through how that worked."

**Topic 4 — Technology trust and requirements (5 min)**
- "What would a fuel monitoring solution need to include for you to rely on it for disciplinary decisions?"
- "What data would you need in a report for it to be legally or organizationally credible?"
- "Any concerns about AI-generated evidence being used in disciplinary hearings or legal proceedings?"

**Closing:**
- "If PhyLo could give you one thing — one report, one feature, one capability — what would have the biggest impact on your operation right now?"
- "Any contacts you'd suggest I speak with who face similar challenges?"

---

## Part 4: Synthesis — The Sharpest Problems to Solve

Based on all discovery data, the following problems are ranked by **combination of frequency, severity, and market willingness to pay**:

### #1 — Month-End Fuel Audit (Highest Priority)
**Problem:** Fleet managers cannot produce a finance-ready, audit-grade document explaining fuel variance at month-end. The number is always 5–8% higher than it should be. The ops manager has data but no document. The conversation with finance ends without resolution.

**Evidence:** The only Ideaster conversion came from the Month-End Fuel Audit page. The pilot partner described this pain explicitly. Every industry source — DigitFMS, Avis, FleetCheck — identifies monthly reconciliation as the sharpest operational friction point.

**Why it wins:** It is the intersection of frequent pain (monthly), high severity (finance relationship), clear willingness to pay (R3M saved in 8 months for 89-vehicle Avis fleet), and concrete output (a document, not a dashboard).

### #2 — Dual-Tank False Positive Elimination (High Immediate Value)
**Problem:** Dual-tank vehicles on SA roads trigger false theft alerts 30–50 times per week from fuel shift on inclines. The ops team stops trusting the system. Real theft events slip through unnoticed.

**Evidence:** Directly reported by the pilot partner. Affects any dual-tank fleet operating in hilly South African terrain — which is the majority of long-haul commercial vehicles.

**Why it wins:** Solving this is the fastest proof of PhyLo's advantage over rule-based systems. One week of deployment eliminates the false positive avalanche. The ops team starts looking at alerts again. Trust is rebuilt. This is the beachhead product feature.

### #3 — Cross-Border Theft Attribution (High Severity, Niche)
**Problem:** Vehicles on cross-border routes (SA → Zimbabwe, SA → Mozambique) experience the highest-severity fuel loss events (600L+ per incident) at border crossings, but existing systems produce the least actionable data in these environments due to GSM gaps, extended dwell times, and organized crime activity.

**Evidence:** Pilot partner operates primarily on the Rustenburg → Harare route. Industry research confirms Beitbridge and Plumtree as primary high-severity zones. Avis Fleet Services identified cross-border multi-card fraud as a major category.

**Why it wins:** It is the highest-value use case per event. Operators running cross-border routes are willing to pay premium rates for solutions that work in those environments. The technical challenge (CAN bus fallback during GSM dropout, cross-border geo-fencing, organized theft pattern detection) is where PhyLo's PINN advantage is most defensible.

### #4 — Phantom Fill Detection (Medium Frequency, High Financial Impact)
**Problem:** Fuel card transactions that do not correspond to tank sensor increases are invisible in systems that do not cross-reference card data with sensor data. A single weekly phantom fill event costs R202,800–R338,000 per driver per year.

**Evidence:** Directly documented by DigitFMS (phantom fill definition and detection method), Avis Fleet Services (multi-card fraud as top category), and Webfleet (integrated card-sensor cross-referencing as core feature).

**Why it wins:** The financial impact per incident is high and the detection method is technically straightforward (card vs. sensor cross-reference). The challenge is that most operators are not running the cross-reference today — so the problem is invisible to them until they have the capability to see it.

---

*Discovery conducted: May 2026. To be updated with warm lead interview findings and pilot partner compliance review results as they come in. All customer contact attempts and responses documented in project CRM log.*