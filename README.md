# CentipedeTCM

CentipedeTCM is the Markdown-based Test Case Management repository for the CSci 136 Software Engineering II project named Centipede.

The system under test is MathWiz Arena, a secure web-based mathematics competition platform with mathlete and organizer workflows. This repository stores manual test cases grouped by testing domain. Admin testing and anti-cheat testing are intentionally omitted from this starter set.

## Repository Structure

Root files:

- `.gitignore`
- `LICENSE`
- `README.md`
- `completed-test-cases.md`

Testing domains:

- [Authentication Testing](Authentication%20Testing/)
- [Profile Testing](Profile%20Testing/)
- [Organizer Application Testing](Organizer%20Application%20Testing/)
- [Problem Bank Testing](Problem%20Bank%20Testing/)
- [Competition Wizard Testing](Competition%20Wizard%20Testing/)
- [Scoring Rules Testing](Scoring%20Rules%20Testing/)
- [Team Management Testing](Team%20Management%20Testing/)
- [Competition Search Testing](Competition%20Search%20Testing/)
- [Competition Registration Testing](Competition%20Registration%20Testing/)
- [Mathlete Arena Testing](Mathlete%20Arena%20Testing/)
- [Notifications Testing](Notifications%20Testing/)
- [Calendar Testing](Calendar%20Testing/)
- [Leaderboard Testing](Leaderboard%20Testing/)
- [History Testing](History%20Testing/)
- [Dispute Testing](Dispute%20Testing/)
- [Participant Monitoring Testing](Participant%20Monitoring%20Testing/)
- [Security Testing](Security%20Testing/)
- [UI Testing](UI%20Testing/)
- [Performance Testing](Performance%20Testing/)

## Naming Conventions

Folders use Title Case with spaces.

Test case files use this format:

```text
<PREFIX>-<NNNN>_<area>_testing_<action_or_topic>.md
```

Examples:

- `AUTH-0001_authentication_testing_google_login.md`
- `TEAM-0001_team_management_testing_create_team.md`
- `ARENA-0001_mathlete_arena_testing_enter_scheduled_competition.md`

Prefixes:

| Prefix | Domain |
| --- | --- |
| AUTH | Authentication Testing |
| PROF | Profile Testing |
| ORGAPP | Organizer Application Testing |
| PBANK | Problem Bank Testing |
| COMP | Competition Wizard Testing |
| SCORE | Scoring Rules Testing |
| TEAM | Team Management Testing |
| SEARCH | Competition Search Testing |
| REG | Competition Registration Testing |
| ARENA | Mathlete Arena Testing |
| NOTIF | Notifications Testing |
| CAL | Calendar Testing |
| LEAD | Leaderboard Testing |
| HIST | History Testing |
| DISP | Dispute Testing |
| MON | Participant Monitoring Testing |
| SEC | Security Testing |
| UI | UI Testing |
| PERF | Performance Testing |

## Test Case Status Guide

Use these values in `completed-test-cases.md`:

- `Not Started`
- `In Progress`
- `Passed`
- `Failed`
- `Blocked`
- `For Retest`
- `Verified`

## How To Add A New Test Case

1. Choose the correct testing domain folder.
2. Create a new Markdown file using the naming convention.
3. Use the same template as the existing test cases.
4. Write concrete preconditions, user actions, expected behavior, post-conditions, and notes.
5. Add the new test case to `completed-test-cases.md` with status `Not Started`.

## How To Update The Tracker

After executing a test case, update `completed-test-cases.md`:

1. Set the `Status` value.
2. Add the tester name or initials.
3. Add the execution date.
4. Record short notes for defects, blocked setup, or retest details.

## Starter Scope

This starter set contains five focused manual test cases per testing domain. The selected cases are based on existing MathWiz Arena routes and supporting automated test coverage in the current Centipede codebase. Admin testing and anti-cheat testing remain excluded. Add more cases only if the target repository decides to expand beyond the current five-case category limit.

## Git Commands For The New Repository

```bash
git init
git add .
git commit -m "initial test case management repository"
git branch -M main
git remote add origin https://github.com/[username]/CentipedeTCM.git
git push -u origin main
```
