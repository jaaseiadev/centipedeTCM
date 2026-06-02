## **ID:** HIST-0002 Hidden scheduled leaderboard shows allowed submission state

### Summary
Validates that a mathlete can see allowed post-competition state without seeing unpublished leaderboard details.

### Priority
Medium

### Preconditions
- Tester is authenticated as a mathlete.
- Tester has completed a scheduled competition.
- The organizer has not published results for that competition.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/history`. | The completed competition appears in the history list. |
| 2 | Open the completed competition details. | The page displays allowed information such as participation or submission state. |
| 3 | Look for score, rank, and full leaderboard values. | Unpublished score, rank, and leaderboard values are hidden. |
| 4 | Return to history. | The history list remains accessible. |

### Post-conditions
- Unpublished leaderboard data remains protected.

### Notes
- Current app route: `/mathlete/history`.
- Related current coverage: `tests/submission/visibility.test.ts` and `tests/leaderboard/visibility.test.ts`.
