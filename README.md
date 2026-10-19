# askNobby plugins

This repository holds the public askNobby plugin. Stratustech Ltd publishes askNobby. The application server is not in this repository. The plugin folder is [asknobby](./asknobby). It contains the manifest, the skills, the icon, and the address of the remote server.

The server is https://www.asknobby.com/api/mcp.

askNobby applies for a person who is looking for work, and lets a recruiter post a role, from the chat they already use. The chat is the interface. ChatGPT, Claude, and Cursor install this plugin and call that server.

## Connect

Click Connect in the assistant. Give your name and email in the chat. Open the message we send in the same browser and press Confirm. Do not paste a code, a link, or a session token into the chat.

- ChatGPT: add a custom connector where the workspace allows it, and paste the server address.
- Claude: Settings, then Connectors. Add a custom connector and paste the same address.
- Cursor: add an MCP server with that address.

A result that lists a search, a role, or an application is drawn as a card when the assistant supports it. The card shows the full profile summary and the name of the CV file. It does not show the CV text.

Guide: https://www.asknobby.com/docs
Privacy: https://www.asknobby.com/privacy
Terms: https://www.asknobby.com/terms

## Skills

| Skill | When it is used |
| --- | --- |
| [get-started](./asknobby/skills/get-started/SKILL.md) | The person has just connected, or has not saved a name and email |
| [find-work](./asknobby/skills/find-work/SKILL.md) | Create a search, including a second search |
| [manage-search](./asknobby/skills/manage-search/SKILL.md) | Show a profile, change a search, or delete a search or the account |
| [manage-applications](./asknobby/skills/manage-applications/SKILL.md) | Show what was submitted, preview matches, apply to one reference, or withdraw one application |
| [post-a-role](./asknobby/skills/post-a-role/SKILL.md) | Create an organisation and post a new role |
| [manage-roles](./asknobby/skills/manage-roles/SKILL.md) | Show, change, or close a posted role, or see who applied |
| [manage-organisation](./asknobby/skills/manage-organisation/SKILL.md) | Update the organisation, invites, members, and member scope |

## Looking for work

The assistant reads the CV, asks for a LinkedIn URL, the titles, the work you want to spend your time doing, and limits for place, engagement, and pay. It asks which employers must never receive an application, including your current company. A day rate stays separate from an annual salary. You can keep two searches. A blocked employer is skipped on the daily run, the top five, and a named reference.

A daily search is the usual choice. You can set it for up to 30 days. If you do not choose a match, it applies at 95%. You can set that line from 90% to 95%. It will not apply below 90%. Place, engagement, pay, and the block list are checked before that. A one-time search shows up to five roles and applies only to the references you name. A short list refreshes on the daily run and submits nothing until you name a reference.

Ask for your profile to see the saved search, the full profile summary, and the latest applications. You can withdraw one application. A CV a recruiter has already opened is not pulled back.

## Hiring

The assistant asks for the organisation name, the registered business name, the website, a phone number, and the company number when you have one. A missing phone does not stop the organisation. It shows a preview and creates the organisation only after you say yes. A company email domain that already has an organisation is not joined from the chat. An admin invites that inbox. A public inbox such as Gmail starts its own organisation.

A role needs a complete definition. A thin role is refused. If a piece is still missing, the assistant asks that question next and does not invent the answer. The reference has four groups of four, such as NBY-7K2Q-9ABC-DEFG-HJKM. Share it unchanged. An organisation can keep 10 open roles, 15 members, and 10 pending invites. A role can be closed and opened again. There is no tool to delete the organisation.

## Switching

A company email can look for work or hire. Ask in the chat to switch. The assistant reads back what stays, and the switch happens only after yes. A saved search stays and still runs until you stop it. An organisation and its roles stay. An invite stays.

## What this repository does not contain

The server, the database, and the card widget live with the application. This repository does not contain a key, a token, or a CV. Connecting opens the askNobby sign-in page. After you confirm the email, the assistant keeps its own access token.

When a role is scored, the server sends the aim, the titles, the CV text, and the work description to Jev at Wrangle. It does not send pay, place, or engagement to Jev. Those limits are checked in our own code. A submitted application shows the recruiting organisation the elevator pitch, the CV, and the match score.
