## **ID:** MON-0001 Organizer views registered participants

### Summary
Validates that an organizer can view registered participants for a competition they manage.

### Priority
Medium

### Preconditions
- Tester is authenticated as an approved organizer.
- Organizer owns at least one competition.
- At least one mathlete or team is registered for that competition.
- Tester can access organizer competition management.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/competition`. | The organizer competition list loads. |
| 2 | Select a competition with registered participants. | The competition management or detail page opens. |
| 3 | Open the participants area or panel. | Registered participants are displayed with allowed participant context. |
| 4 | Review participant details. | The list shows registration context without exposing unrelated sensitive account data. |

### Post-conditions
- Participant records remain unchanged.
- Organizer has only viewed participant information.

### Notes
- Current app routes: `/organizer/competition` and `/organizer/competition/[competitionId]`.
- Related current coverage: `tests/monitoring/routes.test.ts`, `tests/organizer/competition-participants-panel.test.tsx`, and `tests/monitoring/team-live-monitoring.test.ts`.
