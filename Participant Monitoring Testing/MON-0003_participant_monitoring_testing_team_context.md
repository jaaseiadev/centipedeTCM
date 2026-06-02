## **ID:** MON-0003 Organizer sees team participant context

### Summary
Validates that organizer monitoring displays team context for team competitions.

### Priority
Medium

### Preconditions
- Organizer owns a team competition.
- At least one team is registered or active.
- Tester is authenticated as the organizer.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the organizer competition management page. | Owned competitions are listed. |
| 2 | Select the team competition. | Competition detail or monitoring page opens. |
| 3 | Open participants or monitoring section. | Team participant context is displayed. |
| 4 | Review team rows. | Team name and allowed roster context are shown. |
| 5 | Compare with individual competition view if available. | Team competition view clearly distinguishes team participants from individual participants. |

### Post-conditions
- Team participant data remains unchanged.

### Notes
- Current app route: `/organizer/competition/[competitionId]`.
- Related current coverage: `tests/monitoring/team-live-monitoring.test.ts` and `tests/organizer/competition-participants-panel.test.tsx`.
