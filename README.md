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
- **Real media so far:** the hero film (`assets/video/`: AV1 WebM, H.264 MP4 fallback and a poster), the gallery photos and the seven book covers (small WebP images inlined in `index.html`), and the student stories (`assets/stories/`: three student videos, three class clips, five student photos).
- **Captions:** the spoken student videos still need captions. When the transcripts are ready, add a `<track kind="captions" …>` to each story video (see the comment above the stories rail in `index.html`).
- **Placeholders:** Vinit's portrait, the program reels,
  prices and durations are still marked `[...]` or "coming soon" until the real material arrives.
- **Search engines:** `vercel.json` sends `X-Robots-Tag: noindex`, so the site stays out of search results
  until it is ready. Remove that header to let search engines index it.

## Files

- `index.html`: the page (fonts from Google Fonts; Motion and Locomotive Scroll from jsDelivr, pinned versions).
- `vercel.json`: clean URLs and response headers.
- `assets/video/`: the hero film (`hero.webm`, `hero.mp4`) and its poster (`hero-poster.webp`).
- `assets/books/`, `assets/gallery/`: the large, uncropped covers and photos that open when a visitor clicks one (loaded only then).
- `assets/stories/`: the story clips (`*.webm` AV1 first, `*.mp4` H.264 for Safari; loaded only when a visitor presses play), their posters (`*.webp`), and the student photos (`*-card.webp` in the cards, the larger `*.webp` in the viewer).
- `brand/yoga-with-vkb-logo-icon.svg`: the logo icon from the client's official logo file.
