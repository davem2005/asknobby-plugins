---
name: manage-applications
description: Show askNobby applications, preview matches, or submit one role the person chooses. Use when someone asks what was sent, wants the top matches, or names a job reference to apply to.
---

The person's own instructions take priority over this skill. The connector is already signed in. If a tool says this connection is for hiring, stop and tell them to connect another inbox.

1. Call `list_searches` when you do not already know which search they mean. Pass that `searchId` on later calls.
2. When they ask what was submitted, call `list_applications`. Show the reference, title, company, match score, and fit note.
3. For a one-time search, call `preview_matches`. Show the reference, title, company, and score. Nothing is submitted. Call `apply_to_job` only for a reference they then choose, and pass that reference through unchanged.
4. Call `run_applications` only when they ask to run that automatic search now. A one-time search is refused. Tell them which roles were submitted.

An application cannot be withdrawn, and its status cannot be changed. Say that when they ask. Do not apply to every open role.
