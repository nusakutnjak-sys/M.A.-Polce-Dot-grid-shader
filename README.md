# M.A. Polce — Dot Grid Shader

A browser-based WebGL/GLSL tool that converts an uploaded video into a live, animated **dot-grid (halftone) treatment**. The source video is never shown directly — instead the canvas is divided into a perfectly uniform grid and one crisp circle is drawn per cell, its size and opacity driven by the video's luminance.

Everything is contained in a single self-contained `index.html` — no build step, no dependencies. Just open it in a modern browser.

## Getting started

Open `index.html` directly in a browser (Chrome, Edge, Safari, or Firefox), then click **Upload video** under SOURCE.

> Uploaded videos must be muted to autoplay — the source `<video>` is muted by default.

## Features

- **Live dot-grid shader** — fragment-shader halftone; uniform grid, perfect circles, luminance-driven size/opacity, temporal smoothing to prevent flicker.
- **Source controls** — upload, play/pause, restart, loop, speed, scale, position, and fit (Contain keeps the source's true aspect ratio inside the frame; Cover fills it).
- **Dot grid** — dot spacing (distance between dots) and dot size in pixels, fully decoupled so spacing never changes dot size.
- **Image processing** — brightness, contrast, gamma, source blur, temporal smoothing, invert luminance.
- **Mask / background removal** — luminance cutoff + feather, invert, mask preview, and a **green-screen (chroma key)** with adjustable key color, tolerance, and feather.
- **Dot style** — custom color (with hex input) and opacity.
- **Independent background layer** — transparent, solid, multi-stop gradient, image, or video, with scale/position/fit and opacity.
- **Compositing** — shader opacity and blend modes (Normal, Screen, Lighten, Multiply, Overlay, Soft Light).
- **16:9 preview** with fullscreen.
- **Presets** — saved to the browser (grid of tiles, a Custom state, ×-to-delete), plus `.json` export/import. Settings are also remembered automatically between sessions.
- **Export** — transparent **PNG (APNG)**, transparent **GIF**, **MP4** and **WebM** video, and a self-contained **HTML** snippet with the current settings baked in, at selectable resolution / duration / frame rate.

## Notes

- Presets and remembered settings are stored per browser origin (localStorage). Use **⬇ .json** to back them up.
- Transparent output: PNG and GIF export the dot layer with transparency. WebM can keep alpha; MP4 cannot carry transparency.
