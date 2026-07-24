# Brutalitops — splash page

A single static HTML file, no build step, no backend.

## Deploying to brutalitops.com (Cloudflare Workers)

This is a Worker with static assets (`wrangler.jsonc`), same pattern as a
regular Workers site — no build step, it just serves the files in this repo
directly. A Worker named `brutalitops` already exists in the Cloudflare
account; connect it to this repo once and every push to `main` deploys:

1. Cloudflare dashboard → **Workers & Pages** → **brutalitops** (the existing
   worker) → **Settings** → **Build** (or **Git integration**) → connect it to
   `jmashley1982/brutalitops`, branch `main`. No build command needed —
   Wrangler picks up `wrangler.jsonc` and deploys the repo root as-is.
   - If it's not already connected, **Create** → **Workers** → **Connect to
     Git** → this repo works the same way; just make sure the Worker name
     stays `brutalitops` to match what's already provisioned.
2. **Custom domain**: on the `brutalitops` worker → **Settings** → **Domains &
   Routes** → add `brutalitops.com` (and `www.brutalitops.com` if you want
   it). Since the domain's already on Cloudflare, this just adds the DNS
   record — no registrar changes needed.

## Editing content

Everything is in `index.html` — copy, styling, and the tiny bit of JS (footer
year) are all inline, nothing else to touch.

Things you'll probably want to fill in once you have them:
- `booking@brutalitops.com` / `@brutalitops` Instagram handle in the Contact section — placeholders, set up the real inbox/handle or swap the links.
- The "Coming Soon" Spotify/Bandcamp/YouTube buttons in `#listen` — replace `href="#"` with real URLs and drop the `soon` class once you have music up.

`images/logo.png` is the full logo artwork (skull + the band name worked into
the spiky lettering around it) — displayed with a CSS `invert()` so its white
background reads as transparent against the black page. `images/hero-band.png`
is the live photo used both in the hero section and as the `og:image` link-preview.
