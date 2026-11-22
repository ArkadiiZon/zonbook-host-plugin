---
name: zonbook-owner-summary
description: Write a monthly summary for a Zonbook host or for the owner of an apartment — nights booked, occupancy, income recorded, cancellations and notable events — from the host's own reservations. Use when the host asks for a monthly report, owner statement or performance summary.
---

# Zonbook monthly owner summary

Turns a month of reservations into a plain-language summary the host can send. Reads only.

1. `list_my_organizations`; ask which organization and which apartments or building, and the month, if not given.
2. `list_units` for the apartments; `list_reservations` with `from` / `to` set to the month (overlap window). Page by
   apartment with `unitId` if the list is truncated.
3. For stays with money recorded call `list_stay_payments`; for any single reservation the host asks about,
   `get_reservation`.
4. Compute only what the tools give directly: number of stays, nights booked in the month, nights available (days in
   the month minus blocked nights from `get_calendar_overview`), occupancy = booked / available, payments recorded
   in the month by method, cancellations. Say when a figure is incomplete (for example an OTA payout not yet
   recorded) instead of estimating.
5. Write the summary: headline numbers, a short table by apartment, then three or four sentences on what stood out
   (best week, gaps, cancellations). Offer it in the language the owner reads. Show the draft; the host sends it.

Money and availability come from Zonbook's services: quote them exactly and label anything you derived as derived.
This is an operational summary, not tax or accounting advice. Never include guests' contact details in a summary
for an owner unless the host explicitly asks.
