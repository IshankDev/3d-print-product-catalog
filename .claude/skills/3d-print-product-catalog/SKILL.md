---
name: 3d-print-product-catalog
description: >-
  Generate a complete sales catalog for 3D printed products from one product
  photo: 10 marketplace-ready listing images (hero, angles, detail, scale,
  lifestyle, features, dimensions, packaging, trust) plus optional wall-placed
  and desk-placed shots when asked. Use when selling 3D prints on Etsy, Amazon,
  Shopify, or D2C and the user needs a full product catalog, listing gallery,
  or ecommerce photo set from a single print photo.
license: MIT
compatibility: >-
  Requires an image generation tool available to the coding agent
  (Cursor GenerateImage or equivalent image MCP/API). Works best with a
  clear photo of the finished 3D printed product.
metadata:
  author: Ishank Choudhary
  author_title: Software Architect & AI Engineer
  homepage: https://ishankdev.github.io/
  website: https://ishankdev.github.io/
  github: https://github.com/IshankDev/3d-print-product-catalog
  contact: https://ishankdev.github.io/
  version: "1.1.0"
  category: ecommerce
  keywords: 3d-print, 3d-printing, product-catalog, etsy, ecommerce, listing-images, marketplace, desk-decor, wall-decor
  logo: assets/logo.svg
  repository: https://github.com/IshankDev/3d-print-product-catalog
  skill_path: .claude/skills/3d-print-product-catalog
---

# 3D Print Product Catalog

Turn **one photo of a 3D printed product** into a complete **sales-ready product catalog** for marketplaces.

**Author:** Ishank Choudhary — Software Architect & AI Engineer  
**Website / contact:** [https://ishankdev.github.io/](https://ishankdev.github.io/)  
**GitHub:** [https://github.com/IshankDev/3d-print-product-catalog](https://github.com/IshankDev/3d-print-product-catalog)

## When to use

- User has a 3D printed product and needs a full catalog for sale
- User wants Etsy, Amazon, Shopify, or D2C listing images for a print
- User asks for a product catalog, listing gallery, or “10 product images” from a print photo
- User later asks for **wall placed** or **desk placed** variants (common for printed decor)

## Non-negotiable rules

1. **Core set = images 01–10.** Generate these by default.
2. **Wall-placed (11) and desk-placed (12) are optional.** Create them **only** if the user explicitly asks (e.g. “wall placed”, “on the wall”, “desk placed”, “on the desk”).
3. Keep the **product identity identical** to the reference: shape, colors, materials, layer/finish cues, logos, proportions. Do not invent features.
4. Image **01 (hero)** must be pure white background `#FFFFFF`, product ~85% of frame, **no text / props / watermarks**.
5. Prefer **1:1** aspect ratio unless the user or target marketplace requires another ratio.
6. Save outputs under `product-images/<product-slug>/` in the workspace (create folders as needed).
7. If real dimensions are unknown, use clear placeholders on image 08 and tell the user to confirm print measurements.

## Inputs

| Input | Required | Notes |
|-------|----------|--------|
| Product photo | Yes | Photo of the finished 3D print (attached or absolute path) |
| Product name / slug | No | Infer from filename or ask; used in output filenames |
| Dimensions | No | Height × width × depth for image 08 (print size) |
| Creative direction | No | Mood, room style, gifting, material look, etc. |
| Wall / desk extras | No | Only if user requests |

Confirm the reference image exists on disk before generating. If the user attached an image in chat, copy/save it to a stable workspace path first and use that path as the reference.

## Workflow

Copy and track:

```text
3D Print Catalog Progress:
- [ ] 0. Resolve reference image path + product slug
- [ ] 1. Hero white
- [ ] 2. Three-quarter
- [ ] 3. Side profile
- [ ] 4. Detail macro
- [ ] 5. Scale / hand
- [ ] 6. Lifestyle
- [ ] 7. Feature infographic
- [ ] 8. Dimensions
- [ ] 9. Packaging
- [ ] 10. Lifestyle / trust
- [ ] 11. Wall-placed (ONLY if user asked)
- [ ] 12. Desk-placed (ONLY if user asked)
- [ ] Copy/save all files to product-images/<slug>/
- [ ] Summarize paths + note placeholder dimensions if any
```

### Step 0 — Prepare

1. Resolve absolute path to the reference product photo.
2. Choose a short kebab-case `slug` (e.g. `olive-gopuram-print`).
3. Output dir: `product-images/<slug>/`
4. Filenames: `<slug>-01-hero-white.png` … `<slug>-10-…png` (+ optional 11/12)

### Step 1 — Generate core images 01–10

Use the agent’s image generation tool with the **reference image** attached every time.

**Cursor:** use `GenerateImage` (`CallDynamicTool` namespace `cursor`) with:
- `reference_image_paths: [<absolute-path-to-product-photo>]`
- `aspect_ratio: "1:1"` (default)
- `filename`: the target filename
- `description`: shot-specific prompt from [references/prompt-templates.md](references/prompt-templates.md)

**Other agents:** use whatever image tool is available (MCP image API, local script, etc.) with the same reference + prompt pattern. Do not skip the reference image.

Generate in parallel batches when the tool allows (e.g. 01–06, then 07–10).

Shot definitions: [references/shot-list.md](references/shot-list.md)

### Step 2 — Optional wall / desk

Only if the user asked:

- **11 wall-placed:** product mounted or hanging on a clean interior wall as wall decor
- **12 desk-placed:** product sitting on a modern desk / work surface as desk decor

If the user did **not** ask, skip 11 and 12 entirely — do not offer them unless useful as a one-line optional next step after delivery.

### Step 3 — Deliver

1. Ensure all generated files are in `product-images/<slug>/`.
2. Reply with a compact table: `# | file | role`.
3. Call out any placeholder dimensions on image 08.
4. Do not dump huge prompt text in the final reply.

## Prompt quality bar

Every generation prompt must:

- Say **“exact same product as the reference”** (colors, geometry, accents)
- State the **shot purpose** (hero / macro / lifestyle / etc.)
- State **background / scene** constraints
- Say **photorealistic ecommerce product photography of a 3D printed product**
- Forbid unwanted text except on intentional infographic/dimension shots (07, 08)

## Marketplace compliance (hero)

For image 01:

- Pure white background (RGB 255,255,255)
- Single product, centered, fills ~85% of frame
- No text, logos, watermarks, props, or lifestyle elements
- Sharp focus, soft even studio light, subtle base shadow OK

Supporting images (02–12) may use lifestyle scenes, props, and text overlays.

## Additional resources

- Shot roles and buyer questions: [references/shot-list.md](references/shot-list.md)
- Ready-to-use prompt templates: [references/prompt-templates.md](references/prompt-templates.md)
- Example invocations: [references/examples.md](references/examples.md)
