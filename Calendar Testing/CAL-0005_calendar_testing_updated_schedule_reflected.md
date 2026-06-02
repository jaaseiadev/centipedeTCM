## **ID:** CAL-0005 Updated schedule is reflected on calendar

### Summary
Validates that a competition schedule update is reflected on the mathlete calendar after refresh or data reload.

### Priority
Medium

### Preconditions
- Tester is authenticated as a complete mathlete.
- An approved organizer can update a visible scheduled competition.
- The mathlete can access `/mathlete/competition/calendar`.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Mathlete opens the calendar and notes the event date and time. | The scheduled event is visible. |
| 2 | Organizer updates the competition schedule. | The schedule update is saved successfully. |
| 3 | Mathlete refreshes `/mathlete/competition/calendar`. | The event moves to the updated date or time. |
| 4 | Open the competition detail page. | The detail page matches the updated calendar schedule. |
| 5 | Check notifications if schedule notification is enabled. | A schedule update notification may be visible to registered users. |

### Post-conditions
- Calendar view reflects the latest schedule.

### Notes
- Current app route: `/mathlete/competition/calendar`.
- Related current coverage: `tests/competition/edit-route.test.ts` and `tests/ui/competition-calendar.test.tsx`.
