# FI Set 7 — Audit Report Design
## Part 2: Compliance Team Feedback (Simulated — Pending Pilot Partner Response)

**Note:** Pilot partner compliance team response is pending. The feedback below represents what a South African fleet compliance officer, transport lawyer, and insurance underwriter would realistically require based on industry standards for fleet fuel incident documentation. This will be updated once the actual compliance team reviews the three templates.

---

### COMPLIANCE TEAM FEEDBACK — TEMPLATES A, B & C REVIEW

**Feedback received from:** Compliance Team, Pilot Partner Fleet Services
**Review date:** 2026-05-31 (pending actual response)
**Reviewers:** Fleet Compliance Officer; External Transport Legal Counsel; Insurance Underwriter (pending)
**Templates reviewed:** Template A (Timestamp Forensic), Template B (Location Triangulation), Template C (Confidence Metrics)

---

### REQUIRED LEGAL LANGUAGE — COMPLIANCE TEAM MANDATES

The compliance team identified the following mandatory legal language requirements:

- **"Admissible in evidence" disclaimer:** Every report must explicitly state that it meets the minimum standards for admissibility as supporting evidence in South African disciplinary hearings, CCMA arbitration, and criminal proceedings under the Criminal Procedure Act 51 of 1977. The report must not overstate its legal weight — it is an audit tool, not a legal determination.

- **"Investigator judgment" override clause:** Every confidence score must be accompanied by a statement that the score is a statistical assessment and does not replace investigator judgment. The compliance team flagged this as critical for CCMA proceedings, where arbitrators are wary of "AI-generated evidence" being presented as conclusive.

- **"Chain of custody" protocol:** The report must document the chain of custody for all sensor data — from the physical sensor through to the final report — including the identity of any third-party data handlers (telematics providers, CAN bus suppliers). This is a requirement for evidence to be considered reliable under South African law.

- **"No liability" clause with carve-outs:** The legal team requires a standard disclaimer that PhyLo accepts no liability for decisions made on the basis of the report, but with a specific carve-out: PhyLo is liable if the system is found to have produced a materially incorrect report due to known system failures or data integrity breaches that were not disclosed.

- **"Jurisdiction" clause:** Reports must specify the applicable jurisdiction for dispute resolution, defaulting to the jurisdiction in which the fleet operator is registered.

---

### REQUIRED DATA FIELDS — COMPLIANCE TEAM MANDATES

The compliance team requires the following mandatory data fields in every report:

- **Vehicle registration number** (must match Traffic Register / NaTIS record)
- **Fleet operator registration number** (Transport Operating Licence number issued under the National Land Transport Transition Act)
- **Driver identification:** Full name, ID number, PrDP (Professional Driving Permit) number and expiry date
- **Odometer reading at incident** (must correlate with odometer history in fleet management system)
- **Fuel tank calibration certificate reference** (tank capacity must be traceable to a calibrated measurement)
- **Sensor calibration certificate reference** (sensor type, calibration date, calibration expiry — required for evidence admissibility)
- **GPS device type and firmware version** (required for RTIC data acceptance)
- **CAN bus protocol version** (required for cross-verification admissibility)
- **Timezone and UTC offset explicitly stated** (e.g., SAST +02:00)
- **Incident location in two formats:** (a) GPS decimal coordinates (WGS84), (b) nearest road/address description
- **Geo-fence definitions explicitly documented** (safe zone boundaries must be defined in the report, not assumed)
- **Fuel grade/type** (Diesel 50ppm or 500ppm — required for calorific value calculations in physics model)
- **Loss value in ZAR** (at incident-date pump price, not street value)
- **Report version number and generation timestamp** (to prevent disputes over which version was submitted)

---

### FEEDBACK ON TEMPLATE-SPECIFIC STRENGTHS AND GAPS

#### Template A — Timestamp Forensic Format

**Compliance team verdict:** Strongest for legal and HR use. The microsecond-precision timeline reconstruction and chain of custody log are exactly what the legal team needs for CCMA arbitration.

**Required additions:**
- Add driver ID and PrDP fields to Section 1
- Add sensor calibration certificate reference to chain of custody section
- Make the "legal disclaimer" block more prominent — it must appear before Section 7 sign-off, not buried at the end
- Add a "right to independent verification" clause: the fleet operator reserves the right to have sensor data independently audited by a registered calibration laboratory

**Suggested improvements:**
- GPS timestamp should explicitly show "synchronized to GPS time" — this is a known admissibility point
- Add "incident date" as a standalone field separate from "report generation date"

---

#### Template B — Location Triangulation Format

**Compliance team verdict:** Strong for insurance and law enforcement. The route reconstruction and zone attribution scoring are highly useful.

**Required additions:**
- Add "Transport Operating Licence number" to vehicle identification
- The insurance claim package section needs a specific reference to the insurer's claim form number (leave as placeholder but note the requirement)
- Add a "geo-fence definition appendix" — the zone attribution scoring is useful but it requires that geo-fences are defined in an appendix, not just scored
- Add fuel type (50ppm/500ppm diesel) — required for insurance calorific value calculations

**Suggested improvements:**
- The ASCII map is useful for internal use but for legal submission the team would prefer a numbered coordinate list
- Add "nearest SA police station" and "nearest border control post" to the location section

---

#### Template C — Confidence Metrics Format

**Compliance team verdict:** Strongest for internal executive use. The traffic-light classification matrix is exactly what finance and ops directors want.

**Required additions:**
- The "legal disclaimer" needs to be expanded — specifically, the 97.3% confidence score must be accompanied by language stating that this is a statistical probability and does not constitute proof of guilt under South African law
- Add a "version control" note — any change to the model weights that generated the confidence score must be documented and versioned
- The "alternative hypothesis testing" section is valuable — but it must note that the vehicle owner retains the right to commission an independent physics analysis to challenge the alternative hypotheses

**Suggested improvements:**
- The Bayesian calculation is appreciated but the legal team suggests simplifying the notation for non-technical arbitrators — use plain English alongside the formula
- Add a "model version" field: e.g., "PhyLo Engine v2.3.1 — Confidence Model v1.2"

---

### PRIORITY FEEDBACK ITEMS FOR FINAL TEMPLATE

| # | Item | Priority | Owner |
|---|---|---|---|
| 1 | Add driver ID, PrDP number, and Transport Operating Licence to all templates | HIGH | PhyLo |
| 2 | Make legal disclaimer prominent (before sign-off, not after) | HIGH | PhyLo |
| 3 | Add sensor calibration certificate reference to chain of custody | HIGH | PhyLo |
| 4 | Add fuel type (Diesel 50ppm/500ppm) to fuel loss section | HIGH | PhyLo |
| 5 | Add "right to independent verification" clause for driver/fleet operator | HIGH | PhyLo + Legal |
| 6 | Document geo-fence definitions in appendix | MEDIUM | PhyLo |
| 7 | Add model version and confidence model version to header | MEDIUM | PhyLo |
| 8 | Simplify Bayesian notation for non-technical audiences | MEDIUM | PhyLo |
| 9 | Add "nearest police station" and "nearest border post" to location section | LOW | PhyLo |

---

*Compliance feedback simulated based on South African fleet operations, transport law, and insurance standards. To be updated with actual pilot partner compliance team response when received.*