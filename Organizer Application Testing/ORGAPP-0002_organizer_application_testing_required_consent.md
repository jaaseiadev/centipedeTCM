## **ID:** ORGAPP-0002 Organizer application requires legal consent

### Summary
Validates that organizer application submission is blocked unless required legal consent fields are accepted.

### Priority
High

### Preconditions
- The application is running.
- Tester can access `/organizer/apply`.
- Tester has valid applicant and organization details.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/apply`. | The organizer application form loads. |
| 2 | Fill in all required personal and organization fields. | The form accepts valid field values. |
| 3 | Leave Data Privacy Act or Terms and Conditions consent unchecked. | The consent field remains visibly unchecked. |
| 4 | Submit the form. | Submission is blocked and the page communicates that consent is required. |
| 5 | Check the required consent fields and submit again. | The application submits successfully if all other fields are valid. |

### Post-conditions
- No application is created from a submission missing required consent.
- A valid application may be created only after consent is accepted.

### Notes
- Current app route: `/organizer/apply`.
- Related current coverage: `tests/organizer/applications-route.test.ts` and `tests/organizer/validation.test.ts`.
