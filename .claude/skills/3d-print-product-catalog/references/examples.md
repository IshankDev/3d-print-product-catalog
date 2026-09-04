# Examples

## Example 1 — Full catalog (default)

**User:**  
Attach 3D print photo → “Create the complete product catalog for this print.”

**Agent:**

1. Save product photo; resolve style-ref paths under `assets/style-refs/`.
2. Slug e.g. `sacred-gopuram-shadow-frame`.
3. Generate **01–11** (includes brand hero, gift, desk, wall).
4. For 06/09/10/11 pass product photo **and** matching style ref.
5. Skip 12 unless multiple sizes.
6. Save under `product-images/<slug>/` and return the table.

## Example 2 — With brand + dimensions

**User:**  
“Brand is WORK18 Studios. Product name Sacred Gopuram Shadow Frame. Size 12 inch (30 cm) tall, 9.5 inch (24 cm) wide. Generate the catalog.”

**Agent:**

- Fill `{{BRAND}}`, `{{PRODUCT_NAME}}`, `{{DIMENSIONS}}` on 06/08/09/10/11.
- Still keep image 01 text-free white.

## Example 3 — Size comparison add-on

**User:**  
“Also add a size comparison for 6 inch and 12 inch.”

**Agent:**

- Generate only `12-size-comparison` (or include it in the batch).
- Label both sizes clearly.

## Example 4 — Slash invoke

**User:**  
`/3d-print-product-catalog` + attached print photo

**Agent:**  
Follow SKILL.md; default to core 01–11 with style refs on hero-brand / gift / desk / wall.
