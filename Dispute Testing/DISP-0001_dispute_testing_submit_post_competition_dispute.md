## **ID:** DISP-0001 Mathlete submits post-competition dispute

### Summary
Validates that a mathlete can submit a dispute for a completed competition when answer review or result review allows disputes.

### Priority
Medium

### Preconditions
- Tester is authenticated as a mathlete.
- Tester participated in a completed competition.
- Published result or answer review is available.
- Dispute submission is enabled for the selected competition state.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the completed competition from history. | The result or answer review page loads. |
| 2 | Find a problem or result area that allows dispute submission. | The dispute action is visible only where disputes are allowed. |
| 3 | Submit the dispute form with the reason empty. | The form blocks submission or shows a required reason message. |
| 4 | Enter a clear dispute reason and submit. | The dispute is recorded and the page shows confirmation or updated dispute status. |

### Post-conditions
- A dispute record exists for organizer review.
- The score is not changed until an accepted dispute resolution changes it.

### Notes
- Current feature evidence: release notes mention answer-key review and dispute workflows.
- Related current coverage: `tests/leaderboard/visibility.test.ts`, `tests/submission/routes.test.ts`, and `tests/submission/summary.test.ts`.
