---
name: zonbook-checkin-readiness
description: Check whether upcoming arrivals at a Zonbook host's apartments are ready — online check-in submitted, house guide published, apartment cleaned, balance settled. Use before arrivals, or when the host asks what could go wrong tomorrow. Read-only.
---

# Zonbook check-in readiness

Checks each arrival in the next 48 hours (or the window the host names) and reports what is missing. Reads only.

1. `list_my_organizations`, then `list_reservations` with `from` / `to` covering the window. Keep arrivals only.
2. For each arrival gather, with the fewest calls that answer it:
   - **Online check-in** — `list_checkin_submissions` (filter by unit): submitted, reviewed, outstanding. The tools
     never return document images; report only whether one exists.
   - **House guide** — `get_house_guide` for the unit: is a version published, and does it open before arrival
     (`hoursBefore`)?
   - **Cleaning** — `list_cleanings` for the unit and day: scheduled, assigned, done.
   - **Money** — `list_stay_payments` for the stay: what is paid and what is due on arrival.
   - **Guest contact** — `get_guest_chat` only if there is an unanswered question.
3. Report one line per arrival with a status (Ready / Needs attention / Blocked) and the exact missing item.
   Order by arrival time. Then list the fixes the host can ask for: remind the guest to check in, publish the
   guide, assign a cleaner.

Do not change anything. If the host asks you to act on a finding (publish the guide, message the guest),
describe the change first and wait for their approval; messages to guests follow the zonbook-guest-replies
rules.
