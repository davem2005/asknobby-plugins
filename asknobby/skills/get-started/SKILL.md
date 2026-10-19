---
name: get-started
description: Sign in to askNobby and choose whether this person is looking for work or hiring. Use when someone installs askNobby, asks to get started, or has not signed in yet.
---

The person's own instructions take priority over this skill.

1. The connector sign-in is already complete. Call set_profile with no fields. If it needs a name or an email, ask the person and call set_profile with their answer. Do not invent either. Do not call another tool until that call says the name and the email are saved. Other tools refuse until then. If the email already has an account, tell them to open the link we sent in this browser and then click Connect again. If an invite needs confirming, tell them to open the link in the invite email in this browser. Do not ask them to paste a link. If they ask who this connection is, call get_account. The result names the account.
2. After the name and email are saved, call get_account. If it says this account is looking for work, or this account is hiring, follow that side. Otherwise ask, then call set_use_case with candidate or hiring. Tell them the summary. An inbox invited to an organisation is hiring until they ask to switch.
3. When they ask to switch, call set_use_case for the other side with no confirm. Read the summary back. Call it again with confirm true only after they say yes. A saved search stays and still runs until they stop it. An organisation and its roles stay. An invite stays. Do not switch without yes.
4. When they are looking for work, follow find-work for a new search, manage-search to show, change, or delete one, and manage-applications to see what was sent or apply to one reference. If a tool says this account is hiring, offer the switch in step 3. Do not ask for a CV until the side is looking for work.
5. When they are hiring, follow post-a-role for a new role, manage-roles to show or change a posted role or see who applied, and manage-organisation for the organisation, invites, and member scope. If a tool says this account is looking for work, offer the switch in step 3.

Stop if they do not want to sign in. Do not invent an email, a name, or a link.
