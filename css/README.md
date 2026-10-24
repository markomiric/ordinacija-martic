# Site assets

The site remains plain HTML and CSS. Asset tools are only needed when rebuilding
these files; there is no runtime or hosting build step.

## Bulma subset

`bulma.min.css` is Bulma **0.9.4** (MIT), reduced with PurgeCSS **7.0.2**
against `index.html`, including its inline JavaScript and custom CSS. Keep the
original Bulma rules and their order; do not replace them with hand-written
approximations.

After adding Bulma classes, regenerate from the full upstream file, not the
already reduced file:

```sh
bulma_source=$(mktemp -d)
curl --fail --location \
  https://raw.githubusercontent.com/jgthms/bulma/0.9.4/css/bulma.min.css \
  --output "$bulma_source/bulma.min.css"
npx --yes purgecss@7.0.2 \
  --content index.html \
  --css "$bulma_source/bulma.min.css" \
  --safelist is-active is-hidden is-loading is-focused is-hovered \
    is-success is-danger is-light is-mobile is-desktop \
  --output css
```

Keep these states even when a screenshot does not show them. Verify the mobile
menu, all case tabs, gallery controls, keyboard focus, form loading/disabled
state, success/error notices, reduced motion, and responsive layouts afterward.

## Fonts and icons

`../fonts/` contains local WOFF2 subsets of the existing Google Fonts versions:
Inter v20 (CSS weights 400–700) and Plus Jakarta Sans v12 (400–800). Both retain
variable weights, hinting, Latin-1, Croatian letters, combining accents, and
punctuation. Their `@font-face` rules and critical font preloads are in
`index.html`. FontTools 4.63.0 was used to subset the files. Regenerate the
subsets before adding text from another alphabet; the contact fields also use
them.

The local Font Awesome Free **5.15.4** subsets retain the original solid and
regular glyphs, metrics, and class names. The inline CSS maps each used `fa-*`
class to its original codepoint. When adding an icon, update both its font
subset and CSS mapping. Keep decorative `<i>` elements `aria-hidden="true"`.

Each font's license and copyright notice is included in `../fonts/`. There are
no requests to Google Fonts or the Font Awesome kit, and site initialization no
longer waits for the remote icon script.

## Partner logos

The 3M and Ivoclar WebP files use lossless compression. Ivoclar is exactly half
its original dimensions, sufficient for the current 72 CSS pixel height at 3×
pixel density. Kerr keeps its smaller original PNG. All three logos have native
lazy loading, asynchronous decoding, and intrinsic dimensions. Original PNGs
remain available for cached pages and future asset work.
