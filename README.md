# 3D Rust Map Viewer

Interactive 3D terrain viewer for Rust maps. Load a heightmap + satellite texture (or try the built-in demo island) and explore from any angle with free orbit, pan, and zoom.

**Live demo** (GitHub Pages): once enabled, it will be at  
`https://jkh2.github.io/3d-rustmap-viewer/`

## Features

- Drag-and-drop or file-select heightmap (grayscale PNG) + optional satellite/texture image
- Procedural **Demo Island** that generates a Rust-style terrain on the fly
- Smooth OrbitControls (left-drag orbit, right-drag pan, scroll zoom)
- Vertical exaggeration slider (terrain is relatively flat at true scale)
- Water plane with adjustable level
- Height-based coloring when no texture is provided (sand → grass → rock → snow)
- Wireframe toggle, camera reset, soft shadows, and atmospheric fog
- Gold/black metallic aesthetic

## How to Use

1. Open the page (or enable GitHub Pages on the `main` branch).
2. Click **Demo Island** to explore immediately, or
3. Select a heightmap PNG and (optionally) a satellite texture, then click **Load Map**.
4. Adjust vertical exaggeration and water level with the sliders.
5. Drag to orbit, right-drag to pan, scroll to zoom.

### Getting heightmaps and textures from Rust

- **rustmaps.com**: Open a map → download the high-res images or use the "Use" link for the full `.map` (future support planned).
- **Local `.map` files**: Export a heightmap + satellite render from tools like RustEdit, Crucible Heightmap, or the [Rustmap-Parser](https://github.com/Cooperkit/Rustmap-Parser).
- Best results come from a real 16-bit or high-resolution heightmap paired with a clean satellite view.

## Tech

- Pure client-side (no backend required for the current version)
- Three.js (r128 via CDN) + OrbitControls
- Self-contained `index.html` for easy GitHub Pages deployment

## Roadmap

- Direct `.map` file upload and parsing (via Rustmap-Parser or a WASM port)
- rustmaps.com URL paste → automatic image/heightmap fetch
- Monument markers and overlays
- Free-fly camera mode
- LOD / chunked terrain for very large maps
- Export screenshots or glTF

## Development

This is a single-file viewer for simplicity and instant deployment. For larger features (full `.map` parsing, server-side processing), a small Python (FastAPI) backend using [Rustmap-Parser](https://github.com/Cooperkit/Rustmap-Parser) is the natural next step.

---

Built for accurate, explorable 3D views of Rust maps.  
Feel free to fork, improve, and share.
