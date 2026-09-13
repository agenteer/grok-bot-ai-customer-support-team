# Grok Bot AI customer support team — companion files

Build a support team with two Grok Bots and Slack: Sage handles customer requests, Atlas reviews escalations, and decisions above their authority come to you. Marveno is the fictional coffee-roasting app used in the example.

These are text files to paste into Grok Bot, plus the Slack settings and test tickets.

## Start here

[Follow the full written guide](https://agenteer.com/resources/grok-bot-ai-customer-support-team/) for the setup and walkthrough.

Use a Grok Bot account with available usage and a Slack workspace for the example. Invite a separate desk account and customer account alongside yourself. [Cursor's plans page](https://cursor.com/help/grok-bot/plans) explains access options.

Follow this order:

| Step | Action | File |
| --- | --- | --- |
| 1 | Create Sage and Atlas; paste their descriptions into their profiles | [Sage](bots/sage/description.md), [Atlas](bots/atlas/description.md) |
| 2 | Ask Atlas to create a shared folder named `marveno-support`, save the company rules there as `rules.md`, and return its path. Ask Sage to read the same file | [Company rules](rules.md) |
| 3 | Save each agent's procedure as a skill, using the save lines below | [Sage's skill](bots/sage/skill.md), [Atlas's skill](bots/atlas/skill.md) |
| 4 | Create the Slack channels, connect the plugin as the desk account, connect Cursor's Slack integration, and add Cursor to the two monitored channels | [Slack setup](slack-setup.md) |
| 5 | Set the two Auto-review rules | [Auto-review rules](auto-review-rules.md) |
| 6 | Create one routine for each Bot, with the named channel and skill | [Routines](routines.md) |
| 7 | Post the test tickets as the customer and follow the replies and log entries | [Tickets](tickets.md) |

To save Sage's procedure, paste this line followed by the contents of [Sage's skill](bots/sage/skill.md) into Sage's chat:

```text
Save this exactly as a skill named "Marveno support desk". No questions.
```

For Atlas, paste this line followed by [Atlas's skill](bots/atlas/skill.md) into Atlas's chat:

```text
Save this exactly as a skill named "Marveno Atlas escalations". No questions.
```

Open each saved card and compare its instructions with the file. After creating the routines, confirm that Sage's uses `#support-inbox` and Atlas's uses `#escalations`.

## What the example establishes

The tests exercise a rules-based answer, a handoff from Sage to Atlas, a refund decision brought to the owner, and another reply with the desktop app closed. The files reproduce the September 2026 setup; the notes below clarify what the example establishes.

- **Ticket two passes from Sage to Atlas and back.** Atlas answers the team-account question, and Sage relays the answer to the customer.
- **The owner replies to the newest pending escalation.** Run the examples one at a time. The instructions do not bind simultaneous owner replies to unique ticket IDs.

Skills and files can be shared across the account's Bots. A routine names the Bot and skill that should handle its trigger; the descriptions are not separate access boundaries.

The same support-team example on Hermes: [Hermes companion files](https://github.com/agenteer/hermes-agent-ai-customer-support-team).

## License

[MIT](LICENSE).
