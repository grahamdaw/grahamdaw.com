# AGENTS.md

Static Astro site for grahamdaw.com. Keep it small.

- Package manager: bun. Use `bun run build` (not `bun build`).
- Lint and format: `bun run check` (Biome). Run it before committing.
- Content (name, bio, links) is in `src/data/site.ts`. Do not hard-code it in pages.
- Colours come from CSS variables in `src/styles/global.css`. Both themes must work: check light and dark after any visual change.
- The buoy animation is CSS only. The rope follows the knot on the ring, so the bob, rock and rope animations share one 4s cycle. If you change the buoy shape or motion, recompute the rope keyframe in `Buoy.astro`.
- Respect `prefers-reduced-motion`.
- Fonts are self-hosted via `@fontsource`. Do not add external font requests.
