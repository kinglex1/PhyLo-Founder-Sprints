# Validation Sprint — Set 4: Mockup Demo
## PhyLo | Founder Institute South Africa 2026 | Launch Track

**The Mockup:** `VALIDATION_SET3_MOCKUP.html` (committed in Set 3)
**Demo Duration:** 3 minutes
**Format:** Live walkthrough on laptop/tablet with screen share, no slides

---

## Part 1: Demo Flow Outline

| Time | Section | What I'm Saying | What I'm Doing on Screen |
|---|---|---|---|
| 0:00–0:20 | Hook | "A 60-vehicle fleet lost R78,440 to fuel variance last month. The ops manager couldn't tell finance where it went. Watch how PhyLo turns that into an answer." | Show the dashboard headline metric: R 78,440 variance |
| 0:20–0:50 | The dashboard | "This is what the fleet ops manager sees when they open PhyLo at month-end. Every vehicle. Route-verified expected vs actual. Variance in Rands. Status flags." | Show the metrics row, then scroll the vehicle list |
| 0:50–1:25 | The theft audit | "Two vehicles have confirmed theft — both on cross-border routes. Watch what happens when I click." | Click ZAN 123 GP (Rustenburg → Harare) — opens audit modal |
| 1:25–1:55 | The audit report | "This is the document no telematics vendor produces. ISO 8601 microsecond timeline. GPS coordinates. Engine state from CAN bus. 97.3% confidence. Five alternative hypotheses eliminated — sensor malfunction, thermal contraction, dual-tank shift, idle burn, GPS error. Plain-English narrative. Loss value in Rands." | Scroll the audit modal — timeline, geospatial, sensor integrity, confidence score, hypotheses, narrative |
| 1:55–2:15 | The false positive filter | "And here's why PhyLo restores trust. Your telematics flagged 30–50 false alerts a week. PhyLo filters them. Watch." | Click JHB 882 GP — shows the dual-tank shift explanation: vehicle on 4.7° incline, fuel drained from front to rear tank, total fuel unchanged |
| 2:15–2:45 | The finance export | "This is the part the finance director has been asking for. One click. PDF. Vehicle by vehicle. Loss value. Action recommendations. This is the document that goes in the file and the email." | Click "Export for Finance" — show the PDF view |
| 2:45–3:00 | The ask | "30-day pilot. 5 of your vehicles. Free. Read-only access to your existing telematics data. We give you the report whether you sign or not. Who's the right person on your team to talk to?" | Close the demo |

Total: ~3 minutes when delivered at 165 wpm.

---

## Part 2: Mockup End-to-End Test

### Test Results (Run May 31, 2026)

**Path tested:** Dashboard → click ZAN 123 GP → audit modal loads → scroll all sections → close → click JHB 882 GP → false positive modal → close → click "Export for Finance" → PDF modal → "Download as PDF" triggers print dialog

**Issues found and fixed during test:**

| # | Issue | Fix | Round |
|---|---|---|---|
| 1 | Initial timeline was too dense for 3-min delivery — 8 rows including irrelevant "loading" and "departure" events | Trimmed to 7 rows, kept only the 5 rows that drive the narrative (border cross, parking, stable, drop, recovery) | 1 |
| 2 | The 6-channel confidence score breakdown initially showed all 6 channels at the same size, making the headline 97.3% feel less prominent | Made the 97.3% headline larger (36px) and demoted the channel list to a smaller grid | 1 |
| 3 | The "Export for Finance" PDF view originally opened inside the same modal overlay as the audit report — created visual confusion about whether the user was still in the audit or had moved to export | Made the PDF modal completely separate with its own close button and a "Back" navigation | 1 |
| 4 | The hypothesis table was originally a 3-column layout; the "ELIMINATED" / "ACCEPTED" pills were hard to scan quickly | Reordered columns to show "Hypothesis → Probability → Ruling" left-to-right, with the accepted hypothesis highlighted in green at the bottom | 2 |
| 5 | The narrative was 250+ words — too long for 3-min delivery and read like a legal disclaimer | Rewrote to ~140 words in plain English, second-person ("you can hand this to finance") | 2 |
| 6 | The false positive modal lacked the same visual punch as the theft modal — operators might not realize the value of the filter without the same richness | Added a side-by-side comparison: "Telematics Alert" vs "PhyLo Verdict" with the same dashboard style | 2 |
| 7 | The "Download as PDF" button originally opened a blank print preview | Switched to `window.print()` which works in any browser; the print stylesheet renders the PDF modal cleanly | 1 |

**Final state:** Mockup runs reliably end-to-end in Chrome, Edge, and Firefox. No JavaScript errors. All modal interactions work. Print/PDF export functions.

---

## Part 3: Rehearsal Notes

### Three Rehearsals Logged

**Rehearsal 1 (alone, with timer):** 3:42 — 42 seconds over. Need to cut.
**Rehearsal 2 (after edits):** 3:08 — 8 seconds over. Almost there.
**Rehearsal 3 (final, on camera):** 2:54 — under 3 minutes. Delivery feels natural.

### What Got Cut Between Rehearsals

- The "physics-informed" technical explainer — moved to the Q&A only, kept the demo language simple
- The "May 2026 diesel price shock" context line — assumed audience already knows
- The "PinN vs statistical models" technical aside — moved to a single phrase: "physics-informed engine"

### What Got Added Between Rehearsals

- The "who's the right person on your team to talk to?" close — replaced the generic "let's book 20 minutes" with a specific, professional close
- The "fuel drained from front to rear tank" language in the false positive demo — uses the operator's mental model, not a physics term

### Pacing Markers

- **0:50 mark:** Should be in the middle of the dashboard scroll. Don't rush.
- **1:25 mark:** Should be deep in the audit report — at the timeline or geospatial section. Let the report breathe.
- **2:15 mark:** Should be transitioning to the false positive demo. The "trust restoration" message is critical here.
- **2:45 mark:** Should be closing on the ask. Direct, specific, no apologies.

### Body Language

- **Stand during the demo** — it's a hotseat, not a boardroom presentation
- **One physical prop:** the laptop/tablet with the mockup loaded. No slides, no PDF handouts.
- **Hand the screen over deliberately:** "Let me show you what this looks like" — then physically point or zoom into the screen so the audience follows
- **The click is the moment:** when you click ZAN 123 GP, pause for half a second to let the modal open before you start talking. The visual is part of the demo.

---

## Part 4: Working Group Practice Run

**Working Group Meeting:** Pending — to be scheduled within Sprint 1 deadline window.

### Anticipated WG Feedback (To Be Updated After Practice Run)

| Likely Feedback Theme | My Planned Response |
|---|---|
| "Lead with the dual-tank filter, not the audit report" | The audit IS the lead — the filter is the supporting story. Without the audit context, the filter is just a feature. |
| "Show the financial impact earlier" | The R78,440 is the headline metric on the dashboard. The viewer sees it within 5 seconds of opening. |
| "The false positive demo is too short" | Deliberately so — the false positive is the trust story, the theft is the value story. Different jobs. |
| "What about the customer who's already seen a similar demo?" | Lead with the PDF export. "You may have seen other fuel monitoring demos. Have you seen the document?" — then show the PDF. |
| "Where's the live data integration?" | Phase 2. This is a prototype with synthetic data. The pilot connects to real telematics. |

---

## Part 5: Demo Self-Assessment

### Did I Demonstrate Understanding of the Customer's Problem?

**Yes.** The hook names the specific pain (R78,440 unexplained variance), the dashboard shows the real artifact the ops manager needs (variance by vehicle in Rands), and the audit report demonstrates the output that doesn't exist in their current stack.

### Did I Show the Cost / Frustration / Risk of the Problem?

**Yes.** The cost is in Rands (R78,440). The frustration is the false positive noise. The risk is the 2 confirmed theft events that didn't get caught by their current system. The 97.3% confidence score shows the operator what it looks like to have proof instead of a guess.

### Did I Demonstrate How PhyLo Solves the Problem?

**Yes, three ways:**
1. **Validates** — the 6-channel confidence score and 5 alternative hypotheses eliminated show the operator the proof is real
2. **Filters** — the false positive demo shows the operator PhyLo removes the noise their current system creates
3. **Reports** — the finance PDF shows the operator the document they can hand to finance

### Did I Focus on Customer Outcomes, Not Features?

**Yes.** The narrative section in the audit report is in plain English. The PDF export is described in terms of what the operator does with it (forward to finance, hold up in CCMA). The false positive demo is framed as "you stop wasting time on noise."

### Did I Include a Short Demo / Visual?

**Yes.** The mockup is the demo. The PDF view is the visual. No slides, no slideshow, no handouts.

### Did I Clearly Explain the Next Step?

**Yes.** "30-day pilot. 5 of your vehicles. Free. Read-only access to your existing telematics data. We give you the report whether you sign or not. Who's the right person on your team to talk to?"

### Would the Customer Be Interested Enough to Continue the Conversation?

**Self-assessment:** Yes, if the customer is the right ICP (50+ vehicle fleet with existing telematics, month-end reconciliation pain, finance director as payer). For customers outside the ICP, the demo won't land.

---

## Part 6: Working Group Feedback and Changes

*To be updated after the WG practice run is conducted.*

| Feedback | Change Made |
|---|---|
| (Pending) | (Pending) |

---

*Set 4 deliverable complete. The demo is rehearsed to 2:54, the mockup runs end-to-end, and the ask is specific. Ready for the Working Group practice run and then the Weekly Strategy Presentation.*