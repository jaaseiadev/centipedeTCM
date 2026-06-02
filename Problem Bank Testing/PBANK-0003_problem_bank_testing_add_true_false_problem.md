## **ID:** PBANK-0003 Organizer adds true or false problem

### Summary
Validates that an organizer can add a true or false problem with exactly one correct truth value.

### Priority
Medium

### Preconditions
- Tester is authenticated as an approved organizer.
- At least one problem bank exists.
- Tester can open the problem bank editor.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open an existing problem bank from `/organizer/problem-bank`. | The problem bank editor or detail page loads. |
| 2 | Add a new true or false problem. | The form changes to true or false problem controls. |
| 3 | Enter a question without selecting true or false. | The form blocks saving or shows that the correct answer is required. |
| 4 | Select either true or false as the correct answer. | Exactly one truth value is selected. |
| 5 | Save the problem. | The problem is saved and listed with the correct type. |

### Post-conditions
- The problem bank contains the true or false problem.

### Notes
- Current app route: `/organizer/problem-bank/[bankId]`.
- Related current coverage: `tests/problem-bank/validation.test.ts` and `tests/ui/problem-form.test.tsx`.
