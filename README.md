# Nexova Service Template

A working front-end prototype of a website + online booking + deposit payment + studio admin for a service business — built as a client demo, not a static mock-up. This version is dressed as **Aina Lash Atelier**, a fictional premium eyelash-extension studio in Bangsar, Kuala Lumpur.

Everything is one file: `index.html`. No backend, no build step, no framework.

## What it demonstrates

**Customer side**
- Editorial landing page: lash sets, pricing with deposits shown up front, results, studio, FAQ.
- Booking flow: choose a set → pick a date and time (live availability across two artists) → details → review → pay a deposit (mock FPX / card / Touch 'n Go / DuitNow QR) → confirmation with reference number, deposit paid, balance remaining and when it is due, plus a preview of the WhatsApp confirmation.
- Balance payment page reached from a link (`/pay/<ref>` in the mock), with the deposit already deducted.

**Studio side** (`Studio Admin ↗`, or `/admin`)
- Today: two-chair schedule, month figures, "needs attention" list, recent clients.
- Bookings: search, filters, and a drawer where the owner can send a WhatsApp payment link for the balance, record a payment taken at the studio, mark completed or cancel.
- Calendar (week / list), Clients (history, spend, notes), Payments (deposits, balances, refunds, settlement, automatic balance requests).

Bookings made on the site appear in the admin immediately. Demo data regenerates around the current date; changes made during a demo persist in the browser until "Reset demo changes" in the admin footer.

## Deploy on Vercel

1. Import this repository at [vercel.com/new](https://vercel.com/new).
2. Framework preset **Other**, no build command, output directory left blank.
3. Deploy. `vercel.json` adds clean URLs and the `/book` and `/admin` routes.

Useful URLs once deployed:

| Path | Opens |
|---|---|
| `/` | The website |
| `/book` | Straight into the booking flow |
| `/admin` | The studio admin sign-in |

## Run locally

Open `index.html` in a browser, or serve the folder with any static server (for example `npx serve .`). Photos load from Unsplash and display fonts from Google Fonts, so an internet connection is needed; Satoshi is embedded in the file.

## Adapting it for another business

All content lives in `index.html`:

- **Services, prices, deposits, durations** — the `SERVICES` array near the top of the script (`id`, `name`, `desc`, `mins`, `price`, `deposit`).
- **Staff** — the `ARTISTS` array; availability is computed per artist.
- **Opening hours and closures** — `OPEN`, `CLOSE`, `HOLIDAYS`, and `closedReason()`.
- **Brand, copy and photos** — the HTML sections in `<body>`; images are Unsplash URLs you can swap.
- **Colours and type** — the CSS custom properties at the top of the stylesheet.

## Notes

- Fictional business. No real bookings or payments are processed; the checkout is a front-end mock.
- Photography via [Unsplash](https://unsplash.com) (free licence). Satoshi typeface by Indian Type Foundry via Fontshare; Bodoni Moda and DM Mono via Google Fonts.
