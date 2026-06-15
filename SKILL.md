---
name: lyf4kids-site
description: Rules, conventions, and non-obvious decisions for the LYF4Kids.org static website built in this workspace. Load when working on the LYF4Kids website — any page update, new page, build, zip, or asset integration. Prevents common mistakes with routing, images, PDF generation, and branding.
---

# LYF4Kids Website Skill

## When to Use

- Any page, component, or route change in `artifacts/lyf4kids/`
- Rebuilding the Hostinger zip
- Adding new content, characters, or product pages
- Adding downloadable PDFs or printable pages

---

## Project Identity

**Product:** LYF4Kids.org public website — story-first SEL for children ages 4–12  
**Organization:** LYF Matters Globally  
**Brand tagline:** Loving Yourself First  
**NO Pretty2Me content anywhere on this site — ever.**

---

## Stack

- React + Vite + TypeScript in `artifacts/lyf4kids/`
- Tailwind CSS v4 (`@tailwindcss/vite`)
- Framer Motion for animations
- Wouter with **hash routing** — use `useHashLocation` from `wouter/use-hash-location`
- All images imported via `@assets/` alias pointing to `/attached_assets/`

## Hash Routing — Critical

All navigation uses hash routing for static hosting (`/#/books`, `/#/lyf-robot-stories`, etc.).  
**`<Link href="/books">` NOT `<Link href="/#/books">`** — wouter handles the hash prefix.  
Back button works. No `.htaccess` needed on Hostinger.

---

## Image Imports

Images in `attached_assets/` must be imported via the `@assets/` alias:

```tsx
import coverImg from "@assets/ChatGPT_Image_May_8,_2026,_06_30_29_AM_1780070038891.png";
```

**Never reference `attached_assets/` as a URL path** — the folder is not served by the web server.

---

## Printable PDF Pages

Printable pages use `window.print()` + CSS `@page` / `@media print` rules.  
No backend PDF library needed.

Pattern:
1. Each page gets a `useEffect` that injects a `<style>` tag with `@page { size: letter portrait; margin: 0.5in; }` and `@media print { .no-print { display: none; } .print-page { page-break-after: always; } }`
2. A sticky "Print / Save as PDF" button calls `window.print()`
3. Pages render as 816px × 1056px divs (letter @ 96dpi) in browser; browser print dialog saves as PDF

Routes added in `App.tsx`:
- `/#/printable/activity-pack` → `PrintableActivityPack.tsx`
- `/#/printable/coloring-book` → `PrintableColoringBook.tsx`

---

## Building the Hostinger Zip

Run from workspace root:
```bash
node artifacts/lyf4kids/build-hostinger.mjs
```

- Uses `configFile: false` (bypasses `vite.config.ts` which requires PORT)
- Sets `base: "./"` for static file hosting
- Uses `adm-zip` (Node.js) — `zip` binary is not installed in this environment
- Output: `LYF4Kids-Website-Hostinger-Upload.zip` in workspace root

---

## All 22 + 2 Routes

| Route | Page |
|---|---|
| `/` | Home |
| `/books` | 72 Books Library |
| `/lyf-robot-stories` | LYF Robot Stories |
| `/activities` | Activities Dashboard |
| `/feelings` | Feelings |
| `/feelings/happy` | Happy Feeling |
| `/mindfulness` | Breathing & Mindfulness |
| `/games` | Games & Activities |
| `/wonderhood` | Wonderhood Adventures |
| `/hearte-family` | The Hearte Family |
| `/curriculum` | Curriculum |
| `/music` | Music |
| `/videos` | Videos |
| `/store` | Store |
| `/parents` | Parents |
| `/educators` | Educators |
| `/camps` | Camps |
| `/app` | App Early Access |
| `/partner` | Partner |
| `/contact` | Contact |
| `/privacy` | Privacy |
| `/terms` | Terms |
| `/printable/activity-pack` | Printable Activity Pack (10 worksheets) |
| `/printable/coloring-book` | LYF Robot Coloring Book (15 pages) |

---

## Design System

```
Background: #FFF7EC (cream)
Deep plum heading: #3E2437
Mauve/subtext: #8E5A6F
Body text: #504347
Muted: #827378
Border: #E8E5E1

Blue: #72C7E7    Green: #7BC47F    Gold: #F6C85F
Purple: #BFA7F2  Pink: #D9899E    Orange: #FF7A6B
```

Fonts: Poppins (headings/UI), Nunito Sans (body), Fraunces (pull quotes)

---

## Content Sources of Truth

- 10 LYF Robot Stories: `attached_assets/LYF4Kids_10_Short_Stories_1780069943992.pdf`
- LYF Robot Coloring Book (15 robots): `attached_assets/LYF_Robot_Coloring_Book_Starter_1780085635412.docx`
- Hearte Family: `attached_assets/ChatGPT_Image_May_2,_2026,_03_36_58_PM_(1 & 2)_...png`
- Wonderhood Adventures: `attached_assets/ChatGPT_Image_May_2,_2026,_06_50_42_AM_(3)_...png` and `May_4_...png`
- Character images: 11 diverse child character PNGs starting with `1776458148239_...` through `1777659706620_...`
- YouTube: always link to `https://www.youtube.com/@Lyf4kids`

---

## Common Mistakes to Avoid

1. **Don't use `zip` binary** — use `adm-zip` in build script
2. **Don't hardcode ports** — Vite reads `PORT` env var from workflow
3. **Don't add `/` prefix to hash routes** — wouter handles it
4. **Don't import from `attached_assets/` as URL** — use `@assets/` import alias
5. **Don't include Pretty2Me content** — separate product, not on this site
