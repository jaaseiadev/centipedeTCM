## **ID:** HIST-0004 Published answer review shows score context

### Summary
Validates that a mathlete can review published answer or result context after competition completion.

### Priority
Medium

### Preconditions
- Tester is authenticated as a mathlete.
- Tester completed a competition with published results or answer review enabled.
- The competition includes submitted answers and scoring output.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/history`. | The history page lists past competitions. |
| 2 | Select the completed competition. | The result or answer review page opens. |
| 3 | Review problem answer details if available. | The page shows allowed answer review content. |
| 4 | Review score context. | Score, correctness, or rank details are visible only after publication. |
| 5 | Check for dispute action if enabled. | Dispute action appears only where allowed. |

### Post-conditions
- Result data remains unchanged unless a dispute is submitted separately.

### Notes
- Current app route: `/mathlete/history`.
- Related current coverage: `tests/submission/summary.test.ts` and `tests/submission/visibility.test.ts`.
