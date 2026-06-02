## **ID:** HIST-0005 Mathlete cannot view unrelated competition history

### Summary
Validates that a mathlete cannot access another participant's private competition history or result details.

### Priority
High

### Preconditions
- Tester A and Tester B are separate mathlete accounts.
- Tester A has a past competition result.
- Tester B did not participate in Tester A's past competition result context.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Tester A opens their history and records a result page URL if visible. | Tester A can access their own history. |
| 2 | Tester A signs out. | The session ends. |
| 3 | Tester B signs in and opens the same result URL. | Tester B is blocked, redirected, or shown no unauthorized result data. |
| 4 | Tester B opens `/mathlete/history`. | Tester B sees only their own past competitions. |
| 5 | Tester B searches for Tester A's private result data. | Tester A's private result data is not exposed. |

### Post-conditions
- Participant history remains scoped to the correct user.

### Notes
- Current app route: `/mathlete/history`.
- Related current coverage: `tests/submission/visibility.test.ts` and `tests/auth/routing.test.ts`.
