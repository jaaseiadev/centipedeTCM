## **ID:** COMP-0005 Team competition validates team size and capacity

### Summary
Validates that team competition setup enforces allowed member count and team capacity ranges.

### Priority
High

### Preconditions
- Tester is authenticated as an approved organizer.
- Tester can access the team competition setup path.
- The wizard supports team size and maximum team count fields.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/competition/create` and choose team competition. | Team configuration fields appear. |
| 2 | Enter a team size below 2. | The wizard rejects the value or displays a validation error. |
| 3 | Enter a team size above 5. | The wizard rejects the value or displays a validation error. |
| 4 | Enter a maximum team count below 3 or above 50. | The wizard rejects the invalid capacity. |
| 5 | Enter team size 2 to 5 and capacity 3 to 50. | The values are accepted and the wizard can proceed. |

### Post-conditions
- Invalid team constraints are not saved.

### Notes
- Current app route: `/organizer/competition/create`.
- Related current coverage: `tests/competition/validation.test.ts` and `tests/registrations/validation.test.ts`.
