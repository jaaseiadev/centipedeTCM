## **ID:** REG-0004 Non-leader cannot register team

### Summary
Validates that a regular team member cannot register the team for a team competition unless they are the team leader.

### Priority
High

### Preconditions
- Tester is authenticated as a complete mathlete.
- Tester is a member, not leader, of an eligible team.
- A published team competition is open for registration.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the target team competition detail page. | The competition detail page loads. |
| 2 | Review available team registration actions. | The member is not allowed to submit registration for the team. |
| 3 | Attempt to register the team if a control is visible. | The request is blocked with a clear permission message. |
| 4 | Ask the team leader to open the same page. | The leader sees the valid registration path if the team is eligible. |
| 5 | Check the team registration state as the non-leader. | No unauthorized registration was created by the member. |

### Post-conditions
- Team registration remains unchanged unless submitted by the leader.

### Notes
- Current app route: `/mathlete/competition/[competitionId]`.
- Related current coverage: `tests/registrations/validation.test.ts` and `tests/teams/guards.test.ts`.
