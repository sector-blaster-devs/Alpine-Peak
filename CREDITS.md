# Alpine Peak — Credits, Asset Packs, Code & References

This document lists all code modules, visual & mesh/sprite asset packs, audio synthesis systems, third-party dependencies, typography, and real-world/technical references used in **Alpine Peak**.

---

## 1. Application Codebase

All core simulation, world-generation, rendering, procedural audio, and HUD logic is implemented in vanilla browser JavaScript and CSS:

- **`index.html`** — Full-viewport Canvas 2D stage, HUD Style 2 markup (Desktop & Mobile responsive controls), inline SVG favicon, and preloaded sprite atlas links.
- **`css/sanctuary.css`** — Carved Tyrolean Chalet Timber, Frost-Pine, Hemp Rope & Wrought-Iron UI theme, responsive layout, and legal/credits modal styling.
- **`js/world.js` (`SanctuaryWorld`)** — `28x28` procedural isometric heightfield across 5 elevations (`Lv 0..4`), 8-neighbor Chebyshev BFS slope propagation, 17 terrain surfaces, 4 hydrology/crevasse systems, 10 uphill lift systems, 5 `2x2` composite landmarks, Swiss mountain rack-railway, 174+ craftable items, and 5 resort presets.
- **`js/simulation.js` (`SanctuarySim`)** — Real-time tycoon economy, 60 animated entity species (180–247+ active skiers, hikers, pond hockey players, snowcats, Swiss trains, VIP helicopters, balloons, paragliders, mountain coasters), pooled pixel fireworks, and 12 resort milestones.
- **`js/renderer.js` (`SanctuaryRenderer`)** — Tall isometric `128x224` zero-seam Canvas 2D compositor, Night Mode 2.0 directional floodlights & emissive window/lantern pass, Aurora Borealis shader-like curtains, Catmull-Rom Showcase Glide camera, and 1:1 PNG snapshot exporter.
- **`js/audio.js` (`SanctuaryAudio`)** — 100% pure Web Audio API procedural soundscape & SFX synthesizer (zero external audio files).
- **`js/ui.js` (`SanctuaryUI`)** — Interactive Chalet Studio controller, 5-tab 174-item catalog with search/sub-filters, live inspector card, isometric minimap, Resort Guide drawer, mobile sheet, and Legal/Credits modal.
- **`js/atlas_data.js` & `js/atlas_inline_fallback.js`** — Auto-generated sprite atlas coordinate tables and offline Base64 fallback bundle.

---

## 2. Mesh Pack, 2:1 Isometric Sprite Atlases & HUD Asset Packs

### Mesh Pack & 3D Geometry Notice
- **2D Tall-Isometric Sprite Architecture (No External 3D Mesh Pack Required):** Alpine Peak renders all terrain, architecture, lifts, vehicles, and characters via a custom **2:1 tall-isometric (`128x224`) Canvas 2D pixel-art sprite compositor** rather than runtime 3D `.glb`/`.obj`/`.fbx` meshes.
- **Custom / Derivative Mesh Pack Slot:** If you integrate any external 3D mesh pack or isometric geometry kit into a derivative build, record its attribution below:
  - `[Mesh Pack Name]` — Author: `[Creator / Studio]` — Source: `[URL]` — License: `[CC-BY 4.0 / CC0 / Commercial]`

### Packed Sprite Atlases (`assets/`)
- **`assets/atlas_tiles.png` & `assets/atlas_tiles_2.png`** — 2,127 packed `128x224` pixel-art terrain, lift, mountain coaster, rail, flora, water, and architectural sprites (+868 aliases), packed via `scripts/build_sprite_atlas.py`.
- **`assets/atlas_entities.png`** — 1,352 packed `64x64` animated skier, hiker, mascot, lift-carrier, train, helicopter, balloon, and wildlife sprite frames (+388 aliases).
- **`assets/hud_thumbnails.png`** — 423 pre-packed `48x48` HUD catalog and inspector portrait thumbnails (`1052x1052` sheet).

### HUD Style 2 Carved Tyrolean UI Pack (`assets/hud_style2/`)
- 23 transparent RGBA UI textures powered by **Nano Banana 2 Pro (`gempix-2`)** asset generation pipeline:
  - `atmo_dial.png`, `cat_tabs.png`, `catalog_tray.png`, `chalet_apron.png`, `chalet_apron_wide.png`, `chalet_ridge_crest.png`, `chalet_roof_cap.png`, `chalet_roof_wide.png`, `inspector_card_empty.png`, `milestone_banner.png`, `minimap_bezel.png`, `pill_guide.png`, `pill_mode.png`, `pill_snapshot.png`, `socket_active.png`, `socket_active_opt.png`, `socket_idle.png`, `socket_idle_opt.png`, `status_bar_empty.png`, `tool_bulldoze.png`, `tool_camera.png`, `tool_inspect.png`, `tool_rotate.png`.

---

## 3. Procedural Audio & Web Platform APIs

- **Web Audio API (`js/audio.js`)** — Synthesizes alpine wind, pentatonic larch-marimba & sleigh-chime pads, ski-edge snow carving, chairlift bullwheel clicks, Swiss mountain train horns, hearth fire crackle, glockenspiel milestone fanfares, carousel calliope waltzes, and firework bursts.
- **HTML5 Canvas 2D API** — Hardware-composited pixel-art offscreen buffering and 1:1 PNG diorama snapshot export.
- **Inline SVG Iconography (`index.html`)** — Custom alpine peak diamond crest favicon and minimalist HUD vector glyphs (undo, redo, sound, zen eye, search, menu).

---

## 4. Third-Party Libraries & Build Tooling

| Package | Version | Role | License |
| --- | --- | --- | --- |
| **Vite** (`vite`) | `^8.3.0` | Local dev server & static bundle builder | MIT License |
| **TypeScript** (`typescript`) | `^7.0.2` | Type checking (`tsc --noEmit`) & Vite config compilation | Apache License 2.0 |
| **@types/node** | `^22.14.0` | Node.js type definitions for Vite build scripts | MIT License |

---

## 5. Typography (Google Fonts)

Loaded via Google Fonts (`fonts.googleapis.com`):
- **Cinzel** (weights 600, 700) — Designed by Natanael Gama — *SIL Open Font License 1.1*
- **JetBrains Mono** (weights 500, 600, 700) — Designed by JetBrains — *SIL Open Font License 1.1*
- **Newsreader** (optical size, weights 500, 600, italic) — Designed by Production Type — *SIL Open Font License 1.1*
- **Plus Jakarta Sans** (weights 500, 600, 700) — Designed by Tokotype — *SIL Open Font License 1.1*

---

## 6. Real-World, Cultural, Architectural & Technical References

All real-world place names, landmarks, railways, and equipment names appear strictly as creative homage within a fictionalized alpine simulation. All trademarks remain the property of their respective owners:

- **Zermatt & The Matterhorn (Valais, Switzerland)** — Inspiration for the *Zermatt Grand Valley* preset, Matterhorn Pyramid Horn, Star-of-Zermatt mosaic plaza, Air-Zermatt-inspired VIP red rescue helicopter, and Valais Trycheln & Accordion folk parades.
- **Jungfraujoch Sphinx Observatory (Bernese Alps, Switzerland)** — Inspiration for the `sphinx_observatory_2x2` summit astronomical dome and high-altitude skywalk.
- **Bernina Express & Landwasser Viaduct (Rhaetian Railway, Graubünden, Switzerland)** — Inspiration for the Swiss valley cogwheel railway, `valley_train_station`, and arched granite `stone_viaduct`.
- **Kapellbrücke / Chapel Bridge (Lucerne, Switzerland)** — Inspiration for the covered timber `kapellbrucke_bridge` walkway span.
- **Davos Wooden Toboggan Heritage** — Inspiration for the `davos_toboggan_pair` ash-wood sledders.
- **PistenBully (Kässbohrer Geländefahrzeug AG)** — Referenced in the fictionalized *PistenBully Snowcat Barn* (`groomer_garage`) & snowcat vehicle names; *PistenBully* is a trademark of Kässbohrer Geländefahrzeug AG.
- **Sapporo Snow Festival (Hokkaido, Japan)** — Inspiration for the monumental carved snow dragon & mountain centerpiece (`giant_snow_sculpture`).
- **Alpine Ropeway & Mountain Coaster Engineering** — 3S tri-cable tramways, detachable bubble chairs, stepped cliff cog funiculars, and tubular gravity mountain coasters.
- **Tyrolean & Swiss Folk Traditions** — Schirmbar umbrella après-ski bars, Glühwein Christmas market pyramids, Raclette stone cellars, Alphorn trios, Glockenspiel clock towers, Krummholz dwarf pines, and Alpine Ibex wildlife.
- **Computer Graphics & Simulation References** — Classic 2:1 isometric tycoon dioramas, 8-neighbor Chebyshev BFS integer slope propagation, Catmull-Rom spline camera glide paths, and pentatonic procedural audio synthesis.
