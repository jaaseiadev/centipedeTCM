## **ID:** SEC-0005 Sensitive tokens are not exposed in URL or logs

### Summary
Validates that sensitive session, recovery, and access tokens are not displayed in user-facing URLs or visible application logs after authentication flows.

### Priority
High

### Preconditions
- Tester can perform a login or password recovery flow.
- Browser address bar and developer console can be inspected.
- The application is running in a test environment.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Complete a normal login flow. | The user reaches the proper workspace. |
| 2 | Inspect the browser address bar after redirect. | Access tokens and refresh tokens are not visible in the URL. |
| 3 | Open browser console and visible network logs if available. | Sensitive tokens are not printed in user-facing console messages. |
| 4 | Start a password recovery flow if available. | Recovery route handles tokens without leaving them exposed after completion. |
| 5 | Refresh the final page. | The page remains usable without exposing raw token values. |

### Post-conditions
- Sensitive token values are not exposed to normal users through UI-visible locations.

### Notes
- Current app routes: `/auth/login`, `/auth/confirm`, and `/auth/update-password`.
- Related current coverage: `tests/auth/callback.test.ts` and `tests/auth/session-route.test.ts`.
