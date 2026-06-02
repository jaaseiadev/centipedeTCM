## **ID:** PERF-0005 Competition list remains usable with many records

### Summary
Validates that the competition discovery list remains responsive when many competition records are visible.

### Priority
Low

### Preconditions
- Tester is authenticated as a complete mathlete.
- Test environment has many visible competitions, preferably 50 or more; otherwise use the largest available dataset.
- Browser cache and network conditions are representative of normal test conditions.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/competition`. | The competition list loads without layout breakage. |
| 2 | Scroll through the list. | Scrolling remains smooth enough for manual use. |
| 3 | Search for a known competition. | Results filter within 1 second after typing stops. |
| 4 | Clear the search field. | The full list returns without a long freeze. |
| 5 | Open a competition detail page from the list. | Navigation remains responsive. |

### Post-conditions
- No competition state changes occur.

### Notes
- Current app route: `/mathlete/competition`.
- Related current coverage: `tests/competition/discovery.test.ts` and `tests/ui/competition-list.test.tsx`.
