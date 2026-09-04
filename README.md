# 3D Print Product Catalog

**Author:** [Ishank Choudhary](https://ishankdev.github.io/) — Software Architect & AI Engineer  
**Website:** https://ishankdev.github.io/  
**GitHub:** https://github.com/IshankDev/3d-print-product-catalog  
**Skill folder:** https://github.com/IshankDev/3d-print-product-catalog/tree/main/.claude/skills/3d-print-product-catalog  
**Contact:** Via website — [ishankdev.github.io](https://ishankdev.github.io/)

Generate a **complete sales catalog** for your **3D printed product** from a single photo — marketplace-ready listing images for Etsy, Amazon, Shopify, and D2C.

## MCP Market import URL

```text
https://github.com/IshankDev/3d-print-product-catalog/tree/main/.claude/skills/3d-print-product-catalog
```

## What it generates

### Core set (always)

| # | Shot | Job |
|---|------|-----|
| 01 | Hero (pure white) | Main / search thumbnail |
| 02 | Three-quarter | Depth / alternate angle |
| 03 | Side / profile | Silhouette / thickness |
| 04 | Detail / macro | Print finish & craftsmanship |
| 05 | Scale (hand/reference) | Real-world size |
| 06 | Lifestyle | In-context use |
| 07 | Feature infographic | Benefits callouts |
| 08 | Dimensions | Print size diagram |
| 09 | Packaging / unboxing | What’s in the box |
| 10 | Second lifestyle / trust | Gift / brand context |

### Optional (only if the user asks)

| # | Shot | Trigger phrases |
|---|------|-----------------|
| 11 | Wall-placed | “wall placed”, “wall mount”, “on the wall” |
| 12 | Desk-placed | “desk placed”, “on the desk”, “desk decor” |

## Install

### MCP Market

1. Paste the skill-folder URL above
2. Set price (or Free), then Publish

### Cursor (local)

```bash
mkdir -p ~/.cursor/skills/3d-print-product-catalog
cp -R .claude/skills/3d-print-product-catalog/* ~/.cursor/skills/3d-print-product-catalog/
```

## Usage

```text
/3d-print-product-catalog

Create the complete product catalog for this 3D printed product.
```

## Package layout

```text
3d-print-product-catalog/
├── .claude/skills/3d-print-product-catalog/
│   ├── SKILL.md
│   ├── references/
│   │   ├── examples.md
│   │   ├── shot-list.md
│   │   └── prompt-templates.md
│   └── assets/logo.svg
├── .cursor-plugin/plugin.json
├── plugin.json
├── LICENSE
└── README.md
```

## License

MIT © Ishank Choudhary
