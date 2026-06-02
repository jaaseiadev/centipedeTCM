## **ID:** ORGAPP-0003 Organizer application requires personal and organization data

### Summary
Validates that required applicant identity and organization fields must be completed before an organizer application can be submitted.

### Priority
High

### Preconditions
- Tester can access `/organizer/apply`.
- Tester has valid sample personal and organization data.
- No organizer login is required to open the application page.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/apply`. | The organizer application form loads. |
| 2 | Fill only the consent fields and leave personal data blank. | Required personal fields remain visibly incomplete. |
| 3 | Submit the form. | Submission is blocked and required personal fields are identified. |
| 4 | Fill personal data but leave organization data blank. | Required organization fields remain visibly incomplete. |
| 5 | Submit again. | Submission remains blocked until all required applicant and organization fields are valid. |

### Post-conditions
- No incomplete organizer application is created.

### Notes
- Current app route: `/organizer/apply`.
- Related current coverage: `tests/organizer/applications-route.test.ts` and `tests/organizer/validation.test.ts`.
