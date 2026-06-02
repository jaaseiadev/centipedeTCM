## **ID:** LEAD-0004 Tie-breaker order is visible on leaderboard

### Summary
Validates that leaderboard ordering visibly applies the configured tie-breaker when scores are equal.

### Priority
Medium

### Preconditions
- A completed competition has at least two participants or teams with equal scores.
- The tied entries have different final submission times.
- Leaderboard is available to the tester.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the leaderboard for the completed competition. | Leaderboard rows are displayed. |
| 2 | Locate tied entries with equal scores. | The tied entries show the same score. |
| 3 | Compare their order against submission timing. | The earlier final submission appears first if that tie-breaker is configured. |
| 4 | Refresh the page. | The tie-breaker order remains stable. |
| 5 | Check participant-facing view if results are published. | Participant-facing ranking matches the computed order. |

### Post-conditions
- Tie-breaker order remains deterministic.

### Notes
- Related current coverage: `tests/leaderboard/visibility.test.ts` and `tests/scoring/policies.test.ts`.
