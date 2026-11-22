---
name: project-checks
description:
  'Select and run local validation for the public practice website when checking
  a change, approving a plan, or preparing a review.'
---

# Project checks

The site is static: `index.html` with the Bulma subset in `css/`, fonts in
`fonts/` and images in `img/`. There is no package manifest or build step.

1. Run `git diff --check`.
2. When a change adds Bulma classes, fonts or icons, rebuild and verify them as
   `css/README.md` describes. Those files are subsets of what `index.html` uses.
3. Serve the repository root with the `bulma-site` launch configuration, or
   `python3 -m http.server --bind 127.0.0.1 --directory . 8766`. Check each
   affected section at 390px and 1440px: links and anchors, keyboard focus, the
   mobile menu, and console and network panels free of errors and 404s.
4. When a change touches `CNAME`, `robots.txt`, `sitemap.xml`,
   `site.webmanifest` or an asset path, confirm each still loads at its URL.

Report the exact checks and results. Keep source, browser, hosted, and provider
evidence separate. Use the local or synthetic fixtures allowed by the project.
