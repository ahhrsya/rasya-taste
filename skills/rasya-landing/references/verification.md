# Verification

A successful build is not proof that a landing page works.

## Browser Loop

When browser tooling is available:

1. Run the app.
2. Open the page.
3. Wait for intro animation and media.
4. Capture desktop and mobile screenshots.
5. Check console errors, page errors, network failures, and HTTP 400+.
6. Inspect layout at the required breakpoints.
7. Fix and repeat.

Minimum breakpoints:

```text
1440 x 900
1024 x 768
768 x 1024
390 x 844
360 x 740
```

## Visual Checks

```text
□ Above-the-fold content is not clipped
□ CTA is visible and readable
□ No horizontal overflow
□ Long words and button labels fit
□ Text does not overlap media
□ Media has correct aspect ratio
□ Decorative overlays do not block clicks
□ Fonts resolve to intended families
□ Reduced-motion mode keeps content visible
□ Mobile order tells the same story as desktop
```

## Asset Checks

```text
□ No broken images
□ Images have nonzero natural width
□ New raster assets are WebP unless justified
□ New videos are WebM unless justified
□ LCP asset is not unnecessarily huge
□ Below-fold assets lazy load
```

## Animation Checks

```text
□ No blank hero caused by from-state/to-state mismatch
□ GSAP contexts clean up
□ ScrollTrigger does not fire hidden intro content too early
□ Three.js canvas is nonblank
□ Reduced motion disables heavy movement
```

If browser verification cannot be run, say so directly and complete the static checklist.
