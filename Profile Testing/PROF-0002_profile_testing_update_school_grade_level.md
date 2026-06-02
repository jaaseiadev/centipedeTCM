## **ID:** PROF-0002 Mathlete updates school and grade level

### Summary
Validates that a complete mathlete can update editable profile information without changing protected role fields.

### Priority
Medium

### Preconditions
- Tester is authenticated as a complete mathlete.
- Tester can access the mathlete settings or profile area.
- Tester has valid replacement school and grade level values.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/mathlete/settings`. | The mathlete settings page loads for the signed-in mathlete. |
| 2 | Locate editable profile fields such as school and grade level. | Editable profile fields are visible if supported by the current UI. |
| 3 | Change the school and grade level values. | The new values are accepted by the form controls. |
| 4 | Save the changes. | The page confirms the update or keeps the saved values visible. |
| 5 | Refresh the page. | The updated school and grade level values remain saved. |

### Post-conditions
- The mathlete profile contains the updated allowed fields.
- The mathlete role remains unchanged.

### Notes
- Current app route: `/mathlete/settings`.
- Related current coverage: `tests/auth/settings.test.ts` and `tests/auth/profile-write.test.ts`.
