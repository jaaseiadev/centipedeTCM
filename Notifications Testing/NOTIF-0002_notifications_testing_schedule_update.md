## **ID:** NOTIF-0002 Mathlete receives schedule update notification

### Summary
Validates that a registered mathlete receives a readable notification when a competition schedule is updated.

### Priority
Medium

### Preconditions
- Tester is registered for a scheduled competition.
- An approved organizer can edit the competition schedule.
- Notifications are enabled in the test environment.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Organizer updates the scheduled competition time using the organizer competition workflow. | The schedule update is saved. |
| 2 | Tester opens `/notifications` or the notification dropdown. | The notification view loads without error. |
| 3 | Locate the schedule update notification. | The message clearly identifies the competition and schedule change context. |
| 4 | Refresh the notification view. | The same update is not duplicated repeatedly for one schedule change event. |

### Post-conditions
- The mathlete has one readable notification for the schedule update event.

### Notes
- Current app routes: `/notifications` and `/organizer/competition/[competitionId]`.
- Related current coverage: `tests/notifications/dispatch.test.ts`, `tests/notifications/sql-contracts.test.ts`, and `tests/competition/edit-route.test.ts`.
