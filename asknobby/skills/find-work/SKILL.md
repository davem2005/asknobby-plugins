---
name: find-work
description: Create an askNobby job search from a CV. Use when someone is looking for work and needs a new search, including a second search.
---

The person's own instructions take priority over this skill. The connector is already signed in.

1. A company email can look for work. If `setup_job_search` says this account is hiring, ask if they want to switch. Call `set_use_case` with candidate and no confirm, read the summary, and pass confirm true only after they say yes. Do not ask for a CV until that switch is saved.
2. Read the CV. Ask for the LinkedIn URL, the titles they want, the work they want to spend their time doing, where they will work, how far they will travel, whether they want permanent, contract, fractional, or either, and the pay they will accept. Ask which employers must never receive an application, including their current company. Pass those names as `excludedEmployers`. An empty answer means there is no block list.
3. Keep a day rate in `minDayRate` and an annual salary in `minSalary`. Do not fold a day rate into the salary. Use `fractional` when they want contract or fractional work and not a permanent role. Use `either` when they want both. Remote work with some travel stays `remote`, and the travel goes in `travel`.
4. Call `setup_job_search` with the CV text, the original file when you have it, the limits they stated, and `excludedEmployers` when they named any. An account can keep two searches. Pass `newSearch` for the second one. Show the elevator pitch the server returns. It is written from their words and the CV.
5. Ask whether the search should apply automatically or show a one-time top five. Automatic is the default: up to 30 days, and a match percentage from 90 to 95. When they do not choose, the period is 30 days and it applies at 95%. Do not offer a line below 90.
6. For a one-time search, call `preview_matches`, show the reference, title, company, and score, and call `apply_to_job` only for a reference they choose. Pass the reference through unchanged. The server runs an automatic search once a day. A new application emails the address on the account. A Monday email summarises the past seven days when a search ran or a role was submitted. The fit note stays in the chat.

Later changes follow manage-search. Later applications follow manage-applications.

Do not invent a title, a pay floor, a location, or a reference. Do not apply to every open role.
