## **ID:** PERF-0003 Leaderboard loads within acceptable time

### Summary
Validates that leaderboard or results pages become usable within an acceptable manual testing threshold.

### Priority
Low

### Preconditions
- Tester can access a completed competition with leaderboard data.
- Browser cache and network conditions are representative of normal test conditions.
- A stopwatch or browser timing tool is available.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Start timing and open the leaderboard or result page. | Navigation begins without a broken loading state. |
| 2 | Stop timing when leaderboard rows are readable. | Leaderboard becomes usable within 3 seconds on normal local or staging connection. |
| 3 | Sort, refresh, or change available result view if supported. | The UI responds within 1 second per action. |
| 4 | Open a participant or team detail if supported. | Detail content loads without noticeable freeze. |
| 5 | Refresh the page. | Leaderboard reloads within the same acceptable threshold. |

### Post-conditions
- Leaderboard data remains unchanged by viewing it.

### Notes
- Related current coverage: `tests/leaderboard/routes.test.ts` and `tests/leaderboard/visibility.test.ts`.
