## **ID:** SCORE-0001 Organizer configures scoring rules

### Summary
Validates that organizer scoring controls accept valid scoring policy values and reject invalid scoring configuration.

### Priority
Medium

### Preconditions
- Tester is authenticated as an approved organizer.
- Tester can access the organizer scoring page.
- At least one competition or scoring context exists if required by the UI.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/scoring`. | The scoring workspace loads for the organizer. |
| 2 | Review available scoring controls. | The page shows supported scoring options such as point rules or grading policies. |
| 3 | Enter valid scoring values. | The UI accepts valid numeric or option values without validation errors. |
| 4 | Try an invalid value such as a negative point value if the field allows typing. | The UI blocks the value or displays a clear validation message. |
| 5 | Save the valid scoring configuration. | The scoring configuration is saved or reflected in the scoring preview. |

### Post-conditions
- Valid scoring settings remain available for the organizer.
- Invalid scoring values are not persisted.

### Notes
- Current app route: `/organizer/scoring`.
- Related current coverage: `tests/scoring/validation.test.ts`, `tests/scoring/policies.test.ts`, and `tests/ui/scoring-controls.test.tsx`.
