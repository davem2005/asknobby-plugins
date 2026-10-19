---
name: manage-organisation
description: Update an askNobby recruiting organisation and manage its invites and member scope. Use when a recruiter wants to change organisation details, invite a colleague, revoke an invite, or change who can see every role.
---

The person's own instructions take priority over this skill. The connector is already signed in.

1. To change the organisation name, business name, website, phone, or company number, call `create_recruiting_org` with the full set of details. An admin on a company email domain updates the existing organisation. A colleague who is not an admin is told they already belong to it.
2. Call `invite_recruiter` only when an admin asks to invite someone. Ask once whether that person should have aligned roles or all roles. The result says the invite was sent and does not include the token.
3. Call `list_invites` when an admin asks who is invited. Call `revoke_invite` with the email when they ask to cancel one. The token stops working.
4. Call `set_member_scope` when an admin names a member and a new scope. This does not make them an admin.
5. When someone pastes an invite token, call `accept_invite` with that token. Do not repeat it.

There is no tool to list every member, remove a member, or delete the organisation. Say that when they ask. Do not invent an email or a scope.
