# Ridgeglass

**Live demo:** [ridgeglass.vercel.app](https://ridgeglass.vercel.app/)

A 3D explorer for [Rust](https://rust.facepunch.com/) maps. Paste a [RustMaps](https://rustmaps.com/) link, a size and seed, or pick a chart from the live catalog, then orbit, tilt, and fly the island.

## What it does

- Pulls real maps from the RustMaps catalog (size, seed, or map URL)
- Drapes the official chart image over a terrain mesh
- Builds relief from the chart: ocean stays flat, coast rises inland, snow sits higher
- Monument pins with names, decluttered so they stay readable
- Rust grid readout (column / row, east, north, elevation) under the cursor
- Orbit camera and a free-fly camera (WASD, mouse look, Shift to sprint, Space / Ctrl for altitude)
- Vertical exaggeration, small-monument toggle, and a compass

Terrain height is reconstructed from the rendered map image. It matches the coastline, biomes, and monument layout of that exact chart. It is not yet the server's raw heightfield from a `.map` file.

## Run

```bash
npm install
npm run dev
```

The dev server listens on port 8080.

```bash
npm run typecheck
npm run build
```

## Earlier demo

`prototype/index.html` is the first single-file viewer: drop in a heightmap PNG and a satellite texture, or generate a procedural island. The live app is the Vercel deploy above.

## Stack

TanStack Start, React 19, Three.js, Tailwind. Map data comes from `https://api.rustmaps.com`. Chart images are loaded through a same-origin proxy so the canvas can read pixels.
