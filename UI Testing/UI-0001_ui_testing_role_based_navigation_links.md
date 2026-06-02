## **ID:** UI-0001 Role-based navigation links are displayed

### Summary
Validates that the visible workspace navigation matches the authenticated user's role.

### Priority
Medium

### Preconditions
- Tester has one complete mathlete account.
- Tester has one approved organizer account, or can ask another tester with organizer access to execute the organizer portion.
- Each account can sign in successfully.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Sign in as a complete mathlete and open `/mathlete`. | Mathlete workspace navigation appears. |
| 2 | Review visible navigation links. | Mathlete-focused links such as competitions, teams, history, and settings are shown. |
| 3 | Sign out and sign in as an approved organizer. | The organizer workspace opens. |
| 4 | Review visible organizer navigation links. | Organizer-focused links such as competitions, problem banks, scoring, history, profile, or settings are shown. |
| 5 | Compare both workspaces. | Mathlete-only and organizer-only navigation items are not mixed incorrectly. |

### Post-conditions
- Navigation state remains role-appropriate after refresh.

### Notes
- Current app routes: `/mathlete` and `/organizer`.
- Related current coverage: `tests/mathlete/workspace-nav.test.tsx`, `tests/organizer/organizer-nav.test.tsx`, and `tests/navigation-feedback.test.ts`.
