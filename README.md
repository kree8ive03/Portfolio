# Kaycee Nwachukwu - Portfolio

Static site. No build step, no dependencies, no framework.

## Deploying

Push this folder to GitHub, import the repo on Vercel, accept the defaults.
Vercel serves `folder/index.html` at `/folder`, so the URLs come out clean
with no rewrite rules:

| File | URL |
|---|---|
| `index.html` | `/` |
| `projects/index.html` | `/projects` |
| `projects/penchant-signature/index.html` | `/projects/penchant-signature` |

`vercel.json` only sets `cleanUrls` and disables trailing slashes. It is optional.

## Structure

```
.
├── index.html                  landing
├── projects/
│   ├── index.html              all work
│   ├── penchant-signature/
│   ├── bubblebee/
│   ├── kree8studios/
│   ├── pearl-uvo/
│   ├── dfx-gadgets-hub/
│   ├── stellas-kitchen/
│   ├── nike-sneakers-store/
│   └── netflix/
├── assets/
│   ├── img/                    38 WebP files, shared across pages
│   └── Kelechi-Nwachukwu-Product-Designer-CV.pdf
├── vercel.json
└── README.md
```

## Replacing a placeholder image

Placeholders are dashed boxes that name the shot they need:

```html
<div class="ph" data-label="penchant-homepage - shot needed (full homepage render)"></div>
```

Export the image as WebP, drop it in `assets/img/`, and replace the whole div:

```html
<img src="/assets/img/penchant-homepage.webp" alt="Penchant Signature homepage" loading="lazy" />
```

Alt text is not optional. Every carousel and card image needs one.

## Conventions

- **Hyphens only.** No em or en dashes anywhere, in copy or comments.
- **Oxford spelling.** `-ize` endings with British word forms: *monetization*, *colour*.
- **Design tokens** live in `:root` at the top of every file. Colour, type and
  spacing are all variables. Change them in one place per page.
- **Carousels** auto-scroll when the track carries `data-autoscroll`. Speed is
  overridable per track with `data-autoscroll="20"`.
- **Case study sections** carry `data-title`, which is what builds the floating
  section menu. A section without one will not appear in it.

## Adding a case study

1. Copy any folder under `projects/`
2. Replace the header block, hero gallery, TL;DR (always exactly four rows) and sections
3. Update the two related cards at the foot, and check nothing links to itself
4. Add the card to `index.html` and `projects/index.html`

## Known gaps

- Cover art missing: Penchant Signature, BubbleBee, Pearl Uvo, Kree8Studios
- Body screenshots missing: BubbleBee, Kree8Studios
- The About mosaic runs two portraits. Six-tile CSS is retained for when the rest arrive
- Kree8Studios has no live or prototype URL yet
- CV should be reworded so the BubbleBee figure reads as a subset, then replaced here
