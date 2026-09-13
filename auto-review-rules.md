# The two Auto-review rules

Open Settings → General, then find Auto-review in the Bot section. Each rule is a sentence in a "When Grok Bot wants to:" field plus an "It should:" dropdown. Choose the required behavior and click Add Rule. Check the dropdown again when entering the next rule.

## Rule 1 — Allow automatically

```text
Post a message, reply, or thread reply in any channel of the Marveno Support Slack workspace, or send a direct message to another Bot.
```

## Rule 2 — Ask first

```text
Perform a refund, cancellation, payment, or account change inside a billing or account system, or send any email. Writing about a refund in a Slack message is not this.
```

## Why these two

There are two gates in this desk, and they do different jobs.

The **rulebook** (`rules.md`) is the gate on *decisions*: "nobody decides alone — refunds over $50, or anything legal" is what produces the card in `#escalations`. That is where the human belongs.

**Auto-review** is the gate on *actions*: it evaluates what a Bot is about to do. Rule 2 asks before actions in billing/account systems and before email.

The first version of rule 1 was the other way round — one Ask-first rule reading close to *ask me before any message goes to a customer*. On a single ticket the desk stopped and asked eight times. The reviewer is a model reading prose, not a filter matching a channel, so it read a log line in `#desk-log` as a message to a customer, and the manager's card in `#escalations` as a message to a customer, and asked before each. Meanwhile the rulebook was already routing that ticket to the owner, so the same ticket arrived twice by two routes.

The last sentence of rule 2 distinguishes a message about a refund from an action that performs one.

Rule 1 permits ordinary Slack posts without a click. The rulebook separately tells Atlas which decisions to bring to the owner.

## Earlier instructions can still affect a run

An earlier test instruction in a Bot's chat affected an approval request during this build. When investigating an unexpected approval, check the conversation as well as the current Auto-review rules.
