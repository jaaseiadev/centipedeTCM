## **ID:** TEAM-0002 Team leader invites member

### Summary
Validates that a team leader can invite another mathlete to join a team and that the invitation appears for the invited member.

### Priority
Medium

### Preconditions
- Tester A is authenticated as a mathlete team leader.
- Tester B is a separate complete mathlete account.
- Tester A has an existing team that is not locked by registration.
- Tester B is not already committed to an incompatible roster for the same target context.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Tester A opens the team detail page from `/mathlete/teams`. | The team page loads with leader management controls. |
| 2 | Use the invite member action and enter Tester B's allowed identifier. | The invite form accepts the member identifier. |
| 3 | Send the invitation. | The system confirms the invitation was sent or created. |
| 4 | Tester B opens `/mathlete/teams/invites`. | The pending invitation is visible to Tester B. |
| 5 | Tester B leaves the invitation pending. | The team roster does not add Tester B until the invite is accepted. |

### Post-conditions
- A pending invitation exists for Tester B.
- The team roster remains unchanged until acceptance.

### Notes
- Current app routes: `/mathlete/teams`, `/mathlete/teams/[teamId]`, and `/mathlete/teams/invites`.
- Related current coverage: `tests/teams/invite-route.test.ts` and `tests/teams/invite-response-route.test.ts`.
