## **ID:** ORGAPP-0005 Applicant status lookup shows safe fields only

### Summary
Validates that organizer application status lookup returns useful applicant-facing status without exposing private or administrative fields.

### Priority
Medium

### Preconditions
- Tester has an organizer application reference or lookup email in test data.
- Tester can access `/organizer/status`.
- The application is in pending, approved, or rejected state.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/status`. | The status lookup page loads. |
| 2 | Submit an empty or invalid lookup value. | The page shows validation feedback and does not perform a valid lookup. |
| 3 | Submit a valid applicant lookup value. | The page displays the application status. |
| 4 | Review displayed fields. | The page shows safe applicant-facing fields such as status and submitted organization context. |
| 5 | Check for sensitive fields. | Internal reviewer IDs, private notes, tokens, and raw database identifiers are not exposed. |

### Post-conditions
- Application status remains unchanged.

### Notes
- Current app route: `/organizer/status`.
- Related current coverage: `tests/organizer/applications-route.test.ts`.
