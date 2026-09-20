---
name: rasya-landing
description: Build distinctive landing pages, marketing sites, product pages, ecommerce campaigns, SaaS pages, and brand homepages. Use when the user asks for a landing page, website hero, marketing page, product launch page, conversion page, or wants a UI that should not look generic. The workflow combines source-based art direction, conversion structure, image/video generation, motion, responsive layout, media optimization, and browser verification.
metadata:
  short-description: Distinctive landing pages with source-based taste
---

# Rasya Landing

Build landing pages that feel intentionally art-directed and commercially useful.

The core idea:

**Generic UI comes from committing to a mood. Strong UI comes from committing to a source and a job.**

Before implementation, the page must have both:

- a commercial job: what action the page should make easier
- a visual source: a concrete artifact, publication, product, place, era, or interface the design can borrow logic from

Do not treat this as a fixed template. Treat it as a decision system.

## Flow

### Step 1: Read The Job

Infer the page kind, audience, offer, desired action, trust burden, and content depth.

State a concise design read before implementation:

```text
Design Read: <page kind> for <audience>, optimizing for <primary action>, leaning <style>.
```

Ask at most one clarifying question if the audience, offer, or primary action is unclear enough to affect the design. Otherwise proceed.

### Step 2: Lock Theme And Media Path

Theme is independent of style. If the user has not specified it, ask:

```text
Should this be light, dark, or mixed?
```

Image and video generation is first-class in this skill. If the user has not specified an asset path, default to:

```text
Media Path: OpenAI gpt-image-2 for still images; code/SVG/CSS for diagrams; OpenArt MCP when connected for image or video generation that the project specifically needs.
```

Never write, echo, or commit API keys. Read keys from the environment or use connected MCP tools.

Read [references/assets.md](references/assets.md) before generating, converting, or placing media.

### Step 3: Commit To A Source

Read [references/source-commitment.md](references/source-commitment.md).

Before coding, state:

```text
Reference Source: <specific noun, artifact, place, era, publication, product, or interface>
Palette Rule: <4-6 colors or token rule>
Type System: <display/body/mono families or local equivalents>
Layout Bet: <the main composition choice>
Motion Bet: <the one interaction or animation idea that matters>
```

If the reference source is only an adjective, keep pushing. "Premium", "modern", "clean", and "futuristic" are not sources.

### Step 4: Pick A Style

Pick one style, or honor the user's named style.

| Style | Best For |
| --- | --- |
| `conversion` | ecommerce SaaS, Shopify apps, growth tools, lead-gen pages |
| `premium-commerce` | DTC, beauty, fashion, food, wellness, home, object-led brands |
| `technical-saas` | developer tools, AI SaaS, workflow products, B2B platforms |
| `warm-saas` | productivity, consumer SaaS, collaborative tools, playful B2B |
| `service` | healthcare, professional services, local services, trust-heavy businesses |
| `editorial-brand` | portfolios, agencies, personal brands, launches with a strong point of view |

Read in this order:

1. [references/universal-rules.md](references/universal-rules.md)
2. `references/styles/<style>.md`
3. [references/components.md](references/components.md)
4. [references/assets.md](references/assets.md)
5. [references/motion.md](references/motion.md) when motion, scroll effects, Three.js, or GSAP are involved
6. [references/verification.md](references/verification.md) before delivery

### Step 5: Build

Default stack when the repository allows it:

```text
Framework: React / Next.js
Styling: Tailwind or the existing project system
Animation: CSS and Motion for UI state; GSAP for scroll choreography; Three.js for real 3D scenes only
Media: WebP for raster, WebM for loops, SVG/CSS for diagrams
Icons: existing project icon set; otherwise lucide or phosphor, consistently
```

Use existing project conventions first. Do not introduce GSAP, Three.js, or a video dependency unless the interaction earns it.

### Step 6: Verify

Run the browser loop described in [references/verification.md](references/verification.md).

Minimum viewports:

```text
1440 x 900
1024 x 768
768 x 1024
390 x 844
360 x 740
```

Check console errors, asset failures, horizontal overflow, font loading, responsive text fit, animation reduced-motion behavior, and media weight.

If you cannot run a browser, say which checks could not be performed.

## Non-Negotiables

- Use real copy lengths. Placeholder copy creates fake layouts.
- Do not fake testimonials, customer logos, metrics, awards, or press quotes.
- One primary CTA per page section; repeated CTAs may exist, but the hierarchy must be clear.
- No generic purple-blue gradient on white unless the brand explicitly calls for it.
- No empty image slots. Use generated assets, source assets, SVG/CSS diagrams, or styled placeholders.
- Generated raster media must be converted to WebP before shipping when used in the repo.
- Generated video loops must be converted to WebM, with MP4 fallback only when needed.
- Honor `prefers-reduced-motion`.
- Do not ship centered stacked sections from top to bottom. Use a real composition system.
- Verify mobile layout. A landing page that only works at desktop width is unfinished.
