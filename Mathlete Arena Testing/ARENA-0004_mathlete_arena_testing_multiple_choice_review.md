## **ID:** ARENA-0004 Mathlete answers multiple choice question and reviews summary

### Summary
Validates that multiple choice answers can be selected, retained, and reviewed before final submission.

### Priority
High

### Preconditions
- Tester is authenticated as a registered mathlete.
- The live competition includes at least one multiple choice problem.
- Tester can enter the arena.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Enter the live competition arena. | The arena displays problem navigation. |
| 2 | Open a multiple choice problem. | Choices are shown as user-facing option labels. |
| 3 | Select one answer choice. | The selected choice is visibly marked. |
| 4 | Navigate away and return to the problem. | The selected answer remains retained. |
| 5 | Open the review summary. | The selected multiple choice answer is represented in the summary before final submission. |

### Post-conditions
- The answer remains editable until final submission or timer expiration.

### Notes
- Current app route: `/mathlete/competition/[competitionId]`.
- Related current coverage: `tests/ui/arena-experience.test.tsx` and `tests/ui/review-submission.test.tsx`.
