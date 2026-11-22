# Zonbook Host for Claude

Connects Claude to your [Zonbook](https://zonbook.com) hosting account and adds six skills for the work a
short-term-rental host repeats every day. It works on your own organizations only, with the permissions of
your role in each, and every change it makes is recorded in your organization's audit log.

## Install

```
/plugin marketplace add ArkadiiZon/zonbook-host-plugin
/plugin install zonbook-host@zonbook
```

The first time Claude uses a Zonbook tool it opens a Zonbook page asking you to approve the connection.
Sign in with your host account and approve. You can see and revoke connections in the Zonbook host portal under
Settings → AI clients. Without the plugin you can add the same connector by hand: Settings → Connectors → Add
custom connector → `https://api.zonbook.com/mcp/host`.

## Skills

| Skill | Ask for it like this |
| --- | --- |
| `zonbook-daily-brief` | "What is happening at my apartments today?" |
| `zonbook-guest-replies` | "Draft replies to my unread guest messages." |
| `zonbook-checkin-readiness` | "Is everything ready for tomorrow's arrivals?" |
| `zonbook-calendar-pricing` | "Review next month's calendar and prices." |
| `zonbook-cleaning-schedule` | "Plan this week's cleanings." |
| `zonbook-owner-summary` | "Write last month's summary for the owner of Casa del Mar." |

## What it can and cannot do

It can read your reservations, calendar, prices, guest conversations, check-ins, cleanings and house guides,
and, when you ask, block dates, set calendar prices, edit listing drafts and house guides, and send a guest
message after you approve the exact text. It cannot create accounts, change roles, change payout details or move
money. Anything that changes data or messages a guest is shown to you first; nothing is sent on its own.

## Data and privacy

Nothing is copied in advance: each question becomes a live request to Zonbook. What Claude reads in answering is
handled under Anthropic's terms for your Claude plan. Zonbook never sends identity-document images, selfies or
payment card numbers. See <https://zonbook.com/en/ai-assistants#privacy> and the
[privacy policy](https://zonbook.com/en/privacidad).

## Support

<https://zonbook.com/en/ai-assistants#support> or support@zonbook.com. Licensed under MIT (the plugin files only;
the Zonbook service is covered by its own terms).
