---
name: zonbook-calendar-pricing
description: Review a Zonbook host's calendar and prices for a period — gaps, orphan nights, blocked dates, season prices — and, if asked, apply price changes or date blocks after approval. Use for questions about vacancy, minimum stays and nightly rates.
---

# Zonbook calendar and pricing review

1. `list_my_organizations`, then `list_units` to learn the apartments, base prices and minimum stays.
2. `get_calendar_overview` for the period (max about a year; default the next 60 days): booked, blocked and free
   nights per apartment.
3. `list_price_overrides` for the same apartments: the seasonal prices already set. To see what a guest would be
   charged for a specific stay call `get_unit_pricing`; quote the result exactly as returned and never add fees
   yourself.
4. Report, per apartment: occupancy for the period, free gaps shorter than the minimum stay (orphan nights),
   long blocked stretches, nights whose price differs from the base price, and the weeks with the most free
   nights. Suggest changes as a short list with the reason for each; mark them as suggestions.
5. **Apply nothing by yourself.** When the host approves a specific change, show it once more (apartment, dates
   — end date inclusive — price, minimum nights) and then call `set_price_override`, or `block_dates` /
   `unblock_dates` for blocks. Confirm what was written by reading the result back. `delete_price_override`
   removes a season price: ask before using it.

Prices are in euros as returned by the service. Do not infer availability from anything other than
`get_calendar_overview` or `get_type_availability`.
