## **ID:** CAL-0002 Calendar uses local timezone

### Summary
Validates that scheduled competition dates and times are displayed according to the user's local timezone context.

### Priority
Medium

### Preconditions
- Tester is authenticated as a complete mathlete.
- At least one scheduled competition is visible.
- The scheduled competition has a known start time.
- Tester can compare the displayed time against the expected local timezone conversion.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/competition/calendar`. | The calendar page loads. |
| 2 | Locate the scheduled competition. | The event appears on the expected local calendar date. |
| 3 | Compare the displayed event time with the expected local time. | The displayed time matches the local timezone conversion used by the app. |
| 4 | Open the competition detail from the calendar or list. | The detail page displays a consistent schedule. |

### Post-conditions
- No competition state is changed.

### Notes
- Current app route: `/mathlete/competition/calendar`.
- Related current coverage: `tests/ui/competition-calendar.test.tsx` and `tests/competition/events.test.ts`.
