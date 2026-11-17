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
- **Real media so far:** the hero film (`assets/video/`: a 14-second silent preview that plays on its own, the full 51-second film with sound that loads only when a visitor turns the sound on, and a poster), the seven book covers, Vinit's portrait, the student stories (`assets/stories/`: three student videos, two class clips, five student photos and the small photo beside the booking form), all four program reels, and Vinit's gallery photos (`assets/gallery/`, `assets/thumbs/gallery/`).
- **Captions:** the spoken student videos still need captions. When the transcripts are ready, add a `<track kind="captions" srclang="…" label="…" src="assets/stories/NAME.vtt" default>` inside each story `<video>` in `index.html`.
- **Placeholders:** class durations, the diet details, refund terms and the team size are still marked `[...]` until Vinit confirms them.
- **Booking emails:** every booking is also emailed to vinitk.bansal@yogawithvkb.com through FormSubmit (`var BOOKING_EMAIL` in `index.html`). After the site is live, send one test booking: FormSubmit emails that address an activation link, and bookings arrive only after it is clicked.
- **Search engines:** the site is open to search engines. `robots.txt` allows everything and points to `sitemap.xml`; update the sitemap's `<lastmod>` date after big changes. To hide the site again, add an `X-Robots-Tag: noindex` header in `vercel.json`.
- **Link preview:** when the link is shared (WhatsApp, Instagram, Facebook, X), apps show `assets/og-image.jpg` (1200x630) with the title and description from the `og:` and `twitter:` tags in `index.html`. Apps cache previews: WhatsApp keeps the preview it first saw for a link, so a link shared before the preview existed can stay bare for a while. To see the current preview at once, share the link with `?v=2` on the end (any new number works), or check it at opengraph.xyz.

## Files

- `index.html`: the page (Manrope from `assets/fonts/`, preloaded, so nothing blocks the first paint; Locomotive Scroll from jsDelivr, a pinned version, for smooth mouse scrolling on computers only).
- `vercel.json`: clean URLs and response headers. Browsers keep files in `assets/` and the icons for a day (then use them while checking for a newer copy, for up to a week) and the fonts for a year; the page itself is always checked. So if you replace a file in `assets/`, give it a new name (and update `index.html`), or returning visitors may see the old one for up to a day.
- `favicon.ico`, `icon.svg`: the browser-tab icon (the logo emblem; the SVG gets a cream disc behind it in dark mode). `apple-touch-icon.png` (180px), `icon-192.png`, `icon-512.png`, `icon-512-maskable.png` and `site.webmanifest`: the icons for phones' home screens and Android.
- `assets/fonts/`: Manrope (the latin and latin-extended files; `OFL.txt` is its licence).
- `404.html`: the page shown for any address that doesn't exist (Vercel serves it automatically), with Back to home and Refresh buttons.
- `robots.txt`, `sitemap.xml`: for search engines.
- `assets/og-image.jpg`: the link-preview image; `assets/logo.svg`: the logo as a file (used by the 404 page); `assets/apple-touch-icon.png`: the emblem picture on the 404 page.
- `assets/video/`: the hero film: the silent preview loop (`hero-loop.webm`, `hero-loop.mp4`, under 1.3MB, on computers and tablets; `hero-loop-sm.webm`, `hero-loop-sm.mp4`, 720px at 24fps and about half the size, on phones), the full film with sound (`hero.webm`, `hero.mp4`) and the poster (`hero-poster.webp`).
- `assets/books/`, `assets/gallery/`: the large, uncropped covers and photos that open when a visitor clicks one (loaded only then); `assets/thumbs/` holds the small covers and gallery prints shown on the page.
- `assets/about/`: Vinit's portrait for the About section (`vinit-640.webp`, `vinit-960.webp`; the browser picks one by screen width).
- `assets/reels/`: the program reels (`video1.*` Desk Detox, `video2.*` Stress & Sleep, `video3.*` Morning Energy Flow). The Inside a class reel uses `assets/stories/class-steps.*`.
- `assets/stories/`: the story clips (`*.webm` AV1 first, `*.mp4` H.264 for Safari; loaded only when a visitor presses play), their posters (`*.webp`), the student photos (`*-card.webp` in the cards, the larger `*.webp` in the viewer) and `mandeep-face.webp` beside the booking form.

The logo is built into `index.html`; the icons are the files at the root. The client's original logo file is kept with the design files, outside this repository.
