## **ID:** DISP-0002 Organizer resolves dispute with notes

### Summary
Validates that an organizer can resolve a submitted dispute with resolution notes and that the participant receives the updated dispute state.

### Priority
Medium

### Preconditions
- A mathlete has submitted a dispute for a completed competition.
- Tester is authenticated as the organizer who owns the competition.
- The organizer can access the relevant competition history or result management workflow.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Organizer opens the relevant completed competition from `/organizer/history`. | The completed competition detail or results view loads. |
| 2 | Open the dispute submitted by the mathlete. | The dispute reason and context are visible to the organizer. |
| 3 | Attempt to resolve the dispute without notes if notes are required. | The form blocks resolution or asks for resolution notes. |
| 4 | Enter resolution notes and accept or reject the dispute. | The dispute status changes and the notes are saved. |
| 5 | Mathlete checks the dispute or notification state. | The mathlete can see the updated status or receives a notification if supported. |

### Post-conditions
- The dispute has a resolved status and resolution notes.
- Any score recalculation occurs only when supported by the accepted resolution path.

### Notes
- Current app route: `/organizer/history`.
- Related current coverage: `tests/submission/routes.test.ts`, `tests/leaderboard/routes.test.ts`, and `tests/notifications/dispatch.test.ts`.
