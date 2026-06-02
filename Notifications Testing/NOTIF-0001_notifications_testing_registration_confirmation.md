## **ID:** NOTIF-0001 Mathlete receives registration confirmation notification

### Summary
Validates that a mathlete receives a readable notification after successful competition registration.

### Priority
Medium

### Preconditions
- Tester is authenticated as a mathlete with a complete profile.
- Tester can register for an eligible competition.
- Notifications are enabled in the application environment.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Register for an eligible competition. | Registration succeeds and the page shows the registered state. |
| 2 | Open the notifications page or notification dropdown. | A notification area opens without an error state. |
| 3 | Locate the registration notification. | The notification text identifies the competition or registration event in readable user-facing language. |
| 4 | Refresh the notification view. | The same event does not create duplicate notifications for one registration action. |

### Post-conditions
- The registration confirmation notification remains available until read or cleared by supported UI behavior.

### Notes
- Current app routes: `/notifications` and `/settings/notifications`.
- Related current coverage: `tests/notifications/dispatch.test.ts`, `tests/notifications/notification-components.test.tsx`, and `tests/registrations/register-route-notifications.test.ts`.
