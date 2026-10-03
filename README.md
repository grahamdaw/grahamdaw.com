# grahamdaw.com

My personal site, because the domain should have something. A static [Astro](https://astro.build) site: a name, a short bio, three links, and a buoy bobbing in the background. Light and dark mode.

## Run it

```bash
bun install
bun run dev        # http://localhost:4321
bun run build      # static output in dist/
bun run preview    # serve dist/ locally
```

Use `bun run build`, not `bun build` (that is Bun's own bundler).

## Edit content

Name, bio and links live in `src/data/site.ts`. Check the GitHub and LinkedIn URLs there.

## Layout

| Path                               | What it is                                          |
| ---------------------------------- | --------------------------------------------------- |
| `src/pages/index.astro`            | The page                                            |
| `src/layouts/Base.astro`           | `<head>`, fonts, saved-theme script                 |
| `src/components/Buoy.astro`        | The animated buoy (inline SVG + CSS, no JavaScript) |
| `src/components/ThemeToggle.astro` | Light/dark toggle, remembers the choice             |
| `src/styles/global.css`            | Colour tokens for both themes, type, layout         |
| `src/data/site.ts`                 | Name, bio, links                                    |
| `public/favicon.svg`               | Favicon                                             |

## Theme

Dark mode follows the system setting until the visitor uses the toggle. The tokens are in `src/styles/global.css` (`--buoy`, `--ink`, `--bg` and so on). Reduced-motion users get a still buoy.

## Code quality

Biome handles lint and format (`bun run check`). Biome's Astro support is experimental, so it is switched on in `biome.json`.

## Deploy

`bun run build` produces plain static files in `dist/`. Any static host works (S3 + CloudFront, Netlify, Cloudflare Pages). The site URL is set in `astro.config.mjs`.
