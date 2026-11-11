# BloodLink — exact prompt used

This is the prompt submitted with the entry. Paste it verbatim into the submission form.

---

```
ROLE
You are a senior product designer and front-end engineer who has shipped
health-sector web products. You care about typography, restraint and
accessibility more than decoration.

TASK
Build a single-page homepage prototype for "BloodLink", a platform that
connects voluntary blood donors, hospitals and authorised blood banks. This is
a design prototype for a prompt-engineering challenge — not a working medical
service. Output one self-contained index.html with all CSS and JS inline. No
build step, no npm, no CDN, no external fonts, no external images: every icon
must be inline SVG and every illustration must be CSS or SVG. It must open by
double-clicking the file and deploy unchanged to Netlify, Vercel or GitHub
Pages.

BRAND
Name: BloodLink. Tagline: "Every Drop Connects a Life."
Personality: calm and clinical, not a charity campaign. Confident, precise,
quietly urgent. It should feel like infrastructure a hospital would trust, not
a donation drive poster.
Identity rules:
- Editorial serif for headlines (Georgia / Iowan Old Style stack), clean
  sans-serif for UI, monospace for blood groups and numeric data.
- Palette: warm off-white paper (#FBF7F3), near-black ink with a plum bias
  (#150E13), one blood red (#C4162E), deep plum (#3B1030), and small doses of
  clinical green (#1B6E4E) and amber (#A85B12) used only for stock status.
- No gradients as decoration, no emoji, no stock photography, no drop-shadow
  soup. Depth comes from hairline borders and soft low-opacity shadows.
- Blood groups always render in monospace with the proper minus sign (O−, not
  O-). This is a detail that signals care.

SECTIONS — build all seven, in this order

1. STICKY NAV + HERO
   - Logo mark: a red droplet inside a thin pulsing ring.
   - Nav links: Find a donor, Urgent requests, Blood banks, Learn, Our impact.
     Right side: "Find blood" (ghost) and "Become a donor" (solid red).
   - Hero headline: "Every drop connects a life" with "a life" in italic red
     and a hand-drawn SVG underline that animates as if being drawn.
   - Sub-headline explaining the coordination problem in one or two sentences.
   - Two CTAs. Below them a live-status line with a pulsing green dot:
     "41 verified requests open across 6 cities right now · Demo data".
   - A thin animated ECG trace across the bottom of the hero.
   - HERO COMPONENT (the signature idea): a "Compatibility" card that is a real
     working ABO/Rh tool. Eight blood-group buttons; selecting one shows two
     rows — "Can receive from" and "Can donate to" — as animated monospace
     pills, plus live counts ("1 group" / "All 8 groups"). Use medically
     correct rules: O− receives only O− and donates to all eight; AB+ receives
     from all eight and donates only to AB+. Add a footnote saying a clinician
     confirms before transfusion. This must actually work, not be a picture.

2. TRUST BAR
   Four inline items with small SVG icons: ID-verified donors only; requests
   checked by partner hospitals; median match time under 40 minutes; 12,480
   voluntary donors registered.

3. FIND A DONOR
   - Filter bar: blood-group chips (All groups, O−, O+, A−, A+, B−, B+, AB+)
     and a city select (Bengaluru, Mumbai, Pune, Hyderabad, Chennai, Delhi NCR).
   - Live result count above the grid, updating with the filters.
   - Grid of 12 fictional donors. Each card: initials avatar, name, area and
     city, distance in km, monospace blood-group badge, "Last donated N days
     ago", a status line with a coloured dot ("Available this week" in green /
     "Next eligible in N days" in amber), and a Send request button.
   - Donors inside the 90-day window render with a disabled button reading
     "Unavailable" — visible but not actionable.
   - Filtering must genuinely work and show a designed empty state.
   - Invent plausible Indian names and localities. Use synthetic names only.

4. URGENT REQUESTS (dark section)
   - Inverted near-black background with a subtle red radial glow.
   - Four request cards, each with a green "Hospital verified" badge with a
     check icon, hospital name, city and department, an urgency label with a
     pulsing dot (Critical / High / Routine), the needed blood group in
     monospace, a progress bar showing units collected vs needed (e.g. 4/6),
     "still needed" arithmetic, time raised, and a Respond button.
   - Invent hospital names. Do NOT use real hospital names.

5. BLOOD BANK NETWORK
   - A vertical directory of five authorised centres. Each row: building icon,
     name, a type tag (Licensed bank / Hospital), city and distance, opening
     hours, and a stock strip of all eight blood groups colour-coded
     healthy / low / critical.
   - Include a legend explaining the three stock states.

6. DONATION AWARENESS
   - Two columns. Left: an interactive eligibility checklist of five items with
     real criteria (18–65 years, 50 kg+, 90 days since last donation, no fever
     in 14 days, ate and drank today). Rows are toggleable with checkboxes and
     keyboard support; a status line updates ("Looks good to donate" /
     "1 item to check at screening").
   - Right: a five-step walkthrough of what actually happens — screening,
     the 8–12 minute donation, rest, testing, recovery — with specific
     durations and volumes.
   - Below: five myth-vs-fact accordion items using <details>, each labelled
     Myth 01–05, with a factual correction that names the real reason.

7. OUR IMPACT + BECOME A DONOR + FINAL CTA
   - Four metric cards whose numbers count up when scrolled into view:
     12,480+ donors, 3,140 units matched, 38 min median match, 3 patients
     helped per unit.
   - A bar chart of donation mix by blood group (O+ 37%, B+ 32%, A+ 23%,
     AB+ 7%, O− 6%, A− 4%, B− 3%, AB− 1%), animated on reveal, with a caption
     explaining that O− is only 6% of collections but is the trauma default.
   - Registration form on a dark panel: full name, blood group, city, mobile,
     and last donation date. The form must validate required fields and, when a
     last-donation date under 90 days is entered, refuse the submission and
     compute the actual next-eligible date. On success, replace the form with a
     confirmation naming the donor's group and city. Add a reset action.
   - Closing CTA band: "The gap isn't willingness. It's coordination." with
     Become a donor, Find blood near me, and a Spread awareness button that
     uses the Web Share API with a clipboard fallback.

FOOTER
Four columns of links, and a clearly visible prototype disclaimer: all donors,
requests, hospitals and statistics are fictional demonstration data, no real
medical service exists, and the site must not be used to seek or offer blood.

BEHAVIOUR AND CRAFT REQUIREMENTS
- Responsive from 360px to 1440px+. Collapse the nav to a working hamburger
  below 860px, stack the donor grid to one column below 640px, and keep every
  tap target at least 44px.
- Smooth in-page scrolling, sticky nav that gains a hairline border on scroll.
- Motion should be brief and purposeful: card entry stagger, hover lift,
  progress bars filling, counters counting, the ECG loop, the underline draw.
- Honour prefers-reduced-motion: disable all of it.
- Accessibility: skip link, semantic landmarks, one h1, ordered headings,
  visible focus rings, aria-pressed on the blood-group chips, role="checkbox"
  with aria-checked on eligibility rows, aria-live on the results count and on
  toasts. Colour must never be the only carrier of meaning — pair it with text.
- All interactive elements must work with the keyboard alone.
- Use a single toast for transient feedback, hidden by default, announced
  politely. It must not be visible until triggered.
- No dark patterns, no fake urgency timers, no autoplaying audio.

QUALITY BAR
- Every visible string must be purposeful; no lorem ipsum, no placeholder text,
  no "TODO", no broken glyphs or tofu boxes.
- Content is visible by default. Do not gate section headings behind a
  scroll-reveal that could leave the page looking empty.
- Comment the non-obvious logic: the ABO matrices, the 90-day calculation, the
  count-up easing.
- Finish with a short list of what a real implementation would require
  (identity verification, hospital authorisation, consent, encryption,
  audit logging, medical review of copy).

Deliver only the complete index.html.
```
