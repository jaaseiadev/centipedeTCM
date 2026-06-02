## **ID:** DISP-0005 Duplicate dispute for same problem is blocked

### Summary
Validates that a mathlete cannot create repeated duplicate disputes for the same competition problem or result item.

### Priority
Medium

### Preconditions
- Tester is authenticated as a mathlete.
- Tester has already submitted a dispute for a specific completed competition problem.
- Dispute submission remains visible for the competition context.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the completed competition result or answer review page. | Existing dispute status is visible for the disputed item. |
| 2 | Attempt to submit another dispute for the same item. | The duplicate action is disabled or rejected. |
| 3 | If a form opens, submit a second dispute reason. | The system blocks the duplicate and shows a clear message. |
| 4 | Refresh the page. | Only the original dispute is shown for that item. |
| 5 | Submit a dispute for a different eligible item if available. | A separate dispute may be allowed for a different item. |

### Post-conditions
- Only one active dispute exists per eligible item identity.

### Notes
- Related current coverage: `tests/submission/routes.test.ts` and `tests/submission/sql-contracts.test.ts`.
