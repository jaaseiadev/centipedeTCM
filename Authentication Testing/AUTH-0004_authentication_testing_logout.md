## **ID:** AUTH-0004 User logout clears protected access

### Summary
Validates that signing out ends the active session and blocks protected workspace routes until the user signs in again.

### Priority
High

### Preconditions
- Tester is authenticated as a complete mathlete or approved organizer.
- Tester can access a protected workspace page.
- The logout or sign-out control is visible in the current workspace.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the current user's workspace dashboard. | The protected dashboard loads. |
| 2 | Use the profile menu or visible sign-out action. | The sign-out route is requested and the UI leaves the workspace. |
| 3 | Wait for sign-out to finish. | The user is redirected to a public or login page. |
| 4 | Manually open the previous protected workspace route. | The protected page is blocked and the user is redirected to login or an auth gate. |
| 5 | Sign in again with valid credentials. | Protected access returns according to role and profile state. |

### Post-conditions
- The signed-out browser session cannot access protected pages.
- No role or profile data is changed by logging out.

### Notes
- Current app route: `/auth/sign-out`.
- Related current coverage: `tests/auth/sign-out-route.test.ts`.
