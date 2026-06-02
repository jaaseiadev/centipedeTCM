## **ID:** SCORE-0004 Custom point scoring applies configured values

### Summary
Validates that custom point values configured by an organizer are used in scoring previews or results.

### Priority
High

### Preconditions
- Tester is authenticated as an approved organizer.
- A scoring setup exists where custom point values can be configured.
- Sample problems or submissions exist for preview.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/scoring`. | The scoring workspace loads. |
| 2 | Choose custom point scoring if available. | Custom point controls become available. |
| 3 | Enter valid point values for selected problems or groups. | The values are accepted and reflected in the preview. |
| 4 | Try a negative or nonnumeric point value. | The invalid value is blocked or flagged. |
| 5 | Save the valid configuration. | Scoring preview or saved settings use the configured custom values. |

### Post-conditions
- Valid custom points are retained.
- Invalid values are not saved.

### Notes
- Current app route: `/organizer/scoring`.
- Related current coverage: `tests/scoring/validation.test.ts` and `tests/ui/scoring-controls.test.tsx`.
