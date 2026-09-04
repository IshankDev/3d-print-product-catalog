---
name: 3d-print-product-catalog
description: >-
  Generate a complete sales catalog for 3D printed products from one product
  photo: marketplace white hero, angles, detail, scale, brand marketing hero,
  features, dimensions, festive gift unboxing, desk lifestyle, and wall
  lifestyle — styled like premium heritage décor catalogs. Use when selling
  3D prints on Etsy, Amazon, Shopify, or D2C and the user needs a full product
  catalog, gift/desk/wall listing images, or ecommerce photo set from a single
  print photo.
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
  version: "1.2.0"
  category: ecommerce
  keywords: 3d-print, 3d-printing, product-catalog, etsy, gift, desk-decor, wall-decor, ecommerce, listing-images, heritage
  logo: assets/logo.svg
  repository: https://github.com/IshankDev/3d-print-product-catalog
  skill_path: .claude/skills/3d-print-product-catalog
---

# 3D Print Product Catalog

Turn **one photo of a 3D printed product** into a complete **sales-ready product catalog** — including premium **hero**, **gift**, **desk**, and **wall** creatives.

**Author:** Ishank Choudhary — Software Architect & AI Engineer  
**Website / contact:** [https://ishankdev.github.io/](https://ishankdev.github.io/)  
**GitHub:** [https://github.com/IshankDev/3d-print-product-catalog](https://github.com/IshankDev/3d-print-product-catalog)

## When to use

- User has a 3D printed product and needs a full catalog for sale
- User wants Etsy / Amazon / Shopify / D2C images including gift, desk, and wall shots
- User asks for a product catalog, listing gallery, or sales creatives from a print photo
- User wants WORK18-style premium heritage décor catalog layouts

## Non-negotiable rules

1. **Core set = images 01–11.** Generate these by default (includes gift, desk, and wall).
2. **Size comparison (12)** only if the user asks or sells multiple sizes.
3. Keep the **product identity identical** to the user’s product photo: shape, colors, materials, frame, layer/finish cues. Do **not** swap in the sample product from style refs.
4. Image **01 (marketplace hero)** must be pure white `#FFFFFF`, product ~85% of frame, **no text / props / watermarks**.
5. For **06 hero-brand, 09 gift, 10 desk, 11 wall**: attach **both** the product photo and the matching `assets/style-refs/*.jpg` as references. Match catalog *mood/layout*, not the sample SKU.
6. Prefer **1:1** for marketplace slots; brand/gift/desk/wall may use **4:3** or **3:4** if that better matches catalog creatives.
7. Save under `product-images/<product-slug>/`.
8. If dimensions are unknown, use clear placeholders on 08 / 10 / 11 and ask the user to confirm.

## Style references (bundled)

| Shot | Style file |
|------|------------|
| Brand hero (06) | `assets/style-refs/catalog-hero-style.jpg` |
| Gift (09) | `assets/style-refs/gift-style.jpg` |
| Desk (10) | `assets/style-refs/desk-hero-style.jpg` |
| Wall (11) | `assets/style-refs/wall-hero-style.jpg` |

Resolve these to absolute paths from the skill directory when calling the image tool.

## Inputs

| Input | Required | Notes |
|-------|----------|--------|
| Product photo | Yes | Finished 3D print (attached or absolute path) |
| Product name | No | Used on brand/gift/desk/wall titles |
| Brand name | No | Optional overlay; omit if unknown |
| Dimensions | No | For 08, 10, 11 callouts |
| Creative direction | No | Festival mood, office desk, pooja wall, etc. |

## Workflow

```text
3D Print Catalog Progress:
- [ ] 0. Resolve product photo + slug + style-ref absolute paths
- [ ] 1. hero-white (marketplace)
- [ ] 2. three-quarter
- [ ] 3. side-profile
- [ ] 4. detail-macro
- [ ] 5. scale-hand
- [ ] 6. hero-brand (+ catalog-hero-style.jpg)
- [ ] 7. feature-infographic
- [ ] 8. dimensions
- [ ] 9. gift (+ gift-style.jpg)
- [ ] 10. desk (+ desk-hero-style.jpg)
- [ ] 11. wall (+ wall-hero-style.jpg)
- [ ] 12. size-comparison (ONLY if asked / multi-size)
- [ ] Save to product-images/<slug>/ + summary table
```

### Step 0 — Prepare

1. Absolute path to the product photo.
2. Absolute paths to the four style refs above.
3. Slug e.g. `sacred-gopuram-shadow-frame`.
4. Collect `PRODUCT_NAME`, `BRAND`, `DIMENSIONS` if available.

### Step 1 — Generate 01–05 (studio facts)

Product photo only. Use prompts in [references/prompt-templates.md](references/prompt-templates.md).

### Step 2 — Generate 06, 09, 10, 11 (catalog creatives)

For each shot, pass **product photo + matching style ref** in `reference_image_paths` (product first). Use the WORK18-inspired prompts in the prompt templates.

**Cursor:** `GenerateImage` with both paths, `aspect_ratio` `1:1` or `4:3`.

### Step 3 — Generate 07–08 (+ optional 12)

Infographic and dimensions; size comparison only when needed.

### Step 4 — Deliver

1. Files in `product-images/<slug>/`.
2. Compact table: `# | file | role`.
3. Note placeholder dimensions if any.

## Prompt quality bar

- Product identity from **user photo** only
- Style/mood from **style refs** for 06/09/10/11
- Warm premium lighting; product sharpest subject
- No stolen logos from style refs unless user owns that brand
- Photorealistic ecommerce / catalog photography

## Marketplace compliance (image 01)

- Pure white RGB 255,255,255
- Single product, ~85% frame
- No text, logos, watermarks, props

## Additional resources

- [references/shot-list.md](references/shot-list.md)
- [references/prompt-templates.md](references/prompt-templates.md)
- [references/examples.md](references/examples.md)
