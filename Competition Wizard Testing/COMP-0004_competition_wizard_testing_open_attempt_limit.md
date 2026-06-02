## **ID:** COMP-0004 Organizer creates open competition with attempt limit

### Summary
Validates that open competition setup accepts only supported attempt limits and stores the selected limit.

### Priority
Medium

### Preconditions
- Tester is authenticated as an approved organizer.
- At least one problem bank with usable problems exists.
- Tester can access `/organizer/competition/create`.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/competition/create`. | The competition wizard loads. |
| 2 | Select open competition mode. | Open mode fields, including attempt limit if implemented, are displayed. |
| 3 | Try to enter an attempt limit below 1 or above 3. | The wizard rejects the value or shows validation feedback. |
| 4 | Select a valid attempt limit from 1 to 3. | The wizard accepts the value. |
| 5 | Complete required fields and save or publish. | The open competition is created with the selected attempt limit. |

### Post-conditions
- The open competition stores only a valid attempt limit.

### Notes
- Current app route: `/organizer/competition/create`.
- Related current coverage: `tests/competition/validation.test.ts` and `tests/ui/competition-wizard-lifecycle.test.tsx`.
