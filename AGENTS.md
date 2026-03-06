# Agents Guidelines


## Project Structure

- Static HTML site with zero dependencies. All styling is inline `<style>` per page plus a shared `common.css`.
- Character drawing is done via Canvas 2D API in JavaScript. Each character has a full-detail version (in `count.html`) and a mini version (in `index.html` for the preview grid).


## Screenshots

When visual changes are made (new characters, layout changes, styling updates), the README screenshot must be updated to stay consistent:

- `docs/screenshot-index.png` — screenshot of `index.html` at 1280x800 desktop resolution.

Take a fresh screenshot after any visible change and overwrite the existing file.


## Characters

The counting game (`count.html`) has selectable characters. Each character requires:

1. A full drawing function `drawCharName()` in `count.html` (used on the counting canvas).
2. A mini drawing function `drawMiniCharName()` in `index.html` (used in the preview grid on the launcher card).
3. A `<button class="char-btn">` with a preview `<canvas>` in the left panel of `count.html`.
4. Registration in the `DRAW_FNS` map and the `drawPreviews()` function in `count.html`.
5. Addition to the `chars` array in the counting preview IIFE in `index.html`.

Current characters: R2D2, Bluey, Marshall, H. Potter.


## Mobile Responsiveness

All pages use a `@media (max-width: 768px)` breakpoint to switch from horizontal side-by-side layouts to vertical stacking. Mobile-specific styles are in:

- `common.css` — shared layout overrides (body overflow, container stacking, h1 sizing).
- Each page's inline `<style>` — page-specific adjustments (panel widths, button sizes, etc.).

After layout changes, verify at 375px and 430px portrait widths and at 1280x800 desktop.
