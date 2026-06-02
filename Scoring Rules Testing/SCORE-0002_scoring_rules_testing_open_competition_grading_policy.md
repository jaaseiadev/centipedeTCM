## **ID:** SCORE-0002 Organizer selects open competition grading policy

### Summary
Validates that open competition grading policy options can be selected and saved using supported values.

### Priority
Medium

### Preconditions
- Tester is authenticated as an approved organizer.
- An open competition scoring setup is available, or the scoring page supports previewing open grading policies.
- Tester can access `/organizer/scoring`.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/scoring`. | The organizer scoring workspace loads. |
| 2 | Locate open competition grading policy controls. | Supported options such as highest score, latest score, or average score are available if implemented. |
| 3 | Select a supported grading policy. | The selected policy is visibly active. |
| 4 | Save or preview the scoring configuration. | The selected policy is accepted without validation errors. |
| 5 | Reload or revisit the scoring context. | The saved or selected grading policy remains consistent with the previous selection. |

### Post-conditions
- The selected grading policy is stored or reflected in the current scoring configuration.

### Notes
- Current app route: `/organizer/scoring`.
- Related current coverage: `tests/scoring/policies.test.ts`, `tests/scoring/summary.test.ts`, and `tests/ui/scoring-controls.test.tsx`.
