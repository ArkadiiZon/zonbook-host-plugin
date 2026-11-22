---
name: zonbook-cleaning-schedule
description: Plan and check a Zonbook host's cleaning schedule — which apartments need cleaning between stays, who is assigned, what is overdue. Use when the host asks about cleanings, turnovers or a cleaner's week. Read-only.
---

# Zonbook cleaning schedule

Builds a turnover plan from the live calendar. Reads only; assigning cleaners and editing cleanings is done in the
Zonbook portal or app.

1. `list_my_organizations`, then `get_ops_board` for the window (default today to +7 days): cleanings and in-person
   check-ins together, plus the organization's cleaning settings.
2. `list_cleanings` with `from` / `to` (and `cleanerUserId` when the host asks about one person) for statuses and
   assignments. `list_reservations` for departures and arrivals in the window to find same-day turnovers.
3. Present the plan day by day: apartment, checkout time, next arrival time (flag **same-day turnovers**),
   assigned cleaner, status (scheduled / in progress / done). Call out: departures with no cleaning scheduled,
   cleanings with no cleaner, cleanings still open after checkout time.
4. If the host wants a message for a cleaner, draft the text for them to send themselves. This skill does not message
   cleaners.

Report times and statuses exactly as returned. Do not invent cleaners or assignments.
