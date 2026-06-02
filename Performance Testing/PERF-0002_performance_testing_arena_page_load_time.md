## **ID:** PERF-0002 Arena page loads within acceptable time

### Summary
Validates that the mathlete arena page becomes usable within an acceptable manual testing threshold.

### Priority
Low

### Preconditions
- Tester is authenticated as a registered mathlete.
- The target competition is live and has several problems.
- Browser cache and network conditions are representative of normal test conditions.
- A stopwatch or browser timing tool is available.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Start timing and click the arena entry action for a live competition. | Navigation begins without a broken loading state. |
| 2 | Stop timing when the first problem can be read and answered. | The arena becomes usable within 3 seconds on a normal local or staging connection. |
| 3 | Navigate between two problems. | Problem navigation responds within 1 second per action. |
| 4 | Enter an answer and move away from the problem. | The UI remains responsive and does not freeze during answer state updates. |

### Post-conditions
- The active attempt remains available.
- No final submission is made unless the tester intentionally submits.

### Notes
- Current app route: `/mathlete/competition/[competitionId]`.
- Related current coverage: `tests/arena/page-data.test.ts`, `tests/ui/arena-experience.test.tsx`, and `tests/submission/summary.test.ts`.
