# askNobby

askNobby applies for a person who is looking for work, and lets a recruiter post a role, from the chat they already use. Stratustech Ltd publishes it. The chat is the interface. This folder is the plugin that ChatGPT, Codex, and Claude install. The application server is not in this folder.

![askNobby monogram](./assets/icon.png)

The remote server is https://www.asknobby.com/api/mcp.

## Connect

Click Connect in the assistant. Give your name and email in the chat. We send a message. Open that message in the same browser and press Confirm. Do not paste a code, a link, or a session token into the chat.

- ChatGPT: add a custom connector where the workspace allows it, and paste the server address.
- Claude: Settings, then Connectors. Add a custom connector and paste the same address.
- Cursor: add an MCP server with that address.

A result that lists a search, a role, or an application is drawn as a card when the assistant supports it. The card uses the Nobby monogram. It shows the full profile summary and the name of the CV file. It does not show the CV text.

## Skills

| Skill | When it is used |
| --- | --- |
| get-started | The person has just connected, or has not saved a name and email |
| find-work | Create a search, including a second search |
| manage-search | Show a profile, change a search, or delete a search or the account |
| manage-applications | Show what was submitted, preview matches, apply to one reference, or withdraw one application |
| post-a-role | Create an organisation and post a new role |
| manage-roles | Show, change, or close a posted role, or see who applied |
| manage-organisation | Update the organisation, invites, members, and member scope |

## Looking for work

The assistant reads the CV, asks for a LinkedIn URL, the titles, the work you want to spend your time doing, and limits for place, engagement, and pay. It asks which employers must never receive an application, including your current company. A day rate stays separate from an annual salary. You can keep two searches.

A daily search is the usual choice. You can set it for up to 30 days, and a match from 50% to 95%. If you do not choose, it runs for 30 days and will auto-apply when at a 90% match. Place, engagement, pay, and the block list are checked before that. A one-time search shows up to five roles and applies only to the references you name.

Ask for your profile to see the saved search, the full profile summary, and the latest applications. The card names the CV file. Ask to read the CV if you want the text.

You can withdraw one application. A CV a recruiter has already opened is not pulled back.

## Hiring

The assistant asks for the organisation name, the registered business name, the website, a phone number, and the company number when you have one. A missing phone does not stop the organisation. It shows a preview and creates the organisation only after you say yes. A company email domain that already has an organisation is not joined. An admin invites that inbox. A public inbox such as Gmail starts its own organisation.

A role needs a complete definition. A thin role is refused. The reference has four groups of four, such as NBY-7K2Q-9ABC-DEFG-HJKM. Share it unchanged. An organisation can keep 10 open roles, 15 members, and 10 pending invites. A role can be closed and opened again. The organisation itself cannot be deleted from the chat.

## Switching

A company email can look for work or hire. Ask in the chat to switch. The assistant reads back what stays, and the switch happens only after yes. A saved search stays and still runs until you stop it. An organisation and its roles stay.

## Data

The plugin files do not contain a key or a token. The assistant keeps its own access token after you confirm the email.

The server receives what the assistant sends for the tool you asked for. For a candidate, that includes the CV text, the original CV file when the assistant has it, the aim, titles, LinkedIn URL, location, engagement, pay limits, and employers you ask us not to contact. For a recruiter, that includes the organisation details and the role text. When a role is scored, we send the aim, the titles, the CV text, and the work description to Jev at Wrangle. We do not send pay, place, or engagement to Jev. Those limits are checked in our own code. A submitted application shows the recruiting organisation the elevator pitch, the CV, and the match score.

The guide is at https://www.asknobby.com/docs. The privacy policy is at https://www.asknobby.com/privacy and the terms are at https://www.asknobby.com/terms.
