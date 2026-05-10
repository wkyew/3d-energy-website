# 3D Energy Project — Marketing Site

A single-page editorial marketing site for the 3D Energy Project — an international blended-learning programme funded by the British Council Going Global Partnerships.

## Files

```
site/
  index.html        ← the site (open this)
  sitemap.xml       ← upload to your domain root
  robots.txt        ← upload to your domain root
  images/           ← drop the photos in here (see filenames below)
```

## Required images

The site references the following filenames. Drop matching JPGs into `site/images/`:

| Filename | Used for | Notes |
|---|---|---|
| `cohort4_malaysia_2026.jpg` | Hero banner + Cohort 04 card | Wide landscape (≥ 1800×1000); favour the people in the frame |
| `cohort1_malaysia_2022.jpg` | Cohort 01 card | 16:10 |
| `cohort2_vietnam_2023.jpg`  | Cohort 02 card | 16:10 |
| `cohort3_china_2024.jpg`    | Cohort 03 card + "Approach" right card | 16:10 |
| `workshop_session.jpg`      | "Approach" left card | 16:9 |
| `decarbonisation.jpg`       | Pillar 01 background | Optional · landscape · subtle, will be dimmed to 30% |
| `decentralisation.jpg`      | Pillar 02 background | Optional · landscape |
| `digitalisation.jpg`        | Pillar 03 background | Optional · landscape |

Anywhere a photo is missing, the page renders a striped paper placeholder with the filename — so the layout never breaks while you source images.

## Deploying

### Netlify / Vercel / GitHub Pages
Drag the `site/` folder onto Netlify Drop, or push the contents of `site/` to a GitHub repo and enable Pages. Fully self-contained — only external dependency is Google Fonts.

### University web server
Upload `index.html`, `sitemap.xml`, `robots.txt`, and the `images/` folder via SFTP. Preserve the relative `images/` path.

## Before going live — swap list

1. **Canonical URL.** Replace `https://www.3denergy.org/` in:
   - `<link rel="canonical">`
   - `og:url` meta tag
   - `og:image` and `twitter:image` (currently absolute paths)
   - JSON-LD `@id`, `url`, `logo`, and `provider.@id`
   - `sitemap.xml` (every `<loc>`)
   - `robots.txt` `Sitemap:` directive
2. **Hero photo** — drop `cohort4_malaysia_2026.jpg` into `images/`. Use `object-position: center 38%` if heads are getting cropped (already set; tune in CSS).
3. **Video.** The "Watch" section uses a click-to-load YouTube embed. Replace the placeholder ID `dQw4w9WgXcQ` on `#videoFrame[data-yt]` with your real video ID.
4. **Testimonials.** The four pull-quotes in `#voices` are illustrative. Swap with real attributions before publishing.
5. **Featured publication + list.** Replace title, authors, venue, and DOI in `.featured-pub` and the four `.pub` rows.
6. **Cohort statistics.** Verify participant counts and dates in each `.cohort` block.
7. **FormSubmit activation.** The form posts to `https://formsubmit.co/w.yew@hw.ac.uk`. On the **first** real submission, FormSubmit emails a confirmation link to that address — click it once to activate. Until then, submissions silently fail. There is a `mailto:` fallback in the form's error path.
8. **Pillar background images** (optional). Drop `decarbonisation.jpg` / `decentralisation.jpg` / `digitalisation.jpg` into `images/` to upgrade the pillar triptych from solid colour to photo-led panels at 30 % opacity.

## What's in the page

Sticky glassy nav · scroll progress bar · hero (giant typographic statement, lede, funder credit, banner photo, four numerical stamps) · about (asymmetric 1:1.35) · approach (two cards) · pillar triptych (full-bleed, three accent colours, ghost letterforms) · network (dark map stage with animated dashed arcs + four-city legend) · cohorts (2×2 photo grid) · video (click-to-load YouTube) · voices (auto-rotating carousel with manual nav, pause on hover, reduced-motion respected) · research (featured pub + list) · closing statement (giant ghost watermark) · contact (two-column copy + working form with mailto fallback) · footer.

## Accessibility & performance

- Skip-to-main-content link
- ARIA labels on nav, progress bar, carousel
- Alt text on every photo
- Visible focus rings (keyboard users)
- `prefers-reduced-motion` respected (carousel, fades, pulse, dashed arcs)
- Preconnect + preload for Google Fonts
- No JS frameworks; all interactivity vanilla
- Click-to-load video saves the YouTube cookie cost until the user opts in

## SEO

- Semantic landmarks (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- Meta description + keywords + author
- Open Graph + Twitter card
- JSON-LD: `EducationalOrganization` + `Course` (+ `CourseInstance`)
- Canonical URL
- `sitemap.xml` + `robots.txt`

After deploy, submit the sitemap to Google Search Console and Bing Webmaster Tools.
