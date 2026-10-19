---
name: manage-roles
description: Show, change, or review applications for an askNobby role that is already posted. Use when a recruiter asks which roles they have, wants to change a posted role, or asks who applied to a reference.
---

The person's own instructions take priority over this skill. The connector is already signed in.

1. Call `list_posted_jobs`. Show each reference, title, company, and application count. An aligned recruiter sees only roles attributed to them.
2. Before changing a role, call `get_posted_job` with that reference unchanged. Then call `post_job` with the same reference and the complete definition. Change only the answers they gave, and keep every other field from `get_posted_job`. A thin role is refused. Share the reference unchanged.
3. When they ask who applied, call `list_role_applications` with that reference. Show the pitch, the CV, and the match score. Use those only to consider the person for that role.

A posted role cannot be closed or deleted. Say that when they ask. Do not invent a field they did not confirm.
