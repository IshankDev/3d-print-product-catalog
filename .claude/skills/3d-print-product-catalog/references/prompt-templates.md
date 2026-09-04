# Prompt templates

Replace placeholders:
- `{{PRODUCT}}` — concrete description of the 3D printed item (shape, color, frame if any)
- `{{PRODUCT_NAME}}` — listing title (e.g. Sacred Gopuram Shadow Frame)
- `{{BRAND}}` — brand name if provided, else omit brand text
- `{{DIMENSIONS}}` — e.g. 6" H × 4.8" W (15 × 12 cm)

**Always attach:**
1. The user’s product photo (identity lock)
2. The matching style reference from `assets/style-refs/` for hero / gift / desk / wall shots

Keep the **exact same product** as the user’s reference. Match the **layout mood, lighting, and premium catalog composition** of the style ref — do not copy unrelated products or brand marks from the style ref unless the user supplied that brand.

---

## 01 — Marketplace white hero

```text
Amazon-style main product photo of the exact same {{PRODUCT}} from the product reference. Pure white RGB 255,255,255 background only. Straight-on front view, eye-level, product centered and filling about 85% of the frame. Soft even studio lighting, subtle soft shadow under the base. Photorealistic ecommerce photography of a 3D printed product. No text, no props, no logos, no watermark.
```

## 02 — Three-quarter / angled depth

```text
Product photo of the exact same {{PRODUCT}} from the product reference at a 45-degree three-quarter angle to reveal shadow-box depth and 3D print detail. Pure white or soft dark studio background. Soft directional lighting that shows layer texture and frame depth. Clean ecommerce catalog style, no text.
```

## 03 — Side profile

```text
Product photo of the exact same {{PRODUCT}} from the product reference in clear side profile so frame depth and silhouette are obvious. Pure white background, soft studio lighting, centered. Keep materials and colors faithful. No text, no props.
```

## 04 — Detail macro

```text
Macro close-up of the exact same {{PRODUCT}} from the product reference focusing on 3D print ridges, architectural detail, and frame edge finish. Soft studio lighting, shallow depth of field, cream or dark blurred background. Show craftsmanship. No text overlays.
```

## 05 — Scale hand

```text
Scale reference: a person's hand presenting the exact same {{PRODUCT}} from the product reference so buyers can judge real size. Clean light cream or white background, soft natural studio light. Product must match the product reference exactly. No text.
```

## 06 — Brand marketing hero (WORK18 catalog style)

Style ref: `assets/style-refs/catalog-hero-style.jpg` (+ product photo)

```text
Premium brand marketing hero for a 3D printed product catalog, matching the composition mood of the style reference. Exact same {{PRODUCT}} from the product reference as the clear centerpiece — warm directional lighting, shallow depth of field lifestyle background (wood surface, soft plants, heritage books or tasteful decor blurred behind). Elegant serif title "{{PRODUCT_NAME}}" and short tagline about heritage for modern spaces. 3–4 circular gold/line feature icons with short labels (e.g. Iconic Design, Premium 3D Print Quality, Home & Office, Meaningful Gift). Optional thin footer bar with "3D PRINTED", "DESIGNED WITH PASSION", "MADE IN INDIA" style badges if space allows. Photorealistic, high-end catalog layout. Do not invent a different product. Brand text: {{BRAND}}.
```

## 07 — Feature infographic

```text
Ecommerce feature callout featuring the exact same {{PRODUCT}} from the product reference on a soft cream or warm beige background. Clean modern layout with 3–5 short benefit callouts and thin leader lines or circular icons. Elegant serif + sans typography. Product large and central. Marketplace-ready secondary listing image.
```

## 08 — Dimensions

```text
Product dimensions graphic of the exact same {{PRODUCT}} from the product reference. Front view with clean measurement arrows and labels for {{DIMENSIONS}}. Soft studio or light wall background, readable typography, gold or white thin dimension lines. Product must match the product reference. Ecommerce secondary image.
```

## 09 — Gift catalog image (festive unboxing)

Style ref: `assets/style-refs/gift-style.jpg` (+ product photo)

```text
Premium festive gift catalog photo matching the mood of the style reference. Exact same {{PRODUCT}} from the product reference presented as a ready-to-gift piece: open kraft gift box with crinkle paper, satin gold ribbon, optional closed matching gift box, warm wooden surface, soft bokeh fairy lights, subtle traditional accents (diya, flower petals) without hiding the product. Include tasteful headline space for a gift message like "A Sacred Gift for Your Loved Ones" and 3–4 short occasion callouts (festivals, housewarmings, meaningful gift, cultural heritage). Footer badges for 3D printed / made with passion. Photorealistic, warm gold-orange palette, product identity locked to the product reference. Brand: {{BRAND}}.
```

## 10 — Desk catalog image

Style ref: `assets/style-refs/desk-hero-style.jpg` (+ product photo)

```text
Premium desk lifestyle catalog photo matching the mood of the style reference. Exact same {{PRODUCT}} from the product reference standing on a polished wooden work desk among soft office props (notebook, pen, plant, mug, laptop edge) — product remains the hero. Warm directional light. Overlay clean dimension labels for {{DIMENSIONS}} and a short size callout like "ON DESK". Title "{{PRODUCT_NAME}}" with tagline about heritage for everyday spaces. 2–3 circular value icons (elevate your space, timeless design, meaningful gift). Photorealistic. Do not change the product. Brand: {{BRAND}}.
```

## 11 — Wall catalog image

Style ref: `assets/style-refs/wall-hero-style.jpg` (+ product photo)

```text
Premium wall lifestyle catalog photo matching the mood of the style reference. Exact same {{PRODUCT}} from the product reference mounted on a light warm interior wall as wall décor, with soft ambient lamp light. Below or beside: a console/sideboard with tasteful books, plant, or cultural décor for context — do not obscure the product. Include dimension arrows for {{DIMENSIONS}} and a small realistic-view callout (e.g. "ON WALL"). Title "{{PRODUCT_NAME}}" with tagline "Traditional art. Modern spaces." Feature icons for design quality, home & office, meaningful gift. Optional human silhouette for scale at the edge. Photorealistic. Product identity locked. Brand: {{BRAND}}.
```

## 12 — Size comparison (optional / when multiple sizes)

```text
Clean size comparison catalog panel showing the exact same {{PRODUCT}} design from the product reference in two clear sizes side by side (use user-provided sizes; if only one size known, show that size next to a faint scale reference). Soft studio background, labeled size captions, photorealistic, no cluttered text beyond size labels.
```
