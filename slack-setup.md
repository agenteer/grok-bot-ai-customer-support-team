# Slack setup

Everything Slack needs, in the order it has to happen. The two connections at the end are separate things and are the easiest part to get wrong.

## The workspace

Create a workspace from [slack.com](https://slack.com/) and name it for the company — Marveno Support here.

Three members:

| Member | Who it is | Why |
| --- | --- | --- |
| You | the owner | you answer the escalation cards |
| Marveno Support | a Slack account of its own | the Bots post as this account |
| Alex River | the customer | posts tickets in `#support-inbox`; cannot see the two private desk channels |

The desk account and the customer each need their own email address and their own browser session. Without a separate customer account, the ticket and the desk's reply come from the same Slack user and the thread reads as one person answering themselves.

## The three channels

| Channel | Visibility | Members | What lives there |
| --- | --- | --- | --- |
| `#support-inbox` | public | all three | the customer's message, the desk's reply in the thread |
| `#escalations` | private | you, Marveno Support | the manager's card, and your answer |
| `#desk-log` | private | you, Marveno Support | one line per event: REPLIED, ESCALATED, PENDING OPERATOR, RESOLVED |

This example makes `#support-inbox` public. An invited customer could also participate in a private channel. Keep the other two channels private and do not add the customer, so internal discussions and logs stay separate from the support conversation.

## Connection 1 — the plugin, which is the hands

Open Grok Bot's Marketplace and add Slack. Current documentation calls this area Plugins.

**Sign the browser in to Slack as the desk account before adding the plugin.** It authorizes against whichever Slack session is already signed in, and that account is the name on every post the team makes from then on — [the plugin "posts as the Slack user you connected, not as a separate bot that has to be invited"](https://cursor.com/help/grok-bot/connect-plugins).

If the posts come out under your own name, the fix is a sign-in and not a build: sign the browser in as the desk account, then ask a Bot to re-authorize Slack for the default account with a fresh sign-in, and authorize the card that appears in the chat as the desk user.

Both Bots share that one sign-in, so Slack shows one author for two agents. That is what the `Sage:` and `Atlas:` prefixes in the descriptions are for.

## Connection 2 — the Cursor app, which is the ears

The plugin lets a running Bot read and post. It cannot start one. Waking a Bot is the other connection: [Cursor account integrations "can start a routine from an event, such as a Slack message"](https://docs.x.ai/grok-bot/skills-routines-and-automations).

1. [cursor.com/dashboard/integrations](https://cursor.com/dashboard/integrations) → Slack → Connect. Authorize the Marveno Support workspace. This build used the workspace owner's account for this connection.
2. Add the Cursor app to each channel a routine listens to. Open the member panel in `#support-inbox`, choose **Add agents or apps**, and select **Cursor**. Repeat in `#escalations`.

`#desk-log` is written to and never listened to, so it needs no invitation.

Before testing, confirm that Cursor appears among the apps in both channels, and that each Bot has a routine naming its channel and skill.

## The footer

Posts from the team in this build carry `Sent using @Cursor`. The author is the account the plugin is signed in as. Both skills use the footer as a cue to ignore the team's posts.
