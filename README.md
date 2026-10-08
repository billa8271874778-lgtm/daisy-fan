# Daisy Creator Club — Razorpay-ready website

This is a mobile-first full-stack starter for a creator/fan membership site.

## Included
- Home/profile page
- Follow UI
- ₹899 private chat checkout
- ₹499 monthly Razorpay Subscription checkout
- Login modal placeholder
- Members-only content placeholder
- Support/account navigation
- Server-side Razorpay order creation
- Server-side payment signature verification
- Verified Razorpay webhook endpoint using raw request body + HMAC SHA-256
- `.env.example` for secrets

Razorpay's current documentation recommends using webhooks for asynchronous payment/subscription state and API verification for immediate user-facing confirmation. Webhook signatures should be checked against the raw request body. See the official docs:
https://razorpay.com/
https://razorpay.com/subscriptions/

## Run locally
1. Install Node.js 20+.
2. `npm install`
3. Copy `.env.example` to `.env`.
4. Add your Razorpay Test Key ID and Secret.
5. In Razorpay Dashboard, create a monthly ₹499 plan and put its Plan ID into `RAZORPAY_PLAN_ID`.
6. `npm start`
7. Open `http://localhost:3000`.

## Before going live
- Replace all placeholder media with media you are authorized to use.
- Add a real database (users, orders, payments, subscriptions, bookings, webhook event IDs).
- Add real authentication and sessions.
- Make member content protected; do not expose private media through public URLs.
- Store and process Razorpay webhooks idempotently using the event ID.
- Add booking availability/time-slot logic.
- Add Terms, Privacy, Refund/Cancellation and Contact pages.
- Configure your public HTTPS webhook URL in Razorpay Dashboard.
- Test in Razorpay Test Mode before Live Mode.
- Review Razorpay merchant terms and your applicable laws/business requirements.
- Never put `RAZORPAY_KEY_SECRET` or webhook secret in frontend code or GitHub.

## Important
This package does not deploy a live website or create a Razorpay account for you. It is an upload-ready starter that still needs your hosting, database/auth setup and live Razorpay credentials.
