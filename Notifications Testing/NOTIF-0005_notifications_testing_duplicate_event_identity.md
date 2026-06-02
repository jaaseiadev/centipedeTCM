## **ID:** NOTIF-0005 Duplicate notifications are not created for same event

### Summary
Validates that repeated handling of the same event identity does not create duplicate notifications for one user.

### Priority
Medium

### Preconditions
- Tester has a registered mathlete account.
- A notification-generating event is available, such as registration confirmation.
- Tester can refresh or retry the action safely.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Perform a notification-generating action such as competition registration. | One notification appears for the event. |
| 2 | Refresh the page after the action completes. | The notification count does not increase for the same event. |
| 3 | Retry the same action if the UI allows a duplicate attempt. | The action is blocked or does not create another notification for the same identity. |
| 4 | Open `/notifications`. | Only one notification exists for the single event. |
| 5 | Trigger a different valid event. | A separate notification may be created for the different event. |

### Post-conditions
- Notification identity deduplication is preserved for repeated events.

### Notes
- Current app route: `/notifications`.
- Related current coverage: `tests/notifications/dispatch.test.ts` and `tests/notifications/sql-contracts.test.ts`.
