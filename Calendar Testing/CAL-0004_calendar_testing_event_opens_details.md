## **ID:** CAL-0004 Calendar event opens competition details

### Summary
Validates that selecting a calendar competition event opens the correct competition detail context.

### Priority
Medium

### Preconditions
- Tester is authenticated as a complete mathlete.
- A scheduled competition appears on the calendar.
- The competition has a title and detail page.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/competition/calendar`. | The calendar displays scheduled competition events. |
| 2 | Select a known competition event. | The app opens detail content or navigates to the competition detail page. |
| 3 | Compare the detail title with the selected event. | The title matches the selected calendar event. |
| 4 | Review displayed schedule data. | The schedule is consistent with the calendar entry. |
| 5 | Return to the calendar. | The calendar remains usable. |

### Post-conditions
- No registration is created by opening the event.

### Notes
- Current app route: `/mathlete/competition/calendar`.
- Related current coverage: `tests/ui/competition-calendar.test.tsx` and `tests/competition/events.test.ts`.
