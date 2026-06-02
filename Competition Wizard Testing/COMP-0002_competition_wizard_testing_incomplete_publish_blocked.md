## **ID:** COMP-0002 Organizer cannot publish incomplete competition

### Summary
Validates that the competition wizard blocks publishing when required competition information is missing.

### Priority
High

### Preconditions
- Tester is authenticated as an approved organizer.
- Tester can access `/organizer/competition/create`.
- At least one problem bank exists if the wizard requires problem selection.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/competition/create`. | The competition wizard loads. |
| 2 | Leave required fields such as title, description, rules, schedule, or problem selection incomplete. | The wizard keeps required fields empty or incomplete. |
| 3 | Attempt to publish the competition. | Publishing is blocked. |
| 4 | Review the validation messages. | Missing required fields are identified with clear user-facing messages. |
| 5 | Fill in the missing required fields and try again. | Publishing becomes available only when required data is complete and valid. |

### Post-conditions
- No incomplete competition is published.
- Any saved draft remains a draft if supported by the current implementation.

### Notes
- Current app route: `/organizer/competition/create`.
- Related current coverage: `tests/competition/validation.test.ts` and `tests/ui/competition-wizard-lifecycle.test.tsx`.
