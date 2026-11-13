# AEOUM site design record

Check this file before every change. Source of truth is landing-page-design SKILL.md. Where the user's words conflict with the skill, the user wins.

## Approved

**Fonts.** Geist only, weights 400, 500, 600. No italics, no 700 or heavier, no second typeface. Sizes sit on Tailwind steps with named styles: Heading 1 (60/60 desktop, 48/48 tablet, 36/40 phone), Heading 3 (36/40), Title 1 (20/28, 500), Body 3 (16/24, 400), Caption 3 (12/16, 600), Button-md (16/24, 600), Button-sm (14/20, 600). Headings use text-wrap balance, body uses pretty.

**Colors.** Page #181818, surface #1F1F1F, raised and hover #272727, borders #313131 (all from the skill's dark list). Text #FFFFFF, muted #9B9B9B. Accent orange #F26A1B. Button text #131209. Logo navy #0B1F3A only behind the logo mark. The only gradient is the hero heading text, #FFFFFF to #9B9B9B.

**Spacing.** Only 2, 4, 8, 12, 16, 24, 32, 40, 48, 64, 80, 96 px.

**Radius.** Cards 16, inputs 8, floating chips 12, buttons and nav pill fully round. Nested radius follows outer minus gap, and only when the result is above 2.

**Buttons.** Main button: Button-md, padding 8px by 12px, orange fill, #131209 text, fully round. Header button: Button-sm, same padding. Hover lifts 1px with a lighter orange, active scales to 0.98, focus shows a 2px white outline. One primary action everywhere: "Get a free estimate".

**Motion.** Curve cubic-bezier(0.22,1,0.36,1). Color changes 300ms, position changes 500ms. Scroll reveals rise 32px and fade over 700ms, once. Only transform and opacity. Reduced motion falls back to a plain fade.

**Content.** Sentence case, no hyphens in copy, no orphaned words. Contact is `admin@aeoum.one` only. Consulting and design each cover planning, designing, construction and budget. Free estimate is mentioned, with no response time.

## Rejected

- Stock photos shown as AEOUM's work, invented testimonials, statistics, prices, guarantees, or client logos.
- Phone numbers, license or insurance claims, response time promises.
- Decorative or background gradients.
- Generic repeated card grids for every section.
- The word "renovation" as positioning.
- The full "AEOUM" wordmark inside the logo. Approved logo is the A-frame symbol only.
- Inter, Roboto, Arial, Open Sans, Helvetica. Italics. 900 weight. Material icons.

## Open items to settle in later sections

- Final CTA and the 404 page buttons still use the older large size and need Button-md.
- Hover orange #FF7F33 and error red #FF6B6B are not skill values. Keep until the user objects.
- Form has no state or city field. Proposed, not approved.
- `og:image` needs a real image. Project photos need real files from the user.

## Change log

- Hero (approved): wider text column, buttons moved to the skill's sizes, redrawn illustration with chips that no longer cover it. Button stays at 40px tall to follow the skill's padding.
- Services: replaced four identical bordered cards with a split layout, heading on the left and three plain rows on the right (Construction, Consulting, Design). Rows have no surface or border. Icons are Phosphor regular, 24px, orange (hard-hat, clipboard-text, pencil-ruler). Removed repeated copy ("estimate at no charge", project type list, "cover everything").
- Fixed a bug: only cards lift on hover now, not section heads, the FAQ list or the form.
- Tagline reveal: now a full width flat band in #1F1F1F with centered text at Heading 2 (48/48) on every screen size, capped at 680px. Section headings stay at 36px, so the tagline is always the larger type. Words still light one at a time, and reduced motion shows all white. The muted start state is a deliberate animation state, not the resting design.

- Hero house (requested by user): the drawing now builds itself and then remodels, in a 16 second loop. Build: ground line, walls rise, roof lowers into place, door, window, dimension lines (0 to 6.4s). Hold. Remodel: a new wing slides in, the window is replaced by a larger one, the width dimension extends (8.5 to 11.4s). Hold, fade out, restart. Only transform and opacity are animated, using the base curve. Reduced motion shows the finished remodeled house with no movement. The three chips keep floating and never touch the drawing at any point in the loop.

- Hero house, second version (requested by user: faster, longer hold, 3D): now a real 3D model drawn on a canvas, with no library. Flat shaded faces from the approved dark list, white edges, orange dimension lines. The camera swings slowly from left front to right front and back over each loop. Loop is 12 seconds (was 16). Build 0 to 3.0s, hold 3.4s, remodel 3.0 to 8.4s window with the new wing sliding in with orange edges that settle to white, hold 3.0s, fade out. It uses the same base curve as the rest of the site. It pauses when scrolled off screen or the tab is hidden. Reduced motion shows one still frame of the finished house. The old flat SVG remains only as a fallback if canvas is unavailable. A test hook `window.__houseT` can set the time for checks.

- Hero house, third version (requested by user: modern architecture, kitchen remodel, going inside, faster). The simple pitched house is replaced by a modern two volume house: a glass fronted ground floor with a cladding panel and door, an upper volume that cantilevers out over a slim column, and thin flat roof slabs. Loop is 11 seconds (was 12) and the events run 15 percent faster. Build takes about 1.7s. Camera then moves in and the front, upper volume and roofs fade away as a cutaway so the kitchen fills the frame. Old kitchen (gray) collapses, then new fridge, base run, uppers, backsplash, island, countertops, stools and two pendant lamps appear with orange edges that settle to white. Camera pulls back, the house closes up, hold about 3.3s, fade, repeat. Floating chips fade out during the close up so they never cover the kitchen, and a pixel test confirms they never touch the house at the other times. Same canvas, base curve, flat colors from the approved list (plus the muted gray #9B9B9B for countertop tops), pauses off screen, and reduced motion shows one still frame of the finished house.

## Layout rule for later sections

Do not reuse the bordered card grid for new sections. How it works and the FAQ are the next ones to differ from it.
