# Examples

## Example 1 — Core 10 only

**User:**  
Attach 3D print photo → “Create the full product catalog for this print.”

**Agent:**

1. Save/copy reference to a workspace path.
2. Slug e.g. `olive-gopuram-print`.
3. Generate `01`–`10` with reference attached.
4. **Do not** generate wall/desk.
5. Save under `product-images/olive-gopuram-print/`.
6. Return a 10-row file table.

## Example 2 — Core + optional placements

**User:**  
“Generate the sales catalog. Also add wall placed and desk placed.”

**Agent:**

1. Generate core `01`–`10`.
2. Also generate `11-wall-placed` and `12-desk-placed`.
3. Deliver all 12 paths.

## Example 3 — Optional later

**User (after core set exists):**  
“Make a wall placed and desk placed version too.”

**Agent:**

1. Reuse the same reference image.
2. Generate only `11` and `12`.
3. Save beside the existing set.

## Example 4 — Real print dimensions

**User:**  
“Dimensions are 22cm high, 12cm wide, 6cm deep.”

**Agent:**

- On image `08`, use those exact measurements.
- If `08` already existed with placeholders, regenerate only `08`.

## Example 5 — Explicit slash invoke

**User:**  
`/3d-print-product-catalog` + attached print photo

**Agent:**  
Follow SKILL.md workflow end-to-end; default to core 10 unless extras are requested.
