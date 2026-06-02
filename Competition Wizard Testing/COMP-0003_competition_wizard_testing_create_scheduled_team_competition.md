## **ID:** COMP-0003 Organizer creates scheduled team competition

### Summary
Validates that an organizer can create a scheduled team competition with valid team roster constraints.

### Priority
High

### Preconditions
- Tester is authenticated as an approved organizer.
- At least one problem bank with eligible problems exists.
- Tester can access `/organizer/competition/create`.
- Future schedule values are available.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/competition/create`. | The competition wizard loads. |
| 2 | Select a scheduled team competition type. | Team-specific fields are displayed. |
| 3 | Enter title, description, rules, schedule, and duration. | Required common fields accept valid data. |
| 4 | Configure valid team size and team capacity values. | Values within allowed range are accepted. |
| 5 | Select problems and publish or save. | The scheduled team competition is created and appears in organizer competition management. |

### Post-conditions
- A scheduled team competition exists with valid team constraints.

### Notes
- Current app route: `/organizer/competition/create`.
- Related current coverage: `tests/competition/create-route.test.ts` and `tests/ui/competition-wizard-lifecycle.test.tsx`.
