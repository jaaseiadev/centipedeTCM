## **ID:** COMP-0001 Organizer creates scheduled individual competition

### Summary
Validates that an approved organizer can create a scheduled individual competition with required description, rules, schedule, and problem selection data.

### Priority
High

### Preconditions
- Tester is authenticated as an approved organizer.
- At least one problem bank with usable problems exists.
- Tester can access `/organizer/competition/create`.
- A future start date and duration are available for scheduling.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open `/organizer/competition/create`. | The competition creation wizard loads. |
| 2 | Choose an individual scheduled competition type. | The wizard shows fields relevant to scheduled individual competition setup. |
| 3 | Enter a title, description, and organizer rules. | Required text fields accept the values. |
| 4 | Select a future start time and duration. | Schedule values are accepted and displayed consistently. |
| 5 | Select eligible problems from the problem bank. | Selected problems are shown in the wizard review or summary step. |
| 6 | Save or publish the competition. | The competition is created and appears in the organizer competition list. |

### Post-conditions
- A scheduled individual competition exists in organizer competition management.
- The competition can be discovered by eligible mathletes after publication.

### Notes
- Current app routes: `/organizer/competition/create` and `/organizer/competition`.
- Related current coverage: `tests/competition/create-route.test.ts`, `tests/competition/validation.test.ts`, and `tests/ui/competition-wizard-schedule.test.tsx`.
