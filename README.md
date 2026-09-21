# Almena launch page

The page at almena.id until the platform opens: the mark, the name, the date
and a countdown to 11 November 2026. Nothing else — no copy, no links, no
explanation. Built with [Astro](https://astro.build) as a static site and
driven by [Task](https://taskfile.dev).

## Working on it

```
task dev      # http://localhost:4321
task check    # Astro templates and TypeScript
task build    # writes dist/
task preview  # serves dist/ the way the edge will
```

`task branding` refreshes `public/logo.png` and `public/favicon.png` from
`../assets/branding`, the only source of the mark.

## What is where

- `src/pages/index.astro` — the one page, and the countdown script with it.
- `src/styles/global.css` — the brand tokens (the logo's orange, the icon
  manifest's background) and everything drawn from them.
- `public/` — the mark and the favicon, served as they are.
- `dist/` — the build output, ignored by git. The edge serves it; routing and
  TLS are configured outside this repository.

## The countdown

The target is midnight in Madrid on the launch day, written once at the top
of the page's script as an ISO instant with its UTC offset, so every visitor
counts down to the same moment whatever their clock says. When it reaches
zero it stops at `00:00:00:00`; what replaces this page is the platform.
