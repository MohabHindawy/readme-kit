# Readme Kit

Readme Kit is a browser tool for building animated SVG banners for your GitHub profile.

> Formerly SVG Crafter.

GitHub's image proxy (camo) makes fonts and animations a pain in READMEs. Readme Kit deals with that for you, including embedding Google Fonts as Base64, so you can just focus on the design.

**[Open the live app](https://mohabhindawy.github.io/readme-kit/)**

## What's new

- **UI upgrade:** a refreshed editor with a cleaner layout and easier navigation.
- **Templates:** ready-made designs where you only swap in your own content. fastfetch is the first one, with more planned.

## Examples

Here are a few designs you can make.

|                                     Terminal                                     |                                    Arcade                                    |                                    Clean                                     |
| :------------------------------------------------------------------------------: | :--------------------------------------------------------------------------: | :--------------------------------------------------------------------------: |
| [![Terminal](./assets/terminal.svg)](https://mohabhindawy.github.io/readme-kit/) | [![Arcade](./assets/sci-fi.svg)](https://mohabhindawy.github.io/readme-kit/) | [![Clean](./assets/ambient.svg)](https://mohabhindawy.github.io/readme-kit/) |

_The links only work because the markdown wraps the image. GitHub's proxy strips `<a>` tags inside raw SVGs._

## What it can do

- **Multiple lines:** cycles through up to 6 lines of text.
- **Animations:** typewriter effects (smooth or per character), plus Float, Bob, Sway and Orbit.
- **Colours:** solid or multi-stop gradients, with opacity, brightness and basic motion.
- **Fonts:** any Google Font, baked into the SVG as Base64 so it actually renders on GitHub.
- **Effects:** scanlines, matrix rain, border beams and aurora glows and more.
- **Templates:** ready-made and more complex designs where you only change the content.

## Templates

<details>
  <summary><b>fastfetch</b></summary>
  <br>
  <div align="center">
    <a href="https://mohabhindawy.github.io/readme-kit/">
      <img src="./assets/fastfetch.svg" alt="fastfetch" width="80%">
    </a>
  </div>
</details>

## How to use it

1. Design your banner in the [live app](https://mohabhindawy.github.io/readme-kit/).
2. Download the `.svg` or copy the code.
3. Save it in your repo, e.g. `assets/banner.svg`.
4. Add the snippet the app gives you:

```markdown
![Banner Name](./assets/banner.svg)
```

## Known limitations

- **Camo:** `animateTransform`, `stroke-dashoffset` and some CSS transforms are hit or miss. Simple rotate and opacity effects are usually fine. Push and check before relying on anything.
- **Fonts:** only the Latin subset is fetched, and custom fonts stay at their regular weight. Templates use a monospace stack instead of an embedded font.
- **Mobile:** drag-and-drop reordering isn't touch-friendly yet. Use the arrow buttons.

## Development

```bash
git clone https://github.com/MohabHindawy/readme-kit.git
cd readme-kit
npm install
npm run dev
```

### Adding a template

Drop a file in `src/templates/` exporting an object with `id`, `name`, `desc`, plus `defaults()`, `sanitize(raw)`, `generate(config)`, `alt(config)` and an `Editor` component. Register it in the `TEMPLATES` list in `src/templates/index.js`. Reuse helpers from `shared.jsx` where you can.

## Contributing

Issues and PRs welcome. Keep new effects and templates CSS or SMIL only (no `<script>`) so they have a chance of surviving GitHub's proxy.

## License

MIT. See `LICENSE`.
