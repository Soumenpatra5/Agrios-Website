# AgriOS Integrated Farm — Website Build Bible

**The authoritative specification for the company website**
Design · Content · Structure · Build · Roadmap
Version 1.3 · 2026 · Prepared with the same discipline as the Ascendo build specs

---

## Contents

0. How to use this document
1. Project overview
2. Locked decisions
3. Brand & design system
4. Site structure & navigation
5. Page-by-page specification
6. Content sources
7. Component library
8. Technical build notes
9. Go-live checklist
10. The AgriOS platform (admin & backend)
11. Future expansion
12. Competitor benchmarking & our edge
13. Delivery roadmap & next actions

---

## 0. How to use this document

This is the Build Bible for the AgriOS Integrated Farm website — the single source of truth. It works exactly like the Ascendo app spec documents: every decision is locked here first, and the build follows this document rather than the reverse. **If the website and this document ever disagree, this document wins, or it gets formally updated.**

**Order of authority:** (1) this Build Bible, (2) the live website code, (3) anything else. When you want a change, change it here first, then build to match.

> **The build already exists.** A working version of this website has already been built to this specification (`index.html`). This document records *why* it is the way it is, so it can be rebuilt, handed to a developer, or extended without losing the original intent.

---

## 1. Project overview

### 1.1 What this is

A multi-page marketing website for AgriOS Integrated Farm Pvt Ltd — a commercial integrated farm in Jhargram, West Bengal. The site is the company's public face and brand home.

### 1.2 Who it is for

| Audience | What they need from the site |
|---|---|
| Banks / investors | Confidence that this is a real, professional, credible company |
| Integrators (Suguna, IB Group, etc.) | A serious counterpart worth contracting with |
| Future customers | A trustworthy source of farm products — feed, breeding stock, produce, farm-fresh goods |
| General public / community | Clear information about who the farm is and what it does |

### 1.3 What it must achieve

- Establish credibility from the first screen.
- Explain the integrated-farm model simply.
- Prepare the ground for selling branded products.
- Make it easy to get in touch (form, phone, email, WhatsApp).

---

## 2. Locked decisions

Every foundational decision, settled during the specification interview. Fixed unless deliberately changed here.

| # | Decision | Locked value |
|---|---|---|
| 1 | Company name | AgriOS Integrated Farm Pvt Ltd |
| 2 | Primary purpose | Mixed — credibility + future sales + info presence |
| 3 | Site structure | Multi-page: Home, About, What We Do, Products, Contact |
| 4 | Visual language | Ascendo design, farm-tuned |
| 5 | Primary colour | Farm green — `#3D6B4F` |
| 6 | Accent colour | Terracotta — `#CC785C` (Ascendo signature) |
| 7 | Background | Warm paper — `#FAF9F5` |
| 8 | Text colour | Warm near-black — `#1A1A17` |
| 9 | Typeface | Hanken Grotesk |
| 10 | Content source | From the DPR; more added over time |
| 11 | Contact method | Form + phone + email + address + WhatsApp button |
| 12 | Products page | Full range: AgriOS feed brand (formula confidential), breeding stock, produce, farm-fresh, cocopeat (Yr5) |

---

## 3. Brand & design system

The design language is inherited from Ascendo and tuned for a farm brand: the same calm minimalism and warm paper, but with a farm-green primary so it reads instantly as agriculture, and terracotta kept as the connective accent that ties the website to the Ascendo family and the DPR paperwork.

> **Logo & tagline.** A full logo kit was supplied (primary, secondary, icon, black & white, transparent). Used across the site: the clean AgriOS wordmark (from the primary) in the header, the full logo with tagline in the footer, the icon as favicon and in the admin sidebar. Black & white kept on file for print. Official tagline: **"Smart Farming. Better Future."**

### 3.1 Colour tokens

| Token | Hex | Role |
|---|---|---|
| Paper | `#FAF9F5` | Page background |
| Paper 2 | `#F3F1E9` | Alternate section band |
| Green (primary) | `#3D6B4F` | Brand colour — primary buttons, logo, links |
| Green dark | `#2F5540` | Button hover, dark green bands |
| Green tint | `#EDF1EA` | Soft green cards / stat cards |
| Clay (accent) | `#CC785C` | Terracotta accent — secondary buttons, highlights |
| Clay tint | `#F7EDE8` | Soft terracotta cards |
| Ink | `#1A1A17` | Primary text |
| Muted | `#5A574E` | Secondary text |
| Line | `#E4E0D5` | Borders / hairlines |

> **One accent rule.** Green is the brand. Terracotta is the single accent, used sparingly — secondary buttons, one stat card, a highlight. Never let terracotta compete with green for dominance; that restraint is what keeps it feeling like Ascendo.

### 3.2 Typography

| Element | Font / weight | Size |
|---|---|---|
| Display / H1 | Hanken Grotesk 600 | 30–52px (fluid) |
| Section / H2 | Hanken Grotesk 600 | 24–34px (fluid) |
| Card title / H3 | Hanken Grotesk 600 | 19px |
| Body | Hanken Grotesk 400 | 15–16px |
| Lead paragraph | Hanken Grotesk 400 | 16–19px, muted |
| Eyebrow / label | Hanken Grotesk 600 | 12px, uppercase, letter-spaced, green |

Case: sentence case everywhere except the eyebrow labels (uppercase). Letter-spacing tightened slightly on large headings (-0.02em).

### 3.3 Shape, spacing & motion

- **Corner radius:** 14px on cards, 9–11px on buttons and inputs, 20px on pills.
- **Cards:** white background, 1px line border, soft lift + shadow on hover.
- **Spacing:** generous — 72px section padding on desktop, 52px on mobile.
- **Motion:** gentle only — page fade-in, card hover lift, smooth scroll. Nothing flashy.
- **Max width:** 1120px content column, centred.

---

## 4. Site structure & navigation

### 4.1 Pages

| Page | Route | Purpose |
|---|---|---|
| Home | `/` | Hook, overview, route to everything |
| About | `/about` | Story, promoter, principles, gallery, certifications |
| What We Do | `/what` | All enterprises + integrated model + sustainability + expansion |
| Products | `/products` | Full product range — feed brand, breeding stock, produce, farm-fresh |
| Contact | `/contact` | Form, contact details, WhatsApp, map, FAQ |

*(In the current single-file build these are one HTML file with JS page-switching, not separate routes. When rebuilt in React they become real routes.)*

### 4.2 Navigation

- Sticky header, translucent with blur, on every page.
- Left: AgriOS wordmark logo (clickable → home).
- Right: Home, About, What We Do, Products, and a green "Contact" button.
- Active page is highlighted in green.
- Below 860px: links collapse into a hamburger menu.
- Footer repeats navigation, contact links, full logo + tagline, and a discreet "Admin" link.

---

## 5. Page-by-page specification

### 5.1 Home

| Section | Content |
|---|---|
| Hero | Eyebrow (location), headline "Farming, integrated the way nature intended.", lead paragraph, two buttons (Schedule a farm visit / See what we do), stat stack (5,000 birds, 4 ponds, 16 bigha, 9 enterprises) |
| The AgriOS idea | Centred band: "One farm, many enterprises, zero waste" + 4-step loop + one-line vision |
| What we raise & grow | 4 enterprise cards + "Explore all enterprises" button |
| Farm by the numbers | Impact strip: 16 bigha, 5,000 birds/batch, 9 enterprises, 4 ponds |
| A word from our founder | Signed note from Soumen Patra with photo/avatar |
| Products teaser | Green band: farm-fresh products coming soon + button to Products |

### 5.2 About

| Section | Content |
|---|---|
| Hero | "Rooted in Jhargram, built on real experience." + intro |
| Our story | Two-column: narrative + promoter card (Soumen Patra, experience, ICAR training) |
| Vision & mission | Two cards — green vision card + white mission card (see 5.6) |
| Our principles | 4 cards: Nothing wasted, Built to last, Done scientifically, Good for the region |
| Gallery | "The farm in pictures" — photo placeholder frames, ready for real images |
| Certifications & trust | 4 badge cards: Registered Pvt Ltd, GST, FSSAI, Udyam/MSME (placeholders — real numbers to follow) |

A one-line vision statement also appears on the Home page beneath the integrated-loop, linking through to About.

### 5.3 What We Do

| Section | Content |
|---|---|
| Hero | "Nine enterprises, one connected system." |
| Enterprise grid | 9 cards: contract poultry, pig, goat, duck, aquaculture, horticulture, beekeeping, vermicompost, AgriOS Feed |
| The AgriOS Cycle | **INTERACTIVE signature:** a circular 5-node diagram (Livestock → Compost → Crops → Ponds → Fodder). Tapping a node updates a side panel explaining how that stage feeds the next. No competitor shows integration visually. |
| Integrated model | Green band: how one enterprise feeds the next (litter → compost → ponds → fodder) |
| Sustainability | Two-column: rationale + 5 sustainability points |
| Future expansion | Horizontal 5-phase timeline: Year 1 (done) → Year 10 |

### 5.4 Products

| Section | Content |
|---|---|
| Hero | "From our farm — and our own brand." |
| Own feed brand (feature) | **PROMINENT** — a dedicated feature block. Feed is branded **"AgriOS"** (same name as the company — one unified brand across farm and feed), made on a proprietary in-house formula. The formula is referenced as a strength but kept **CONFIDENTIAL** on the public site (Biochem "protect the formula" instinct). Poultry/pig/goat/fish feed. |
| Live breeding stock | Piglets, goat kids, ducklings, fish fingerlings — "available fairly soon" (near-term) |
| Farm produce | Bananas, papaya (Red Lady 786), black pepper |
| Farm-fresh goods | Raw honey, farm eggs, farm meat; cocopeat marked "Year 5" |
| CTA | "Interested in our stock, produce or feed?" + Get in touch |

> **Feed formula is confidential.** The AgriOS feed brand is a major line and gets prominence, but the proprietary formula is never shown on the public site — only the brand, the products and the benefits. Mirrors the Biochem approach of protecting formulas from competitors.

### 5.5 Contact

| Section | Content |
|---|---|
| Hero | "Let's talk — or better, let's meet." + welcoming line |
| Form | Name, Email, Phone, Message + Send button (demo until wired to a form service) |
| Contact panel | Phone +91 97491 63932, email Soumanpatra5@gmail.com, farm address, green "Schedule a farm visit" button (pre-filled WhatsApp), and a WhatsApp chat button |
| Location map | Embedded Google Map of the area + address caption + "Open in Google Maps" link. Centres on exact pin once coordinates are supplied. |
| FAQ | 5 common questions (visits, supply area, feed availability, product timing, partnerships) as an accordion |

### 5.6 Vision & mission (current copy)

Placed on the About page between "Our story" and "Our principles". Draft copy in use now; the promoter will supply final wording later.

**Vision** — To become Eastern India's model integrated farm — a self-sustaining enterprise that proves modern, scientific and environmentally responsible farming can be profitable, and that inspires a new generation of rural entrepreneurs.

**Mission** — To run a diversified, closed-loop farm where poultry, livestock, aquaculture and horticulture strengthen one another — producing safe, quality food, creating local employment, caring for the land, and building a trusted brand for farm-fresh produce.

---

## 6. Content sources

All current copy is drawn from the AgriOS Detailed Project Report (DPR). This table tracks where each piece comes from and what still needs the promoter's input.

| Content | Source | Status |
|---|---|---|
| Farm story, model, enterprises | DPR | Final for now |
| Promoter profile | DPR | Final for now |
| Vision & mission | Drafted for site | Placeholder — promoter to finalise |
| Stats (5,000 birds, 4 ponds, 16 bigha) | DPR | Final for now |
| Contact details | DPR | Confirm before go-live |
| Product descriptions | Written for site | Placeholder — refine at launch |
| Own feed brand + formula | Promoter | Named "AgriOS"; brand public; formula CONFIDENTIAL — never on site |
| Breeding stock, crops, cocopeat | Promoter | Added — breeding stock near-term, cocopeat Year 5 |
| Logo | Promoter | RECEIVED — full kit (primary, secondary, icon, B&W, transparent); placed across site |
| Tagline | Logo | "Smart Farming. Better Future." — used in footer |
| SEO / social tags | Built | Added — title, description, Open Graph, Twitter, geo, Google structured data |
| Certifications | Promoter | Placeholder badges (Pvt Ltd, GST, FSSAI, Udyam) — real numbers to follow |
| Location map | Built + promoter | Area map embedded now; exact GPS pin when coordinates supplied |
| Photographs | — | TO ADD (farm, promoter, products) |

---

## 7. Component library

Reusable building blocks. Building any new page means composing these, not inventing new patterns.

| Component | Description |
|---|---|
| Header / nav | Sticky, translucent, logo + links + green Contact button; hamburger on mobile |
| Eyebrow label | Small uppercase green label above headings |
| Stat card | Rounded card, big number + small label; green or clay variant |
| Enterprise card | White card, icon tile, title, description; hover lift |
| Loop step | Numbered step in the integrated-model row |
| Interactive AgriOS Cycle | Circular 5-node SVG diagram with a click-updated side panel (the signature element) |
| Impact strip | 4-up row of big farm numbers, hairline-divided |
| Founder note | Signed quote block with avatar |
| Feed-feature block | Two-column green feature for the AgriOS feed brand (formula kept confidential) |
| Product-category header | Eyebrow + heading + intro above each product grid |
| Expansion timeline | Horizontal 5-phase roadmap (Year 1 done → Year 10) |
| Gallery | Photo-frame grid (placeholder until real images added) |
| Certification badge | Icon card with title, detail and a status tag (Coming / In process) |
| Location map | Embedded Google Map iframe with address caption |
| FAQ accordion | Expandable question/answer rows (native details/summary) |
| Coloured band | Full-width section in paper-2, green, or green-tint |
| Product card | Image top, status pill (Coming soon / Available soon / Year 5), title, description |
| Feature list | Checklist with terracotta bullets |
| Contact form | Labelled fields with green focus ring |
| Info panel | Green-tint panel with phone/email/address + WhatsApp button |
| Footer | Dark footer: full logo + tagline, links, contact, admin link, copyright |
| Buttons | Primary (green), ghost (clay outline), dark (ink) |

---

## 8. Technical build notes

### 8.1 Current build

- **Format:** single self-contained HTML file (`index.html`) — HTML + CSS + a little JavaScript, no dependencies.
- **Pages:** all five in one file; JavaScript swaps the visible page (single-page style) with smooth fade.
- **Fonts:** Hanken Grotesk from Google Fonts.
- **Logo:** references 3 external PNGs (header wordmark, footer full logo, favicon). A fully self-contained variant embeds them as base64.
- **Responsive:** breakpoint at 860px; mobile hamburger menu; all grids collapse to one column.
- **No backend:** contact form is a front-end demo until connected to a form service.

### 8.2 To take it live

The single-file build is perfect for previewing and sharing. For a public launch:

| Step | What to do |
|---|---|
| Domain | Register a domain (e.g. agriosfarm.in or similar) |
| Hosting | Deploy the static files on Vercel or Netlify (free tier is enough) |
| Contact form | Connect to Formspree / Google Forms / a small backend so messages arrive by email |
| Social image | Add an og-image.jpg (referenced in the head) for link previews |
| SEO URLs | Replace the placeholder domain in canonical/og/JSON-LD tags with the real one |
| Real pages (optional) | If desired, rebuild in React + Vite for one codebase with the admin panel |
| Analytics | Add a privacy-friendly analytics tag |

> **If you later rebuild in React.** Because the Ascendo apps use React + Vite + TypeScript + Tailwind, the website can be rebuilt on the same stack for a fully consistent codebase. This Build Bible — tokens, structure, page specs, components — maps directly onto that build. The current HTML file is the reference implementation.

---

## 9. Go-live checklist

- [ ] Confirm contact details (phone, email, address) are correct
- [x] Logo — DONE (header wordmark, footer full logo, favicon)
- [ ] Add real farm photographs into the gallery frames
- [ ] Add real certification numbers (GST, FSSAI, Udyam) to the badge cards
- [ ] Send exact farm GPS coordinates to centre the map pin
- [ ] Refine product descriptions for launch
- [ ] Register a domain name
- [ ] Deploy to hosting (Vercel / Netlify)
- [ ] Connect the contact form to a real service
- [ ] Add an og-image.jpg for social-share previews
- [ ] Test the WhatsApp button on a phone
- [ ] Test on phone, tablet and desktop
- [ ] Proofread every page once more
- [ ] Confirm "Farm" vs "Farms" wording (logo says "Farms" plural; site says "Farm")

---

## 10. The AgriOS platform (admin panel & backend)

> **This is what makes AgriOS genuinely unique.** Every competitor has a static brochure website. AgriOS's website is the front door to a real management platform. The same login manages both the public site and the actual farm — something no integrated-farm competitor offers. This is the deep "develop ourselves" differentiator, not a borrowed feature.

### 10.1 Concept

One admin console, two jobs: run the farm, and run the website. The public site is the visible tip; behind it sits a backend where the promoter and team manage batches, stock, finance, enquiries and site content. Builds directly on the app-building practice already established with the Biochem, DyeHouse and KnitHouse tools.

### 10.2 Modules (built in the demo — `admin.html`)

| Module | What it does |
|---|---|
| Dashboard | Live metrics — active birds, monthly revenue, stock alerts, new enquiries — plus active batches and a "needs attention" list |
| Livestock & batches | Every unit (broiler, goat, duck, fish, bees) with stock, stage, health status and notes |
| Production & stock | Egg/compost/harvest output and a two-tier stock-alert system (order now / plan order) — same pattern as the Biochem ERP |
| Finance | Monthly revenue, expenses, net, loan-EMI tracking and a transaction log |
| Content & products | Edit the live website — hero, impact numbers, founder note, vision — and flip products from "Coming soon" to "Go live" with no developer |
| Enquiries & visits | Every message and farm-visit request from the public site, tagged (visit / product / partner) |
| Settings & roles | Team members with role-based access (Owner / Manager / Member) and the farm profile |

### 10.3 The website–backend link

- Enquiries and farm-visit requests submitted on the public Contact page land directly in the admin "Enquiries & visits" module.
- Products marked "Go live" in admin appear as real listings on the public Products page (replacing "Coming soon").
- Content edited in admin (hero, numbers, founder note) publishes to the live site.
- A discreet "Admin" link sits in the website footer; the admin's "View site" button links back — the two halves are one system.

### 10.4 Build path

| Stage | Approach |
|---|---|
| Now | Working demo panel (`admin.html`) with sample data — proves the concept and the design |
| Live build | Rebuild on React + Vite + TypeScript + Firebase (same stack as the Ascendo apps and the farm ERP), with real auth and a database |
| Data model | Reuse the Biochem ERP patterns — entities, two-tier stock alerts, role-based permissions, clickable data links |
| Hosting | Deploy alongside the public site; admin behind a login |

---

## 11. Future expansion

Expansion lives in two places: a public teaser on the site (to signal ambition to banks, investors and integrators) and this fuller internal plan.

### 11.1 Public teaser (on the site)

A 5-phase horizontal timeline on the What We Do page — Year 1 (done) through Year 10 — showing the farm is built to grow.

### 11.2 Full phase plan

| Phase | Adds |
|---|---|
| Year 1 — Foundation (now) | Contract poultry, goat, duck, fish, plantation, core infrastructure |
| Year 2 — Scale up | EC poultry house, pig breeding unit, automation, water storage, expanded stock |
| Year 3 — Self-reliance | Own feed mill, solar power, expanded beekeeping, staff facilities |
| Year 5 — Value addition | Cold storage, meat processing, cocopeat unit, branded farm products, market expansion |
| Year 10 — Beyond the farm | Farmer training centre, agri-tourism, full digital farm platform (the admin backend, matured) |

### 11.3 Website expansion (kept in step)

- Gallery of real farm photos (the one trust-builder still to add).
- Certifications & partners strip (FSSAI, integrator, scheme logos as they arrive).
- Products go from "Coming soon" to a real catalogue with enquiry/ordering.
- News / farm-updates section for milestones and seasons.

---

## 12. Competitor benchmarking & our edge

Three integrated-farming / agri websites were studied to learn what serious operators put on their sites — and, deliberately, to do something none of them do.

### 12.1 What they do well

| Site | What they get right |
|---|---|
| Pasupati Group | Live daily chicken-rate ticker; big trust-numbers (8,000 farms); farmer testimonials with names & villages; signed chairman's note |
| IB Group | Founder-led vision ("Father of Modern Poultry"); "we are first to…" claims; a named programme (Parivartan) aimed at young broiler entrepreneurs; investor / ESG / R&D sections |
| Growfast | Certifications strip; news/blog; video hero — but full of template dummy text (a warning: never ship placeholder-looking content) |

### 12.2 What we borrowed — rendered our way

- Impact numbers strip (from Pasupati/IB) — but calm and minimal, not loud counters.
- Signed founder's note (from Pasupati/IB) — a real human face for the bank.
- A named model: "The AgriOS Cycle" (inspired by IB's Parivartan) — makes the idea ownable.
- "Schedule a farm visit" CTA — the relationship-first approach from the Biochem site ("Schedule a Meeting"), fitting a farm's trust-based sales cycle.

### 12.3 What makes us unique

> **Substance of an integrator, styling of a design-led startup.** Every competitor looks like a busy corporate feed company. AgriOS takes the credibility features they rely on — numbers, founder note, named model — and renders them in the calm, warm, minimal Ascendo language none of them have. The signature piece is the interactive AgriOS Cycle: competitors list their divisions; we are the only one that lets a visitor *see* the integration by tapping through the loop.

---

## 13. Delivery roadmap & next actions

The build sequence for getting everything live, in the same phased spirit as the farm and the apps.

| Phase | Focus |
|---|---|
| Phase 1 (now) | Credibility site (5 pages) + interactive AgriOS Cycle + demo admin panel. **DONE.** |
| Phase 2 | Real photos, proper logo, live domain + hosting, working contact form |
| Phase 3 | Admin panel goes real — React + Firebase build with login and live data |
| Phase 4 | Products go live from admin; gallery, farm updates, partnerships |
| Phase 5 | Full platform — farm management + website + customer accounts in one system |

> **Next action.** Send the farm photos and confirmed details whenever ready — those unlock Phase 2. The website, interactive cycle, expansion timeline and demo admin panel are all built and waiting.
