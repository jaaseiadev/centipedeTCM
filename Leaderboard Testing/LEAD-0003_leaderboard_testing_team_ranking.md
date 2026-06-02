## **ID:** LEAD-0003 Team leaderboard ranks teams correctly

### Summary
Validates that team competition leaderboard entries are grouped and ranked by team, not by individual member rows.

### Priority
High

### Preconditions
- A completed team competition exists.
- At least two teams have submitted attempts and have computed scores.
- Results are published or organizer view is available for verification.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the team competition leaderboard or organizer results view. | Team result entries are visible. |
| 2 | Review each leaderboard row. | Rows represent teams with team names or allowed team context. |
| 3 | Compare team scores. | Higher scoring teams appear above lower scoring teams. |
| 4 | Open a team entry if supported. | Member context is shown only as allowed by the UI. |
| 5 | Refresh the leaderboard. | Team ranking remains consistent. |

### Post-conditions
- Leaderboard data remains unchanged by viewing it.

### Notes
- Related current coverage: `tests/leaderboard/routes.test.ts` and `tests/monitoring/team-live-monitoring.test.ts`.
