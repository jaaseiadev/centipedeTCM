## **ID:** REG-0005 Withdrawal after attempt exists is blocked

### Summary
Validates that a mathlete cannot withdraw from a competition after an attempt has already been created.

### Priority
High

### Preconditions
- Tester is authenticated as a registered mathlete.
- The competition has started or allowed arena entry.
- Tester has already entered the arena so an attempt exists.
- The competition still displays registration details.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the registered competition detail page. | The page shows registered or active attempt state. |
| 2 | Look for withdrawal controls. | Withdrawal is disabled, hidden, or marked unavailable after an attempt exists. |
| 3 | Attempt withdrawal if any action remains available. | The system blocks withdrawal and explains that an attempt already exists. |
| 4 | Refresh the page. | The registration and attempt state remain unchanged. |
| 5 | Reopen the arena if allowed. | The existing attempt is still associated with the mathlete. |

### Post-conditions
- The registration remains active.
- The existing attempt is not deleted by withdrawal attempts.

### Notes
- Current app route: `/mathlete/competition/[competitionId]`.
- Related current coverage: `tests/registrations/validation.test.ts` and `tests/submission/routes.test.ts`.
