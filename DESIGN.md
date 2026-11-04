# Salon booking app: design decisions

## Status
- Single diary per salon is live for Salon Rina (one chair).
- Multi-stylist support is agreed but NOT built yet. Wait for feedback from the salon being visited now before building.

## Multi-stylist design (agreed 2026-11-04)
- Clients see stylist names only. No chair numbers.
- Each stylist is a bookable name with its own time slots (same working hours as the salon by default).
- Booking page order:
  1. Client picks a stylist name.
  2. Page shows only that stylist's free times.
  3. Optional "any available stylist" button: system assigns whichever stylist is free at that time.
- Double-booking rule: one booking per stylist per time (not one per salon per time).
- Owner has ONE diary for the whole salon. Each booking shows the stylist name next to the time.
- Stylist changes: the name attached to a station can change (e.g. Sophia leaves, Tamarin starts). Old bookings keep the name they were made under. New bookings use the new name.
- Name changes are done by us, included in the monthly subscription. Other requests can be done for the salon under that subscription.

## Pricing (suggestion, not final)
- Flat R99 per month for the whole salon, 12-month signup. First month may be free.
- Fresha comparison: Team plan R89.95 per staff member (from owner screenshot). Booklink competitor: R79 flat.
- No marketplace commission (we do not run a marketplace).

## Open items
- Salon Rina: hours, services and durations, prices, chair/stylist count, address, photos, deposit/late-cancel policy.
- Booking link previews in WhatsApp work (confirmed 2026-11-04).
- Diary "Remove" deletes cancelled or blocked entries only (owner_remove function in Supabase).
