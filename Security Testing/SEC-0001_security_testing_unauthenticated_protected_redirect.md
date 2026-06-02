## **ID:** SEC-0001 Unauthenticated user is redirected from protected page

### Summary
Validates that protected mathlete routes are not accessible without an authenticated session.

### Priority
High

### Preconditions
- Tester is signed out of MathWiz Arena.
- Browser session cookies for the app are cleared or a private browser session is used.
- The application is running.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete`. | The app does not display the mathlete dashboard. |
| 2 | Observe the destination route or visible page. | The user is redirected to authentication or a protected-route gate. |
| 3 | Try opening `/profile/complete` while signed out. | The app requires authentication before profile completion can proceed. |
| 4 | Sign in with a valid account. | The protected route becomes available according to the user's role and profile state. |

### Post-conditions
- No protected mathlete data is exposed to unauthenticated users.

### Notes
- Current app routes: `/mathlete`, `/profile/complete`, and `/auth/login`.
- Related current coverage: `tests/auth/routing.test.ts`, `tests/auth/proxy.test.ts`, and `tests/auth/session-route.test.ts`.
