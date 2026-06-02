## **ID:** UI-0005 Dashboard profile menu shows correct links

### Summary
Validates that dashboard or profile menus show role-appropriate links and allow common navigation actions.

### Priority
Medium

### Preconditions
- Tester has a complete mathlete account.
- Tester has an approved organizer account if organizer verification is included in the test session.
- Each account can access its dashboard.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Sign in as a mathlete and open `/mathlete`. | Mathlete dashboard loads. |
| 2 | Open the profile or account menu. | Mathlete-appropriate links such as settings, notifications, or sign out are shown. |
| 3 | Click settings. | The mathlete settings page opens. |
| 4 | Sign in as an organizer and open `/organizer` if available. | Organizer dashboard loads. |
| 5 | Open the organizer profile menu. | Organizer-appropriate links are shown without mathlete-only team actions unless intentionally shared. |

### Post-conditions
- Account navigation remains role-appropriate.

### Notes
- Current app routes: `/mathlete`, `/mathlete/settings`, `/organizer`, and `/organizer/settings`.
- Related current coverage: `tests/mathlete/workspace-nav.test.tsx` and `tests/organizer/organizer-nav.test.tsx`.
