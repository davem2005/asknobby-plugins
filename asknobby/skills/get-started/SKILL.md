---
name: get-started
description: Sign in to askNobby and choose whether this person is looking for work or hiring. Use when someone installs askNobby, asks to get started, or has not signed in yet.
---

The person's own instructions take priority over this skill.

1. The connector sign-in is already complete. Call set_profile with no fields. If it needs a name or an email, ask the person and call set_profile with their answer. Do not invent either. Do not ask for a code, a link, a token, or a session token. If set_profile names an organisation, they have joined it and this connection is for hiring. If it says the invite has expired, tell them to ask the admin for a new one.
2. Ask whether they are looking for work or hiring. When they answer and nothing is saved yet, call set_use_case with candidate or hiring. The first choice is kept. An inbox invited to an organisation is hiring. A company email can do either until that choice is made.
3. When they are looking for work, follow find-work for a new search, manage-search to show, change, or delete one, and manage-applications to see what was sent or apply to one reference. If a tool says this connection is for hiring, stop and tell them to connect another inbox.
4. When they are hiring, follow post-a-role for a new role, manage-roles to show or change a posted role or see who applied, and manage-organisation for the organisation, invites, and member scope. If a tool says this connection is for looking for work, stop and tell them to connect another inbox.

Stop if they do not want to sign in. Do not invent an email, a name, or a link.
