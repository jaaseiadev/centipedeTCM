## **ID:** PBANK-0005 Invalid problem data cannot be saved

### Summary
Validates that problem authoring rejects invalid or incomplete problem data before it is saved into a problem bank.

### Priority
High

### Preconditions
- Tester is authenticated as an approved organizer.
- At least one problem bank exists.
- Tester can access the problem authoring form.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open a problem bank editor. | Existing problems and add problem controls are available. |
| 2 | Create a new problem with no question text. | The form marks the question as required. |
| 3 | Add answer options with duplicate or empty values if the type supports options. | The form blocks invalid option data or shows validation feedback. |
| 4 | Enter an invalid difficulty, point value, or answer configuration if editable. | The invalid value is rejected or corrected before save. |
| 5 | Try to save the invalid problem. | No invalid problem appears in the problem bank list. |

### Post-conditions
- Problem bank data remains unchanged except for valid saved edits.

### Notes
- Current app route: `/organizer/problem-bank/[bankId]`.
- Related current coverage: `tests/problem-bank/validation.test.ts` and `tests/ui/problem-form.test.tsx`.
