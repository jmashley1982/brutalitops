# Brutalitops — splash page

A single static HTML file, no build step, no backend.

## Deploying to brutalitops.com (Cloudflare Pages)

1. Cloudflare dashboard → **Workers & Pages** → **Create** → **Pages** → **Connect to Git** → this repo (`jmashley1982/brutalitops`).
2. Build settings:
   - Framework preset: `None`
   - Build command: *(leave empty)*
   - Build output directory: `/` (repo root)
3. Deploy. Point it at your `main` branch for production.
4. **Custom domain**: in the new Pages project → **Custom domains** → add
   `brutalitops.com` (and `www.brutalitops.com` if you want it). Since the domain
   is already on Cloudflare, it just adds the DNS record for you — no registrar
   changes needed.

## Editing content

Everything is in `index.html` — copy, styling, and the tiny bit of JS (footer
year) are all inline, nothing else to touch.

Things you'll probably want to fill in once you have them:
- `booking@brutalitops.com` / `@brutalitops` Instagram handle in the Contact section — placeholders, set up the real inbox/handle or swap the links.
- The "Coming Soon" Spotify/Bandcamp/YouTube buttons in `#listen` — replace `href="#"` with real URLs and drop the `soon` class once you have music up.
- `og:image` meta tag points at `/images/og-band.jpg` — drop a real band photo in `images/` at that filename for link previews (socials, iMessage, etc. use this).

The hero skull is a hand-drawn inline SVG (no image file), so it stays crisp at
any size and needs no asset — swap it for the real logo/photo once it's in `images/`.
