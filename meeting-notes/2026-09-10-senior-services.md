# Senior Services — Sep 10, 2026

Attendees: Karen Kolb, Syed, Talha Qureshi, Genise Heard, Nick Atoyebi.
Subject: CAS Supervisor dashboard walkthrough (first review with Syed), plus the SLA clock and caseworker logging.

---

## Applied to `index.html`

### Team Performance — tiles

| Was | Now | Why |
| --- | --- | --- |
| Cases: Total Assigned | **Cases: Currently Assigned** | "Total" read as a year total. Karen wants both — this tile is the live queue, the year numbers moved to the cumulative row. |
| Cases: Overdue | **Cases: Exceeded Priority Timeframe** | Karen: avoid "expired" — "in many instances means someone's dead." Landed on exceeded / priority timeframe. |
| Cases: Pending Recommendation / Submission | *unchanged* | Matches the wording already on the CAS staff dashboard. |
| Cases: Closed This Month | **Case Performance** (split tile) | Now closed-against-referred as a count and a percentage, this month on the left and year to date on the right. |

### Team Performance — new second row

- **Cumulative — Year to Date**: referred / closed / pending with percentages, resets January 1.
- **Contractual: First Visit Within Priority Timeframe** — this month and YTD.
- **Contractual: Case Completed Within Priority Timeframe** — this month and YTD.

Both contractual measures were missing entirely from the dashboard.

### Team Performance by Caseworker

Rebuilt with grouped two-row headers so the extra columns fit:

- **Current Queue** — Assigned · Past Priority TF · Pending Rec/Submission · Pending Supervisor Review · Sent Back
- **Year to Date** — Referred · Closed · Closed %
- **Contractual Measures (YTD)** — 1st Visit in TF · Completed in TF

Per Talha, added as columns on the right rather than as another table.

### Needs Supervisor Action

"Needs My Action" → **Needs Supervisor Action**. Every "my" on this dashboard is now "supervisor" — it is a supervisor dashboard, so "my" was ambiguous.

The combined *Cases: Sent Back by DFSS* tile is **split in two**, giving four tiles here matching four tiles up top:

| Was | Now |
| --- | --- |
| Cases: Unassigned | **Cases: Referrals (Unassigned)** |
| Cases: Pending My Review | **Determinations: Pending Supervisor Review** (tile) / **Determinations: Pending Supervisor Review of Recommendation** (table) |
| Sent Back by DFSS: Determinations | **Determinations Rejected by DFSS — Requiring Revision** |
| Sent Back by DFSS: Closeouts | **Sent Back by DFSS: 311 Review Page Closeout** |

The last two are deliberately worded differently because ECM itself words them differently: the determination section has **Approve / Reject**, the 311 review page Closeout Review tab has **Send Back**. Syed asked that 311 be named explicitly so it is obvious which page a row came from. General theme from Karen: name the exact page or button.

### All four action tables

- **Days Waiting** on every table, not just Unassigned (Syed).
- **Pri** → **Priority**, and the priority pill is wider and more prominent (Karen: an oval, not a circle).
- Rows waiting **more than three days** get a red `!` flag — Karen: "look here, look here, these are the assignments you have to make."

### DFSS dashboard — CAS Supervisor Performance (new)

The layered approach Syed proposed and Karen agreed to: the supervisor dashboard reports on the team, the DFSS dashboard reports on the supervisors. New table covering average days to assign by priority code, average days to review a recommendation (month and YTD), and what is sitting in each supervisor's queue right now including the oldest item.

This exists because nothing today tells DFSS that a recommendation has sat unreviewed for four days on an emergency case.

---

## Open — needs an answer before the next build

1. **City of Chicago holiday list.** The clock excludes weekends but not holidays, and we just ran through one. Karen is asking Tiffany for the list. Two things needed: the City's observed days, and whether CAS / Salvation Army observes the same schedule (Karen's read: probably not — e.g. they are closed the day after Thanksgiving; Pulaski Day is likely City-only). Once we have it, code them as recurring rules ("Thanksgiving and the day after," "January 1") rather than hard dates per year.
2. **On-screen *Time in Queue* counter on the 311 page.** Tiffany reported a case showing over-SLA within a minute of referral (SR from Sep 8, 9:57 AM referral, 9:58 AM email). The clock reads correctly now — 2 days 3 hours — and the reports and these dashboards were rebuilt with the weekend timer, but that page's counter has not been touched in years. Being reviewed separately. Karen is asking Tiffany to resend the screenshot.
3. **Caseworker logging quality.** On the case we pulled up: the appointment was logged as the same day at midnight rather than the actual visit time, and the communication method was marked both phone *and* in-person. Karen wants to know whether this is isolated to Mariela or across the board before deciding between a recorded one-on-one and a full retraining — she does not want another all-hands training. Talha to pull the list. Worth noting the mock data now reflects this hypothesis: Mariela is the outlier on both contractual measures. Replace with real numbers once we have them.
4. **"Cases: Currently Assigned" wording.** Talha said he would come back with a better version. Current label is a placeholder that at least distinguishes the live queue from the year total.
5. **Label drift between dashboards.** The CAS *staff* dashboard still says "Cases: Total Assigned" and "Cases: Overdue." Karen only reviewed the supervisor page, so those were left alone — but they now disagree with the supervisor page. Needs a decision.
6. **Supervisor reporting.** The report today covers CAS as a whole with no supervisor section. Karen wants days-waiting built into a supervisor report, not just the dashboard.

## Housekeeping

- Sep 17 meeting cancelled. Next meeting **Thursday Sep 24** — Talha to send the updated draft ahead of time so it is not reviewed cold.
- Karen needs a printed **seen/unseen report** after the 15th (by Friday of that week).
- Remove the "Chris Demo" test case from the live submitted queue — Talha's, not real data.
- Senior Fest Thu Sep 18; Nick attending. Genise noted DTI has not been notified in ~3 years.
