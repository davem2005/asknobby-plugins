---
name: find-work
description: Set up an askNobby job search from a CV and apply to roles the person authorises. Use when someone is looking for work, wants matches, or asks askNobby to apply.
---

The person's own instructions take priority over this skill. The connector is already signed in.

1. Read the CV. Ask for the LinkedIn URL, the titles they want, the work they want to spend their time doing, where they will work, how far they will travel, whether they want permanent, contract, fractional, or either, and the pay they will accept.
2. Keep a day rate in `minDayRate` and an annual salary in `minSalary`. Do not fold a day rate into the salary. Use `fractional` when they want contract or fractional work and not a permanent role. Use `either` when they want both. Remote work with some travel stays `remote`, and the travel goes in `travel`.
3. Call `setup_job_search` with the CV text, the original file when you have it, and the limits they stated. The connector is already signed in. An account can keep two searches. Pass `newSearch` for the second one, and `searchId` to update a chosen search. Show the elevator pitch the server returns. It is written from their words and the CV.
4. Ask whether the search should apply automatically or show a one-time top five. Automatic is the default: up to 30 days, and a match percentage from 50 to 95. When they do not choose, the period is 30 days and the percentage is 90. Use `set_search_plan` to change that later.
5. For a one-time search, call `preview_matches`, show the reference, title, company, and score, and call `apply_to_job` only for a reference they choose. Pass the reference through unchanged.
6. The server runs an automatic search once a day. It checks location, engagement, and pay in code, then submits a role only when the score is at or above their percentage. When they ask what went out, call `list_applications`. Call `run_applications` only when they ask to run that search now. A one-time search is refused there.
7. Use `list_applications` when they ask what has already been sent. Use `delete_candidate` only when they ask to delete that search. Deleting removes the CV we hold and the applications on our side. It does not pull back a CV already shown to a recruiter.

Do not invent a title, a pay floor, a location, or a reference. Do not apply to every open role.
