# Validation Sprint 3 — Set 3: Team
## PhyLo | Founder Institute South Africa 2026 | Launch Track

**Deliverable:** Map out the human and agent roles needed to deliver PhyLo's selected business (Month-End Fuel Audit) at the chosen diagnostic-led / Path A-default revenue model.

---

## Part 1: Every Role Required to Generate Revenue

| # | Role | Human / Agent / Combined | Why | Agent skills / integrations needed |
|---|---|---|---|---|
| 1 | **Sales / customer development** | Combined (Qhayiya is sole human for next 6 months; agent does prep, follow-up, transcript synthesis) | 15 interviews + 5 customer sessions is human work; scheduling, prep briefs, follow-up emails are agent work | Web search, LinkedIn automation, audio-transcription, document generation |
| 2 | **Detection engine maintenance** | Combined (Qhayiya does model changes; agent writes tests, code review, deployment scripts) | PINN retraining is human; CI/CD and bug triage are agent | Code execution, TDD, deployment (GitHub Actions), model retraining scripts |
| 3 | **Customer onboarding** | Combined (Qhayiya does the first 3; agent builds the SOP and runs onboarding 4+ via Loom + check-in) | First few are human because edge cases define the product; rest can be SOP'd | Document generation, video scripting, Loom upload, calendar automation |
| 4 | **Customer support / dispute packs** | Combined (Qhayiya reviews each dispute pack; agent drafts from detection logs) | Dispute packs are legal-adjacent; need human sign-off | PDF generation, document templating, evidence-pack assembly |
| 5 | **Marketing / content** | Agent-first (LinkedIn posts, case-study drafts, landing-page copy; Qhayiya approves) | Solo founder's voice is the moat; agent produces drafts | Content writing, image generation, scheduling (Buffer / LinkedIn API) |
| 6 | **Finance / accounting** | Human (bookkeeper R2-3k/month) | Tax compliance is non-negotiable | n/a (bookkeeper uses Xero / Sage) |
| 7 | **Compliance / legal** | Human (ad-hoc attorney R5-10k/quarter) | SOW + dispute-pack liability is real | n/a (attorney + SaaS contract templates) |
| 8 | **Pilot partner account management** | Human (Qhayiya) | The pilot partner is the proof point; relationship is the product | n/a |
| 9 | **Connector maintenance** (Cartrack, Tracker, Netstar, Webfleet, MiX, Ctrack) | Combined (Qhayiya builds the connectors; agent writes tests, monitors API changes) | Connector health is a 24/7 concern; humans can't watch all 6 dashboards | API monitoring, code execution, alert routing |
| 10 | **Investor relations / fundraising** | Human (Qhayiya) | R15M seed raise needs a founder's voice, not an agent's | Deck generation (assisted), financial model maintenance |

**Summary:** 10 roles. 4 are human-only (bookkeeper, attorney, pilot account management, investor relations). 6 are combined human + agent.

---

## Part 2: The Single Most Important Human Hire

- **Role title:** **Sales Lead / Founding Account Executive**
- **Why this role:** 15 customer interviews + 5 customer sessions in 6 weeks is a one-person ceiling. The next 6 months need 5x that — and Qhayiya cannot do customer development, pilot management, AND engineering simultaneously once the e-hailing gig starts in June 2026.
- **Skills required:**
  - SA B2B SaaS sales experience (fleet/logistics/industrial buyers ideal)
  - Comfortable with R50-200k ACV deals
  - Can write a 1-page proposal without legal review
  - Knows what an "RFP response" looks like for a parastatal
  - Has a phone that rings when Cartrack's former customers are unhappy
  - Cold-call resilience: willing to make 30 calls/day in months 1-3
- **Compensation Qhayiya can offer:**
  - **Base:** R25,000-35,000/month (below market for experienced AE in Johannesburg, but the upside is in the commission)
  - **Commission:** 5% of closed ARR for year 1 (uncapped)
  - **At R1M ARR (31 customers × R32,400/year),** 5% = R50,000 in commission — doubles the base
  - **No equity in year 1** (Qhayiya is keeping founder equity for the eventual CTO hire, which is the harder recruit)
  - 3-month probation, then permanent
- **Three known candidates from my network:**

  1. **[CANDIDATE 1 — TO BE FILLED]** — current role, why a fit, how I know them
  2. **[CANDIDATE 2 — TO BE FILLED]** — current role, why a fit, how I know them
  3. **[CANDIDATE 3 — TO BE FILLED]** — current role, why a fit, how I know them

  *(Format: name, current role, why they're a fit, how I know them. To be filled by Qhayiya from his network before submission.)*

---

## Part 3: 6-Month Cost Estimate by Month

| Month | Human comp | Agent API fees | Tool subs | Total |
|---|---|---|---|---|
| M1 (Jul 2026) | R0 (Qhayiya only) | R500 | R2,000 | R2,500 |
| M2 (Aug 2026) | R0 | R500 | R2,000 | R2,500 |
| M3 (Sep 2026) | R0 | R500 | R2,000 | R2,500 |
| M4 (Oct 2026) | R0 | R700 | R2,500 | R3,200 |
| M5 (Nov 2026) | R25,000 (first sales hire month) | R1,000 | R3,000 | R29,000 |
| M6 (Dec 2026) | R25,000 | R1,200 | R3,500 | R29,700 |
| **6-month total** | **R50,000** | **R4,400** | **R15,000** | **R69,400** |

### Cost line item assumptions

- **Human comp:**
  - M1-M4: Qhayiya only (no salary — the founder doesn't pay himself in year 1)
  - M5-M6: First sales hire at R25,000/month base. Commission is paid in arrears (after month 7+ when first deals close), so M5-M6 commissions are not in this 6-month window.
- **Agent API fees:** (M1 R500 → M6 R1,200)
  - M1-M3: R500/month = ~5M tokens at LLM-as-judge, transcript synthesis, draft generation, code review
  - M4: R700/month = +40% as the sales-prep workload scales
  - M5-M6: R1,000-1,200/month = +60-80% with the sales hire's prep + onboarding
- **Tool subscriptions:** (M1 R2,000 → M6 R3,500)
  - GitHub Pro (R100), Sentry (R500), Hetzner VPS (R500), Vercel/Render (R200), LinkedIn Premium (R1,000), Calendly Pro (R200), Loom Business (R300), Notion (R100), domain + email (R200) = base R3,100 from M5
  - M1-M4: lighter (no LinkedIn Premium, smaller VPS) = R2,000-2,500
  - M5-M6: full stack + CRM (HubSpot free tier → R800/month at M6) + Zoom R200/month

---

## Part 4: Human vs Agent Decision Framework

For every role added after M6, ask:

1. **Is the work a one-off, low-volume, relationship-driven decision?** → **Human.** (Pilot account management, fundraising, key hires.)
2. **Is the work repeatable, high-volume, and rules-based?** → **Agent.** (Transcript synthesis, draft generation, code review, monitoring.)
3. **Is the work creative + quality-sensitive + needs founder voice?** → **Human approves, agent drafts.** (Marketing, dispute packs, SOW contracts.)
4. **Is the work regulatory / legal / financial?** → **Human + compliance review.** (Bookkeeper, attorney, tax.)

This is the framework that makes the M5+ hires defensible: every R25k/month hire must justify the expense against an agent that could do 70% of the role for R1,200/month in API fees.

---

## Part 5: Open Items / Risks

- **3 known candidates placeholder** — Qhayiya to fill from his network before FI submission
- **No equity in year 1 for the sales hire** — defensible at M5 but may need to revisit in year 2 if the right candidate is equity-motivated
- **M5 sales hire CAC step-up** (R12k → R25k) — accepted trade-off; 4.4-9.3 month payback (4.4 at R12k founder-time CAC, 9.3 at R25k sales-hire CAC)
- **Connector maintenance is the silent killer** — if 2 of 6 connectors break in M3 and the founder is on the e-hailing gig, customer confidence erodes. Agent monitoring + human escalation path is the mitigation.

---

*Set 3 deliverable substantively complete. 10 roles mapped, top hire (Sales Lead / Founding AE) identified, 6-month run cost R69,400, human-vs-agent decision framework documented.*
