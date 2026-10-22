# SpendNest Revenue Intelligence Studio & KIT UDHAYAM 2027 Blueprint

**Volopay Growth Associate Challenge Submission**  
**Candidate:** Nandhini R (nandhinirameshn66@gmail.com)  
**Evaluation Scope:** 21 August 2026 (Asia/Kolkata)  

---

## 🔗 Quick Submission Links

- 🌐 **Live Deployed Application (GitHub Pages):** [https://nandhini-rsk.github.io/Volopay_assignment/](https://nandhini-rsk.github.io/Volopay_assignment/)
- 💻 **GitHub Source Repository:** [https://github.com/nandhini-rsk/Volopay_assignment](https://github.com/nandhini-rsk/Volopay_assignment)
- 🎥 **Video Walkthrough Recordings (Google Drive):** [https://drive.google.com/drive/folders/1jMxm71YuC14YRJPHxTCXfDM497vry9WC?usp=sharing](https://drive.google.com/drive/folders/1jMxm71YuC14YRJPHxTCXfDM497vry9WC?usp=sharing)
  - *Video 1 (3-Min): SpendNest Revenue Intelligence Walkthrough*
  - *Video 2 (5–8 Min): KIT UDHAYAM 2027 College Event Plan Walkthrough*

---

## 1. How to Launch & Explore the Application

- **Live Deployed Web App:** Open [https://nandhini-rsk.github.io/Volopay_assignment/](https://nandhini-rsk.github.io/Volopay_assignment/) in any modern web browser (Chrome, Safari, Edge, Firefox). The interface is self-contained with zero external API dependencies.
- **Local Browser Execution:** Simply double-click [`index.html`](file:///index.html) to run locally in your browser.
- **Local Development Server:**
  ```bash
  python -m http.server 8080
  # Open in browser: http://localhost:8080/index.html
  ```

---

## 2. Mathematical Rigor & Metric Denominators

Every high-level indicator is grounded in exact, verifiable denominators:

1. **Total Unique Records (44):** Strict deduplication by `(source_type, source_id)` across all deliveries (30 calls, 14 meetings).
2. **Transcript Evidence Coverage (40.91% post-update, 38.64% pre-update):**
   - *Formula:* Total Usable Transcripts (18) / Total Ingested Records (44).
   - *Calls Usable Coverage:* 10 / 30 (33.33%).
   - *Meetings Usable Coverage:* 8 / 14 (57.14%) post-update (7 / 14 pre-update before M07 arrives).
   - *Integrity Note:* Denominators deliberately include silent intake records without transcripts to prevent deceptive performance inflation.
3. **Telephony Connection Rate (36.67%):**
   - *Formula:* Calls with `is_connected=true` (11) / Total Calls (30).
   - *Substantive Dialogue Rate:* Only 8 of 30 calls resulted in completed two-way sales discussions (26.67%), highlighting the crucial delta between telephony carrier signaling and true customer discovery.
4. **Strict Role Separation:**
   - *Call SDRs (5 Verified Reps):* Arun (15 calls), Leela (8 calls), Meera (5 calls), Kiran (1 call), Dev (1 call).
   - *Calendar Coordinators (10 Distinct Emails):* Organizers (`team06`–`team14` and `arun@example.com`) are administrative calendar coordinators, not confirmed sales quota holders or meeting attendees.

---

## 3. Five-Queue Routing Architecture

All inbound records are categorized into five operational action queues:

- **`Deal Next Steps` (7 Records):** Active commercial opportunities requiring proposals, quotes, or agreed follow-up calls (M01, M03, C03, C05, C07, C08, M06).
- **`Customer Follow-up` (4 Records):** Existing client account management, cardholder migration, and platform bug resolutions (M04, M07, M09, M06).
- **`Sales Coaching` (4 Records):** Unsolicited cold call pushback, phone gatekeeper transfers, identity mismatches, and compliance boundaries (C01, C06, C09, C10).
- **`Internal / Vendor` (2 Records):** External technology vendor evaluations and internal operations training (M02 LedgerBridge e-invoicing provider, M10 billing walkthrough).
- **`Human Review` (1 Record + Silent Intake):** Ambiguous records requiring manual triage (C02 gatekeeper transfer, C04 misdirected message, and short silent dials).

---

## 4. Three Critical Findings from Source Evidence

1. **Vendor Misclassification in Meeting M02:**
   - *Observation:* Titled `"LedgerBridge / SpendNest discussion"`, automated CRM scrapers would misclassify this meeting as a prospective customer opportunity.
   - *Transcript Evidence:* `M02, Turn 1–2` (*"electronic invoicing... Supplier A: technical integration"*) and `Turn 30` (*"commercial relationship is between SpendNest and LedgerBridge"*).
   - *Operational Resolution:* Routed to `Internal / Vendor` to prevent false sales pipeline inflation.
2. **Telephony Identity Discrepancy & Boundary Respect (C06, C09, C10):**
   - *Observation:* In C06, metadata logs the representative as `Meera`, but the caller introduces himself as `"Ravi here"`. In C09, contact Vedant refers SpendNest to business head Rishabh but strictly forbids using his name. In C10, contact Aniket requests a brief via messaging but strictly forbids follow-up phone calls.
   - *Transcript Evidence:* `C06` (*"Ravi here"*), `C09` (*"No, please don't use my name"*), `C10` (*"No. I said I will contact you"*).
   - *Operational Resolution:* Added caller discrepancy tags and boundary enforcement flags to safeguard brand reputation and prevent compliance violations.
3. **Deceptive UI Workarounds Masking Bugs in Meeting M07 (Revision 2):**
   - *Observation:* During screen-share discovery, Customer A demonstrates four platform defects. The multi-step invoice review workaround masked an unresolved upload bug, and amount persistence carried over INR 18,200.
   - *Transcript Evidence:* `M07 Turn 15` (*"The workaround does not mean the direct upload issue has been resolved"*) and `Turn 21–24` (previous amount persists in next item).
   - *Operational Resolution:* Created a `"Product Defect Alert"` badge in Customer Follow-up, escalating tickets directly to engineering.

---

## 5. Deliberately Rejected Decision & Key Trade-Off

- **Decision Considered & Rejected:** Fabricating synthetic pipeline currency totals or win probabilities via regex/NLP extraction of numbers mentioned in transcripts (e.g. guessing INR 10–13 Lakh in M03 or USD 65,000 in M01).
- **Why Rejected:** `DATA_CONTRACT.md` explicitly specifies that no CRM deal table exists. Extrapolating financial numbers from unstructured text creates deceptive phantom revenue.
- **Accepted Trade-Off:** We present qualitative customer budget bands as context and empower managers with manual routing overrides rather than publishing ungrounded financial figures.

---

## 6. Reproducing the 6 Data Contract Replay Steps

The application includes an automated test runner in the **🧪 Replay Verification Lab** tab verifying all 6 data contract requirements:

1. **Initial Import:** Loads `01_initial.json`. Ingests 44 unique records and 17 usable transcripts. M07 transcript is withheld (0 turns).
2. **Shuffled Ingestion:** Re-ingests `01_initial.json` in randomized order. The unique record count remains strictly at **44** (proving zero duplicate inflation).
3. **Manual Route Override:** Manager updates M07 route to `Customer Follow-up`.
4. **Update Batch:** Ingests `02_update.json`. Revision 2 applies to M07, turns increase from 0 to 27, usable transcripts rise to **18**, and **the manual M07 route survives intact**.
5. **Stale Replay:** Ingests `01_initial.json` (Revision 1) again. Correctly rejected because $\text{rev } 1 \le \text{rev } 2$. M07 keeps its 27 turns.
6. **Persistence:** State reloads from `localStorage` verify that all 44 records and manual route overrides persist across browser reloads.

---

## 7. Part B: College Event Summary (KIT UDHAYAM 2027)

- **Institution:** Kalaignarkarunanidhi Institute of Technology (KIT), Coimbatore.
- **Event Name:** **KIT UDHAYAM 2027** (Upcoming Edition Planning & Proposal Blueprint, February 2027, Day 1 & Day 2; verified fest heritage via `kitudhayam.in`).
- **Scale:** 3,500+ attendees from 120+ colleges across South India.
- **Deliverables:** Complete 10-page event planning blueprint in Word DOCX ([`growth_associate/KIT_Udhayam_2027_Event_Plan.docx`](file:///growth_associate/KIT_Udhayam_2027_Event_Plan.docx)) and PDF ([`growth_associate/KIT_Udhayam_2027_Event_Plan.pdf`](file:///growth_associate/KIT_Udhayam_2027_Event_Plan.pdf)).

---

## 8. Deliverables Directory

- `index.html`: Fully functional single-page SaaS application ready for GitHub Pages.
- `exports/manifest.json` & `exports/manifest.csv`: Machine-readable manifests.
- `exports/analyses/`: 44 individual Markdown analysis files.
- `exports/brief/manager_brief_2026-08-21.md`: Grounded Executive Manager Brief.
- `exports/Revenue_Intelligence_Inbox_Presentation.pptx` & `.pdf`: 5-slide presentation.
- `growth_associate/KIT_Udhayam_2027_Event_Plan.pdf` & `.docx`: Comprehensive 10-page event plan.
- `videos/README.md`: Video walkthrough documentation and hosting instructions.
