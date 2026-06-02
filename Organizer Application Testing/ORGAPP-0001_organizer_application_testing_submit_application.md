## **ID:** ORGAPP-0001 Organizer submits eligibility application

### Summary
Validates that a prospective organizer can submit an eligibility application with required personal, organization, and consent data.

### Priority
High

### Preconditions
- The application is running and accessible without organizer login.
- Tester has valid applicant and organization details.
- Tester can access the Data Privacy Act and Terms and Conditions links if needed.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/apply`. | The organizer eligibility application page loads. |
| 2 | Attempt to submit the application without required fields. | Required fields show validation feedback and the application is not submitted. |
| 3 | Fill in required personal and organization information. | The form accepts valid text, email, and organization values. |
| 4 | Agree to the Data Privacy Act and Terms and Conditions. | Consent fields are selected and remain selected before submission. |
| 5 | Submit the application. | The system records the application and shows a confirmation or next-step status message. |

### Post-conditions
- A new organizer application exists for review.
- The applicant does not automatically receive organizer dashboard access.

### Notes
- Current app route: `/organizer/apply`.
- Related current coverage: `tests/organizer/applications-route.test.ts`.
