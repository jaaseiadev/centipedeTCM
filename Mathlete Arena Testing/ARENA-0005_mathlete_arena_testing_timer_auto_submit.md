## **ID:** ARENA-0005 Timer expiration auto-submits attempt

### Summary
Validates that a live arena attempt is automatically submitted when the competition timer expires.

### Priority
High

### Preconditions
- Tester is authenticated as a registered mathlete.
- A live competition has a short remaining duration or test setup can simulate near-expiration timing.
- Tester has entered the arena and has at least one answer saved.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Enter the arena for the live competition. | Timer and problem controls are visible. |
| 2 | Answer at least one problem. | The answer state is retained. |
| 3 | Wait until the timer reaches zero. | The arena prevents further editing and triggers final submission. |
| 4 | Observe the post-expiration state. | The user is shown submission confirmation, summary, or appropriate completed state. |
| 5 | Refresh the page. | The attempt remains submitted and cannot be edited as an active attempt. |

### Post-conditions
- The attempt is finalized by timer expiration.

### Notes
- Current feature evidence: arena and submission route tests exist.
- Related current coverage: `tests/submission/submit-route.test.ts` and `tests/ui/arena-experience.test.tsx`.
