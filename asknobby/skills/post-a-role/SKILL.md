---
name: post-a-role
description: Create an askNobby recruiting organisation and post a new role. Use when someone is hiring and wants to publish a role that is not already posted.
---

The person's own instructions take priority over this skill. The connector is already signed in. A company email can hire. If `create_recruiting_org` says this account is looking for work, ask if they want to switch. Call `set_use_case` with hiring and no confirm, read the summary, and pass confirm true only after they say yes. The saved search stays.

1. Ask for the organisation name, the registered business name, the website, a phone number, and the company registration number when they have one. A missing phone does not stop the organisation. Ask for it again later. Call `create_recruiting_org` without confirm and show the preview. Call it again with confirm true only after they say yes. A company domain that already has an organisation is not joined. Tell them an admin has to invite this inbox. A public inbox such as Gmail starts its own organisation. The first person becomes the admin.
2. Ask for the role in this order, and do not invent an answer: title and company; where the employment is based; office, hybrid, or remote; permanent or contract; full-time or part-time; the pay floor; why the role exists; what the week actually is; what the person must already have done; who they report to; how the team works; and the team culture. Also ask team size, who they work with, days in the workplace, and what good looks like after six months when the recruiter knows.
3. Call `post_job` only after those answers exist. A thin role is refused. The result names the organisation, the recruiter the role is attributed to, and a reference in four groups of four. Share that reference unchanged. Ask any follow-up of that recruiter. Pass `reference` to add the richer answers. Pass `attributedEmail` only when an admin is attributing the role to another member.
4. An organisation can keep 10 open roles, 15 members, and 10 pending invites.

Changes to a posted role follow manage-roles. Invites and organisation details follow manage-organisation.

Do not fill a blank with a plausible answer. Do not post a role for an organisation that has not been created.
