# FPV. — First Person View Drones

<div align="center">

**An interactive single-file reference website for everything FPV — from physics to freestyle tricks, featuring a real-time 3D model of the SpeedyBee Bee35 cinewhoop.**

`Three.js r128` · `WebGL Shaders` · `Zero Dependencies` · `Single HTML File`

---

[Live Demo](#usage) · [Features](#features) · [3D Model](#3d-interactive-model) · [Contributing](#contributing)

</div>

## Overview

A comprehensive, self-contained FPV drone educational site built as a single HTML file. No build tools, no frameworks, no external assets — just one file you can open in any browser.

The site covers the fundamentals of FPV flying, component anatomy, flight physics, freestyle tricks, and getting started — all wrapped in a dark, cockpit-inspired aesthetic with animated WebGL backgrounds and a fully interactive 3D drone model.

## Features

- **Animated WebGL Background** — Procedural noise-field shader simulating aerial flight trails, rendered in real-time via raw WebGL
- **7 Content Sections** — Home, Basics, 3D Model, Components, Physics, Freestyle, Start Flying
- **Tab-Based SPA Navigation** — Instant section switching with no page reloads
- **Responsive Design** — Adapts from desktop to mobile with reorganized grids and navigation
- **Dark HUD Aesthetic** — JetBrains Mono + Syne + Source Serif 4 typography stack, glassmorphism panels, accent color system

## 3D Interactive Model

The crown jewel — a real-time Three.js model of the **SpeedyBee Bee35** ducted cinewhoop with:

### Rendering
- ACES filmic tone mapping with physically correct lights
- Procedural cube-mapped environment reflections on all metallic surfaces
- PCF soft shadow mapping (2048×2048)
- sRGB output encoding
- Atmospheric fog and 600+ floating dust particles (additive blending)
- Reflective dark ground plane with subtle grid

### Drone Model Detail
- **Carbon fiber frame** — Procedural woven texture, X-arms with bevels, hex standoffs with nuts, Phillips head screws
- **Prop guard ducts** — Double-wall construction with inner lip, top/bottom torus rings, cross-braces
- **Motors ×4** — 12-tooth stators with copper windings, two-piece bell housing, visible magnets, mounting screws, shaft detail
- **Propellers** — Curved extruded blade geometry (not flat boxes), tri-blade with hub cap
- **Flight controller** — PCB with gyro chip (BMI270 marking dot), STM32 processor, USB-C port, status LED, gold solder pads
- **4-in-1 ESC** — MOSFET array with thermal pads, capacitors, PCB bump texture
- **FPV Camera** — Yellow housing, chrome lens ring, glass element with specular flare, visible sensor board
- **VTX** — Heatsink fins, SMA connector, dipole antenna with tip
- **LiPo Battery** — Cell dividers, label with text detail, XT30 with gold pins, balance lead with colored wires, rubber straps with buckle
- **Wiring** — Per-motor silicone wires (red/blue/yellow) routed along arms via CatmullRom tube geometry
- **RX Antennas** — Curved tube geometry with tip spheres
- **RGB LED rings** — 48 LEDs per duct with rainbow chase animation + additive glow halos

### Interaction
- Click-drag orbit, scroll zoom, touch support (1-finger orbit, 2-finger pinch)
- Auto-rotate after 2.5s idle with subtle hover bob animation
- Interactive legend panel — click to isolate/highlight any component group
- Spinning props with per-motor speed variation

### Materials
Every material uses physically-based properties with environment map reflections:

| Surface | Metalness | Roughness | Special |
|---------|-----------|-----------|---------|
| Carbon fiber | 0.35 | 0.25 | Procedural weave texture + bump |
| Aluminium | 0.95 | 0.06 | Scratched roughness map |
| Motor bells | 0.85 | 0.12 | Directional scratch texture |
| Copper windings | 0.82 | 0.22 | Warm tint, high env reflection |
| Gold connectors | 0.92 | 0.08 | Maximum env intensity |
| Lens glass | 0.98 | 0.02 | Transparent, ultra-reflective |
| LiPo shrink wrap | 0.08 | 0.52 | Bump texture for surface grain |
| Rubber/silicone | 0.0–0.05 | 0.7–0.95 | Minimal reflection |

## Tech Stack

| Layer | Technology |
|-------|-----------|
| 3D Engine | Three.js r128 (CDN) |
| Background | Raw WebGL 1.0 fragment shader |
| Textures | Procedural Canvas2D generation |
| Layout | CSS Grid + Flexbox |
| Fonts | Google Fonts (JetBrains Mono, Syne, Source Serif 4) |
| Bundling | None — single file |

## Usage

```bash
# Just open it
open index.html

# Or serve locally
python3 -m http.server 8000
# → http://localhost:8000
```

No build step. No `npm install`. No configuration. Works offline once fonts are cached.

## File Structure

```
.
└── index.html    # Everything — HTML, CSS, WebGL shaders, Three.js scene, content
```

That's it. That's the whole project.

## Browser Support

Requires WebGL 1.0 support (all modern browsers). Tested on:
- Chrome / Edge (Chromium)
- Firefox
- Safari 15+
- Mobile Chrome & Safari (iOS/Android)

## Performance

The renderer caps pixel ratio at 2× and uses efficient geometry (no imported models, no texture file I/O). The WebGL background shader uses a 1.5× DPR cap. Typical frame budget is well under 16ms on integrated graphics.

## SpeedyBee Bee35 Specs

The 3D model represents a real drone — the SpeedyBee Bee35 3.5" ducted cinewhoop:

| Spec | Value |
|------|-------|
| Frame | 155mm true-X, 3mm carbon arms |
| Motors | 1404 4500KV brushless |
| Props | 3.5" tri-blade |
| FC | F405 + BMI270 gyro, 8kHz PID |
| ESC | 35A BLHeli_S, DShot600 |
| VTX | 400mW 5.8GHz |
| Battery | 4S 850mAh 75C LiPo |
| AUW | ~185g |

## Contributing

Contributions welcome — especially additional content sections, model detail improvements, or mobile UX refinements.

## Contributors

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/cskgcskg">
        <strong>The Best</strong>
      </a>
      <br />
      <sub>Creator · Design · Content</sub>
    </td>
    <td align="center">
      <a href="https://claude.ai">
        <strong>Claude</strong>
      </a>
      <br />
      <sub>Anthropic · Claude Opus 4.6</sub>
      <br />
      <sub>3D Model Engineering · WebGL · Code</sub>
    </td>
  </tr>
</table>

## License

MIT — do whatever you want with it. Build something cool and go fly.

---

<div align="center">
  <sub>Built with caffeine and propwash · 2025–2026</sub>
</div>
