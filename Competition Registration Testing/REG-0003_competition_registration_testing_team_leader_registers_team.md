## **ID:** REG-0003 Team leader registers team for team competition

### Summary
Validates that a team leader can register an eligible team for a scheduled team competition.

### Priority
High

### Preconditions
- Tester is authenticated as a complete mathlete.
- Tester is the leader of a team with valid roster size.
- A published scheduled team competition is open for registration.
- The team is not already registered for the competition.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the target team competition detail page. | The competition detail page shows team registration information. |
| 2 | Select the eligible team. | The team appears as a valid registration option. |
| 3 | Submit team registration. | The UI shows a pending state. |
| 4 | Wait for registration to complete. | The page confirms the team is registered. |
| 5 | Open the team detail page. | The team shows registered context or roster lock if supported. |

### Post-conditions
- A team registration record exists for the competition.
- The registered roster may become locked according to competition rules.

### Notes
- Current app routes: `/mathlete/competition/[competitionId]` and `/mathlete/teams/[teamId]`.
- Related current coverage: `tests/registrations/api.test.ts` and `tests/registrations/validation.test.ts`.
