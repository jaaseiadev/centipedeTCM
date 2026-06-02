## **ID:** HIST-0001 Mathlete views published past results

### Summary
Validates that a mathlete can view past competition presence and published result details from the history workflow.

### Priority
Medium

### Preconditions
- Tester is authenticated as a mathlete with at least one past competition.
- At least one past competition has published results.
- Tester can access `/mathlete/history`.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/history`. | The history page loads without redirecting away. |
| 2 | Locate a completed competition. | The completed competition appears with recognizable title or schedule information. |
| 3 | Open the competition result details if available. | The page shows allowed result details such as score, rank, or submission state. |
| 4 | Return to the history list. | The history page remains available and preserves the past competition list. |

### Post-conditions
- No score, submission, or registration state is changed.

### Notes
- Current app route: `/mathlete/history`.
- Related current coverage: `tests/submission/visibility.test.ts`, `tests/submission/summary.test.ts`, and `tests/leaderboard/visibility.test.ts`.
