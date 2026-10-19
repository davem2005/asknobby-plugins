---
name: manage-roles
description: Show, change, close, or review applications for an askNobby role that is already posted. Use when a recruiter asks which roles they have, wants to change or close a posted role, or asks who applied to a reference.
---

The person's own instructions take priority over this skill. The connector is already signed in.

1. Call `list_posted_jobs`. Show each reference, title, company, and application count. An aligned recruiter sees only roles attributed to them.
2. Before changing a role, call `get_posted_job` with that reference unchanged. Then call `post_job` with the same reference and the complete definition. Change only the answers they gave, and keep every other field from `get_posted_job`. A thin role is refused. Share the reference unchanged.
3. After a role is posted, call `fill_role_gap` with the reference. If it names a next question, ask that question and do not invent the answer. Call `fill_role_gap` again with that field and their words. For pay, pass `pay` as a whole number. A copied paragraph from another field is refused. Ask the next question until none remains. `correct_role` records a note and does not change the advert.
4. When they ask who applied, call `list_role_applications` with that reference. Show the pitch, the CV, and the match score. Use those only to consider the person for that role.
5. When they ask to close a role, call `close_job` with that reference. It leaves the board. Applications already made stay readable. When they ask to open it again, call `reopen_job`. Reopening counts toward the 10 open roles.

Do not invent a field they did not confirm. Do not delete a role.
