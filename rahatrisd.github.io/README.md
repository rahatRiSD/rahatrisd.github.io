# Atlas — AI Company Knowledge Assistant

A single-page product site for an AI knowledge assistant built for offices and
growing teams. Upload company documents, ask questions in plain language, get
answers that always name the file, page and revision they came from.

**Live site:** https://rahatrisd.github.io

Designed & built by [rahatRiSD](https://github.com/rahatRiSD).

---

## What's on the page

| Section | What it does |
| --- | --- |
| Hero | Live WebGL knowledge graph — 320 document nodes on a rotating shell, ~520 proximity-linked edges, a wireframe assistant core, and query pulses travelling outward. Parallaxes with the cursor. |
| Document stack | CSS 3D layered document cards with a slow ambient drift. |
| Ask console | Five real questions. Click one and the answer types out, then source chips (file + page/clause) animate in with a retrieval-confidence meter. The last question deliberately returns low confidence to show honest failure. |
| How it works | The three ingest passes: read and split, connect the pieces, retrieve and cite. |
| Capabilities | Six cards that tilt in 3D under the cursor, icon and text on separate depth planes. |
| Offices | Per-office table with live / syncing / onboarding states, plus counters that animate into view on scroll. |

## Tech

- One self-contained `index.html` — no build step, no bundler, no dependencies to install
- [Three.js r128](https://threejs.org/) from cdnjs for the WebGL scene
- Google Fonts: Sora (display), IBM Plex Sans (body), IBM Plex Mono (data), Caveat (signature)
- Light and dark themes via CSS custom properties, following the visitor's system setting
- Responsive down to ~360px; honours `prefers-reduced-motion`

## Files

```
rahatrisd.github.io/
├── index.html    the entire site
├── 404.html      styled not-found page
├── .nojekyll     tells GitHub Pages to serve the files as-is
├── LICENSE       MIT
└── README.md     this file
```

## Deploying

This repo is named `rahatrisd.github.io`, which makes it a GitHub **user site** —
it serves from the root domain automatically.

1. Push these files to the `main` branch
2. **Settings → Pages** → Source: *Deploy from a branch* → Branch `main`, folder `/ (root)` → Save
3. Wait 1–2 minutes, then open https://rahatrisd.github.io

### Using your own domain later

Add a file named `CNAME` at the root containing just your domain (for example
`rahatrisd.com`), point an `ALIAS`/`A` record at GitHub's Pages IPs, then set the
custom domain in **Settings → Pages** and tick *Enforce HTTPS*.

## Editing the content

Everything is plain HTML and JS near the bottom of `index.html`:

- `QA` array — the sample questions, answers, sources and confidence scores
- `data` array in the capability-cards block — the six feature cards
- The offices `<table>` — office names, headcount, document counts and index state
- `N`, `maxD` and `palette` in the WebGL block — node count, link distance and graph colours

## License

MIT — see [LICENSE](LICENSE).
