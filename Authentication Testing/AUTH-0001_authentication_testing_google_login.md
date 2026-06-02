## **ID:** AUTH-0001 Google OAuth login redirects mathlete correctly

### Summary
Validates that a mathlete can start Google OAuth login from the login page and is redirected to the correct onboarding or dashboard route after authentication.

### Priority
High

### Preconditions
- The MathWiz Arena application is running.
- Supabase Google OAuth is configured for the test environment.
- Tester has a Google account that can be used as a mathlete account.
- If the account is new or incomplete, no complete profile record exists yet.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/auth/login`. | The login page displays email login fields and a `Continue with Google` button. |
| 2 | Click `Continue with Google`. | The button shows a pending state and the browser starts the Google sign-in flow. |
| 3 | Select or authenticate with the Google account. | Google completes authentication and returns the user to MathWiz Arena through the auth callback route. |
| 4 | Observe the final destination page. | A new or incomplete mathlete is sent to `/profile/complete`; a complete mathlete is sent to `/mathlete`. |

### Post-conditions
- A valid mathlete session exists if authentication succeeds.
- No organizer or admin route is opened for a mathlete account.

### Notes
- Current app route: `/auth/login`.
- Related current coverage: `tests/auth/session.test.ts`, `tests/auth/routing.test.ts`, and `tests/auth/callback.test.ts`.
