---
name: product-listing-image-set
description: >-
  Generate a complete ecommerce product listing image set from one product
  photo: 10 core marketplace shots (hero, angles, detail, scale, lifestyle,
  infographic, dimensions, packaging, trust) plus optional wall-placed and
  desk-placed lifestyle images only when the user asks. Use when the user
  wants product listing images, Amazon/Shopify gallery photos, ecommerce
  product photography sets, or AI product image kits from a reference photo.
license: MIT
compatibility: >-
  Requires an image generation tool available to the coding agent
  (Cursor GenerateImage or equivalent image MCP/API). Works best with a
  clear product reference photo attached or on disk.
metadata:
  author: Ishank Choudhary
  author_title: Software Architect & AI Engineer
  homepage: https://ishankdev.github.io/
  website: https://ishankdev.github.io/
  github: https://github.com/IshankDev
  contact: https://ishankdev.github.io/
  version: "1.0.0"
  category: ecommerce
  keywords: product-images, ecommerce, amazon-listing, lifestyle, marketplace
---

# Product Listing Image Set

Turn **one product photo** into a marketplace-ready listing gallery.

**Author:** Ishank Choudhary — Software Architect & AI Engineer  
**Website / contact:** [https://ishankdev.github.io/](https://ishankdev.github.io/)  
**GitHub:** [https://github.com/IshankDev](https://github.com/IshankDev)

## When to use

- User attaches a product photo and asks for listing / product images
- User wants Amazon, Shopify, Flipkart, or D2C gallery shots
- User asks for a product photo set, image kit, or “10 product images”
- User later asks for **wall placed** or **desk placed** variants

## Non-negotiable rules

1. **Core set = images 01–10.** Generate these by default.
2. **Wall-placed (11) and desk-placed (12) are optional.** Create them **only** if the user explicitly asks (e.g. “wall placed”, “on the wall”, “desk placed”, “on the desk”).
3. Keep the **product identity identical** to the reference: shape, colors, materials, logos, proportions. Do not invent features.
4. Image **01 (hero)** must be pure white background `#FFFFFF`, product ~85% of frame, **no text / props / watermarks**.
5. Prefer **1:1** aspect ratio unless the user or target marketplace requires another ratio.
6. Save outputs under `product-images/<product-slug>/` in the workspace (create folders as needed).
7. If real dimensions are unknown, use clear placeholders on image 08 and tell the user to confirm measurements.

## Inputs

| Input | Required | Notes |
|-------|----------|--------|
| Product photo | Yes | Attached image or absolute path |
| Product name / slug | No | Infer from filename or ask; used in output filenames |
| Dimensions | No | Height × width × depth for image 08 |
| Creative direction | No | Mood, room style, gifting, etc. |
| Wall / desk extras | No | Only if user requests |

Confirm the reference image exists on disk before generating. If the user attached an image in chat, copy/save it to a stable workspace path first and use that path as the reference.

## Workflow

Copy and track:

```text
Product Listing Progress:
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
2. Choose a short kebab-case `slug` (e.g. `olive-gopuram`).
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
- Say **photorealistic ecommerce product photography**
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
- Example invocations: [examples.md](examples.md)
