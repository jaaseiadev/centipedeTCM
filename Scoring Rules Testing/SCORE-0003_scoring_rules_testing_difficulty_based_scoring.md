## **ID:** SCORE-0003 Difficulty-based scoring applies correct points

### Summary
Validates that problems with different difficulty levels award the expected points when difficulty-based scoring is selected.

### Priority
High

### Preconditions
- Tester is authenticated as an approved organizer.
- A competition or scoring preview exists with easy, medium, and hard problems.
- Difficulty-based scoring is available in the scoring configuration.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/scoring`. | The scoring workspace loads. |
| 2 | Select or view difficulty-based scoring. | Difficulty level point mapping is displayed or applied. |
| 3 | Review scoring preview for correct answers by difficulty. | Easy, medium, and hard problems receive their configured point values. |
| 4 | Review preview for incorrect answers. | Incorrect answers do not receive difficulty points unless another rule explicitly applies. |
| 5 | Save or confirm the scoring setup. | The difficulty-based policy remains selected. |

### Post-conditions
- Difficulty scoring configuration remains available for the selected context.

### Notes
- Current app route: `/organizer/scoring`.
- Related current coverage: `tests/scoring/policies.test.ts` and `tests/scoring/snapshot.test.ts`.
