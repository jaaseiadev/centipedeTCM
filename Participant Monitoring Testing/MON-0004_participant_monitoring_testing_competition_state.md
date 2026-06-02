## **ID:** MON-0004 Organizer monitors competition state changes

### Summary
Validates that organizer monitoring reflects competition lifecycle state changes such as scheduled, live, or completed.

### Priority
Medium

### Preconditions
- Tester is authenticated as an approved organizer.
- Organizer owns a competition that can transition through lifecycle states.
- Tester can access organizer competition management.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/competition`. | Competition cards or rows show current state. |
| 2 | Open a scheduled competition detail page. | Scheduled state and start information are visible. |
| 3 | Start the competition manually if supported or wait for scheduled start. | The state changes to live. |
| 4 | Refresh the organizer view. | The live state is reflected in the UI. |
| 5 | Complete or observe completion state if available. | The completed state is reflected when the lifecycle transition occurs. |

### Post-conditions
- Competition lifecycle state matches backend state.

### Notes
- Current app route: `/organizer/competition`.
- Related current coverage: `tests/competition/lifecycle-route-fallback.test.ts` and `tests/monitoring/routes.test.ts`.
