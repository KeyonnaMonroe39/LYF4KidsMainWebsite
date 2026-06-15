# LYF4Kids Website — Hostinger Upload Instructions

## What You're Uploading

A complete 22-page static website for **LYF4Kids.org** — story-first SEL for children ages 4–12 by LYF Matters Globally.

All navigation uses **hash routing** (`/#/books`, `/#/lyf-robot-stories`, etc.) which works on any static host without server configuration.

---

## How to Upload to Hostinger

### Step 1 — Download the Zip
Download `LYF4Kids-Website-Hostinger-Upload.zip` from your Replit workspace.

### Step 2 — Log In to hPanel
1. Go to [hpanel.hostinger.com](https://hpanel.hostinger.com)
2. Click **Websites** → your LYF4Kids.org domain
3. Click **File Manager**

### Step 3 — Upload and Extract
1. Navigate into the `public_html` folder
2. Click **Upload** and select `LYF4Kids-Website-Hostinger-Upload.zip`
3. After upload completes, right-click the zip → **Extract**
4. If prompted, extract into `public_html` (not a subdirectory)

### Step 4 — Verify
Visit your domain. You should see the LYF4Kids homepage immediately.

---

## All 22 Pages

| Route | Page |
|-------|------|
| `/` | Home |
| `/#/books` | 72 Books Library |
| `/#/lyf-robot-stories` | LYF Robot Stories |
| `/#/activities` | Activities Dashboard |
| `/#/feelings` | Feelings |
| `/#/feelings/happy` | Happy Feeling Activity |
| `/#/mindfulness` | Breathing & Mindfulness |
| `/#/games` | Games & Activities |
| `/#/wonderhood` | Wonderhood Adventures |
| `/#/hearte-family` | The Hearte Family |
| `/#/curriculum` | SEL Curriculum |
| `/#/music` | Roots of LYF Music |
| `/#/videos` | Videos |
| `/#/store` | Store |
| `/#/parents` | Parents |
| `/#/educators` | Educators |
| `/#/camps` | Camps & Community Bundles |
| `/#/app` | App Early Access |
| `/#/partner` | Partner / Sponsor |
| `/#/contact` | Contact |
| `/#/privacy` | Privacy Policy |
| `/#/terms` | Terms of Use |

---

## No Backend Required

This site is 100% static HTML/CSS/JS. No PHP, no database, no Node.js.

- Hash routing: no `.htaccess` rules needed
- All videos link to: `https://www.youtube.com/@Lyf4kids`
- All forms are frontend-only with success states (no data is submitted)

---

## Need to Rebuild?

If you update the site in Replit, re-run the build script:

```bash
node artifacts/lyf4kids/build-hostinger.mjs
```

Then re-upload and re-extract the new zip.

---

## Support

Built by LYF Matters Globally. LYF4Kids.org only. No Pretty2Me content.
