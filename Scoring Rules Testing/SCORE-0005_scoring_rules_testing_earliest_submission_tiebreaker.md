## **ID:** SCORE-0005 Tie-breaker ranks earliest final submission higher

### Summary
Validates that participants with equal scores are ordered by earliest final submission time when the tie-breaker is enabled.

### Priority
Medium

### Preconditions
- A completed competition has at least two participants with the same score.
- The participants submitted at different final submission times.
- Leaderboard or scoring preview is available to the organizer.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the competition scoring or leaderboard view. | The tied participants are visible in the result set. |
| 2 | Compare the tied participants' scores. | Scores are equal. |
| 3 | Compare their final submission times. | One participant has an earlier final submission time. |
| 4 | Review the displayed ranking. | The participant with the earlier final submission ranks higher. |
| 5 | Publish or view the participant-facing leaderboard if applicable. | The same tie-breaker order is shown consistently. |

### Post-conditions
- Tie-breaker ranking remains deterministic for tied scores.

### Notes
- Related current coverage: `tests/scoring/policies.test.ts`, `tests/leaderboard/visibility.test.ts`, and `tests/scoring/summary.test.ts`.
