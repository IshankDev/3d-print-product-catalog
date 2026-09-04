# Product Listing Image Set

**Author:** [Ishank Choudhary](https://ishankdev.github.io/) — Software Architect & AI Engineer  
**Website:** https://ishankdev.github.io/  
**GitHub:** https://github.com/IshankDev/product-listing-image-set  
**Contact:** Via website — [ishankdev.github.io](https://ishankdev.github.io/)

Agent skill that turns **one product photo** into a marketplace-ready **10-image listing set**, with optional **wall-placed** and **desk-placed** lifestyle shots when the user asks for them.

Works with Cursor, Claude Code, Codex, ChatGPT agents, and [MCP Market](https://mcpmarket.com/sell) (sync from GitHub or upload `SKILL.md`).

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

1. Re-sync / connect this GitHub repo: `https://github.com/IshankDev/product-listing-image-set`
2. In Hub: set your **price** (paid amount or Free), then **Publish**
3. Listing draft: `https://app.mcpmarket.com/ishank-iandroid/skills/product-listing-image-set`

### Cursor (local)

```bash
# personal (all projects)
mkdir -p ~/.cursor/skills/product-listing-image-set
cp SKILL.md ~/.cursor/skills/product-listing-image-set/
cp -R references assets ~/.cursor/skills/product-listing-image-set/

# or project-scoped
mkdir -p .cursor/skills/product-listing-image-set
cp SKILL.md .cursor/skills/product-listing-image-set/
cp -R references assets .cursor/skills/product-listing-image-set/
```

### Any Agent Skills–compatible agent

Copy this repo folder (or at least `SKILL.md` + `references/` + `assets/`) into the agent’s skills directory.

## Usage

```text
/product-listing-image-set

Create the product listing images from this photo.
```

Optional:

```text
Also create wall placed and desk placed.
```

## Requirements

- An image generation tool available to the agent (Cursor `GenerateImage`, or another image MCP/API)
- A clear product reference photo (attached or path on disk)

## Package layout

```text
product-listing-image-set/
├── SKILL.md
├── references/
│   ├── examples.md
│   ├── shot-list.md
│   └── prompt-templates.md
├── assets/logo.svg
├── .cursor-plugin/plugin.json
├── plugin.json
├── LICENSE
└── README.md
```

## License

MIT © Ishank Choudhary
