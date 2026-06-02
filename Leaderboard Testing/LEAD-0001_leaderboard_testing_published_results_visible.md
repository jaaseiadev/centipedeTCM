## **ID:** LEAD-0001 Published leaderboard is visible to participant

### Summary
Validates that leaderboard results become visible to a participant only after the organizer publishes results.

### Priority
High

### Preconditions
- Tester is authenticated as a mathlete who participated in a completed competition.
- The competition has scored submissions.
- Organizer has published the leaderboard or results.
- Tester can access the competition result or history page.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the mathlete history page. | Past competitions are displayed for the mathlete. |
| 2 | Select the completed competition with published results. | The result page opens. |
| 3 | Review leaderboard information. | Published score and rank information are visible to the participant. |
| 4 | Compare visible result details with the expected participant context. | The page does not expose unrelated private participant data. |

### Post-conditions
- Leaderboard visibility remains controlled by publication state.

### Notes
- Current app route: `/mathlete/history`.
- Related current coverage: `tests/leaderboard/visibility.test.ts`, `tests/leaderboard/routes.test.ts`, and `tests/submission/visibility.test.ts`.
