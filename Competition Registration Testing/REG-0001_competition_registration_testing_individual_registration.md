## **ID:** REG-0001 Mathlete registers for individual competition

### Summary
Validates that a mathlete can register for an eligible individual scheduled competition and receives clear registration feedback.

### Priority
High

### Preconditions
- Tester is authenticated as a mathlete with a complete profile.
- A published individual scheduled competition exists.
- The competition registration window is open.
- The competition has available capacity.
- Tester is not already registered for the competition.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/competition`. | The available competition list loads. |
| 2 | Select the target individual competition. | The competition detail page opens and shows registration information. |
| 3 | Click the registration action. | The UI shows a pending or processing state. |
| 4 | Wait for completion. | The page confirms successful registration and updates the action state to registered. |
| 5 | Refresh the page. | The registered state remains visible after reload. |

### Post-conditions
- A registration record exists for the mathlete and competition.
- The mathlete should not be able to register for the same competition again.

### Notes
- Current app routes: `/mathlete/competition` and `/api/mathlete/competition`.
- Related current coverage: `tests/registrations/api.test.ts`, `tests/registrations/register-route-notifications.test.ts`, and `tests/ui/competition-registration-panel.test.tsx`.
