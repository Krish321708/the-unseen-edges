# The Unseen Edges

> Crafting the unseen edges of digital craft.

A single-file, hand-rolled portfolio for an independent design engineer. Built with a focus on editorial typography, generative motion, and high-friction interactions. No frameworks, no build steps, no lossy translation between design and code.

## ✦ Features

- **Generative Flow Field**: A custom Canvas API particle system (~420 particles) driven by multi-octave pseudo-noise. Cursor proximity applies a radial repulsion force, allowing the user to carve voids in the field.
- **Editorial Typography**: Variable font implementation of Fraunces (optical sizing 9–144) paired with Space Grotesk. Strict typographic hierarchy without relying on system fallbacks.
- **Custom Cursor Mechanics**: Dual-element cursor utilizing `mix-blend-mode: difference` for contrast adaptation, with lerp-based trailing and contextual scaling on interactive elements.
- **Scroll Choreography**: `IntersectionObserver`-driven staggered reveals, magnetic parallax on hero content, and easing curves tuned for inevitability rather than decoration.
- **Hover State Previews**: Selected Work items feature cursor-bound image previews with scale-in transitions, replacing traditional modals or carousels.
- **Atmospheric Polish**: SVG fractal noise overlay, layered radial vignettes, and a real-time timezone-aware clock in the footer.

## ✦ Tech Stack

- **HTML5** — Semantic structure, single file
- **CSS3** — Custom properties, Grid, advanced selectors, `clamp()` fluid typography
- **Vanilla JavaScript (ES6+)** — Canvas rendering, event delegation, DOM manipulation
- **Google Fonts** — Fraunces, Space Grotesk

## ✦ Getting Started

Because this project is built entirely with native web technologies, there is no build step required.

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/the-unseen-edges.git
   ```
2. **Navigate to the directory**
   ```bash
   cd the-unseen-edges
   ```
3. **Open the file**
   Simply open `index.html` in your preferred browser.
   
   *For live-reload during development, use a simple local server:*
   ```bash
   npx serve
   # or
   python3 -m http.server 8000
   ```

## ✦ Customization

All logic, styles, and markup live within a single `index.html` file for portability.

- **Color Palette**: Defined as CSS Custom Properties in the `:root` pseudo-class at the top of the `<style>` tag. Adjust `--bg`, `--fg`, and `--accent` to re-theme.
- **Flow Field Density**: In the `<script>` tag, find `initParticles()`. The formula `Math.min(420, Math.floor(W * H / 3200))` controls particle count. Lower the divisor for a denser field.
- **Cursor Repulsion Force**: In the `Particle.update()` method, adjust the `28000` threshold and `4.5` multiplier to change how aggressively the field reacts to the mouse.
- **Content**: Sections are clearly commented (`<!-- Hero -->`, `<!-- About -->`, etc.). Replace the placeholder text, project data (`data-img` attributes on `.work-item`), and links with your own.

## ✦ Architecture Note

The choice to keep this as a single file is deliberate. It reflects the "person who decides is the person who ships" ethos of the studio itself. For scaling to component-based architectures or migrating the vanilla JS to TypeScript, the logical next step is extracting the CSS to a modular structure and moving the Canvas logic into a class-based TS utility—though the single-file format serves as a highly performant, zero-overhead baseline.

## ✦ License

MIT License. You are free to use, modify, and distribute this code. Attribution is appreciated but not required.
