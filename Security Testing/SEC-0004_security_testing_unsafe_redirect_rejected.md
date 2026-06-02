## **ID:** SEC-0004 Unsafe redirect target is rejected

### Summary
Validates that authentication or navigation redirect parameters do not allow redirecting users to unsafe external targets.

### Priority
High

### Preconditions
- The application is running.
- Tester is signed out.
- Tester can manually edit browser URLs.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open an auth route with an external redirect target parameter if supported by the route. | The app does not immediately navigate to the external unsafe target. |
| 2 | Sign in with a valid account. | Authentication succeeds. |
| 3 | Observe the post-login destination. | The app redirects only to an allowed internal route. |
| 4 | Repeat with a malformed redirect target. | The malformed target is ignored or rejected safely. |
| 5 | Open normal login without redirect parameter. | Normal role-based redirect still works. |

### Post-conditions
- User is not redirected to an untrusted external URL by auth flow parameters.

### Notes
- Current app routes: `/auth/login` and `/auth/confirm`.
- Related current coverage: `tests/auth/routing.test.ts` and `tests/auth/callback.test.ts`.
