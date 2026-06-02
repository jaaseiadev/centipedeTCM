## **ID:** ARENA-0001 Mathlete enters scheduled competition after start

### Summary
Validates that a registered mathlete can enter a scheduled competition only when the competition is live or has reached the allowed start time.

### Priority
High

### Preconditions
- Tester is authenticated as a registered mathlete.
- The target scheduled competition exists and has problems.
- The competition is live or the server start time has passed.
- Tester has not already submitted a final attempt if single attempt rules apply.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the target competition detail page. | The competition detail page displays the current competition state. |
| 2 | Review organizer rules if shown. | Rules are visible before arena entry. |
| 3 | Accept organizer rules if required. | The entry action becomes available after acceptance. |
| 4 | Click the arena entry action. | The arena page opens for the competition. |
| 5 | Confirm that problems and timer are visible. | The arena displays question content, answer controls, and timing information. |

### Post-conditions
- An active attempt exists for the mathlete.
- The mathlete remains within the arena flow for the selected competition.

### Notes
- Current app route: `/mathlete/competition/[competitionId]`.
- Related current coverage: `tests/arena/routes.test.ts`, `tests/arena/page-data.test.ts`, and `tests/ui/arena-experience.test.tsx`.
