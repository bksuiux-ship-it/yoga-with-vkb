# Yoga with VKB: landing page

A single static page (`index.html`): mobile-first landing page for Vinit K. Bansal's online yoga classes.
Visitors book a free trial class on WhatsApp; there is no backend.

## Update

Edit the files, then `git add . && git commit -m "What changed" && git push`. Vercel redeploys every push to `main`.

## Deploy (Vercel)

Import this repository in Vercel (New Project). Framework preset: **Other**, no build command,
output directory: the repository root. Every push to `main` deploys again.

## Before going public

- **WhatsApp number:** set to Vinit's number (`var WHATSAPP_NUMBER = '919815207270';` in `index.html`).
  The WhatsApp links also carry `https://wa.me/919815207270` in their markup so they work without JavaScript;
  if the number ever changes, replace it in both places (search for `919815207270`).
- **Real media so far:** the gallery photos and the seven book covers (small WebP images inlined in `index.html`).
- **Placeholders:** the hero video, Vinit's portrait, the program reels, student stories, the rating,
  prices and durations are still marked `[...]` or "coming soon" until the real material arrives.
- **Search engines:** `vercel.json` sends `X-Robots-Tag: noindex`, so the site stays out of search results
  until it is ready. Remove that header to let search engines index it.

## Files

- `index.html`: the page (fonts from Google Fonts; Motion and Lenis from jsDelivr, pinned versions).
- `vercel.json`: clean URLs and response headers.
- `brand/yoga-with-vkb-logo-icon.svg`: the logo icon from the client's official logo file.
