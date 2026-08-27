# Ema Beauty Salon — Website

A premium, production-ready one-page website for Ema Beauty Salon, a beauty salon in Wembley, London.

Built as static **HTML5 + Tailwind CSS (via CDN) + vanilla JavaScript** — no build step required, so it's easy for a non-technical salon owner to edit and host anywhere.

## What's included

```
ema-beauty-salon/
├── index.html            Main website (all sections)
├── pricing.html          Standalone price list page
├── privacy-policy.html   Placeholder privacy policy
├── cookie-policy.html    Placeholder cookie policy
├── robots.txt            Search engine crawl rules
├── sitemap.xml           XML sitemap
└── README.md             This file
```

## Business information used

- **Name:** Ema Beauty Salon
- **Address:** 5-7B Wembley Hill Rd, Wembley, HA9 8AF, United Kingdom
- **Telephone:** +44 7714 317072
- **Google Business Profile:** https://maps.app.goo.gl/cCQRtFXzxzGdwnet8

## Important — content you still need to add

To keep the site honest and accurate, several things were deliberately left as clearly-marked placeholders rather than invented:

| Item | Where | What to do |
|---|---|---|
| Opening hours | "Opening Hours" section in `index.html` | Replace each `[Opening hours]` with the real hours |
| Service prices | "Services" section in `index.html` **and** `pricing.html` | Replace "Price on consultation" with real prices (e.g. "From £35") in both places — they list the same treatments |
| Preferred Time options | "Contact" section, `<select id="time">` in `index.html` | Currently lists 9:00 AM–6:00 PM in 30-minute steps as a placeholder range — trim it to match your real opening hours once confirmed |
| Customer reviews | "Reviews" section | Replace the placeholder card with real, verified reviews (e.g. embed via a reviews widget, or manually add quote cards in the same style) |
| Photography | Hero, About, Gallery, Featured Services | All images are stock photography from Unsplash. Replace the `src` attributes with real photos of the salon, staff and treatments |
| Privacy / Cookie policy | `privacy-policy.html`, `cookie-policy.html` | Placeholder legal text — have these reviewed/completed (ideally by a professional) before launch |
| Domain / canonical URLs | `<link rel="canonical">`, sitemap.xml, robots.txt, Open Graph tags | Currently set to `https://www.emabeautysalon.co.uk/` as a placeholder — update to the real domain once purchased |
| Contact form backend | "Contact" section, bottom of `index.html` | The form validates in the browser but is **not** connected to an email or booking service yet (see below) |

## Editing the site

Everything is in plain HTML with Tailwind utility classes, so you can:

1. Open `index.html` in any code editor (e.g. VS Code).
2. Search for the text you want to change (e.g. "Price on consultation" or `[Opening hours]`) and replace it.
3. To swap an image, replace the `src="https://images.unsplash.com/..."` URL with a link to your own photo (or a local file path once you're hosting your own images).

No `npm install` or build tools are required — it's ready to open directly in a browser.

## Connecting the contact form

The form in the "Contact" section currently validates fields (name, email, message required) and shows a confirmation message, but does **not** send an email, because no backend was supplied. To make it fully functional, connect it to one of:

- A form backend service (e.g. Formspree, Basin, Getform) — point the form's `action` at their endpoint.
- A serverless function (e.g. on Netlify, Vercel, or Cloudflare Workers) that sends the submission via email.
- A booking platform (e.g. Fresha, Treatwell) — in which case the "Book an Appointment" buttons can link straight to your booking page instead.

## Local preview

Just open `index.html` directly in a browser, or serve the folder locally:

```bash
cd ema-beauty-salon
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deployment

This is a static site, so it can be deployed to any static host, for example:

**Netlify / Vercel (drag & drop)**
1. Create a free account.
2. Drag the `ema-beauty-salon` folder onto the dashboard.
3. Point your domain's DNS at the host once you're happy with the preview.

**Traditional web hosting (cPanel / FTP)**
1. Upload all files in this folder to your hosting account's `public_html` (or equivalent) directory, keeping the same file names.
2. Make sure `index.html` sits at the root so it loads at your domain automatically.

After deploying:
- Update the canonical URL, sitemap.xml and Open Graph `og:url`/`og:image` to your real domain.
- Submit `sitemap.xml` to Google Search Console.
- Add real opening hours to both the visible "Opening Hours" section.

## SEO & structured data

- Semantic HTML with a single `<h1>` and logical heading hierarchy.
- Meta title, description, canonical tag, Open Graph and Twitter meta tags.
- `BeautySalon` structured data (JSON-LD) in `<head>` with only confirmed facts (name, address, phone, Google Business Profile link) — no invented ratings, hours or price range.
- Copy naturally targets local search intent ("beauty salon Wembley", "beauty treatments Wembley") without keyword stuffing.

## Accessibility

- Skip-to-content link, semantic landmarks, visible focus states.
- Descriptive `alt` text on all images.
- Accordion FAQ built with native `<details>`/`<summary>` (keyboard accessible by default).
- Mobile menu and lightbox are keyboard- and screen-reader-friendly, with `aria-*` attributes.
- All animations respect `prefers-reduced-motion`.

## Performance

- No build step, no heavy frameworks — Tailwind is loaded via CDN and the only JavaScript is a small vanilla script for interactivity.
- Images use `loading="lazy"` where appropriate and reasonable widths via Unsplash's `?w=` parameter.
- For a production launch, consider self-hosting fonts and pre-building Tailwind (instead of the CDN build) for the best Lighthouse score.
