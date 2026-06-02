## **ID:** CAL-0003 Current date is highlighted correctly

### Summary
Validates that the calendar visually distinguishes the current date from other dates.

### Priority
Low

### Preconditions
- Tester is authenticated as a complete mathlete.
- Tester can access `/mathlete/competition/calendar`.
- Tester knows the current local date.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/competition/calendar`. | The calendar page loads. |
| 2 | Locate today's date in the calendar. | The current date has a distinct visual highlight. |
| 3 | Compare nearby dates. | Other dates do not use the same current-date highlight unless selected state intentionally differs. |
| 4 | Navigate to another month and return if supported. | The current date highlight returns correctly. |
| 5 | Refresh the page. | Today's date remains highlighted. |

### Post-conditions
- Calendar data and competition state remain unchanged.

### Notes
- Current app route: `/mathlete/competition/calendar`.
- Related current coverage: `tests/ui/competition-calendar.test.tsx`.
