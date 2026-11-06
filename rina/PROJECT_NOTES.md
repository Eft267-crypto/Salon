# Salon booking app: project notes

## Live links
- Client booking page (Salon Rina): https://eft267-crypto.github.io/Salon/rina/
- Owner diary (Salon Rina): https://eft267-crypto.github.io/Salon/rina/diary/
- GitHub repo: https://github.com/Eft267-crypto/Salon
- Supabase project (Salon-Rina): https://supabase.com/dashboard/project/mkgsjpigeuxeupzvdxko

## How it is built
- Booking page and diary are plain HTML files in GitHub Pages (free).
- Database, bookings and PIN login are in Supabase (free tier).
- Each salon gets its own folder in the repo (rina/, thandi/, ...) and its own row in the `salons` table with its own PIN.
- Double-booking is blocked in the database, not just on the page.
- Supabase free projects pause after about a week with no activity. Restore from the Supabase dashboard; nothing is deleted.

## Multi-stylist design (agreed, not built yet; wait for feedback from the salon being visited)
- Clients see stylist names only, no chair numbers.
- Booking order: client picks a stylist name, then sees only that stylist's free times. Optional "any available stylist" button.
- One booking per stylist per time.
- Owner has one diary for the whole salon, showing the stylist name next to each booking.
- When a stylist leaves, the name changes; old bookings keep the name they were made under. We make name changes as part of the monthly subscription.

## Pricing (suggestion, not final)
- R99 per month flat for the whole salon, 12-month signup, first month possibly free.
- Fresha comparison: R89.95 per staff member per month (owner's screenshot). Booklink competitor: R79 flat.
- No marketplace commission, since we do not run a marketplace.

## Backups and restore
- Back up per salon: booking page (index.html), diary (diary/index.html), and a details note (name, WhatsApp number, services, hours, PIN).
- Back up the shared database setup SQL once.
- Keep client bookings OUT of backups where possible. If any client data is backed up, encrypt it.
- Keep two copies: Dropbox (or Google Drive) plus a memory stick. Date the file names.
- Test one restore before selling to anyone: replace one page with its backup, check it works.
- Restore steps: 1) take latest index.html and diary/index.html from backup, 2) upload to that salon's GitHub folder, replacing broken ones, 3) if the database is the problem, run the saved SQL again in Supabase.

## Privacy (POPIA)
- Client names and cellphone numbers are kept so the owner can see who each booking is for and contact them.
- The salon owner is the responsible party. We are the operator.
- Get a written agreement with each salon before onboarding.
- Have a lawyer check the agreement. I'm not a lawyer.
- Breach: tell the salon owner straight away.

## Draft data-handling clause (for lawyer review)
1. Roles: The Salon owner is the responsible party under POPIA and decides what client information is collected and why. [Your name] is the operator and processes that information only on the Salon's written instructions, to provide the booking service.
2. Information processed: Client names, cellphone numbers, chosen services, and booking dates and times, collected through the online booking page.
3. Security: [Your name] will take reasonable technical and organisational measures to protect the information, including access controls, PIN-protected owner access, and encrypted storage of any backups that contain client information.
4. Backups: Backups will exclude client booking details wherever reasonably practicable. Where client information is backed up, the backup will be encrypted and stored only in locations controlled by [Your name].
5. Confidentiality: [Your name] will keep client information confidential and will not sell, share or use it for any purpose other than providing the service to the Salon.
6. Breaches: [Your name] will notify the Salon in writing as soon as reasonably possible after becoming aware of any unauthorised access to or loss of client information, and will help the Salon meet its reporting obligations to the Information Regulator and affected clients.
7. Retention and end of agreement: On termination, [Your name] will, at the Salon's choice, return or securely delete the client information, unless the law requires it to be kept.
8. Access requests: [Your name] will forward any request from a client to access, correct or delete their information to the Salon promptly.

## Open items
- Salon Rina: opening hours, services with durations and prices, number of stylists/chairs, address, photos, deposit and late-cancel policy.
- Confirm the Rina diary "Remove" works on the live page (it does, as of 2026-11-04).
- Pending salon feedback before building multi-stylist support.
- Lawyer review of the data clause before signing any salon.
- Test one backup restore.
