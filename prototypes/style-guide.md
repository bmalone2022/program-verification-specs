# Program Verification — Visual style guide (v1 mock-ups)

> **Purpose:** brand consistency with Twin 87. Copy Twin’s **palette** and **icon construction**. Layout, navigation, and chrome composition are free.
> **Theme:** dark-only for these mock-ups.
> **Product name:** Program Verification (not Twin 87).
> **Twin source:** `twin87-data-viewer/08-gui-layout/style-guide.md` and `app/gui/qml/Theme.qml` (v8).

This document is the visual reference for HTML prototypes under `prototypes/`. It is not a plant-IT constraint list.

---

## 1. What to share with Twin

AC&E products should feel like siblings: same night-shift workbench, same cool CAD hues, same glossy tiled icons. A programmer who uses Twin 87 should recognize Program Verification as the same family’s plant portal.

---

## 2. Theme tokens (lock these)

### 2.1 Typography

- **UI text:** IBM Plex Sans (system-ui fallback).
- **Data / ids / timestamps / job ids:** IBM Plex Mono.
- Base ~13px. Uppercase, letter-spaced micro-labels for section and field headers.

### 2.2 Palette — chrome

| Token | Value | Use |
|-------|-------|-----|
| bg | `#16181c` | app background |
| chrome / chrome2 | `#1f2329` / `#262b32` | title bar, raised chrome, icon tiles |
| panel | `#1c2026` | rails, ribbons, side panels |
| viewport | `#0c0e11` | deep stage (login field, empty canvas, preview well) |
| line / line2 | `#333a44` / `#2a3038` | borders, dividers |
| text / muted / faint | `#d8dde4` / `#8b939f` / `#5c636e` | primary / secondary / tertiary |
| iconline | `#eaf1f8` | glyph outline + interior detail |

### 2.3 Palette — accents (the only hues in chrome and icons)

| Token | Value | Meaning here |
|-------|-------|----------------|
| **blue** | `#4f83f0` | brand, primary actions, **Submit / new job** |
| **fileblue** | `#2f5cb0` | file / package / download family |
| **cyan** | `#39c0f0` | view, selection, **Status**, live/interactive |
| **teal** | `#1fb6a6` | data / tools / import-adjacent |
| **green** | `#34d399` | pass, validated, quality, complete-ok |
| **violet** | `#a78bfa` | supporting (optional) |
| **red** | `#ff5d5d` | fail, stuck, destructive, alert |

**No amber/orange in chrome or icons.** Twin keeps amber only for unrelated fastener data-status; this product does not need it.

**Glyph shading:** colored glyphs use a **top-lit vertical gradient** of the family accent (lighter top → deeper bottom) and a **single** drop shadow `0 1.2px 1.3px rgba(0,0,0,.5)`. Neutral actions are **white line-art** (`iconline`, no fill).

---

## 3. Icon construction (lock these)

Same Twin rules, applied to verification actions.

- **Artboard:** 24px Lucide-style grid.
- **Colored actions:** gradient body + thin `iconline` stroke (~0.85–1.1px) + shadow.
- **Neutral / system:** white line-art (~1.1–1.3px), no fill.
- **Tile:** rounded, `panel`→`chrome2` gradient, 1px border, **left category rail** in the family color with a soft glow.
- **Top-align** glyph; label at the bottom of the tile.
- **Hover:** tile lifts, border brightens; art unchanged.
- **Active:** blue tint (brand).
- **Disabled:** faint, rail off.
- **Max two accent families** in one glyph. Small green detail (check, hub) on a produce/validate metaphor is OK.

Suggested families for this product (not Twin’s File/Produce ribbon):

| Family | Rail / accent | Examples |
|--------|---------------|----------|
| View | cyan | Status, open job, live poll |
| Submit | blue | New verification |
| Package | fileblue | CATPart, RMCD, ETR, downloads |
| Data | teal | Tool list |
| Validate | green | Pass, quality review, PDF report |
| Alert | red | Fail, stuck, quit |

Metaphors to reuse rather than invent: page/document, plus, magnifier, key, list + status dots, cube, check badge, power. Compose (page + check = report).

**Do not** gray out a still-available action. **Do not** bake text into icons. **Do not** mix flat and isometric on one surface. **No raster icons** in command tiles.

---

## 4. Layout (free)

Mock-ups may use a title bar, a vertical command rail, a table, cards, a split detail, or something else. Twin’s CAD object tree, 3D viewport, and license lock chips are **optional inspiration**, not requirements.

v1 mock-ups use a demo-user badge (cyan), not Twin’s Free Viewer / Licensed Producer pair.

---

## 5. Do / don’t

**Do**

- Use the Twin hex tokens above, including IBM Plex.
- Draw command tiles with a glowing left rail when the control is an icon action.
- Map pass → green, fail/stuck → red, status/view → cyan, submit → blue.

**Don’t**

- Introduce new chrome hues (orange, pink, flat Material purple).
- Use amber for brand or buttons.
- Ship a light theme in v1 mock-ups.
- Copy Twin 87 product names, `.w87cell`, or license gating into this portal.
