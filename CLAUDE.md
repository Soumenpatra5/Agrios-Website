# AgriOS Website — Claude Code build instructions

## What this is

The public website for **AgriOS Integrated Farm(s) Pvt Ltd**, a commercial integrated
farm in Jhargram, West Bengal. The complete website is already built and working as a
single `index.html` file. Your job is **not to redesign it** — it's to get it live,
fast, and keep it maintainable.

The authoritative design spec is the **Build Bible** (`AgriOS_Website_Build_Bible.docx`).
If anything is unclear, that document wins. Do not change the design, copy, colors, or
structure without a reason — it was all deliberately decided.

## Files in this folder

- `index.html` — the complete 5-page website (Home, About, What We Do, Products, Contact).
  Single file, all CSS inline in a `<style>` block, a little vanilla JavaScript for page
  switching and the interactive cycle. References 3 external images.
- `admin.html` — a working DEMO of the farm/website admin panel (not wired to a backend).
  Deploy it too, but it is a mockup with sample data for now.
- `logo-header.png` — the "AgriOS" wordmark used in the site header (transparent).
- `logo-footer.png` — the full logo with tagline used in the footer (transparent).
- `logo-secondary.png` — the icon/secondary mark (transparent), for alt uses.
- `logo-bw.png` — black & white version, for print/documents/dark backgrounds.
- `favicon.png` — the browser tab icon (from the icon logo).
- `icon-180.png` — apple-touch icon for mobile home screens.

## Primary goal: GET IT LIVE (fastest path)

Do this first. It should take well under an hour.

1. Keep the site as static HTML — do NOT rebuild in React yet (unnecessary for going live).
2. Verify `index.html` opens correctly with the 3 images alongside it.
3. Deploy to **Vercel** (or Netlify) as a static site:
   - `npm i -g vercel` (if needed)
   - from this folder: `vercel --prod`
   - it's a static site — no build step, no framework. Vercel will just serve the files.
4. The site is now live. Share the URL.

That's the whole "go live" job. Everything below is optional polish.

## Optional improvements (only after it's live)

### 1. Connect the contact form (currently a demo)
The form in the Contact section does not send anywhere yet. Wire it to a form service:
- Easiest: **Formspree**. Create a form, put the endpoint in the `<form>` action, switch
  the `onsubmit` handler to a normal POST (or keep JS and fetch() to Formspree).
- Alternative: Google Forms, or a tiny serverless function.

### 2. Add a social-share image
The `<head>` references `og-image.jpg` (for WhatsApp/Facebook link previews) but the file
doesn't exist yet. Create a 1200×630 image (the logo on the paper background works well)
and add it to the folder.

### 3. Compress the logos (faster load)
The logo PNGs are already reasonably sized but can be optimized further. Run them through
an optimizer (e.g. `sharp`, `squoosh`, or `pngquant`) to cut load time. Keep filenames.

### 4. Point the SEO URLs at the real domain
In `index.html` `<head>`, several tags use `https://agriosfarm.in/` as a placeholder
(canonical, og:url, JSON-LD). Replace with the actual domain once registered.

## If you later rebuild as React (NOT now)

When the time comes to build the real admin platform, rebuild the site on
**React + Vite + TypeScript + Tailwind + Firebase** — the same stack as the Ascendo apps —
so the website and admin share one codebase. The Build Bible maps directly onto that build:
its color tokens, component library, and page specs are the blueprint. The current
`index.html` is the reference implementation — match it exactly.

## Design tokens (from the Build Bible — do not drift)

- Paper `#FAF9F5`, Paper-2 `#F3F1E9`
- Green (primary) `#3D6B4F`, Green-dark `#2F5540`, Green-tint `#EDF1EA`
- Terracotta (accent) `#CC785C`, Clay-tint `#F7EDE8`
- Ink `#1A1A17`, Muted `#5A574E`, Line `#E4E0D5`
- Font: Hanken Grotesk (Google Fonts)
- Card radius 14px, generous whitespace, one accent (green primary, terracotta sparingly)
- Tagline: **Smart Farming. Better Future.**

## Things that still need the owner (Soumen / Saikat) — not your job to invent

- Real farm photographs (the gallery uses placeholder frames — do NOT fake photos)
- Real certification numbers (GST, FSSAI, Udyam — currently placeholder badges)
- Exact GPS coordinates for the map pin
- Confirm "Farm" vs "Farms" wording (the logo says "Farms" plural; the site says "Farm")

Do not invent any of the above. Leave placeholders as they are until real data is provided.

## Deploy checklist

- [ ] `index.html` + 3 images open correctly together locally
- [ ] Deployed to Vercel/Netlify, live URL works
- [ ] `admin.html` reachable (e.g. /admin.html) — footer has a discreet "Admin" link
- [ ] Test on a phone (responsive layout, WhatsApp button, tap the AgriOS Cycle)
- [ ] (Optional) contact form connected
- [ ] (Optional) og-image added, logos compressed, real domain in SEO tags
