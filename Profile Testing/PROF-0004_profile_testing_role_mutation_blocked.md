## **ID:** PROF-0004 User cannot mutate role from settings

### Summary
Validates that a mathlete cannot change their role to organizer or another privileged role through profile or settings updates.

### Priority
High

### Preconditions
- Tester is authenticated as a complete mathlete.
- Tester can access `/mathlete/settings`.
- Browser developer tools or request inspection is available if the UI does not show role fields.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/settings`. | The settings page loads for the mathlete role. |
| 2 | Review visible editable fields. | Role fields are not presented as editable controls. |
| 3 | Save a normal allowed profile update. | The allowed update succeeds and the account remains a mathlete. |
| 4 | If testing through request inspection, attempt to include a role change payload. | The server ignores or rejects the role change. |
| 5 | Refresh and open `/organizer`. | The organizer workspace remains blocked for the mathlete. |

### Post-conditions
- The user's role is unchanged.
- Unauthorized organizer access is not granted.

### Notes
- Current app routes: `/mathlete/settings` and `/organizer`.
- Related current coverage: `tests/auth/settings.test.ts` and `tests/auth/profile-write.test.ts`.
