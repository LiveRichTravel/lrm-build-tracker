# LiveRichMedia Design Package

**One source of truth: `lrm.css`.** Every LRM page links it. Never re-style per page, never invent a new look. If a component is missing, add it to `lrm.css` so all pages get it.

```html
<link rel="stylesheet" href="lrm.css">
```

## The look (non-negotiable)
- **Dark glass.** Background `#0b0b0e` with a slow animated color-mesh (purple/pink/blue blobs). Cards are frosted glass (`.glass`): translucent white, blur, soft shadow, 20–26px rounded corners.
- **Accent colors only** (greens, ambers, blues, purples, pinks from the tokens). The LRM gradient (`--grad`) is for the wordmark, key buttons, and number tiles — not whole backgrounds.
- **Big, cinematic cards** — not chips, not flat rows, not segmented pills. Each meaningful item is a card with a colored/animated "scene" header (gradient + a simple white glyph), a bold title, one line of plain text, then actions.
- **Motion is required.** Cards fade-and-rise in with stagger (`cardIn`), art gently "breathes," a light sheen sweeps on hover, progress bars shimmer. A static page is not done.
- **Readable + babied copy.** Short sentences, name the tool ("Cowork"), no jargon.

## What NOT to do
- ❌ No chip/segmented-pill rows as the primary UI (the old flat look). Use cards or big tiles.
- ❌ No light mode. No gradients on full card backgrounds.
- ❌ No per-page stylesheet that redefines tokens. Extend `lrm.css` instead.

## Core components (in `lrm.css`)
- `.glass` — frosted card base.
- `.card` + `.art` (scene) — the big content card with breathing art + hover sheen.
- `.stepc` + `.scene` — cinematic numbered step card (animated SVG scenes).
- `.dcard.g1/.g2/.g3` — big-number stat card with colored glow.
- `.grid` — responsive auto-fill card grid.
- `.tier-grid` / `.tcard` — compact graphic cards for menus.
- Editor Board: `.eb-id`, `.roletile`, `.eb-cols`, `.rq` (request card with priority-colored animated header), `.ppl`.
- Motion keyframes: `cardIn`, `breathe`, `shine`, `sweep`, `float`, `orb`, `bob`, `pulse`, `draw`.

## Build art = animated SVG scenes
Imagery is gradient SVG scenes with a single white-line glyph, set to `breathe`. (When the Switch image/video connector is authorized in-session, these can be swapped for real generated images/video loops — the package keeps the same card frame.)

## Pages on this package
- `index.html` — Build Tracker
- `editors.html` — Editor Board
Both link `lrm.css`. Any new LRM page does the same.
