## **ID:** MON-0005 Organizer cannot monitor unrelated competition

### Summary
Validates that an organizer cannot view participant monitoring data for a competition owned by another organizer.

### Priority
High

### Preconditions
- Organizer A owns a competition with registered participants.
- Organizer B is a separate approved organizer.
- Tester has access to Organizer B's account.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Organizer A records the competition management URL for their owned competition. | Organizer A can access the participant view. |
| 2 | Sign out and sign in as Organizer B. | Organizer B's workspace opens. |
| 3 | Open Organizer A's competition management URL. | Organizer B is blocked, redirected, or shown no participant data. |
| 4 | Organizer B opens `/organizer/competition`. | Only Organizer B's competitions are listed. |
| 5 | Search for Organizer A's participant details. | Organizer A's monitoring data is not exposed. |

### Post-conditions
- Participant monitoring data remains scoped by organizer ownership.

### Notes
- Current app route: `/organizer/competition/[competitionId]`.
- Related current coverage: `tests/competition/organizer-management.test.ts` and `tests/monitoring/routes.test.ts`.
