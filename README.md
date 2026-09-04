# Product Listing Image Set

**Author:** [Ishank Choudhary](https://ishankdev.github.io/) — Software Architect & AI Engineer  
**Website:** https://ishankdev.github.io/  
**GitHub:** https://github.com/IshankDev  
**Contact:** Via website — [ishankdev.github.io](https://ishankdev.github.io/)

Cursor / coding-agent skill that turns **one product photo** into a marketplace-ready **10-image listing set**, with optional **wall-placed** and **desk-placed** lifestyle shots when the user asks for them.

Inspired by AI product-listing workflows (studio hero, angles, detail, scale, lifestyle, infographic, packaging) used for Amazon, Shopify, and D2C stores.

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
| 10 | Second lifestyle / trust | Gift, pooja, brand context |

### Optional (only if the user asks)

| # | Shot | Trigger phrases |
|---|------|-----------------|
| 11 | Wall-placed | “wall placed”, “wall mount”, “on the wall” |
| 12 | Desk-placed | “desk placed”, “on the desk”, “desk decor” |

## Install

### Cursor Marketplace / plugin

1. Push this folder to a public Git repo (or submit the repo at [cursor.com/marketplace/publish](https://cursor.com/marketplace/publish)).
2. Manifest: `.cursor-plugin/plugin.json`
3. Skill path: `skills/product-listing-image-set/`

### Local Cursor (project)

```bash
cp -R skills/product-listing-image-set /path/to/your-project/.cursor/skills/
```

### Local Cursor (personal / all projects)

```bash
cp -R skills/product-listing-image-set ~/.cursor/skills/
```

### Any Agent Skills–compatible agent

Copy `skills/product-listing-image-set/` into the agent’s skills directory (e.g. `.agents/skills/`, `~/.agents/skills/`, `.claude/skills/`).

## Usage

In Agent chat:

```text
/product-listing-image-set

Create the product listing images from this photo.
```

Optional:

```text
Also create wall placed and desk placed.
```

```text
Real dimensions: 22cm H × 12cm W × 6cm D
```

## Requirements

- An image generation tool available to the agent (Cursor `GenerateImage`, or another image MCP/API the agent can call)
- A clear product reference photo (attached or path on disk)

## Package layout

```text
product-listing-image-set/
├── .cursor-plugin/
│   └── plugin.json
├── skills/
│   └── product-listing-image-set/
│       ├── SKILL.md
│       ├── examples.md
│       └── references/
│           ├── shot-list.md
│           └── prompt-templates.md
├── assets/
│   └── logo.svg
├── LICENSE
└── README.md
```

## License

MIT © Ishank Choudhary
