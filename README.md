# The Bing Lin website — V5 / Nature & Human Nature

Complete Astro project with an editorial homepage and distinct Science, Photography, Writing, Book and Contact pages. Designed for Cloudflare Pages and GitHub.

## Deploy / update

1. Back up the current GitHub repository or keep the previous commit as a rollback point.
2. Open **GitHub Desktop** (recommended for multi-file updates), clone `thebinglin/thebinglin-website` if needed, and copy **all contents of this folder** into the repository root, overwriting the older source files. Retain the `.git` directory within the clone. Do **not** copy this entire folder as one nested directory.
3. Commit a message such as `V5: complete editorial rebuild` and push to `main`.
4. Cloudflare Pages should automatically deploy. Build command: `npm run build`; output directory: `dist`; root: `/`; branch: `main`.
5. Check `/`, `/science/`, `/photography/`, `/writing/`, `/book/`, and `/contact/` on `thebinglin-website.pages.dev`.

## What is in this edition

- Home: split photography opening, personal essay, asymmetrical photographic chapters, cross-disciplinary links.
- Science: research vision, methods, 11 CV-grounded publications, grants/appointments, supervision/teaching, cover feature, downloadable academic CV, Google Scholar and ORCID.
- Photography: 21 selected original gallery images, accessible category filters and a lightbox, original publications and recognition, downloadable creative CV.
- Writing: all 15 entries from the 17 Nov 2026 Squarespace writing export, with original external publication links, grouped into series, narrative reporting, commentary, science news and reviews.
- Book: prose from the Squarespace book page (as of 17 Nov 2026), eight original themes, publisher/support details, 2028 date.
- Contact: existing personal style, "Best fishes, Bing", direct email.
- 404 page, legacy URL redirects and social metadata.

## Sources and fidelity

Content was built from the live public site (checked 18 Nov 2026), user-supplied Squarespace WordPress XML export, the HTML/PDF of the Science page, and both September 2026 CVs. The live Photography page and its two sub-galleries were checked separately because they are not included in the XML export. The photographic gallery is intentionally *curated*, not a verbatim copy of every gallery image.

Publication note: The aquarium-trade article **Extent of threats** was first published online in October 2025 and appears in the February 2026 print volume. The old Science page labels it 2025; the September 2026 academic CV labels it 2026. This edition uses the final journal-volume year, 2026.

Some descriptions and transitions were written specifically for this edition. Public-facing achievements (and under-review proposals) were not silently promoted to awarded funding.

## IMPORTANT — before cancelling Squarespace

**Images are still linked to Squarespace CDN**, using the original asset URLs documented in `src/data/photos.json` and a few directly embedded page references. This supports the current staging preview, but those image URLs must be copied to assets you control before you cancel the Squarespace subscription. We could not download the originals into this build environment. Ask for an image-asset migration pass and provide your original images (or run a controlled image download) before the domain cutover.

The included PDF CV copies have the personal phone number and exact street address redacted for public web use. The source CV uploads are unchanged; email, institution, professional record and links remain. Review the published copies before making the new domain public.

The temporary preview is **noindex** by default. Only when ready to move `thebinglin.com` to the new site, add a Cloudflare Pages build variable `PUBLIC_SITE_LIVE=true` and redeploy, which enables indexing. Do not enable while the Squarespace original is still public and canonical.

## Local commands

```bash
npm install
npm run dev
npm run build
```

Node.js 20+ recommended. Only the official Astro dependency is required.

## Editing later

- Page bodies: `src/pages/*.astro`
- Type and colors / layout: `src/styles/global.css`
- Original portfolio image inventory and captions: `src/data/photos.json`
- Writing archive (title, publisher, excerpt, destination): `src/data/writing.json`
- Academic publications: `src/data/publications.json`
- Shared header/footer, SEO, and deployment `noindex`: `src/layouts/BaseLayout.astro`
- Academic CV/Creative CV: `public/docs/`

## Known limits / pre-launch checks

- This environment could not run `npm install` because `registry.npmjs.org` was unreachable; the Astro build therefore needs to be tested by Cloudflare after upload. JSON and CSS syntax were independently checked.
- Verify all remote images and editorial destination URLs in the deployed browser.
- Test keyboard and mobile gallery behavior, especially the lightbox, on your devices.
- Review the CV PDF copies to confirm the redactions and remaining public contact information meet your preferences.
- Replace remote Squarespace assets, finalize photographic titles and story captions, and verify the site against the original before DNS switch.
- Email links are functional; no newsletter backend is set up yet.
- Do not change DNS or cancel Squarespace until final sign-off.
