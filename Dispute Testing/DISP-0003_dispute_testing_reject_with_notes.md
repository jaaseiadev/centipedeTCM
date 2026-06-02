## **ID:** DISP-0003 Organizer rejects dispute with notes

### Summary
Validates that an organizer can reject a dispute and provide resolution notes visible through the supported result workflow.

### Priority
Medium

### Preconditions
- A mathlete has submitted a dispute.
- Tester is authenticated as the organizer who owns the competition.
- The dispute is pending review.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Organizer opens the completed competition result management view. | Pending disputes are accessible. |
| 2 | Open the submitted dispute. | The dispute reason and problem context are visible. |
| 3 | Select reject without notes if notes are required. | The form blocks resolution or asks for notes. |
| 4 | Enter rejection notes and confirm rejection. | The dispute status changes to rejected and notes are stored. |
| 5 | Mathlete opens result or notification context. | The rejected status or notification is visible if supported. |

### Post-conditions
- The dispute is rejected.
- The score remains unchanged unless another accepted dispute changes it.

### Notes
- Current app route: `/organizer/history`.
- Related current coverage: `tests/submission/routes.test.ts` and `tests/notifications/dispatch.test.ts`.
