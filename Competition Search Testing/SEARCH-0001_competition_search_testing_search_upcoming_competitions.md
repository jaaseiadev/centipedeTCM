## **ID:** SEARCH-0001 Mathlete searches upcoming competitions

### Summary
Validates that a mathlete can view and search upcoming competitions from the mathlete competition discovery page.

### Priority
Medium

### Preconditions
- Tester is authenticated as a mathlete with a complete profile.
- At least one published upcoming competition exists.
- Tester can access `/mathlete/competition`.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/competition`. | The page displays available or upcoming competitions. |
| 2 | Enter part of a known competition title in the search field. | The visible list updates to matching competitions. |
| 3 | Clear the search field. | The list returns to the full available set. |
| 4 | Open a competition from the list. | The competition detail page shows title, schedule, description, and registration or entry state. |

### Post-conditions
- No competition registration is created by search alone.

### Notes
- Current app routes: `/mathlete/competition` and `/mathlete/competition/[competitionId]`.
- Related current coverage: `tests/competition/discovery.test.ts`, `tests/ui/competition-list.test.tsx`, and `tests/competition/upcoming-refresh.test.ts`.
