## **ID:** MON-0002 Organizer views active participant context

### Summary
Validates that an organizer can monitor participant context for a live competition without exposing unrelated sensitive account data.

### Priority
Medium

### Preconditions
- Tester is authenticated as the organizer who owns a live competition.
- At least one mathlete or team has entered the live competition.
- Organizer can access competition management or monitoring view.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/competition`. | Organizer competition management loads. |
| 2 | Select the live competition. | The competition detail or management page opens. |
| 3 | Open the active participants or monitoring section. | Active participant context is displayed if the current implementation supports it. |
| 4 | Review displayed participant information. | The organizer sees competition-relevant context such as participant or team identity and state. |
| 5 | Check for unrelated sensitive data. | Private authentication data, tokens, and unrelated profile fields are not displayed. |

### Post-conditions
- Participant attempt and registration state are not changed by viewing monitoring data.

### Notes
- Current app route: `/organizer/competition/[competitionId]`.
- Related current coverage: `tests/monitoring/routes.test.ts`, `tests/monitoring/server-data-contracts.test.ts`, and `tests/monitoring/team-live-monitoring.test.ts`.
