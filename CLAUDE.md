# CLAUDE.md

## Project: Shoutouts Media

Central media hub website for the Texas Shoutouts Network — a parent brand site for Shoutouts Media that showcases the 20+ Texas Shoutouts local publications, accepts community nominations, and displays regional content spotlights.

## Tech Stack
- Language: TypeScript
- Framework: React 19 + Vite (same stack as control_board in the SEIS repo)
- Styling: Plain CSS with design tokens (no Tailwind — this project owns its visual identity)
- Package manager: npm
- Deployment: Vercel

## Commands
- Install: `npm install`
- Dev server: `npm run dev`
- Build: `npm run build`
- Lint: `npm run lint`
- Typecheck: `npx tsc --noEmit`

## Project Structure
- `src/` — all source code
- `src/components/` — reusable UI components (Nav, Hero, Ticker, RegionHub, Spotlight, SubmitForm, Footer)
- `src/data/` — static data (network publications list, regions, sample spotlight content)
- `src/styles/` — global CSS and design tokens
- `public/` — static assets
- `shouts-media.html` — standalone HTML prototype (reference only, not part of the build)

## Design Tokens (palette)
- Navy: `#0A2342` — primary brand color, hero/nav backgrounds
- Gold: `#F5A623` — accent, CTAs, star markers
- Gold Dark: `#D48B0E` — hover states, eyebrow labels
- Cream: `#FAF8F4` — light mode page background
- Charcoal: `#1A1208` — body text, dark backgrounds
- Both light and dark themes are supported via CSS custom properties

## Coding Style
- ES modules (import/export), not CommonJS
- async/await over .then() chains
- 2-space indentation
- Descriptive variable names
- "Shoutouts" is always one word, capital S — enforce in all copy and code identifiers

## Conventions
- Component files: PascalCase (`RegionHub.tsx`)
- CSS files: kebab-case matching the component (`region-hub.css`)
- Data files: kebab-case (`network-publications.ts`)
- Commit style: conventional commits (`feat:`, `fix:`, `chore:`, `docs:`)
- All copy must match the brand spec: "Shoutouts Media" (parent), "Texas Shoutouts" (network), "Texas Shoutouts Network" (collective)

## What NOT To Do
- Don't use "ShoutOut" (two words or camelCase) — always "Shoutouts" as one word
- Don't add a backend or database until the static prototype is approved
- Don't add dependencies without asking
- Don't hardcode publication names in multiple places — keep them in `src/data/network-publications.ts`
- Don't mix the Shoutouts Media parent brand with Texas Shoutouts network content — they are related but distinct
