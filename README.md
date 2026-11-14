# Yoga with VKB: landing page

A single static page (`index.html`): mobile-first landing page for Vinit K. Bansal's online yoga classes.
Visitors book a free class on WhatsApp ("Book my free class") or start a chat ("Chat on WhatsApp"); each booking is also emailed through FormSubmit. There is no backend of our own.

## Update

Edit the files, then `git add . && git commit -m "What changed" && git push`. Vercel redeploys every push to `main`.

## Deploy (Vercel)

Import this repository in Vercel (New Project). Framework preset: **Other**, no build command,
output directory: the repository root. Every push to `main` deploys again.

## Before going public

- **WhatsApp number:** set to Vinit's number (`var WHATSAPP_NUMBER = '919815207270';` in `index.html`).
  The WhatsApp links also carry `https://wa.me/919815207270` in their markup so they work without JavaScript;
  if the number ever changes, replace it in both places (search for `919815207270`).
- **Real media so far:** the hero film (`assets/video/`: a 14-second silent preview that plays on its own, the full 51-second film with sound that loads only when a visitor turns the sound on, and a poster), the seven book covers, Vinit's portrait, the student stories (`assets/stories/`: three student videos, two class clips, five student photos and the small photo beside the booking form), and two of the four program reels.
- **Captions:** the spoken student videos still need captions. When the transcripts are ready, add a `<track kind="captions" …>` to each story video (see the comment above the stories rail in `index.html`).
- **Placeholders:** two program reels (Desk Detox, Stress & Sleep: videos 1 and 2),
  prices and durations are still marked `[...]` until the real material arrives.
- **Booking emails:** every booking is also emailed to vinitk.bansal@yogawithvkb.com through FormSubmit (`var BOOKING_EMAIL` in `index.html`). After the site is live, send one test booking: FormSubmit emails that address an activation link, and bookings arrive only after it is clicked.
- **Search engines:** `vercel.json` sends `X-Robots-Tag: noindex`, so the site stays out of search results
  until it is ready. Remove that header to let search engines index it.

## Files

- `index.html`: the page (fonts from Google Fonts; Locomotive Scroll from jsDelivr, a pinned version, for smooth mouse scrolling).
- `vercel.json`: clean URLs and response headers.
- `assets/video/`: the hero film: the silent preview loop (`hero-loop.webm`, `hero-loop.mp4`, under 1.3MB), the full film with sound (`hero.webm`, `hero.mp4`) and the poster (`hero-poster.webp`).
- `assets/books/`: the large, uncropped covers that open when a visitor clicks one (loaded only then); `assets/thumbs/books/` holds the small covers in the row.
- `assets/about/`: Vinit's portrait for the About section (`vinit-640.webp`, `vinit-960.webp`; the browser picks one by screen width).
- `assets/reels/`: the program reels (`video3.*` plays in Morning Energy Flow; videos 1 and 2 still to come). The Inside a class reel uses `assets/stories/class-steps.*`.
- `assets/stories/`: the story clips (`*.webm` AV1 first, `*.mp4` H.264 for Safari; loaded only when a visitor presses play), their posters (`*.webp`), the student photos (`*-card.webp` in the cards, the larger `*.webp` in the viewer) and `mandeep-face.webp` beside the booking form.
- `brand/yoga-with-vkb-logo-icon.svg`: the logo icon from the client's official logo file.
