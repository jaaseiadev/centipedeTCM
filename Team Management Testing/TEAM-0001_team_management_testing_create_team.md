## **ID:** TEAM-0001 Mathlete creates a team

### Summary
Validates that a mathlete can create a team from the mathlete teams workspace using a valid unique team name.

### Priority
High

### Preconditions
- Tester is authenticated as a mathlete with a complete profile.
- Tester can access `/mathlete/teams`.
- Tester is allowed to create another team.
- A unique team name is available.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/teams`. | The teams workspace displays create, join, and pending invite actions. |
| 2 | Click `Create New Team`. | The create team page opens. |
| 3 | Submit the form without a team name. | The form blocks submission or shows a required name message. |
| 4 | Enter a unique team name. | The value is accepted. |
| 5 | Submit the form. | The team is created and the tester is shown as the team leader or owner. |

### Post-conditions
- A new team exists with the tester as leader.
- The team can be used for eligible team competition registration.

### Notes
- Current app routes: `/mathlete/teams` and `/mathlete/teams/create`.
- Related current coverage: `tests/teams/validation.test.ts` and `tests/teams/guards.test.ts`.
