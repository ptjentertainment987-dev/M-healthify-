# M Healthify — Netlify deployment package

## What's included
- `index.html` — homepage, calorie calculator, subscription pricing, UPI payment link, order form and meal gallery.
- `menu.html` — sample meal gallery page.
- `assets/` — the three meal photos used on both pages.

## Deploy to Netlify
1. Download and extract this ZIP.
2. In Netlify, choose **Add new site → Deploy manually**.
3. Drag the extracted `mhealthify-deploy` folder (the folder containing `index.html`, `menu.html`, and `assets/`) into the deploy area.
4. No build command, environment variables, Netlify Functions, Supabase, or WhatsApp Cloud API are required for this static version.

## WhatsApp order flow
The order form uses regular WhatsApp click-to-chat for **+91 84178 01211**. After completing the form, the customer's WhatsApp opens with the order details pre-filled. The customer must review the message and press **Send**. Regular WhatsApp does not silently receive website submissions or act as an automated server backend.

## Subscription pricing
- Balanced Protein Plan (fat-loss plan): regular price ₹13,999; limited-time one-month offer ₹10,999.
- The one-month checkout amount remains ₹10,999.

## UPI
The existing UPI ID and payee details are retained from the supplied website source: `8417801211@ybl` — Ritik Kumar Singh. The payment button opens a UPI intent with the selected plan's amount prefilled. Payment is not automatically verified; check the payment in your UPI/bank app before confirming the subscription.

## Before going live
- Test the UPI payment intent on a phone with a UPI app installed.
- Test the order form and confirm the WhatsApp draft contains the correct customer details and amount.
- Confirm the UPI ID/payee, prices, delivery area, menu and nutrition information before accepting orders.
- The meal photos are examples; the menu page clearly says these are not a fixed weekly schedule.

## Important limitation
This version intentionally removes the old `/.netlify/functions/order` submission call and any dependency on WhatsApp Cloud API. It is a static website with a customer-initiated WhatsApp handoff; it does not store orders in a database or provide an automatic admin order inbox.
