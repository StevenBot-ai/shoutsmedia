# PRD: Shoutouts Media — Texas Shoutouts Network Hub

## Problem
Shoutouts Media operates 20+ Texas local publications under the Texas Shoutouts brand but has no central hub that makes the network visible as a network. Visitors to any individual city site have no way to discover the broader ecosystem, and there is no single place to submit a community nomination or browse cross-Texas content. The brand looks like 20 disconnected sites rather than a coordinated media company.

## Goals
1. Make the Texas Shoutouts Network feel established and authoritative on day one by surfacing the existing 20+ publications as a collective footprint.
2. Provide a working nomination funnel ("Lone Star Legend") so community members can submit Shoutouts from a single entry point.
3. Enable regional content browsing so visitors can filter spotlights by Texas region without needing to know which city site to visit.
4. Create a reusable brand template that can be adapted for future Shoutouts Media networks (Florida, Sports, etc.) without a full rebuild.

## Target Users
- **Community members** in Texas who want to nominate a local business, coach, creator, or hero for a Shoutout — they know the story, not necessarily which city site to use.
- **Local business owners** who have heard about the network and want to understand its reach before engaging.
- **Media buyers / advertisers** who need to assess the network's total footprint at a glance.
- **Future network partners** in other states who are evaluating the Shoutouts Media model.

## Scope

### In Scope
- Hero section with brand headline and dual CTAs
- Scrolling ticker displaying all 20+ network publication names
- Regional filter hub (7 Texas regions) with content cards and placeholder cards for sparse regions
- Network Spotlight / Honorary Shoutouts editorial card section
- Lone Star Legend nomination form (name, city, story, submitter email)
- Sticky nav with "Give a Shoutout" persistent CTA
- Footer with "A Shoutouts Media Brand" attribution
- Light and dark theme support
- Mobile-first responsive layout

### Out of Scope (Phase 1)
- User accounts or authentication
- Backend form submission processing (form UI only for now — wire up in Phase 2)
- CMS or dynamic content management
- Individual city site deep-linking (placeholder cards link to "#" until URLs are confirmed)
- Other state networks (Florida Shoutouts, etc.) — this build establishes the template only
- Ad serving or monetization tooling

## Success Criteria
- The page loads and renders correctly on mobile (375px) and desktop (1280px+)
- All 20+ publications appear in the ticker
- Regional filter correctly shows/hides cards for each of the 7 regions
- Nomination form fields validate and display a confirmation state on submit
- Passes basic accessibility check (keyboard navigation, visible focus states, color contrast)

## Risks
- **Copy lock:** Brand copy (headline, taglines) may need Steven's approval before going live — prototype text from the design spec is placeholders until confirmed.
- **Publication list accuracy:** The 20 city names in the ticker need to be verified against the live Letterman/Titanium suite publication list — they may not all be "Shoutouts"-branded yet.
- **Form backend:** No submission handling exists yet — nominations go nowhere until Phase 2 wires up an email or Supabase backend.
- **Future-proofing tension:** Designing for Texas-first while keeping components generic enough for other states adds complexity; keep it simple and refactor later.

## Open Questions
- Which 20 publications are confirmed live as "Texas Shoutouts" branded? (vs. still "From Texas Media" branded)
- Should the ticker say "From Texas Media Network" or "Texas Shoutouts Network" — the spec uses both; which is the canonical label for the logo bar?
- Where do form submissions go in Phase 2 — email, Supabase, a CRM?
- Is there a real Texas Shoutouts logo/wordmark to use, or does the nav wordmark stay as styled text?
- Should the Shoutouts Media parent brand have its own separate page/URL eventually?
