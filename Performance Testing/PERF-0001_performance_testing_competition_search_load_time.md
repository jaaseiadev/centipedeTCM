## **ID:** PERF-0001 Competition search loads within acceptable time

### Summary
Validates that the mathlete competition discovery page and search interaction load within an acceptable manual testing threshold.

### Priority
Low

### Preconditions
- Tester is authenticated as a complete mathlete.
- The test environment has at least ten visible competitions if available; otherwise use the current available competition data.
- Browser developer tools or another timing method is available.
- Network throttling is disabled unless the test session explicitly requires it.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Start timing and open `/mathlete/competition`. | The page becomes usable within 3 seconds on a normal local or staging connection. |
| 2 | Type a known competition keyword in the search field. | Search results update within 1 second after typing stops. |
| 3 | Clear the search field. | The full competition list returns within 1 second. |
| 4 | Open a competition from the results. | The detail page begins loading without a visible long freeze or broken loading state. |

### Post-conditions
- No registration, attempt, or competition state is changed by the performance test.

### Notes
- Current app route: `/mathlete/competition`.
- Related current coverage: `tests/competition/discovery.test.ts` and `tests/ui/competition-list.test.tsx`.
