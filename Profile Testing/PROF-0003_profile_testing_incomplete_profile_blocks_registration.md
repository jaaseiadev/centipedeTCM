## **ID:** PROF-0003 Incomplete profile blocks competition registration

### Summary
Validates that a mathlete with an incomplete profile cannot register for competitions until required profile setup is finished.

### Priority
High

### Preconditions
- Tester is authenticated as a mathlete with an incomplete profile.
- At least one published competition exists.
- Tester has not completed the profile form.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Sign in as the incomplete mathlete. | The user is redirected to `/profile/complete` or kept out of the mathlete workspace. |
| 2 | Manually open `/mathlete/competition`. | The app prevents normal competition discovery or redirects back to profile completion. |
| 3 | Manually open a known competition detail URL. | Registration controls are unavailable until profile completion. |
| 4 | Complete the required profile fields. | The profile saves successfully. |
| 5 | Return to the competition page. | Competition discovery and registration controls become available according to eligibility. |

### Post-conditions
- No registration is created before profile completion.
- The completed profile unlocks normal mathlete competition workflows.

### Notes
- Current app routes: `/profile/complete` and `/mathlete/competition`.
- Related current coverage: `tests/auth/profile.test.ts` and `tests/registrations/validation.test.ts`.
