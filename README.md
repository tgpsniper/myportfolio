# Portfolio — Avelino L. Legion Jr.

Personal portfolio site for **Avelino L. Legion Jr.** — software developer and data analyst,
15+ years across municipal government automation, GIS mapping, fiber ISP platforms and data analysis.

**Live site:** https://tgpsniper.github.io/myportfolio/

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole site — markup, styles and script in one file |
| `portrait.jpg` | Hero portrait, 516×688 |
| `orpheus-ui.jpg` | Orpheus interface shot used on the Platforms card, 1200×564 |

## Running it locally

Open `index.html` in any browser. There is no build step and nothing to install.

## How it's built

- **No framework, no dependencies.** One HTML file, roughly 900 lines including CSS and script.
- **Design language.** Laid out as a survey sheet, after the GIS work that runs through the
  career: a map-collar metadata strip, a keyed legend for the eleven LGU systems, and real
  municipal coordinates for each deployment.
- **Hero contour field.** Drawn on a `<canvas>` — value noise sampled on a grid, then marching
  squares traced at 22 thresholds with every fifth picked out as an index contour. Rendered once
  on load and redrawn on resize or theme change, so it costs nothing while the page sits idle.
- **Typography.** Archivo for headings, Source Serif 4 for body, IBM Plex Mono for coordinates,
  codes and dates — loaded from Google Fonts with local fallback stacks.
- **Theming.** Light and dark are both designed, not inverted. Colours are CSS custom properties
  defined on `:root`, redefined under `prefers-color-scheme: dark` and again under
  `[data-theme="dark"]` so the in-page toggle wins in either direction. The choice persists in
  `localStorage`.
- **Responsive** down to ~360px, with `prefers-reduced-motion` respected.

## Deployment

Publishing is automatic. `.github/workflows/deploy-pages.yml` runs on every push to `main`,
enables Pages if it isn't already on, and deploys the repo root. The site is live at the URL
above a minute or two after a push — no manual step, no branch to keep in sync.
