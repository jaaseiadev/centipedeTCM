## **ID:** SEARCH-0004 Search with no match shows empty state

### Summary
Validates that competition search handles a query with no matching results using a clear empty state.

### Priority
Low

### Preconditions
- Tester is authenticated as a complete mathlete.
- Tester can access `/mathlete/competition`.
- A nonsense search term is available that should not match any competition.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/competition`. | The competition list loads. |
| 2 | Enter a search term that should not match any competition. | The list filters down to no results. |
| 3 | Review the page state. | A clear empty state or no-results message is shown. |
| 4 | Clear the search term. | The normal competition list returns. |
| 5 | Search for a known competition. | Matching results appear again. |

### Post-conditions
- No data is changed by unsuccessful search.

### Notes
- Current app route: `/mathlete/competition`.
- Related current coverage: `tests/ui/competition-list.test.tsx`.
