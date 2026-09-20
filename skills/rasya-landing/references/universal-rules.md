# Universal Rules

These rules apply to every Rasya Landing style.

## Typography

- Pick type deliberately. Do not default to Inter, Roboto, Arial, or `system-ui` without a reason.
- Inter or system fonts are acceptable for dashboards, docs, public-sector work, and neutral SaaS when the choice is intentional.
- Use a display/body pairing or a single variable family with clear contrast in weight and size.
- Keep body measure between 55 and 75 characters.
- Do not scale font size directly with viewport width. Use stable clamps.
- Avoid negative letter spacing except for large display type where it is typographically needed.

## Color

- Define color as tokens or CSS custom properties.
- One color should dominate. Accent colors are accents, not confetti.
- Avoid the default AI tell: purple/blue gradient on white.
- Avoid one-note palettes where every color is a slight variation of the same hue.
- Premium commerce must not default to beige, brass, oxblood, espresso, and cream. Use that family only if the brand truly owns it.

## Layout

- Avoid a page made entirely of centered stacked sections.
- Avoid equal three-card feature rows as the default.
- Use at least one memorable composition move: asymmetry, overlap, broken grid, sticky proof, product strip, editorial scale, or guided scroll.
- Cards are for repeated items, framed tools, product modules, or testimonials. Do not wrap whole page sections in card shells.
- Mobile is not a compressed desktop. Reorder content deliberately.

## Copy

- Write concrete copy. Avoid "elevate", "unlock", "seamless", "next-gen", and "revolutionize" unless the brand voice truly uses them.
- Do not invent real customer logos, testimonials, performance metrics, awards, press mentions, or certifications.
- If mock content is used, label it as mock in the handoff.
- CTA labels should be action-specific: `Book a demo`, `Build my routine`, `Compare plans`, `Start free`, `See the workflow`.

## Interaction

- Motion must communicate hierarchy, storytelling, feedback, or product behavior.
- Do not animate everything. One choreographed sequence beats scattered effects.
- Honor `prefers-reduced-motion`.
- Tap targets must be at least 44 x 44 px on mobile.
- Hover states must have keyboard/focus equivalents where interactive.

## Media

- Prefer real product, interface, place, or generated art that reveals the offer.
- Do not use dark, vague, blurred stock imagery when the user needs to inspect the product.
- Convert raster assets to WebP.
- Convert ambient loops or generated clips to WebM when used on page.
- Use SVG/CSS for diagrams and abstract graphics when that is lighter and sharper than bitmap.

## Final Preflight

Before delivery:

```text
□ Design Read stated
□ Source commitment stated
□ Style selected and relevant reference read
□ Theme locked
□ Media path selected
□ Primary CTA visible above the fold
□ Realistic copy lengths used
□ No fake proof claims
□ No broken or empty media slots
□ Images are WebP or justified otherwise
□ Video loops are WebM or justified otherwise
□ Responsive checks completed
□ Reduced-motion behavior exists
□ Browser console checked when possible
```
