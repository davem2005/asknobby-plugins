---
name: post-a-role
description: Create an askNobby recruiting organisation and post a new role. Use when someone is hiring and wants to publish a role that is not already posted.
---

The person's own instructions take priority over this skill. The connector is already signed in. A company email can hire. If `create_recruiting_org` says this connection is for looking for work, stop and tell them to connect another inbox.

1. Ask for the organisation name, the registered business name, the website, a phone number, and the company registration number when they have one. Call `create_recruiting_org` before posting. A company email domain joins the organisation that already uses that domain. A public inbox such as Gmail starts its own organisation. The first person becomes the admin.
2. Ask for the role in this order, and do not invent an answer: title and company; where the employment is based; office, hybrid, or remote; permanent or contract; full-time or part-time; the pay floor; why the role exists; what the week actually is; what the person must already have done; who they report to; how the team works; and the team culture. Also ask team size, who they work with, days in the workplace, and what good looks like after six months when the recruiter knows.
3. Call `post_job` only after those answers exist. A thin role is refused. The result names the organisation, the recruiter the role is attributed to, and a short reference. Share that reference unchanged. Ask any follow-up of that recruiter. Pass `reference` to add the richer answers. Pass `attributedEmail` only when an admin is attributing the role to another member.
4. An organisation can keep 10 open roles, 15 members, and 10 pending invites.

Changes to a posted role follow manage-roles. Invites and organisation details follow manage-organisation.

Do not fill a blank with a plausible answer. Do not post a role for an organisation that has not been created.
