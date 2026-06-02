## **ID:** CAL-0001 Calendar displays scheduled competitions

### Summary
Validates that the mathlete calendar displays scheduled competitions and presents their date context correctly.

### Priority
Medium

### Preconditions
- Tester is authenticated as a mathlete with a complete profile.
- At least one scheduled competition is visible to the tester.
- Tester can access `/mathlete/competition/calendar`.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/competition/calendar`. | The competition calendar page loads. |
| 2 | Find the date containing a known scheduled competition. | The competition appears on or near the correct date according to the displayed timezone. |
| 3 | Select or open the scheduled competition from the calendar if supported. | The competition detail or summary information is shown. |
| 4 | Check the current date marker. | The current date is visually distinguishable from other dates. |

### Post-conditions
- No registration or attempt state is changed by viewing the calendar.

### Notes
- Current app route: `/mathlete/competition/calendar`.
- Related current coverage: `tests/ui/competition-calendar.test.tsx` and `tests/dashboard/calendar-widget.test.tsx`.
