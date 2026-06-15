# LYF4Kids Website — Launch Checklist

## Before You Go Live

Use this checklist before publishing LYF4Kids.org to the public.

---

## Content Checks

- [ ] All 22 pages load correctly (see route table in README_UPLOAD_TO_HOSTINGER.md)
- [ ] No Pretty2Me content anywhere on the site
- [ ] No old Hostinger or Codex content anywhere
- [ ] LYF4Kids logo appears in the navbar on every page
- [ ] All YouTube buttons link to: `https://www.youtube.com/@Lyf4kids`
- [ ] LYF Robot Stories page — all 10 stories listed with correct titles and SEL skills
- [ ] 72 Books Library — all 4 series showing with filters working
- [ ] Store — LYF4Kids products only (no Pretty2Me products)

---

## Navigation Checks

- [ ] Navbar shows: Home, Books, LYF Robot Stories, Activities, Feelings, Mindfulness, Games, Wonderhood, Curriculum, Music, Videos
- [ ] Mobile hamburger menu opens and closes
- [ ] All nav links navigate to the correct page
- [ ] Logo clicks back to Home
- [ ] "Get Started" → Educators page
- [ ] Back button works (hash routing)

---

## Interactive Features

- [ ] Activities Dashboard — Feeling Check-In responds to taps
- [ ] Quest Path — nodes animate on hover
- [ ] Wonder-Meter progress bar animates on load
- [ ] Breathing Lab — balloon animation starts and stops
- [ ] Happy Feeling — textarea reflection works, affirmations respond to tap
- [ ] Mood Check button shows success state
- [ ] Feelings Wheel page — Happy links to /feelings/happy
- [ ] Daily Challenge button is clickable

---

## Forms (Frontend Only)

- [ ] Contact form — all fields visible
- [ ] Educator Preview form — visible on Educators page
- [ ] Parent Starter Kit form — visible on Parents page
- [ ] App Early Access form — visible on App page
- [ ] Partner inquiry form — visible on Partner page
- [ ] Camp inquiry form — visible on Camps page
- [ ] Mindfulness newsletter — shows success state on submit

---

## Images & Assets

- [ ] LYF4KIDS colorful logo shows in navbar
- [ ] Roots of LYF album art shows on Music page
- [ ] Wonderhood Adventures group photo shows on Wonderhood page
- [ ] Hearte Family photos show on Hearte Family page
- [ ] Character images show on Hearte Family and Games pages
- [ ] LYF Robot images show on LYF Robot Stories page
- [ ] No broken image placeholders visible

---

## Before Hostinger Upload

- [ ] Run build: `node artifacts/lyf4kids/build-hostinger.mjs`
- [ ] Confirm `dist/public/index.html` exists
- [ ] Confirm all image assets are in `dist/public/assets/`
- [ ] Zip created: `LYF4Kids-Website-Hostinger-Upload.zip`
- [ ] Zip size is reasonable (under 30MB)

---

## Post-Upload Checks

- [ ] Visit your domain — homepage loads
- [ ] Click through 5–6 pages using nav links
- [ ] Test on mobile (or use browser mobile view)
- [ ] Test one form submission — success state shows
- [ ] Test one YouTube button — opens in new tab at correct channel
- [ ] Check that hash routing works (no 404 pages when navigating)

---

## Future Integration Tasks (Not Required for Launch)

- [ ] Connect contact form to email (Formspree, Netlify Forms, or similar)
- [ ] Add Google Analytics or Plausible for traffic tracking
- [ ] Connect payment links when ready (Stripe, Square, etc.)
- [ ] Add real audio embeds when Roots of LYF is distributed
- [ ] Add real video embeds when LYF Robot Stories are produced
- [ ] Set up email list (Mailchimp, ConvertKit, etc.) for newsletter forms

---

*LYF4Kids by LYF Matters Globally — Loving Yourself First*
