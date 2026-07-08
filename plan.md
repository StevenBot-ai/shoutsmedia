# Implementation Plan: Shoutouts Media — Phase 1 Static Site

## Overview
Convert the standalone `shouts-media.html` prototype into a proper Vite + React + TypeScript project. The HTML prototype is the approved visual reference — the goal is to componentize it cleanly, wire up the region filter with real data, and get it deployable to Vercel. No backend in Phase 1.

## Approach
Scaffold a standard Vite React TypeScript project, extract the prototype's CSS tokens into a global stylesheet, split the page into 6 components, and move all static data (publications list, regions, spotlight cards) into typed data files. The prototype's HTML is the source of truth for markup and styles — don't redesign, just componentize.

## Steps

### Phase 1 — Project Setup
1. Run `npm create vite@latest . -- --template react-ts` inside `shouts-media/`
2. Remove Vite boilerplate (App.css default styles, logo, counter)
3. Copy design token CSS into `src/styles/tokens.css` and import globally
4. Set up `src/data/network-publications.ts` with the typed publication list
5. Set up `src/data/regions.ts` with the 7 Texas regions and their sample cards

### Phase 2 — Component Build
6. `src/components/Nav.tsx` — sticky nav with logo and CTA button
7. `src/components/Hero.tsx` — full-width hero with headline, sub, and action buttons
8. `src/components/Ticker.tsx` — scrolling publications band (reads from network-publications.ts)
9. `src/components/RegionHub.tsx` — filter bar + card grid with show/hide logic
10. `src/components/Spotlight.tsx` — editorial card stack
11. `src/components/SubmitForm.tsx` — nomination form with client-side validation
12. `src/components/Footer.tsx` — footer with brand attribution
13. Wire all components into `src/App.tsx`

### Phase 3 — Polish & Deploy
14. Verify mobile layout at 375px, 768px, 1280px
15. Check keyboard navigation and focus states
16. Run `npm run build` — confirm clean output
17. Deploy to Vercel via GitHub push

## Files to Create/Modify
- `package.json` — Vite + React 19 + TypeScript deps
- `src/styles/tokens.css` — design tokens (colors, fonts, radii)
- `src/styles/global.css` — reset + base styles
- `src/data/network-publications.ts` — typed list of 20+ publications
- `src/data/regions.ts` — region definitions with card data
- `src/components/Nav.tsx` + `nav.css`
- `src/components/Hero.tsx` + `hero.css`
- `src/components/Ticker.tsx` + `ticker.css`
- `src/components/RegionHub.tsx` + `region-hub.css`
- `src/components/Spotlight.tsx` + `spotlight.css`
- `src/components/SubmitForm.tsx` + `submit-form.css`
- `src/components/Footer.tsx` + `footer.css`
- `src/App.tsx` — page assembly
- `src/main.tsx` — entry point
- `vite.config.ts` — standard config
- `tsconfig.json` — strict mode, ESNext, bundler resolution
- `vercel.json` — SPA routing config (if needed)

## Testing Strategy
- Manual browser test at 375px / 768px / 1280px
- Keyboard tab through all interactive elements
- Confirm region filter shows/hides cards correctly for all 7 regions
- Confirm form fields show validation errors on empty submit
- `npm run build` must complete with zero errors

## Risks & Edge Cases
- Ticker animation requires duplicated DOM nodes for seamless loop — keep this pattern from the prototype
- `text-wrap: balance` may not be supported in older browsers — acceptable for this audience
- Form submit with no backend: show a "Thanks, we'll be in touch!" confirmation state client-side only

## Rollback Plan
The `shouts-media.html` prototype is the source of truth and always deployable as a standalone file. If the React build breaks, the prototype can be served directly from Vercel as a static file with zero setup.

---

## Build History

| Phase | Date | What shipped |
|-------|------|-------------|
| Prototype | 2026-07-04 | Standalone `shouts-media.html` — full page design, all 5 sections, working region filter |
| Phase 1 | — | React/Vite componentization (not started) |
