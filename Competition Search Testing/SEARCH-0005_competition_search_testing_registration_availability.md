## **ID:** SEARCH-0005 Competition cards show registration availability

### Summary
Validates that competition discovery cards communicate whether registration is available, closed, or already completed.

### Priority
Medium

### Preconditions
- Tester is authenticated as a complete mathlete.
- Test data includes competitions in different registration states if possible.
- Tester can access `/mathlete/competition`.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/competition`. | Competition cards or rows are displayed. |
| 2 | Locate a competition with open registration. | The card shows an available registration or view action. |
| 3 | Locate a competition the tester is already registered for. | The card indicates registered state or directs to details. |
| 4 | Locate a closed or unavailable competition if present. | The card does not invite invalid registration. |
| 5 | Open each detail page if needed. | The detail page state matches the card state. |

### Post-conditions
- Registration state is unchanged unless the tester explicitly registers.

### Notes
- Current app route: `/mathlete/competition`.
- Related current coverage: `tests/competition/discovery.test.ts` and `tests/ui/competition-registration-panel.test.tsx`.
