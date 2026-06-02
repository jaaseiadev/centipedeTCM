## **ID:** TEAM-0005 Registered team roster is locked from changes

### Summary
Validates that a team registered for a competition cannot have its roster changed when roster lock rules apply.

### Priority
High

### Preconditions
- A team exists with at least two members.
- The team is registered for a team competition that locks rosters.
- Tester is the team leader.
- Another tester is a team member.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Team leader opens the registered team's detail page. | The roster is visible. |
| 2 | Attempt to remove a member. | Removal is blocked or disabled because the roster is locked. |
| 3 | Attempt to invite another member. | New invitations are blocked or clearly marked unavailable. |
| 4 | Member attempts to leave the locked team. | Leaving is blocked while roster lock applies. |
| 5 | Review the team roster. | The registered roster remains unchanged. |

### Post-conditions
- Registered team roster remains intact.

### Notes
- Current app route: `/mathlete/teams/[teamId]`.
- Related current coverage: `tests/teams/guards.test.ts`, `tests/registrations/validation.test.ts`, and `tests/teams/leadership-selection.test.ts`.
