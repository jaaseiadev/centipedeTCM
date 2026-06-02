## **ID:** SEC-0003 GET routes do not mutate state

### Summary
Validates that visiting read-only GET pages or endpoints does not create, update, delete, or submit application data.

### Priority
High

### Preconditions
- Tester has valid mathlete and organizer accounts.
- Baseline state is known for a selected competition, team, registration, or notification.
- Tester can refresh pages and compare state before and after.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Record baseline state for a selected record such as registration count or team roster. | Baseline state is known. |
| 2 | Open read-only pages such as competition list, detail, calendar, and notifications. | Pages load without performing state-changing actions. |
| 3 | Refresh each page multiple times. | No new registrations, teams, attempts, submissions, or notifications are created by viewing pages. |
| 4 | Return to the baseline record. | The record state matches the original state. |
| 5 | Perform a valid state-changing action intentionally. | Only the intentional action changes state. |

### Post-conditions
- Read-only GET access does not mutate state.

### Notes
- Related current coverage: `tests/competition/api.test.ts`, `tests/registrations/api.test.ts`, and `tests/submission/routes.test.ts`.
