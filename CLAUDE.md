# Personal Webpage - Project Guidelines

## Purpose
Personal webpage for Petr Dvořáček. Keep it minimal and maintainable.

## Tech Stack
- **HTML** - semantic, accessible markup
- **CSS** - inline in `<style>` block or separate `style.css` if it grows
- **JavaScript** - only if needed for interactivity, no frameworks

## Principles
- No build tools, no npm, no frameworks
- Single `index.html` is preferred until complexity demands otherwise
- Fast loading, works without JavaScript enabled
- Mobile-responsive using simple CSS (flexbox/grid, media queries)

## File Structure
```
index.html      # main (and possibly only) page
style.css       # optional, only if styles get large
script.js       # optional, only if JS is actually needed
assets/         # images, fonts if needed
```

## Style Guidelines
- Use semantic HTML5 elements (`<header>`, `<main>`, `<section>`, `<footer>`)
- Prefer system fonts to avoid loading external fonts
- Keep color palette simple (2-3 colors max)
- Ensure sufficient contrast for accessibility

## Hosting
Static hosting (GitHub Pages, Netlify, Cloudflare Pages) - all free for static sites.

---

## Bad examples (patterns) of developer personal pages

* **A wall of buzzwords with no proof**
  * "AI / Web3 / Cloud / Blockchain / Full-stack ninja" with nothing concrete: no shipped work, no repos, no demos, no numbers.
* **Portfolio screenshots with no context**
  * Pretty tiles, but no "what was the problem, what did you do, what was the impact, what's the tech, what would you improve?"
* **"Under construction" or stale content**
  * Blog last updated 2019, "currently learning Rust" for 4 years, broken "recent work" section.
* **CV dump as a webpage**
  * A long resume pasted into HTML with no narrative, no prioritization, no scannability.
* **Dark-pattern UX**
  * Autoplay video, sound on load, forced newsletter popups, full-screen "cookie wall" for a static page.
* **Unreadable design**
  * Low contrast, tiny font, excessive motion, parallax everywhere, neon on black without accessibility, or massive hero area that hides the content.
* **"Look at my tech stack" over "look at my work"**
  * A huge icon grid of tools and frameworks but nothing that demonstrates competence.
* **Overly clever navigation**
  * "Terminal website" that requires commands to find your email, or non-standard scrolling that breaks back button and deep linking.

## Common mistakes developers make

### Content & positioning

* **No clear one-liner**
  * Readers can't answer "who are you and what do you do?" in 5 seconds.
* **No target audience**
  * A hiring manager, a potential client, and an OSS collaborator all need slightly different cues. Many pages satisfy none.
* **Missing impact**
  * Lists tasks instead of outcomes (latency reduced, costs lowered, reliability improved, conversion improved, etc.).
* **Too much personal identity, too little professional signal**
  * Or the opposite: robotic and generic. The problem is imbalance.
* **Not showing decision-making**
  * Good pages reveal judgment: tradeoffs, constraints, what you optimized for.

### Proof & credibility

* **No demos / no links**
  * No live project, no GitHub, no papers, no talks—nothing verifiable.
* **Broken links and 404s**
  * Especially to featured work. This is a credibility killer.
* **Unverifiable claims**
  * "Built scalable systems" without scale, traffic, SLOs, or at least concrete scope.
* **No way to contact you**
  * Or contact is hidden behind a form with captcha; or only a social network.

### UX & accessibility

* **Performance negligence**
  * 20MB of images, heavy JS for a static page, slow fonts, huge animations.
* **Poor mobile experience**
  * Fixed-width layout, hover-only interactions, tiny tap targets.
* **Accessibility omissions**
  * No semantic headings, no alt text, low contrast, focus traps, no keyboard navigation.
* **Over-animated**
  * Motion that distracts or triggers motion sensitivity; no "reduced motion" respect.

### Security & privacy

* **Exposing personal data unnecessarily**
  * Home address, phone number, personal email without spam protection, embedded calendars.
* **Over-tracking**
  * Marketing trackers, session replay, fingerprinting on a personal site. Signals poor judgment.
* **Contact form that leaks**
  * Misconfigured form endpoints, exposed API keys in frontend, public analytics dashboards.

### Professionalism & tone

* **Unforced unprofessional content**
  * Rants about previous employers/clients, edgy jokes, divisive hot takes—unless your brand explicitly depends on that (and you accept the tradeoff).
* **Aggressive "hire me" without substance**
  * Strong ask is fine; strong ask with weak evidence looks needy.
* **Typos and sloppy details**
  * For a developer page, these are often interpreted as engineering sloppiness.

## What not to do (concrete "don't" list)

* Don't make people hunt for: **name, role, location/timezone (optional), and contact**.
* Don't lead with a **100vh hero** that says nothing.
* Don't use **autoplay** (video/audio), forced modals, or heavy tracking.
* Don't list **every tool you've touched**. Curate.
* Don't publish **confidential work** (screenshots, client names, internal metrics) without permission.
* Don't claim expertise in **everything**. Pick a focus and show evidence.
* Don't ship with **broken links**, missing favicons/meta tags, or uncompressed assets.
* Don't ignore **mobile + performance + accessibility**; your page is an implicit code sample.

## Checklist for a good dev personal page

* Above the fold: **one-liner**, **top 2–3 strengths**, **1 featured project**, **contact**.
* For each project: **problem → constraints → your role → solution → outcome → links**.
* Add proof: **repo/demo**, **writeups**, **talks**, **OSS contributions**, or **case studies**.
* Basics: **fast**, **mobile-first**, **accessible**, **minimal tracking**, **working links**.

---

## Fonts on a developer personal page

### How many fonts

* **Best default: 1 font family** (plus system fallback). Use **weights** (400/500/700) and **sizes** to create hierarchy.
* **Common safe: 2 families max**
  * Example: **sans for UI/body** + **mono for code** (mono can be your second family).
* **Avoid: 3+ families** on a small personal site. It usually looks inconsistent and increases load/perf cost.

Rule of thumb:

* **Body**: 1 family
* **Code**: 1 mono family (optional, can be system-mono)
* **Headings**: same as body (preferred) or a second family (only if it clearly improves the look)

### What matters more than count: consistency

* Keep a **small set of tokens**:
  * **Font families**: 1–2
  * **Weights**: 2–3 (e.g., 400, 600, 700)
  * **Base size**: 16–18px (or equivalent)
  * **Line-height**: ~1.5–1.7 for body text
* If you have many styles, people will perceive it as visual noise even if it's technically "one font".

## How to handle fonts well (practical)

### 1) Prefer system fonts if you want maximum performance

System stacks render fast and look good:

* `system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif`

If you use a custom font, do it because it supports your brand/readability, not because "design".

### 2) If you load web fonts, optimize loading

Key goals: **no invisible text**, minimal layout shift, minimal bytes.

* Use **`font-display: swap`** (or equivalent) so text shows immediately.
* **Subset** character sets (Latin only if you don't need more).
* Prefer **WOFF2**.
* Load only the **weights you actually use** (don't pull 9 weights).
* If you use variable fonts, still be careful: they can be larger than a couple of static weights depending on the font.

### 3) Keep weights under control

Many pages load 300/400/500/600/700/800 and only use 400/700. Don't.

* A clean set is often: **400 for body**, **600 for headings**, **700 for emphasis** (optional).

### 4) Make code blocks readable

* Use a **mono font** that matches your aesthetic, but keep it simple.
* Ensure code blocks have:
  * Enough **font-size** (not tiny)
  * Adequate **line-height**
  * Good **contrast**
* If you want maximum speed: use `ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace`.

### 5) Typography beats font choice

Even with a single font, you can get a high-end look by:

* Clear **scale** (e.g., 16 body, 20 subhead, 28 heading, 40 hero)
* Consistent **spacing**
* Good **line length** (~60–80 characters per line for body)
* Strong contrast and comfortable line height

## Font anti-patterns to avoid

* Loading **multiple font families + multiple weights** "just in case".
* Using a decorative display font for body text.
* Low contrast "thin" weights (300) for long paragraphs.
* Inconsistent font usage (random headings in different faces).
* Using web fonts without swap → **FOIT** (text invisible during load).

## Simple font recommendation (works for most dev pages)

* **Body/headings**: one good sans (or system-ui)
* **Code**: system mono
* **Weights**: 400 + 600 (and maybe 700)
* **No more than 2 families**

### Current setup for this site

* **Homepage**: Inter (sans-serif) — clean, modern, professional
* **Blog posts**: Literata (serif) for body — designed for comfortable screen reading
* **Headings**: Inter — maintains visual hierarchy
* **Code**: system monospace stack
