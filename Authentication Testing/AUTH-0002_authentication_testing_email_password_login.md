## **ID:** AUTH-0002 Email and password login redirects by profile state

### Summary
Validates that a user can sign in using email and password and is redirected according to account role, activity state, and profile completion.

### Priority
High

### Preconditions
- The MathWiz Arena application is running.
- Tester has a confirmed mathlete email and password account.
- The account is active and not suspended.
- Tester knows whether the account profile is complete or incomplete.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/auth/login`. | The login page displays email and password fields. |
| 2 | Enter an invalid password and submit. | The page shows a safe error message such as invalid email or password. |
| 3 | Enter the valid email and password, then submit. | The sign-in button shows a pending state while credentials are checked. |
| 4 | Wait for the redirect. | A complete mathlete is sent to `/mathlete`; an incomplete mathlete is sent to `/profile/complete`. |
| 5 | Refresh the destination page. | The signed-in state remains active and the user is not sent back to login. |

### Post-conditions
- A valid session exists after successful login.
- Invalid credentials do not create a session.

### Notes
- Current app route: `/auth/login`.
- Related current coverage: `tests/auth/session.test.ts`, `tests/auth/session-route.test.ts`, and `tests/auth/routing.test.ts`.
