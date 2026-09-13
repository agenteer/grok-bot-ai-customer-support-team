# The three tickets

Post these from the customer account in `#support-inbox`, one at a time. They exercise a direct answer, a manager handoff, and an owner decision.

## Ticket 1 — the rules answer it

```text
How do I export my roast history?
```

Sage should reply in the thread with the export instructions from `rules.md`. Look for this event prefix in `#desk-log`; the subject and summary may vary:

```text
Sage: REPLIED:
```

Atlas is not involved. `#escalations` stays empty.

## Ticket 2 — Sage hands the question to Atlas

```text
We're a three-person roastery — is there a team plan where we can all log to one account? Even a rough sense of when would help us plan.
```

There is no team-plan policy in `rules.md`, and the facts say the company publishes no dates for unreleased work. Sage should send a holding reply and escalate. The observed run then produced this sequence of log event types:

```text
Sage: ESCALATED:
Atlas: RESOLVED:
Sage: REPLIED:
```

The customer received a holding reply. Atlas answered that Marveno does not offer team or shared accounts, each person needs their own subscription, and no timeline could be shared for unreleased features. Sage relayed that answer to the customer.

## Ticket 3 — nobody decides alone

```text
I sold my roaster back in January and stopped roasting, but I completely forgot to cancel. Just noticed I've been charged $9 every month since. It's my mistake, but any chance you can refund me all these months? About $63 I think.
```

Two lines of the rulebook bite: a refund is available on charges from the last 30 days, and nobody decides alone on refunds over $50.

Look for these event prefixes in the log; the subject and explanation may vary:

```text
Sage: ESCALATED:
Atlas: PENDING OPERATOR:
```

Atlas should post one card in `#escalations` and wait. The card's four fields should describe:

```text
Situation: the customer's refund request
Rule: the refund window and amount requiring the owner's decision
Recommendation: Atlas's proposed response
Question: the decision requested from the owner
```

The owner answers in `#escalations`, as themselves:

```text
I understand the situation. Let's make it a one-time exception and refund in full.
```

That message fires Atlas's routine:

```text
Atlas: RESOLVED:
Sage: REPLIED:
```

Sage should communicate the owner's refund decision in the customer's thread.

## A fourth, with the app closed

```text
Where do I find the export button?
```

Quit the Grok Bot app first. The reply still arrives: the Bots run on the cloud computer, and the desktop app is where they are built rather than where they live.
