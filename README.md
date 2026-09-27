# Shaders Hero Section

A full-screen hero-section concept built around real-time GPU shader effects — an animated `MeshGradient` shader background with a pulsing circle accent, glassmorphism badge, serif display headline, and CTA buttons. Built with Next.js and Paper Design's `@paper-design/shaders-react`. Pure front-end demo; fully static-export ready.

## What it does

- Renders a full-viewport hero with an animated mesh-gradient shader canvas (`shader-background.tsx`).
- Overlays marketing content: glass-effect badge ("✨ New Paper Shaders Experience"), large serif headline ("Beautiful Shader Experiences"), supporting copy, and CTA buttons (`hero-content.tsx`).
- Includes a site header (`header.tsx`) and an animated `pulsing-circle.tsx` accent element.
- All animation is client-side (WebGL shaders + CSS); no backend, no API routes.

## Features

- Real-time `MeshGradient` WebGL shader background (animated, interactive lighting feel)
- Glassmorphism badge with SVG filter effect
- Serif display typography for the headline
- Pulsing circle accent component
- Responsive full-screen layout (Tailwind CSS)
- Dark aesthetic with shadcn/ui primitives
- Fully client-side — no backend, static-export ready

## Tech stack

| Layer      | Technology                          |
|------------|-------------------------------------|
| Framework  | Next.js 15 (App Router)             |
| UI         | React 19, TypeScript                |
| Shaders    | @paper-design/shaders-react (WebGL) |
| Styling    | Tailwind CSS 3.4, tailwindcss-animate |
| Components | shadcn/ui (Radix UI primitives), Lucide icons |
| Theming    | next-themes                         |
| Analytics  | @vercel/analytics                   |

## Quick start

Requirements: Node.js 18+ and pnpm (or npm).

```bash
# install dependencies
pnpm install

# start the dev server
pnpm dev
# open http://localhost:3000

# production build (static export into ./out)
pnpm build
```

If peer-dependency conflicts block npm installs, use `npm install --legacy-peer-deps`.

## Project structure

```
app/
  page.tsx                  # entry: composes header + hero
  layout.tsx                # root layout (fonts, metadata, theme)
  globals.css               # Tailwind + global styles
components/
  header.tsx                # top navigation bar
  hero-content.tsx          # headline, badge, copy, CTAs
  shader-background.tsx     # MeshGradient shader canvas
  pulsing-circle.tsx        # animated accent circle
  theme-provider.tsx        # next-themes wrapper
  ui/                       # shadcn/ui primitives
lib/
  utils.ts                  # cn() helper
public/                     # static assets
styles/                     # additional stylesheets
```

## Customizing

- **Background:** edit the shader props in `components/shader-background.tsx` (colors, speed, distortion).
- **Copy/CTAs:** edit `components/hero-content.tsx` — headline, badge text, buttons.
- **Header:** edit `components/header.tsx`.

## Environment variables

None required. The page is fully client-side with no secrets.

## Deployment

The page has no server-side code and is exported as a static site (`output: 'export'` in `next.config.mjs`):

```bash
pnpm build   # emits a static site into ./out
```

Deploy the `out/` directory to any static host (GitHub Pages, Cloudflare Pages, Netlify).

> **Note on `basePath`:** `next.config.mjs` currently sets `basePath: '/shaders-hero-section'` because this project is hosted under a GitHub Pages subpath (`https://girishlade111.github.io/shaders-hero-section`). If you deploy to a domain root (Vercel, custom domain), remove the `basePath` line before building.

## License

Free to use and modify.

---

Built by Girish Lade · https://ladestack.in
