## **ID:** ARENA-0003 Arena entry is disabled before server start time

### Summary
Validates that a scheduled competition cannot be entered before the server-side start time.

### Priority
High

### Preconditions
- Tester is authenticated as a registered mathlete.
- A scheduled competition exists with a future start time.
- Tester can open the competition detail page before start.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the future scheduled competition detail page. | The page shows the competition schedule. |
| 2 | Review the arena entry action. | The entry action is disabled, hidden, or marked unavailable before start. |
| 3 | Try to open the arena route directly if known. | Direct access is blocked before the server start time. |
| 4 | Wait until the competition reaches the allowed start time or use prepared live test data. | The entry action becomes available only after the valid state change. |
| 5 | Enter after start. | Arena access succeeds only once the timing condition is satisfied. |

### Post-conditions
- No attempt is created before valid start time.

### Notes
- Current app route: `/mathlete/competition/[competitionId]`.
- Related current coverage: `tests/competition/scheduled-start.test.ts` and `tests/arena/routes.test.ts`.
