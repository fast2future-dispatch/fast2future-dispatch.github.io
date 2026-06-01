# The Build Journal — blog (`/blog`)

Static, self-contained journey blog served by Netlify at
**https://fast2future.netlify.app/blog**. No build step — Netlify publishes
`sites/landing/` (per root `netlify.toml`), so everything under `sites/landing/blog/`
is live as plain files.

## Structure
```
sites/landing/blog/
├── index.html     ← the blog index (lists posts)
├── posts/         ← one HTML file per post
│   └── 01-building-a-mind-you-can-hand-to-a-machine.html
└── README.md      ← this file
```

## How to publish a new post
1. **Add the post:** create a new file in `posts/`, e.g.
   `posts/02-<slug>.html`. Copy an existing post as the template (it carries the shared
   dark style). Keep links relative: back-to-index is `../index.html`.
2. **Link it from the index:** add a new `<li>` `.post-card` block at the **top** of the
   `<ul class="posts">` list in `index.html` (newest first), pointing at
   `posts/02-<slug>.html`.
3. **Push:** commit + `git push`. Netlify auto-deploys — the post is live in seconds.

## Rules
- **Public-safe only.** No secrets, credentials, account details, or real personal/
  financial info — these pages are public.
- Keep posts static and self-contained (inline CSS, no external/build deps), matching
  the site style. Honest and useful beats hype.

## Site structure decision (2026-05-31)

**Decided: the journey blog lives on the ONE main site (fast2future.netlify.app/blog) for now — not a separate dedicated journey site.** Rationale: at this stage compounding beats separation (one audience, one brand, one SEO footprint, zero extra maintenance), and posts are portable so we're not locked in.

**Future split trigger:** split the journey into its own dedicated site IF/WHEN the audiences genuinely diverge — i.e. fast2future becomes a polished client-facing product/business site where the raw build-in-public journal would clash with the buttoned-up sales face. This maps to the Contact Circles framework (public/builders vs. business/clients): right now they overlap (Justin is a builder building in public, so one site serves both); split when real client-facing needs make them distinct. Until then: one site. (Same "graduate when there's a real reason" logic as the Privacy.com/incorporation trigger.)
