# Product Listing Image Set

**Author:** [Ishank Choudhary](https://ishankdev.github.io/) — Software Architect & AI Engineer  
**Website:** https://ishankdev.github.io/  
**GitHub:** https://github.com/IshankDev/product-listing-image-set  
**Skill folder:** https://github.com/IshankDev/product-listing-image-set/tree/main/.claude/skills/product-listing-image-set  
**Contact:** Via website — [ishankdev.github.io](https://ishankdev.github.io/)

Agent skill that turns **one product photo** into a marketplace-ready **10-image listing set**, with optional **wall-placed** and **desk-placed** lifestyle shots when the user asks for them.

## MCP Market import URL

Use this exact skill-folder URL (not the repo root):

```text
https://github.com/IshankDev/product-listing-image-set/tree/main/.claude/skills/product-listing-image-set
```

## What it generates

### Core set (always, unless user asks for fewer)

| # | Shot | Job |
|---|------|-----|
| 01 | Hero (pure white) | Main / search thumbnail |
| 02 | Three-quarter | Depth / alternate angle |
| 03 | Side / profile | Silhouette / thickness |
| 04 | Detail / macro | Material & craftsmanship |
| 05 | Scale (hand/reference) | Real-world size |
| 06 | Lifestyle | In-context use |
| 07 | Feature infographic | Benefits callouts |
| 08 | Dimensions | Size diagram |
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
mkdir -p ~/.cursor/skills/product-listing-image-set
cp -R .claude/skills/product-listing-image-set/* ~/.cursor/skills/product-listing-image-set/
```

## Usage

```text
/product-listing-image-set

Create the product listing images from this photo.
```

## Package layout

```text
product-listing-image-set/
├── .claude/skills/product-listing-image-set/
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
