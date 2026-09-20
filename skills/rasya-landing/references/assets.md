# Assets

Asset work is part of the design, not a cleanup task.

## Default Media Path

Use OpenAI `gpt-image-2` as the default still-image generator when generation is needed.

Use an MCP image or video provider such as OpenArt when connected and when the task benefits from:

- a model or style not available through the default image path
- generated video loops
- batch variation workflows
- image-to-video or reference-image workflows

Never hardcode, echo, or commit API keys. Use environment variables or connected MCP tools.

## When To Generate

Generate when the visual asset carries the concept:

- hero product photography
- campaign scene
- editorial brand image
- background environment for glass or spatial UI
- texture plate
- video loop that communicates material, motion, or atmosphere

Do not generate when CSS, SVG, or HTML is stronger:

- diagrams
- feature icons
- pricing tables
- interface mockups
- simple abstract geometry
- charts or product workflow previews

## Still Image Prompt Shape

```text
<medium/source>: <subject and action>.
<composition and camera>.
<palette and material>.
<lighting and texture>.
No text, no letters, no words, no watermark, no signature.
```

Generate at the final display ratio. Avoid square-and-crop when the page needs a wide hero or tall mobile crop.

## Video Prompt Shape

```text
<short looping scene>, <camera movement>, <material or product behavior>,
<lighting>, <palette>, seamless 4-6 second loop, no text, no logo, no watermark.
```

Video should earn its weight. Use it for:

- product material motion
- atmospheric brand loops
- generative creative previews
- 3D/physical inspection moments

Do not use video for a moving gradient or decorative noise that CSS can do.

## Conversion

Use project tooling if available. Otherwise use `ffmpeg` or `sharp`/`squoosh` equivalents.

Raster to WebP:

```bash
ffmpeg -i input.png -vf "scale='min(1920,iw)':-2" -c:v libwebp -quality 82 output.webp
```

JPEG/PNG batch to WebP:

```bash
find public -type f \( -iname '*.png' -o -iname '*.jpg' -o -iname '*.jpeg' \) -print
```

Convert only assets introduced for the task unless the user asks for a full media audit.

Video to WebM:

```bash
ffmpeg -i input.mp4 -c:v libvpx-vp9 -b:v 0 -crf 34 -an -row-mt 1 output.webm
```

Small MP4 fallback:

```bash
ffmpeg -i input.mp4 -c:v libx264 -crf 24 -preset slow -an -movflags +faststart output.mp4
```

## Placement

- Always set width and height or use aspect-ratio boxes to prevent layout shift.
- Use `object-fit` intentionally.
- Provide mobile crops when the subject would become unreadable.
- Use `loading="lazy"` below the fold.
- Keep the hero asset eager only when it is truly part of LCP.
