## **ID:** PROF-0001 Mathlete completes required profile

### Summary
Validates that a mathlete with an incomplete profile can complete the required profile fields and unlock mathlete workspace access.

### Priority
High

### Preconditions
- Tester is authenticated as a mathlete with an incomplete profile.
- Tester can access `/profile/complete`.
- Required profile values are available, including full name, school, and grade level if shown by the form.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/profile/complete`. | The profile completion page displays the setup form. |
| 2 | Submit the form with required fields empty. | The form blocks submission or displays clear validation messages for missing required fields. |
| 3 | Fill in all required profile fields using valid values. | The entered values remain visible and selectable values are accepted. |
| 4 | Submit the completed form. | The profile is saved and the user is redirected to the mathlete workspace. |
| 5 | Open `/mathlete`. | The mathlete dashboard loads instead of redirecting back to profile completion. |

### Post-conditions
- The mathlete profile is marked complete.
- The mathlete can access protected mathlete routes.

### Notes
- Current app route: `/profile/complete`.
- Related current coverage: `tests/auth/profile.test.ts` and `tests/auth/profile-write.test.ts`.
