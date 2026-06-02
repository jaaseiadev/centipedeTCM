## **ID:** AUTH-0005 Forgot password request sends recovery flow

### Summary
Validates that a user can request password recovery from the login flow using a valid email address.

### Priority
Medium

### Preconditions
- The application is running.
- Tester has a confirmed email account in the test environment.
- Email delivery or Supabase recovery logging is available for verification.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/auth/login`. | The login page displays a forgot password link. |
| 2 | Click `Forgot Password?`. | The forgot password page opens. |
| 3 | Submit the form with an empty or invalid email. | The form blocks submission or shows clear validation feedback. |
| 4 | Enter a valid account email and submit. | The page shows a safe confirmation that recovery instructions were sent if the account is eligible. |
| 5 | Open the recovery link when available. | The password update page opens through the supported recovery route. |

### Post-conditions
- A password recovery request exists for the account if the email is valid.
- The existing password is not changed until the recovery flow is completed.

### Notes
- Current app routes: `/auth/forgot-password` and `/auth/update-password`.
- Related current coverage: `tests/auth/email-confirmation.test.ts` and `tests/auth/routing.test.ts`.
