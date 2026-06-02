## **ID:** PBANK-0004 Organizer adds numeric problem with accepted answers

### Summary
Validates that an organizer can add a numeric problem with one or more accepted answer values.

### Priority
High

### Preconditions
- Tester is authenticated as an approved organizer.
- At least one organizer-owned problem bank exists.
- Tester has a numeric problem prompt and accepted answers ready.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the target problem bank editor. | The problem bank editor loads. |
| 2 | Add a numeric problem. | Numeric answer controls are displayed. |
| 3 | Enter a prompt and leave accepted answers empty. | Saving is blocked because at least one accepted answer is required. |
| 4 | Add multiple accepted numeric answers or equivalent notation values. | The form accepts the allowed answer entries. |
| 5 | Save the problem and reopen it. | The numeric problem and accepted answers remain stored. |

### Post-conditions
- The numeric problem is available for competition problem selection.

### Notes
- Current app route: `/organizer/problem-bank/[bankId]`.
- Related current coverage: `tests/math/latex-validation.test.ts`, `tests/problem-bank/normalization.test.ts`, and `tests/problem-bank/validation.test.ts`.
