## **ID:** NOTIF-0003 Organizer announcement appears for registered users

### Summary
Validates that organizer announcements are delivered to users registered for the target competition.

### Priority
Medium

### Preconditions
- Tester A is authenticated as an approved organizer.
- Tester B is registered for a competition owned by Tester A.
- Announcement sending is available in the organizer competition workflow.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Organizer opens the target competition management page. | The competition management page loads. |
| 2 | Send an announcement with a short user-safe message. | The announcement is accepted and sent to the target audience. |
| 3 | Registered mathlete opens `/notifications`. | A new announcement notification appears. |
| 4 | Review the message content. | The notification shows readable announcement text and competition context. |
| 5 | An unregistered mathlete checks notifications if available. | The unregistered user does not receive the targeted announcement. |

### Post-conditions
- Registered users have one announcement notification.

### Notes
- Current app routes: `/organizer/competition/[competitionId]` and `/notifications`.
- Related current coverage: `tests/notifications/dispatch.test.ts`.
