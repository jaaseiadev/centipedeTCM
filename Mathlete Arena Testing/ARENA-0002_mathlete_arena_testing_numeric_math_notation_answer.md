## **ID:** ARENA-0002 Mathlete answers numeric question using math notation

### Summary
Validates that a mathlete can enter a numeric answer using supported math notation and retain the answer during the arena flow.

### Priority
High

### Preconditions
- Tester is authenticated as a registered mathlete.
- The target competition is live.
- The competition includes at least one numeric problem.
- Tester can enter the arena.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Enter the live competition arena. | The arena loads problem navigation and answer controls. |
| 2 | Navigate to a numeric problem. | The numeric answer input or math field is visible. |
| 3 | Enter a supported numeric value or math notation answer. | The answer appears in the input without corrupting notation. |
| 4 | Move to another problem and return. | The entered answer remains available through autosave or local answer state. |
| 5 | Open answer review before final submission. | The numeric answer appears in the review summary. |

### Post-conditions
- The answer state is retained until reset, changed, or submitted.

### Notes
- Current app route: `/mathlete/competition/[competitionId]`.
- Related current coverage: `tests/math/latex-validation.test.ts`, `tests/submission/summary.test.ts`, and `tests/ui/review-submission.test.tsx`.
