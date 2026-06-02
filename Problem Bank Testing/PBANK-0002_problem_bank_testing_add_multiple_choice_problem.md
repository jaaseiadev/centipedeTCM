## **ID:** PBANK-0002 Organizer adds multiple choice problem

### Summary
Validates that an organizer can add a valid multiple choice problem to an existing problem bank.

### Priority
High

### Preconditions
- Tester is authenticated as an approved organizer.
- At least one organizer-owned problem bank exists.
- Tester can access the selected problem bank detail or edit page.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/problem-bank`. | The problem bank list loads. |
| 2 | Select an existing problem bank. | The problem bank detail or editor opens. |
| 3 | Add a new multiple choice problem. | The problem form shows question, choices, and correct answer controls. |
| 4 | Submit with missing choices or no correct answer. | The form blocks saving and shows validation feedback. |
| 5 | Enter a question, complete choices, and select the correct answer, then save. | The problem is saved and appears in the problem bank. |

### Post-conditions
- The problem bank contains the new multiple choice problem.
- Invalid multiple choice data is not persisted.

### Notes
- Current app route: `/organizer/problem-bank/[bankId]`.
- Related current coverage: `tests/problem-bank/validation.test.ts`, `tests/ui/problem-form.test.tsx`, and `tests/problem-bank/normalization.test.ts`.
