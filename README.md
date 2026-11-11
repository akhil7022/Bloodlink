# BloodLink — Every Drop Connects a Life

A homepage prototype for the **AI Prompt Battle: BloodLink** challenge (CommunityX × OSCode).

> **Prototype notice.** All donors, requests, hospitals and statistics are fictional demonstration data. There is no donor matching, no hospital integration and no data is stored or transmitted. Do not use this site to seek or offer blood.

---

## What's included

| Section | What it demonstrates |
|---|---|
| **Find a Donor** | Filter 12 demo donors by blood group and city. Cards show distance, last donation date and availability; unavailable donors are disabled rather than hidden. Empty state included. |
| **Compatibility tool** | Live ABO/Rh calculator in the hero — tap a blood group, see who you can receive from and donate to. Runs on real transfusion rules. |
| **Urgent Requests** | Four hospital-verified request cards with urgency levels, units-needed progress bars and "respond" actions. |
| **Blood Bank Network** | Directory of licensed banks and hospital transfusion units with per-group live stock indicators (healthy / low / critical). |
| **Donation Awareness** | Interactive eligibility checklist, 5-step donation walkthrough, and a myth-vs-fact accordion. |
| **Our Impact** | Animated counters plus a blood-group donation-mix bar chart. |
| **Become a Donor** | Registration form with a real 90-day-gap eligibility calculation against the last donation date. |
| **Take Action** | Primary CTAs in the nav, hero, final CTA band and footer, plus a share button using the Web Share API. |

**Technical:** one self-contained `index.html`. No build step, no npm, no CDN, no external fonts or images. All icons are inline SVG. Works offline once loaded.

---

## Deploy in 2 minutes

### Option A — Netlify Drop (easiest, no account needed to test)

1. Go to <https://app.netlify.com/drop>
2. Drag the folder containing `index.html` onto the page.
3. Netlify returns a live URL like `https://bloodlink-xyz123.netlify.app`.
4. Optional: sign in to claim the site and rename it to something like `bloodlink-prototype.netlify.app`.

No configuration required — it is static HTML with no build command.

### Option B — GitHub Pages

```bash
# 1. create the repo on GitHub first (name it: bloodlink), then:
mkdir bloodlink && cd bloodlink
# copy index.html and README.md here
git init
git add index.html README.md
git commit -m "BloodLink: homepage prototype for AI Prompt Battle"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/bloodlink.git
git push -u origin main
```

Then: **Settings → Pages → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
Live at `https://YOUR-USERNAME.github.io/bloodlink/`.

### Option C — Vercel

```bash
npm i -g vercel
cd bloodlink
vercel --prod
```

Framework preset: **Other**. Build command: none. Output directory: `.`

---

## Submission checklist

- [ ] Live URL loads over HTTPS and is publicly accessible (test in a private/incognito window)
- [ ] GitHub repo is public
- [ ] Exact prompt pasted (see `PROMPT.md`)
- [ ] Screenshots uploaded — desktop + mobile
- [ ] AI tools listed
- [ ] LinkedIn post published with @OSCode and @CommunityX tags

Test your live URL in an incognito window before submitting. A link that works only while you are logged in will fail evaluation.

---

## Files

```
index.html    the entire site — styles, markup and scripts
README.md     this file
PROMPT.md     the exact prompt used
```

---

## Accessibility notes

- Semantic landmarks (`header`, `main`, `section`, `footer`), one `h1`, ordered heading levels.
- Skip-to-content link, visible `:focus-visible` rings on every interactive element.
- Blood-group chips and eligibility rows use `aria-pressed` / `role="checkbox"` with `aria-checked`, and are keyboard operable (Space/Enter).
- `aria-live` regions on the donor grid and toast so filter results are announced.
- Full `prefers-reduced-motion` support: all animation, counters and smooth scrolling collapse to instant.
- Colour is never the only signal — status uses text plus a dot, stock uses text labels in the legend.

## Browser support

Chrome, Edge, Firefox, Safari (current and previous major). Uses `IntersectionObserver`, `navigator.share` and `backdrop-filter` with graceful fallbacks for each.
