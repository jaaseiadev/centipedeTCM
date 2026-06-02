## **ID:** PBANK-0001 Organizer creates a problem bank

### Summary
Validates that an approved organizer can create a problem bank that appears in the organizer problem bank workspace.

### Priority
High

### Preconditions
- Tester is authenticated as an approved organizer.
- Organizer profile is complete and active.
- Tester can access `/organizer/problem-bank`.
- A unique problem bank title is available for the test.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/problem-bank`. | The organizer problem bank page loads and shows available banks or an empty state. |
| 2 | Navigate to create a new problem bank. | The create problem bank form opens. |
| 3 | Submit the form with the title empty. | The form blocks submission or shows a required title validation message. |
| 4 | Enter a unique title and valid description if available. | The form accepts the values. |
| 5 | Save the problem bank. | The new bank is created and appears in the problem bank list or detail page. |

### Post-conditions
- The organizer owns a newly created problem bank.
- The problem bank can be selected for later problem authoring or competition setup.

### Notes
- Current app routes: `/organizer/problem-bank` and `/organizer/problem-bank/create`.
- Related current coverage: `tests/problem-bank/api-helpers.test.ts`, `tests/problem-bank/validation.test.ts`, and `tests/ui/bank-form.test.tsx`.
