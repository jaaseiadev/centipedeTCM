## **ID:** PERF-0004 Notification dropdown opens without noticeable delay

### Summary
Validates that the notification dropdown or notification page opens quickly even when the account has several notifications.

### Priority
Low

### Preconditions
- Tester is authenticated.
- The account has multiple notifications if available.
- A timing method is available.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open a workspace dashboard. | Dashboard is usable. |
| 2 | Start timing and open the notification dropdown. | The dropdown begins opening immediately. |
| 3 | Stop timing when notification content is readable. | Content appears within 1 second on a normal local or staging connection. |
| 4 | Close and reopen the dropdown. | Reopen action remains responsive. |
| 5 | Open the full notifications page if available. | The page loads without a broken or frozen state. |

### Post-conditions
- Notification records are not duplicated by opening the dropdown.

### Notes
- Current app routes: `/notifications` and `/settings/notifications`.
- Related current coverage: `tests/notifications/notification-components.test.tsx`.
