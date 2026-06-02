## **ID:** TEAM-0004 Team leader removes unlocked member

### Summary
Validates that a team leader can remove a member when the team roster is not locked by registration.

### Priority
Medium

### Preconditions
- Tester A is a team leader.
- Tester B is an active member of Tester A's team.
- The team is not registered in a locked competition roster.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Tester A opens the team detail page. | The roster and leader controls are visible. |
| 2 | Select Tester B from the roster. | Member management actions are available to the leader. |
| 3 | Choose remove member. | A confirmation or clear removal action is shown. |
| 4 | Confirm removal. | Tester B is removed from the roster. |
| 5 | Tester B opens `/mathlete/teams`. | The removed team no longer appears as an active team for Tester B. |

### Post-conditions
- Tester B is no longer a team member.
- Tester A remains the team leader.

### Notes
- Current app route: `/mathlete/teams/[teamId]`.
- Related current coverage: `tests/teams/guards.test.ts` and `tests/teams/leadership-selection.test.ts`.
