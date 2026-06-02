## **ID:** AUTH-0003 Strict single-session enforcement replaces old session

### Summary
Validates that a user account can keep only the latest accepted session active when the same credentials are used from another browser or device.

### Priority
High

### Preconditions
- The application is running.
- Tester has one active mathlete account with known email and password.
- Tester has access to two separate browsers, browser profiles, or private sessions.
- The account profile is complete so the dashboard can be reached after login.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | In Browser A, sign in using the mathlete account. | Browser A reaches the mathlete dashboard and can access protected pages. |
| 2 | In Browser B, sign in using the same account. | Browser B reaches the mathlete dashboard and becomes the active session. |
| 3 | Return to Browser A and refresh `/mathlete`. | Browser A is no longer accepted as the current session. |
| 4 | Try opening another protected page in Browser A. | The old session is redirected to login or a session replacement page. |
| 5 | Continue using Browser B. | Browser B remains signed in and can access protected pages. |

### Post-conditions
- Only the latest accepted session remains active.
- The replaced session cannot view protected data.

### Notes
- Current app routes: `/auth/session`, `/auth/session-replaced`, and `/mathlete`.
- Related current coverage: `tests/auth/session.test.ts` and `tests/auth/session-route.test.ts`.
