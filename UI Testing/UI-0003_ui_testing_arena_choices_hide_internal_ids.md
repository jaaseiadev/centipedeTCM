## **ID:** UI-0003 Arena choices hide internal option IDs

### Summary
Validates that multiple choice answer options in the arena display user-facing labels instead of raw internal database identifiers.

### Priority
Medium

### Preconditions
- Tester is authenticated as a registered mathlete.
- The live competition includes a multiple choice problem.
- Tester can enter the arena.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Enter the competition arena. | The first problem or problem navigation loads. |
| 2 | Open a multiple choice problem. | Answer options are displayed. |
| 3 | Review each option label. | Options show readable answer text or simple labels, not raw UUIDs or internal option IDs. |
| 4 | Select an option. | The selected state is shown using user-facing text. |
| 5 | Open the review summary. | The selected answer is represented without exposing internal IDs. |

### Post-conditions
- Answer state remains editable until submission.

### Notes
- Current app route: `/mathlete/competition/[competitionId]`.
- Related current coverage: `tests/ui/arena-experience.test.tsx` and `tests/ui/review-submission.test.tsx`.
