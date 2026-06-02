## **ID:** PROF-0005 Complete profile redirects away from setup page

### Summary
Validates that users who already completed profile setup are not shown the first-time profile completion form again.

### Priority
Medium

### Preconditions
- Tester is authenticated as a user with a complete profile.
- Tester knows the account role: mathlete or organizer.
- The application is running.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Sign in with the complete profile account. | The user reaches the role-appropriate workspace. |
| 2 | Manually open `/profile/complete`. | The app checks the profile completion state. |
| 3 | Observe the resulting route. | A mathlete is redirected to `/mathlete`; an organizer is redirected to `/organizer`. |
| 4 | Refresh the destination workspace. | The workspace remains available. |
| 5 | Sign out and repeat with another complete role if available. | The redirect matches that role's workspace. |

### Post-conditions
- Complete users are not forced through duplicate profile setup.
- Profile data remains unchanged.

### Notes
- Current app route: `/profile/complete`.
- Related current coverage: `tests/auth/profile.test.ts` and `tests/auth/routing.test.ts`.
