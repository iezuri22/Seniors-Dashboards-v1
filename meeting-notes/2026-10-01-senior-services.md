# Senior Services — Oct 1, 2026

Attendees: Karen Kolb, Syed, Nikki Proutsos, Talha Qureshi, LaWanda (joined late).
Subject: The CAS Supervisor dashboard's new performance row, the Salvation Army holiday schedule, and the caseworker data-quality analysis (July–September).

---

## Applied to `index.html`

### CAS Supervisor — Team Performance tiles

| Was | Now | Who |
| --- | --- | --- |
| Contractual: First Visit Within Priority Timeframe | **CAS Goal 1: First Visit Within Priority Timeframe** | Syed |
| Contractual: Case Completed Within Priority Timeframe | **CAS Goal 2: Case Completed Within Priority Timeframe** | Syed |

### CAS Supervisor — Team Performance by Caseworker

| Was | Now | Why |
| --- | --- | --- |
| Contractual Measures (YTD) | **Performance Metrics (YTD)** | Syed. Kept "(YTD)". The sub-columns stay "1st Visit" / "Completed", as Syed asked. |
| Exceeded TF | **Overdue** | Karen: staff won't know what "TF" means. The CAS staff dashboard already says "Overdue", so this keeps them consistent. |
| *(new)* | **Referred %** after Referred | Syed: each caseworker's share of all referrals this year (e.g. Marlo 231 / 588 = 39%). It shows who is being assigned the most cases. |

**"Assigned" stays.** Karen floated "Active". Nikki said "Active" is vaguer, and the group header already says Current Queue, so the label is unchanged. Karen confirmed that Assigned is the live queue and Sent Back goes down as cases are dealt with; neither is a running total. This closes open item 4 from Sep 10.

### Holiday wording (tooltip + footer)

The footer now says that holidays come from the CAS provider's schedule, not the City's, and that they pause every clock, Emergency included.

### Readability pass

Karen raised font size and contrast for older adults and people with vision impairments. Grey text is harder to read than dark blue or black.

Talha's answer: this mock-up is outside the ECM theme. Production has to meet ECM's accessibility standards for minimum font size and contrast. He also offered to make the numbers bigger and use less spacing, and Karen said that is her preference.

What changed in the mock-up:
- Muted text went from `#6b7280` to `#374151`.
- Nothing is smaller than 12px.

---

## Decisions

- **Holidays pause the Emergency clock too.** Karen's example: an Emergency referral at 5 PM on the Friday before Memorial Day is due by 5 PM Tuesday.
- **The holiday schedule is per provider, not per site.** ECM's holiday setup applies to a whole site. Salvation Army's schedule differs from the City's:
  - Salvation Army closes the Friday after Thanksgiving and on Employee Appreciation Day.
  - Salvation Army does not close on Indigenous Peoples' Day.
  - The schedule therefore gets tied to the CAS provider, so a second provider (or the ICAS providers later) can carry its own.
  - Karen added a holidays section to the front page of the scopes, so providers fill it in.
- **Negative visit times are floored at 0.** Some cases are DFSS-initiated special assignments: Karen emails CAS, the visit happens, and only afterwards can the case be entered in ECM. Those show the visit before the referral.
  - Time-to-visit and time-to-close figures count them as 0 hours. Nothing counts against the caseworker, and nothing inflates the averages.
  - A run of zeros from one person points to a data-entry problem, not special assignments.
- **The 12 AM fix is the only restriction for now.** 150 of 268 appointments from July through September (56%) had no real visit time; the system defaults it to 12 AM. Almost all of the bad data is that midnight default, and it is concentrated in a few caseworkers.
  - ECM will add a rule on Save that blocks 12:00 AM as an appointment time. The field can't be left blank.
  - No 9-to-5 window, no holiday block, and no "visit must be after referral" rule. Emergency after-hours visits and special assignments are real.
  - Re-check the data after the fix. Karen called tighter rules the "nuclear option", held in reserve if training doesn't work.
- **The team-vs-individual view is fine.** Karen asked whether team and individual numbers can share a page. Only the supervisor sees this page; the staff dashboard shows only that caseworker's own cases. Nikki agreed that's safe.
- **Compliance by priority level stays off the data-quality analysis.** It belongs in dashboards and reporting.

## Open

1. **Caseworker selector.** Karen asked to switch the page to one caseworker so she can supervise them one-on-one. The mock-up isn't built for it yet.
   - Talha: the top tiles stay team-level.
   - The bottom tables (rejected, sent back, pending review) would filter to the person selected.
2. **Data-quality analysis needs a team-total row.** Karen wants a Team Total on the "past appointments never updated" by-month table (row 17), so it visibly ties to the 59 total. That is 59 of 268 appointments with no outcome recorded.
3. **Retraining.** Marlo has consistently not recorded visit times. Mariela improved from about 80% to about 50% and still needs to do better.
   - Karen will take the data to the next CAS team call and is bringing Syed. Syed needs to understand the analysis thoroughly before then.
4. **Label drift — still partly open.**
   - The supervisor tile still says *Cases: Exceeded Priority Timeframe*. Karen chose that wording on Sep 10.
   - The caseworker table now says *Overdue*, which matches the staff dashboard.
   - Decide whether the tile should follow.
5. **Reporting.** DFSS's SPI team is asking about reports. Karen wants to pivot back to reports soon after the dashboards close out. On next meeting's agenda.

## Housekeeping

- **ECM update (single sign-on):** cutover the weekend of Oct 17; go-live Monday Oct 19.
  - Syed is Senior Services' tester. Talha emails him to set time for Oct 2.
  - There are separate sign-in flows for City staff and for external agencies.
- **CAS Seen Unseen Report:** Karen needs it. Syed runs it himself (it's named "CAS Seen Unseen Report") and puts 15 minutes on Karen's calendar to go over it.
- **Senior Fest** was rained on for the first time in decades, but turnout was good.
  - Karen suggested ECM sponsor next year's event and be recognized. Talha to raise it with Roland.
  - ECM gets invited from the start next year.
