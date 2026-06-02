## **ID:** HIST-0003 Organizer views past competitions

### Summary
Validates that an organizer can view competitions they previously managed from the organizer history workflow.

### Priority
Medium

### Preconditions
- Tester is authenticated as an approved organizer.
- Organizer owns at least one completed competition.
- Tester can access `/organizer/history`.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/history`. | Organizer history page loads. |
| 2 | Locate a completed competition owned by the organizer. | The competition appears in the history list. |
| 3 | Open the competition history details. | Details show allowed organizer result or management context. |
| 4 | Return to the history list. | The list remains accessible. |
| 5 | Check for unrelated organizers' competitions if test data exists. | Competitions owned by other organizers are not shown. |

### Post-conditions
- Competition state remains unchanged.

### Notes
- Current app route: `/organizer/history`.
- Related current coverage: `tests/leaderboard/routes.test.ts` and `tests/competition/organizer-management.test.ts`.
