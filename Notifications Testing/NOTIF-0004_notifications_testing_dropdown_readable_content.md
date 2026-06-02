## **ID:** NOTIF-0004 Notification dropdown shows readable content

### Summary
Validates that notification dropdown or modal content is readable, user-safe, and actionable.

### Priority
Medium

### Preconditions
- Tester is authenticated as a mathlete or organizer.
- The account has at least one notification.
- Notification dropdown or page is available.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the workspace page with notification access. | Notification entry point is visible. |
| 2 | Open the notification dropdown or modal. | Notification content appears without layout breakage. |
| 3 | Review notification title and body. | Text is readable and does not expose raw IDs or debug data. |
| 4 | Click a notification with a supported target link. | The app navigates to the relevant page or keeps the user in a valid state. |
| 5 | Close and reopen the dropdown. | Content remains available and usable. |

### Post-conditions
- No notification content is duplicated by opening the dropdown.

### Notes
- Current app routes: `/notifications` and `/settings/notifications`.
- Related current coverage: `tests/notifications/notification-components.test.tsx`.
