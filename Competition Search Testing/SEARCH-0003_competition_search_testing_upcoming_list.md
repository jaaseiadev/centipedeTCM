## **ID:** SEARCH-0003 Mathlete views upcoming competition list

### Summary
Validates that published upcoming competitions appear in the mathlete competition discovery list.

### Priority
Medium

### Preconditions
- Tester is authenticated as a complete mathlete.
- At least one published upcoming competition exists.
- At least one draft or unpublished competition exists for comparison if possible.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/competition`. | The competition discovery page loads. |
| 2 | Review the visible competition cards or rows. | Published upcoming competitions are listed. |
| 3 | Check schedule and organizer labels if shown. | Visible metadata is readable and matches the competition setup. |
| 4 | Check for draft or unpublished competitions. | Draft or unpublished competitions are not shown to the mathlete. |
| 5 | Refresh the page. | The list remains consistent with current available competitions. |

### Post-conditions
- Viewing the list does not create registration state.

### Notes
- Current app route: `/mathlete/competition`.
- Related current coverage: `tests/competition/discovery.test.ts` and `tests/ui/competition-list.test.tsx`.
