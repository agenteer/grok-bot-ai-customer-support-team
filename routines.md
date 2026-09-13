# The two routines

A routine belongs to one Bot and specifies when it runs and what it does. These two routines name the skill to run on each new message; the skills contain the ticket-handling steps. Create each one by typing its sentence into the named Bot's chat.

## Sage — tickets from customers

Typed into Sage's chat:

```text
Set up a routine named "Support inbox tickets": when a new message is posted in the Slack channel #support-inbox, run the skill "Marveno support desk" on it.
```

| | |
| --- | --- |
| Owner | Sage |
| Trigger | Slack message — new messages in `#support-inbox`, any text |
| Runs | the skill `Marveno support desk` |

## Atlas — the owner's answers

Typed into Atlas's chat:

```text
Set up a routine named "Escalations operator answers": when a new message is posted in the Slack channel #escalations, run the skill "Marveno Atlas escalations" on it.
```

| | |
| --- | --- |
| Owner | Atlas |
| Trigger | Slack message — new messages in `#escalations`, any text |
| Runs | the skill `Marveno Atlas escalations` |

Atlas needs its own routine for owner replies in `#escalations`. Without that routine, an owner reply does not trigger Atlas through this Slack event connection.

Both triggers depend on the Cursor app being a member of that channel. See `slack-setup.md`.
