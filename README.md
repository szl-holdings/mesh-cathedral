---
title: Mesh Cathedral
emoji: 🪢
colorFrom: gray
colorTo: yellow
sdk: static
pinned: true
license: apache-2.0
short_description: The Ouroboros loop · 5 surfaces · 45 kernels · live
---

# 🪢 Mesh Cathedral

One rotating 3D scene showing **all 5 SZL capability surfaces** — `command` · `memory` · `policy` · `operator console` · `drones` — as 3D character meshes in an **Ouroboros loop**, with each surface's kernels glowing live and codex links accessible from any surface.

**Live:** https://szlholdings-mesh-cathedral.static.hf.space/

## What you see

- **5 surfaces** as procedural 3D characters, each rotating at its own rate, lit by warm gold rim light:
  - **operator console** — ethereal wireframe head
  - **command** — 16-node knotted Khipu cord
  - **memory** — serpent-coil neural mesh
  - **policy** — hexagonal shield with hex panels
  - **drones** — kestrel + 53 drone dots over terrain
- **Ouroboros ring** — a glowing gold torus threading all 5 surfaces; **receipt particles** flow continuously along it, colour-coded by loop step (sign → gate → chain → memory → replay).
- **Kernel orbits** — 7 universal kernel dots + 2 vertical kernel dots orbit each surface (**45 kernels** total). Click a dot → docs + recent live activity.
- **Center counter** — total signed receipts across the mesh, summed live from each surface's metrics.
- **Top HUD** — live status badges per surface (green/amber/red, polled every 30s).
- **Bottom HUD** — `Doctrine v11 LOCKED · 749 declarations · 14 unique axioms · 163 sorries · 13-axis yuyay_v3 · build SHA`.
- **Codex** — click any surface → side panel opens with that surface's recipes / theses / formulas. Top-right **All Codices** → unified search across all 5.

## The Ouroboros loop

```
intent → SIGN → GATE → (if pass) → ACTION → CHAIN → MEMORY → REPLAY-AVAILABLE → next intent ⟲
                                              ├─ MCP  : visible to any tool consumer
                                              └─ WIRE : traceparent propagates to siblings
```

The output (a signed, replayable receipt) becomes the input substrate for the next intent — the serpent eats its tail.

## The 45 kernels

Each surface = **7 universal kernels** (SIGN · GATE · CHAIN · MEMORY · REPLAY · MCP · WIRE) + **2 vertical kernels**. 9 × 5 = 45. Full spec: `docs/architecture/chakras.md` in the platform repo.

> **"Chakra" is a brand/engineering metaphor** (Sanskrit "chakra" = wheel: a capability surface modelled as a wheel of kernels). It carries **no mystical claim** of any kind — every kernel is a concrete software component.

## Tech

- Three.js **r171** via CDN importmap (`unpkg.com/three@0.171.0`), WebGL2 renderer, `UnrealBloomPass`.
- **Mobile-first** per SZL Mobile-First Standard: `viewport-fit=cover`, `theme-color #0a0e14`, low-power renderer + capped pixelRatio (1.5) on mobile, particle count 200 desktop / 80 mobile, OrbitControls drag-rotate (touch-native), battery-saver render pause, `prefers-reduced-motion` honored.
- Vanilla touch layer: `static/szl-mobile-controls.js`.

## Files

| File | Role |
|------|------|
| `index.html` | scene shell + HUD + codex panel |
| `src/scene.js` | Three.js renderer + 5 procedural surface meshes |
| `src/ouroboros.js` | particle ring + loop logic + live receipt counter |
| `src/kernels.js` | kernel orbits + click handlers + status badges |
| `src/codex.js` | codex panel + cross-surface unified search |
| `src/config.js` | surface / kernel / endpoint config |
| `static/szl-mobile-controls.js` | canonical vanilla touch layer |

---

*Signed — Yachay `<yachay@szlholdings.dev>` · SZL Holdings · Doctrine v11 LOCKED (749 declarations · 14 unique axioms · 163 tracked sorries) · Apache-2.0*
