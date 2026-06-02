## **ID:** DISP-0004 Accepted dispute recalculates affected score

### Summary
Validates that accepting a dispute updates affected score data and notifies or reflects the change for the mathlete.

### Priority
High

### Preconditions
- A mathlete has a submitted dispute that can affect score.
- Organizer is authenticated and owns the competition.
- Original score and rank are known before resolution.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Organizer opens the pending dispute. | Dispute context and current score state are visible. |
| 2 | Accept the dispute with resolution notes. | The dispute status changes to accepted. |
| 3 | Wait for score update or refresh results. | Affected score is recalculated according to the accepted resolution. |
| 4 | Open the leaderboard or result page. | Updated score or rank is reflected where published. |
| 5 | Mathlete checks result or notifications. | The affected mathlete can see the updated state or notification if supported. |

### Post-conditions
- Accepted dispute has notes and updated scoring impact.

### Notes
- Related current coverage: `tests/leaderboard/routes.test.ts`, `tests/scoring/summary.test.ts`, and `tests/notifications/dispatch.test.ts`.
