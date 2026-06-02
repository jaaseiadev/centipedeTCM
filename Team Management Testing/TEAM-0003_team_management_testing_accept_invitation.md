## **ID:** TEAM-0003 Invited member accepts team invitation

### Summary
Validates that an invited mathlete can accept a pending team invitation and become part of the team roster.

### Priority
High

### Preconditions
- Tester A has created a team and sent an invitation.
- Tester B is the invited complete mathlete.
- The team is not locked by competition registration.
- Tester B is not already in an incompatible roster.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Tester B signs in and opens `/mathlete/teams/invites`. | Pending invitations are displayed. |
| 2 | Select the invitation from Tester A's team. | Invitation details are readable. |
| 3 | Click accept. | The system processes the invitation response. |
| 4 | Open `/mathlete/teams`. | Tester B now sees the team in the team list. |
| 5 | Tester A opens the team detail page. | Tester B appears in the roster. |

### Post-conditions
- The invitation is no longer pending.
- Tester B is an active team member.

### Notes
- Current app route: `/mathlete/teams/invites`.
- Related current coverage: `tests/teams/invite-response-route.test.ts` and `tests/teams/join-route-notifications.test.ts`.
