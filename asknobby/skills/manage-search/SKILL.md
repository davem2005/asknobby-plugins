---
name: manage-search
description: Show, change, or delete a saved askNobby job search. Use when someone asks what searches they have, wants to change titles, pay, location, the CV, or the automatic plan, or asks to delete a search.
---

The person's own instructions take priority over this skill. The connector is already signed in.

1. Call `list_searches`. Show the name, titles, place, engagement, pay, blocked employers, and plan for each search. Do not show the CV text unless they ask for it.
2. When the account has two searches, ask which one they mean and keep its `searchId`.
3. To change how often it applies, call `set_search_plan` with that `searchId`. Automatic is up to 30 days and a match percentage from 50 to 95. Pass `searchMode` `once` to stop automatic applications and keep the search.
4. To change the CV, titles, aim, place, engagement, pay, or blocked employers, call `setup_job_search` with that `searchId`. Take unchanged fields from `list_searches`, including `cvText` and `excludedEmployers`. Keep a day rate in `minDayRate` and an annual salary in `minSalary`. Pass an empty `excludedEmployers` list only when they want the block list cleared. Show the new elevator pitch. If the server says this connection is for hiring, stop and tell them to connect another inbox.
5. Call `delete_candidate` with that `searchId` only when they ask to delete that search. Tell them this removes the CV and the applications askNobby holds, and does not pull back a CV a recruiter has already seen.

Do not invent a title, a pay floor, or a location. Do not delete a search they did not name.
