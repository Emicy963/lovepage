# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- `docs/HOSTING_GUIDE.md`: step-by-step deploy guide (folder structure,
  GitHub commit, Vercel project + Root Directory, Cloudflare CNAME setup,
  troubleshooting) + client tracking table + renewal WhatsApp script
- `docs/SALES_PARTNERS.md`: commission structure (20% per sale), lead
  qualification rules, handoff workflow, and Phase 1 → Phase 2 progression
  model for sales partners
- `docs/PARTNER_GUIDE.md`: sales partner onboarding guide — welcome letter,
  product overview, golden rule (demo before price), conversation scripts,
  objection handling, commission recap
- `clients/bercia/`: birthday demo page for Bércia de Oliveira (3 real photos)
- `clients/samia/`: birthday demo page for Sâmia Miguel from Telvy Loth
  (3 real photos, personalised letter, no birthday date)
- Subdomain `nome.lovepage.art` as a Premium and Deluxe exclusive feature;
  Básico delivers a Vercel auto-generated URL
- Annual hosting model: 1 year included in all packages, renewal at 1.500 AOA/year

### Changed

- `docs/BUSINESS_MODEL.md`: full rewrite for evergreen model + annual renewal
  section with renewal revenue projections and client tracking reference
- `docs/MARKETING_COPY.md`: removed Valentine's-specific copy; new demo-first
  scripts; added FAQ answer for "Fica hospedado para sempre?"
- `docs/PACKAGES_GUIDE.md`: feature table with URL/domain and hosting/renewal
  rows; deploy steps rewritten for GitHub → Vercel; upsell scripts updated
- `index.html`: all 3 pricing cards now show "1 ano de hospedagem incluído";
  subdomain shown as excluded in Básico, included in Premium and Deluxe
- `.markdownlint.json`: disable MD013 (line length) and MD060 (table alignment)

## [1.1.1] - 2026-05-19

### Fixed

- Birthday template: duplicate `class` attribute on Memória 8 image — `aspect-wide` was silently ignored by browsers
- Premium template: missing `will-change: transform` on `.float` and `.photo-hover`
- Premium template: missing `type="button"` on lightbox close button
- Premium template: gallery images missing `loading="lazy"` (10 images affected)
- Premium template: footer showed hardcoded "Feliz Dia dos Namorados 2026"
- Deluxe template: missing `will-change` on `.float-luxury`, `.photo-luxury`, `.gold-shine`, `.reveal`
- Deluxe template: missing `type="button"` on lightbox close button
- Deluxe template: gallery images missing `loading="lazy"` (8 images affected)
- Deluxe template: footer showed hardcoded "Dia dos Namorados 2026"
- `vercel.json`: HTML cache-control header used `/(.*)\\.html` pattern which never matches clean URLs; replaced with explicit routes for `/` and `/templates/:path*`
- README: footer text referenced Valentine's Day 2026 — updated to year-round copy
- README: WhatsApp setup instruction referenced placeholder `244XXXXXXXXX` when number was already configured
- README: added birthday template variable table (`{{NOME_ANIVERSARIANTE}}`, `{{NOME_REMETENTE}}`, `{{IDADE}}`, `{{CARTA_PARABENS}}`)

## [1.1.0] - 2026-05-19

### Added

- New `birthday` template — confetti animation, photo grid (10 images), timeline section,
  birthday letter, Spotify embed, violet/gold dark palette
- Scroll reveal animations (IntersectionObserver) wired up in all 5 base templates
- `vercel.json` — security headers, cache rules, and `/docs/` access restriction
- `docs/PARTNERSHIP_PROPOSAL.md` — distributor and affiliate partner program outline

### Changed

- Landing page (`index.html`) pivoted from Valentine's Day only to year-round use:
  removed expired countdown, updated headline/meta/CTA copy to cover birthdays, anniversaries, etc.
- WhatsApp link updated to generic message (no Valentine's-specific text)
- FAQ answers reformatted with cleaner line breaks and more informative language
- Footer updated to `lovepage.art` branding; removed "Angola" from displayed name
- `docs/PACKAGES_GUIDE.md`: added "quick demo" pre-sale step (send partial preview before full payment)
- `docs/MARKETING_COPY.md`, `docs/BUSINESS_MODEL.md`, `README.md`: updated to reflect year-round positioning

### Fixed

- `modern-love` template: missing `type="button"` on lightbox close button
- All gallery images now include `loading="lazy"` to reduce initial page load time
- Added `will-change` hints on animated elements (`float`, `blob`, `photo-hover`, `reveal`) across all templates
- Spotify iframe in all templates now has explicit `border-radius: 12px` via `.spotify-wrap iframe`

## [1.0.0] - 2026-01-15

### Added

- Initial product launch targeted at Valentine's Day 2026 (Angola market)
- 5 HTML/TailwindCSS templates: `classic-romance`, `dark-elegance`, `modern-love`,
  `ocean-breeze`, `sunset-passion` — each with hero, message, gallery (8 photos),
  Spotify embed, love letter, footer, and photo lightbox
- `premium` template with customisable accent colours, timeline, and video section
- `deluxe` template with interactive quiz and QR code feature
- Landing page with pricing, package comparison (Básico 5k / Premium 12k / Deluxe 25k AOA),
  countdown to 14 Feb, FAQ, and WhatsApp CTA
- `docs/BUSINESS_MODEL.md` — pricing model, cost breakdown, projections
- `docs/PACKAGES_GUIDE.md` — step-by-step production guide per package (15–90 min)
- `docs/MARKETING_COPY.md` — WhatsApp scripts, Instagram captions, story templates
- `docs/BRANDING.md` — logo, colours, typography guidelines
- `docs/FLYERS_GUIDE.md` and PDF version
- `docs/NOTION_GUIDE.md` — client management template
- Marketing flyers (`assets/flyers/`) in PNG format, including main, premium, deluxe, and beta variants

[Unreleased]: https://github.com/Emicy963/lovepage/compare/v1.1.1...HEAD
[1.1.1]: https://github.com/Emicy963/lovepage/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/Emicy963/lovepage/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/Emicy963/lovepage/releases/tag/v1.0.0
