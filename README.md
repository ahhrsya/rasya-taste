# Rasya Taste

Rasya Taste is a Codex skill suite for building distinctive, production-minded UI.

The first skill is `rasya-landing`: a landing-page system for websites, marketing
pages, product launches, SaaS pages, ecommerce campaigns, and brand pages. It
combines practical conversion structure with source-based visual taste, image and
video generation workflows, motion guidance, responsive verification, and asset
optimization.

## Install

```bash
npx skills add ahhrsya/rasya-taste
```

## Skills

```text
skills/
└── rasya-landing/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
        ├── assets.md
        ├── components.md
        ├── motion.md
        ├── source-commitment.md
        ├── universal-rules.md
        ├── verification.md
        └── styles/
            ├── conversion.md
            ├── editorial-brand.md
            ├── premium-commerce.md
            ├── service.md
            ├── technical-saas.md
            └── warm-saas.md
```

## Design Position

Rasya Taste is not a component template. It is a workflow:

1. Read the commercial job and audience.
2. Commit to a concrete visual source, not a vague mood.
3. Choose a style, theme, texture, asset plan, and interaction level.
4. Build with responsive layout, real copy, optimized media, and motivated motion.
5. Verify in browser across desktop and mobile before calling the work done.

## Image and Video

The default image path is OpenAI `gpt-image-2`. The skill also supports MCP image
and video tools such as OpenArt when connected. Generated or source media should be
converted to lightweight web formats before shipping:

- raster images: WebP
- looping video: WebM, with MP4 fallback when needed
- decorative diagrams: SVG or CSS when possible

## License

MIT
