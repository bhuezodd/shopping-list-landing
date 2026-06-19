# Shopping List by AI — Landing Page

Marketing landing page for the **Shopping List by AI** mobile app, built with
[Astro](https://astro.build/).

## Tech

- **Astro 5** — static site generation
- Vanilla CSS with design tokens that mirror the mobile app's dark / purple theme
  (see `src/styles/global.css`)
- No UI framework — fast, zero-JS by default

## Project structure

```
src/
  components/    Reusable sections (Header, Hero, Features, HowItWorks, Download, Footer)
  layouts/
    Layout.astro Shared page shell (head, header, footer). Use this for new pages.
  pages/
    index.astro  The landing page
  styles/
    global.css   Design tokens + base styles
public/
  favicon.svg
```

## Adding new pages (e.g. Privacy Policy, Terms & Conditions)

Create a file under `src/pages/` and wrap the content in the shared `Layout`.
The footer already links to `/privacy` and `/terms`:

```astro
---
import Layout from '../layouts/Layout.astro';
---

<Layout title="Privacy Policy — Shopping List by AI">
  <section class="container" style="padding-block: 72px;">
    <h1>Privacy Policy</h1>
    <!-- content -->
  </section>
</Layout>
```

`src/pages/privacy.astro` → `/privacy`, `src/pages/terms.astro` → `/terms`.

## Commands

This project uses [pnpm](https://pnpm.io/).

| Command         | Action                                   |
| --------------- | ---------------------------------------- |
| `pnpm install`  | Install dependencies                     |
| `pnpm dev`      | Start the dev server at `localhost:4321` |
| `pnpm build`    | Build the production site to `./dist/`   |
| `pnpm preview`  | Preview the production build locally     |

## Configuration notes

- Update `site` in `astro.config.mjs` with your production domain.
- Replace the placeholder Google Play URL in
  `src/components/Download.astro` once the app is published.
