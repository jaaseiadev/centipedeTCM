## **ID:** REG-0002 Duplicate individual registration is blocked

### Summary
Validates that a mathlete cannot register twice for the same individual competition.

### Priority
High

### Preconditions
- Tester is authenticated as a complete mathlete.
- Tester is already registered for a published individual competition.
- The registration window is still open.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the already registered competition detail page. | The page shows the mathlete is already registered. |
| 2 | Look for the registration action. | The register action is disabled, hidden, or replaced by registered/withdrawal state. |
| 3 | Attempt to register again if any action remains available. | The system blocks duplicate registration and shows a clear message. |
| 4 | Refresh the page. | Only one registration state is shown for the mathlete. |

### Post-conditions
- Only one registration record exists for the mathlete and competition.

### Notes
- Current app route: `/mathlete/competition/[competitionId]`.
- Related current coverage: `tests/registrations/api.test.ts`, `tests/registrations/validation.test.ts`, and `tests/registrations/messages.test.ts`.
