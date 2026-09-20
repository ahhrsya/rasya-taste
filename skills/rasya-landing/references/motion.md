# Motion

Motion must explain the page. It should clarify sequence, material, state, or attention.

## Library Choice

```text
CSS transitions: buttons, hover, simple reveals
Motion: React UI state, viewport reveals, simple spring interactions
GSAP: scroll choreography, pinning, scrubbed timelines, split text, complex sequencing
Three.js: real 3D, product inspection, spatial scenes, shader-driven hero moments
Lenis: optional smooth scroll; only when paired carefully with GSAP
```

Do not mix animation libraries inside one component unless there is a clear ownership boundary.

## GSAP Rules

- Register plugins once.
- Use `gsap.context()` inside React components and clean up with `ctx.revert()`.
- Use `ScrollTrigger.refresh()` after images or async content change layout.
- Do not animate from the same value already set in CSS.
- Use timelines for above-the-fold intros; scroll triggers can fire before the viewer sees them.
- Disable or simplify scroll choreography under `prefers-reduced-motion`.

## Three.js Rules

Use Three.js only when the scene is the content:

- rotating product form
- spatial device/interface composition
- material study
- interactive hero background that reacts to pointer or scroll

Do not use Three.js for decorative blobs, simple gradients, or static objects that SVG/CSS can handle.

Before shipping a Three.js section:

```text
□ canvas is nonblank at desktop and mobile
□ camera framing works at 1440, 1024, 768, 390, 360 widths
□ scene has fallback or reduced-motion behavior
□ pixel ratio is capped for performance
□ assets load without console errors
□ user can still scroll and click page content
```

## Patterns

### Sticky Proof Stack

Use for feature education, buying arguments, and workflow steps. Pin the visual, scroll the proof.

### Product Reveal

Use clipping, masking, or scroll progress to reveal product details. Strong for physical goods and premium ecommerce.

### Interface Walkthrough

Use a single realistic UI mockup that changes state as sections scroll. Better than separate fake screenshots.

### Ambient Loop

Use WebM for material or atmosphere. Keep it muted, short, and nonblocking.

## Reduced Motion

Under reduced motion:

- remove smooth scroll
- remove scrubbed animation
- keep content visible immediately
- preserve essential state transitions with opacity or no animation
