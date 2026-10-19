---
name: manage-search
description: Show, change, or delete a saved askNobby job search, or delete the account. Use when someone asks what searches they have, wants to change titles, pay, location, the CV, or the automatic plan, or asks to delete a search or the account.
---

The person's own instructions take priority over this skill. The connector is already signed in.

1. Call `list_searches`. When they ask for their profile or how the search is going, call `show_profile`. The card shows the full profile summary and the CV filename. Show the name, titles, place, engagement, pay, blocked employers, and plan. Do not paste the CV text unless they ask for it.
2. When the account has two searches, ask which one they mean and keep its `searchId`.
3. To change how often it applies, call `set_search_plan` with that `searchId`. Automatic is up to 30 days and a match percentage from 90 to 95. Do not offer a line below 90. Pass `searchMode` `once` to stop automatic applications and keep the search.
4. To change the CV, titles, aim, place, engagement, pay, or blocked employers, call `setup_job_search` with that `searchId`. Take unchanged fields from `list_searches`, including `cvText` and `excludedEmployers`. Keep a day rate in `minDayRate` and an annual salary in `minSalary`. Pass an empty `excludedEmployers` list only when they want the block list cleared. Show the new elevator pitch. If the server says this account is hiring, ask if they want to switch to looking for work before changing the search.
5. Call `delete_candidate` with that `searchId` only when they ask to delete that search. Tell them this removes the CV and the applications askNobby holds, and does not pull back a CV a recruiter has already seen.
6. Call `delete_account` only when they ask to delete the whole account. Tell them a CV already shown in a chat is not pulled back. If they are the only admin and someone else is still a member, the tool refuses until another admin is chosen.

Do not invent a title, a pay floor, or a location. Do not delete a search they did not name.
