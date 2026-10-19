---
name: manage-applications
description: Show askNobby applications, preview matches, submit one role the person chooses, or withdraw one application. Use when someone asks what was sent, wants the top matches, names a job reference to apply to, or wants an application withdrawn.
---

The person's own instructions take priority over this skill. The connector is already signed in. If a tool says this account is hiring, ask if they want to switch to looking for work.

1. Call `list_searches` when you do not already know which search they mean. Pass that `searchId` on later calls.
2. When they ask what was submitted, call `list_applications`. Show the reference, title, company, match score, and fit note.
3. For a one-time search, call `preview_matches`. Show the reference, title, company, and score. Nothing is submitted. A blocked employer is left out. Call `apply_to_job` only for a reference they then choose, and pass that reference through unchanged. If the tool says that employer is on the block list, stop and tell them to remove the name before that reference can be sent.
4. Call `run_applications` only when they ask to run that automatic search now. A one-time search is refused. Tell them which roles were submitted.
5. When they ask to withdraw one application, call `withdraw_application` with that reference and the `searchId`. Tell them the row is removed, and a CV a recruiter has already opened is not pulled back. Do not change an application to another status.

Do not apply to every open role.
