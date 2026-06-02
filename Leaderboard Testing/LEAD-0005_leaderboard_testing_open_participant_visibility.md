## **ID:** LEAD-0005 Open leaderboard is visible to participant context

### Summary
Validates that open competition leaderboard results are visible to participants according to the open competition visibility rules.

### Priority
Medium

### Preconditions
- An open competition exists with at least one submitted attempt.
- Tester is authenticated as a participant or eligible mathlete.
- Leaderboard data has been computed.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open the open competition detail or results page. | The page loads open competition context. |
| 2 | Navigate to leaderboard or result area. | Leaderboard information is visible according to open competition rules. |
| 3 | Review visible entries. | Entries show participant-facing ranking without exposing private data. |
| 4 | Submit another valid open attempt if allowed and safe for test data. | The leaderboard updates according to the configured grading policy. |
| 5 | Refresh the leaderboard. | The visible ranking remains consistent. |

### Post-conditions
- Open leaderboard visibility follows participant-context rules.

### Notes
- Related current coverage: `tests/leaderboard/visibility.test.ts` and `tests/scoring/policies.test.ts`.
