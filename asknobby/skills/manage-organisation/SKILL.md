---
name: manage-organisation
description: Update an askNobby recruiting organisation and manage its invites, members, and member scope. Use when a recruiter wants to change organisation details, invite a colleague, revoke an invite, see members, remove a member, or change who can see every role.
---

The person's own instructions take priority over this skill. The connector is already signed in.

1. To change the organisation name, business name, website, phone, or company number, call `create_recruiting_org` with confirm true and the full set of details. An admin on a company email domain updates the existing organisation. Someone who is not a member is not added. An admin has to invite them.
2. Call `invite_recruiter` only when an admin asks to invite someone. Ask once whether that person should have aligned roles or all roles. The email contains the link. Do not read out or ask for the link. An inbox that is looking for work is refused until that person asks to switch it to hiring.
3. Call `list_invites` when an admin asks who is invited. Call `revoke_invite` with the email when they ask to cancel one.
4. Call `set_member_scope` when an admin names a member and a new scope. This does not make them an admin.
5. When someone says they were invited, tell them to add askNobby, click Connect, give their name and the invited email in the chat, then open the invite link in that same browser. Call `accept_invite` with no token only to check. If it says the account has already joined, do not ask them to open the link again. Joining happens on the link. If the result says the invite has expired, tell them to ask the admin for a new one. Do not ask them to paste anything from the email.
6. When an admin asks who is in the organisation, call `list_members`. When they ask to remove a member, call `remove_member` with that email. Refuse is the right result when that person is the only admin. Their open roles stay posted.

There is no tool to delete the organisation. Say that when they ask. Do not invent an email or a scope.
