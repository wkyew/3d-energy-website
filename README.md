# 3D Energy Project — Website

A single-page marketing/showcase site for the 3D Energy Project.

## Files

```
3D_Energy_Website.html          ← the website (open this)
sitemap.xml                     ← upload to your domain root for SEO
robots.txt                      ← upload to your domain root for SEO
images/
  cohort1_malaysia_2022.jpg     ← Malaysia summit, Dec 2022
  cohort2_vietnam_2023.jpg      ← Vietnam summit, Aug 2023
  cohort3_china_2024.jpg        ← China summit, Jun 2024
  cohort4_malaysia_2026.jpg     ← Malaysia summit, Jan 2026 (used in hero)
  workshop_session.jpg          ← Lecture-style workshop
  decarbonisation.svg           ← Pillar 1 illustration (placeholder)
  decentralisation.svg          ← Pillar 2 illustration (placeholder)
  digitalisation.svg            ← Pillar 3 illustration (placeholder)
```

## Deploying

### Option A — Static host (Netlify / Vercel / GitHub Pages)

Drag the entire output folder onto Netlify Drop, or push it to a GitHub
repo and enable GitHub Pages. The site is fully self-contained — only
external dependencies are Google Fonts and the Formspree form endpoint.

### Option B — University web server

Upload everything via FTP/SFTP. Make sure the `images/` folder structure
is preserved relative to the HTML.

### Update the canonical URL

In the `<head>`, change `https://www.3denergy.org/` to your real URL in:

- `<link rel="canonical" ...>`
- `og:url` meta tag
- All entries in `sitemap.xml`

## Replacing the pillar illustrations with AI-generated images

The three pillar panels currently use SVG placeholders (`decarbonisation.svg`,
`decentralisation.svg`, `digitalisation.svg`) sitting at 35% opacity behind the
text. To swap in AI-generated photos:

1. Generate three images, ideally **landscape 4:3 or 16:9, ~1600px wide**.
2. Save them as e.g. `images/decarbonisation.jpg`, `images/decentralisation.jpg`,
   `images/digitalisation.jpg`.
3. In the HTML, find the three `<article class="pillar-panel">` blocks and
   change each `<img src="images/decarbonisation.svg" ...>` to point at your
   `.jpg` file.

The CSS will automatically dim the image to 35% opacity and overlay the
white text — bright, busy images may need their own opacity tweaked.

## Suggested AI image prompts

**Decarbonisation** — "Aerial photograph of a wind farm at golden hour, with
solar panels in the foreground, soft warm light, no people, cinematic, 16:9"

**Decentralisation** — "Aerial photograph of a residential neighborhood at
twilight with solar panels on rooftops and connected fibre/light lines hinting
at a microgrid, cool blue tones, no people, cinematic, 16:9"

**Digitalisation** — "Macro photograph of a glowing circuit board with
abstract data flow patterns, magenta/pink lighting, shallow depth of field,
no text, cinematic, 16:9"

## Contact form

The form posts to **https://formsubmit.co/w.yew@hw.ac.uk** by default.

On the **first** submission, FormSubmit will send a confirmation link to that
email — click it once to activate the endpoint. After that, every submission
arrives as an email.

If you want to use a different service (Formspree, Basin, Web3Forms), change
the `action="..."` attribute on the `<form id="contactForm">`.

## SEO checklist

- ✅ Semantic HTML (`<header>`, `<nav>`, `<main>`, `<article>`)
- ✅ Meta description with target keyword "blended learning"
- ✅ OG + Twitter card meta tags
- ✅ JSON-LD structured data (EducationalOrganization + Course)
- ✅ Sitemap.xml + robots.txt
- ✅ Alt text on all photos
- ✅ Mobile-responsive
- ✅ Skip-to-main-content link for screen readers
- ✅ Canonical URL

After deploying, submit the URL to:
- Google Search Console → https://search.google.com/search-console
- Bing Webmaster Tools → https://www.bing.com/webmasters
