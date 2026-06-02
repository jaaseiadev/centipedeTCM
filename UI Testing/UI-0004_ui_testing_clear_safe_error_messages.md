## **ID:** UI-0004 Error messages are clear and user-safe

### Summary
Validates that validation and failure messages are understandable to users and do not expose stack traces or sensitive internal details.

### Priority
Medium

### Preconditions
- Tester can access forms such as login, profile completion, organizer application, or competition registration.
- Tester has sample invalid inputs ready.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/auth/login` and submit invalid credentials. | The page shows a clear user-safe authentication error. |
| 2 | Open `/profile/complete` as an eligible user and submit missing required fields. | Required field messages are clear. |
| 3 | Open `/organizer/apply` and submit incomplete data. | The application form identifies missing data safely. |
| 4 | Trigger a blocked registration condition if available. | The message explains the blocked action without exposing raw backend errors. |
| 5 | Review all messages. | No stack traces, SQL snippets, access tokens, or internal service keys are shown. |

### Post-conditions
- No invalid data is saved.

### Notes
- Related current coverage: `tests/errors.test.ts`, `tests/navigation-feedback.test.ts`, and `tests/ui/feedback-states.test.tsx`.
