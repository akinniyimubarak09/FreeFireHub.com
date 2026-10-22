# FreeFireHub — Gaming Marketplace Starter

A premium dark-themed responsive gaming storefront built with HTML5, CSS3 and vanilla JavaScript. It opens directly in VS Code using Live Server; no terminal, npm or build process is needed.

## Run in VS Code
1. Download and extract `FreeFireHub.zip`.
2. Open the extracted `FreeFireHub` folder in VS Code.
3. Install the **Live Server** extension if needed.
4. Right-click `index.html` and choose **Open with Live Server**.

## Multi-page navigation
The primary navigation now opens dedicated pages:
- `index.html` — homepage/storefront
- `games.html` — supported game directory
- `topup.html` — top-up game selector
- `game-free-fire.html` — Free Fire diamond top-up
- `game-pubg-mobile.html` — PUBG Mobile UC top-up
- `game-mobile-legends.html` — Mobile Legends diamond top-up, with User ID and Zone ID
- `game-cod-mobile.html` — Call of Duty: Mobile CP top-up
- `marketplace.html` — product listings and search
- `deals.html` — promotions page (no unverified active discounts)
- `guides.html` — news and guides
- `search.html` — full-page search
- `cart.html` — cart and demo checkout
- `account.html` — account interface and local demo order history
- `support.html` — support form and WhatsApp contact
- `about.html`, `terms.html`, `privacy.html`, `refund.html`, `marketplace-rules.html` — informational and policy pages

## Top-ups for all four games
The storefront now has package selectors for:
- Free Fire — Diamonds
- PUBG Mobile — UC
- Mobile Legends — Diamonds (User ID + Zone ID)
- Call of Duty: Mobile — CP

Each game has a dedicated page and can add its selected package to the cart. **All package prices are sample display values and are not verified live prices.** These interfaces do not deliver game currency. A legitimate/authorized top-up supplier or fulfillment API must be integrated before accepting real orders. Do not request game passwords or one-time codes.

## Nigerian payment methods
The cart checkout presents bank transfer, debit card, OPay, PalmPay, USSD and other Nigerian bank methods as selectable preferences. They are **not active payment integrations**. Do not advertise a payment method as live unless your approved provider account supports it.

A licensed payment provider such as Paystack or Flutterwave may offer different payment rails depending on merchant approval and configuration. You do not normally connect every Nigerian bank individually: use provider-supported transfer, card or USSD flows. OPay and PalmPay availability must be confirmed with the chosen provider for your specific merchant setup.

For production payments:
1. Register and verify your merchant account with the chosen provider.
2. Add a backend that creates orders and initializes provider checkout using server-side credentials.
3. Use provider-hosted checkout; never collect or store raw card details yourself.
4. Verify payments server-side via provider APIs and signed webhooks before marking orders paid.
5. Validate amount, currency and order reference; make webhook handling idempotent.
6. Keep all secret keys in server environment variables, never in `app.js`, `pages.js` or HTML.
7. Implement refunds, reconciliation, monitoring and support.

## Implemented frontend interactions
- Responsive navigation and separate pages.
- Game directory and dedicated top-up pages.
- Package selection and basic player identifier validation.
- Marketplace search and add-to-cart.
- Cart subtotal, remove item, local persistence.
- Demo checkout form validation and local order-reference creation.
- Browser-local order history.
- Support form validation and WhatsApp link.
- Full-page search across games, products and guides.

## Not live / production requirements
This is a static frontend starter. It does not provide secure authentication, real payment processing, verified payment status, top-up fulfillment, database-backed orders, a secure admin dashboard, seller accounts, real ticket delivery, live inventory or confirmed discounts. Demo order references are not proof of payment. Browser localStorage is not a secure customer database.

Before launch, connect:
- Backend API and database for users, games, products, listings, orders and audit logs.
- Secure authentication and server-side role permissions.
- Payment provider and verified webhooks.
- Authorized game top-up supplier / fulfillment API.
- Admin tools, seller verification, listing moderation, fraud controls and dispute/refund handling.
- Valid policies, privacy disclosures, support workflow and monitoring.
- Real inventory, images, package prices and business contact information.

## Configure WhatsApp
Edit `FFH_CONFIG.whatsappNumber` near the top of `pages.js` and `CONFIG.whatsappNumber` near the top of `app.js`. Use international digits only, for example `2348012345678`, with no plus sign or spaces.

## Project files
- `index.html` — homepage
- `styles.css` — main responsive design system
- `app.js` — homepage interactions and sample data
- `pages.css` — multi-page layout styles
- `pages.js` — dedicated pages, game top-ups, cart, support and search interactions
- additional `.html` files — separate pages listed above

## Sample-data and publisher notice
All prices/products are sample display data and must be verified. FreeFireHub is an independent concept and is not affiliated with Garena or the other game publishers. Only offer products and account-related services where you have the necessary authorization and publisher rules permit them.
