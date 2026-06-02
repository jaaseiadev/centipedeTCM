## **ID:** LEAD-0002 Scheduled leaderboard is hidden before publish

### Summary
Validates that scheduled competition leaderboard results are not exposed to participants before organizer publication.

### Priority
High

### Preconditions
- Tester is authenticated as a mathlete who participated in a completed scheduled competition.
- The competition has submissions or computed scores.
- Organizer has not published the leaderboard.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/history`. | The history page displays the completed competition. |
| 2 | Open the completed competition result area. | The page does not show unpublished leaderboard ranks or full result data. |
| 3 | Review the visible submission state. | Only allowed state, such as submitted or pending publication, is shown. |
| 4 | Confirm no direct leaderboard data is displayed. | Scores and ranks remain hidden until publication. |

### Post-conditions
- Unpublished leaderboard data remains hidden from the participant.

### Notes
- Current app route: `/mathlete/history`.
- Related current coverage: `tests/leaderboard/visibility.test.ts` and `tests/submission/visibility.test.ts`.
