## **ID:** ORGAPP-0004 Rejected organizer account remains blocked

### Summary
Validates that a rejected organizer applicant cannot access organizer workspace pages as an approved organizer.

### Priority
High

### Preconditions
- Tester has an organizer applicant account or applicant email marked rejected in the test data.
- The application decision state can be inspected through login or status lookup.
- Tester is not using an approved organizer account.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/auth/login`. | The login page loads. |
| 2 | Sign in using the rejected applicant account if credentials exist. | The account is blocked from organizer workspace access or shown an inactive or pending approval message. |
| 3 | Manually open `/organizer`. | The organizer dashboard is not displayed. |
| 4 | Open `/organizer/status` and perform a status lookup if available. | The status lookup shows rejection status without exposing internal review notes beyond safe fields. |
| 5 | Attempt to open organizer management routes directly. | Routes remain blocked. |

### Post-conditions
- Rejected applicants do not gain organizer privileges.

### Notes
- Current app routes: `/auth/login`, `/organizer`, and `/organizer/status`.
- Related current coverage: `tests/organizer/applications-route.test.ts` and `tests/auth/routing.test.ts`.
