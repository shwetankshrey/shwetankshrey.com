# shwetankshrey.com

personal site. astro + markdown, deployed on cloudflare pages.

## stack

- **framework**: astro (latest stable) with the mdx integration.
- **hosting**: cloudflare pages, deployed from `main`.
- **content**: markdown files under `src/content/essays/`.
- **fonts**: crimson pro (serif) + ibm plex mono (mono), via google fonts.

## local dev

```bash
npm install
npm run dev      # localhost:4321
npm run build    # static output → dist/
npm run preview  # serve dist/
```

requires node ≥ 22.12.

## adding an essay

1. drop a markdown file into `src/content/essays/<slug>.md`.
2. frontmatter:

```yaml
---
title: the essay title
deck: one-line summary, optional
date: 2026-05-24
draft: false
---
```

3. body in plain markdown. mdx works too (rename to `.mdx`) if you need to embed components.

essays show up at `/essays/<slug>`. listing on `/essays` is currently a stub — wire it to `getCollection('essays')` when you're ready to publish.

## design constraints (locked)

- **typography**: crimson pro + ibm plex mono only.
- **palette**: midnight bg `#040810`, warm cream ink `#ECE3D2`, amber accent `#E0B660`. single accent.
- **lowercase commit**: every visible word lowercase, including own name, company names, acronyms.
- **no animations, no analytics, no third-party scripts.**
- **sidenote system**: `<Sidenote n="1">…</Sidenote>` inside a `.prose` block. body marker uses `<a class="fn">1</a>`.

see `inbox/website-build-requirements-2026-05-24.md` in the vault for the full brief.

## deploy

cloudflare pages auto-builds on push to `main`. dns lives on cloudflare; full tls on.

build command: `npm run build`. output: `dist/`.
