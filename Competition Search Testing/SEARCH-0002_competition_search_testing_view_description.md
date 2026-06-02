## **ID:** SEARCH-0002 Mathlete views competition description

### Summary
Validates that a mathlete can open a competition listing and read its description, rules, and schedule context.

### Priority
Medium

### Preconditions
- Tester is authenticated as a complete mathlete.
- At least one published competition exists.
- The target competition has a description and rules.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/competition`. | The competition discovery page loads. |
| 2 | Select a published competition. | The competition detail page opens. |
| 3 | Review title, description, schedule, and rules. | The displayed information matches the competition data and is readable. |
| 4 | Return to the competition list. | The tester returns to discovery without changing registration state. |

### Post-conditions
- Viewing the competition does not create registration or attempt records.

### Notes
- Current app route: `/mathlete/competition/[competitionId]`.
- Related current coverage: `tests/competition/discovery.test.ts` and `tests/ui/competition-registration-panel.test.tsx`.
