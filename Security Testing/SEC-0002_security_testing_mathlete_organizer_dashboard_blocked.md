## **ID:** SEC-0002 Mathlete cannot access organizer dashboard

### Summary
Validates that a signed-in mathlete cannot access organizer-only workspace pages.

### Priority
High

### Preconditions
- Tester is authenticated as a complete mathlete.
- Tester does not have organizer role or organizer approval.
- The application is running.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Sign in as a mathlete. | The mathlete workspace is available. |
| 2 | Manually open `/organizer`. | The organizer dashboard is not displayed to the mathlete. |
| 3 | Manually open `/organizer/problem-bank`. | The problem bank management page is blocked or redirects away. |
| 4 | Manually open `/organizer/competition/create`. | The competition creation page is blocked or redirects away. |
| 5 | Return to `/mathlete`. | The mathlete workspace remains accessible. |

### Post-conditions
- Organizer-only data and actions are not exposed to a mathlete.

### Notes
- Current app routes: `/organizer`, `/organizer/problem-bank`, and `/organizer/competition/create`.
- Related current coverage: `tests/auth/routing.test.ts`, `tests/organizer/layout.test.tsx`, and `tests/organizer/organizer-nav.test.tsx`.
