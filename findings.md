# Findings – MediTrack SRS

Compared run-A and run-B (20 minutes, together).

## Disagreements and how we resolved them

| Item | A | B | Agreed answer | Why |
| --- | --- | --- | --- | --- |
| C-09 | No | Yes ? | No | R-14 only lets doctors view a schedule; nothing lets them block time |
| C-12 | No | Yes ? | No | R-10 is staff booking for people who are already present; no booking route for patients who cannot use the website (e.g. by phone) |
| C-05 | Yes ? | Yes | Yes (with a note) | Limit is stated, but "active" is undefined; see F-08 |
| C-06 | No | No ? | No | No requirement mentions user numbers |
| C-16 | No | No ? | No | "at any time" means no cut-off is defined |

## Agreed problems in the document

| # | Req | Problem | Type | Risk / worry | Suggested fix |
| --- | --- | --- | --- | --- | --- |
| F-01 | R-04 vs R-05 | Contradiction: fixed 15 minutes vs doctor-set 10–30 minutes | Contradiction | Wrong slot lengths | Make 15 min the default, changeable by doctor within 10–30 |
| F-02 | R-02 | "quickly" has no number or unit | Untestable | Monday-morning slowness | e.g. "95% of booking requests complete within 3 seconds" |
| F-03 | R-03 | "double booking" not defined; no rule for simultaneous bookings | Ambiguous / incomplete | Double bookings | Define it and require one booking to be rejected when two target the same slot |
| F-04 | R-06 | Reminder has no timing, channel or count | Incomplete | Forgotten appointments cost money | e.g. reminder 24 h and 2 h before, by SMS |
| F-05 | R-08 | "user-friendly for all age groups" is not measurable; no non-web booking path for elderly patients | Untestable / missing | Elderly patients left out | Add measurable accessibility rules and a phone booking route |
| F-06 | R-09 | "securely" is vague; no roles, no access log, no retention | Untestable / missing | Privacy breach | List roles allowed to view records, require audit log, define retention |
| F-07 | R-10 | Walk-ins covered, but emergency priority missing | Missing | Emergency walk-ins | Add a rule for urgent cases that bypass the queue |
| F-08 | R-11 | "active appointment" not defined | Ambiguous | Slot hoarding | Define active (e.g. booked and not yet completed or cancelled) |
| F-09 | R-12 | "normal working hours" not defined; no availability target | Ambiguous | Monday mornings | State clock times and an uptime percentage |
| F-10 | R-07 | "at any time" – no cut-off; does not say the slot is freed | Ambiguous / incomplete | Empty slots, lost money | Add a cancel cut-off and require the slot to be released |
| F-11 | R-13 | Refers to "clinic policy" which is not included; no payment requirements elsewhere | Incomplete | Hidden requirements | Include the policy or remove the requirement |
| F-12 | – | No requirements for clinic administrator or data protection officer | Missing | Two of five users ignored | Add user and role management, and data-protection requirements |
| F-13 | R-14 | Doctors can view schedule but cannot block time for leave or breaks | Missing | Bookings during leave | Add block-time requirement |
| F-14 | – | No load or capacity requirement (about 400 patients per week) | Missing | Monday overload | State the number of simultaneous users to support |

## Ideas to improve the checklist (v0.2)

- Items C-09 and C-12 caused disagreement, so make them more specific (for example, "Does the document let a doctor block a time range?").
- Add an item about rescheduling.
- Add an item about no-shows.
- Add an item about login and authentication.
