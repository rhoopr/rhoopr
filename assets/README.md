# Artwork and font provenance

## Approved artwork

All illustration and reference-derived print texture comes from the AI-generated full render approved by Rob Hooper: ChatGPT Library `libfile_88bf46b39f388191bd97a8ec13332e72`, original PNG `exec-9b6282c1-edd2-4219-bcc1-649ce254d74b.png`. No third-party photograph is used. Every name, heading, description, article title, contact label, and credit is selectable HTML.

- `stone-ink.svg` embeds an artwork-only PNG crop. Pixels outside its vector contour are cleared from the embedded PNG, including the original reference lettering. The contour retains the stone and surrounding irregular ink forms. A continuous luminance-to-alpha color treatment retains fine shading, maps the visible print to the site's ochre, and lets photo blacks reveal the page ink. This is not binary posterization, a gradient transition, or an opacity fade.
- `synctoken-print.webp` and `github-print.webp` are illustration-only crops from the reference thumbnails; their neighboring titles and captions are excluded.
- `reference-paper-frame.webp` contains only the outer paper border from the reference: 27px at top/sides and 11px at bottom. Its center is transparent, excluding the reference lettering and article content.
- `reference-type-wear.png` is a luminance mask of isolated small ink chips recovered from the reference's display-letter strokes. Large connected regions, glyph silhouettes, and counters are excluded. It adds natural print wear to real HTML type; it does not contain readable lettering.
- `reference-creases.svg` and `reference-rule.svg` are vector interpretations of the reference's creases and irregular ruled edges.

The previously deployed `stone-face.webp`, `print-grain.svg`, and `worn-edge.svg` remain for version compatibility. They are not loaded by the pending homepage. Unused, uncommitted typography and mask experiments have been removed from the deployable tree.

## Self-hosted fonts

| Role | Family / CSS weight | File | License | Official upstream source |
| --- | --- | --- | --- | --- |
| ROB HOOPER, BAMBUTOP, WRITING, article-link titles, strap, GET IN TOUCH, article brand | Anton / 400 | `fonts/anton.woff2` | `fonts/OFL.txt` | https://github.com/google/fonts/tree/main/ofl/anton |
| KEI | Archivo Black / 400 (the family's black display cut) | `fonts/archivo-black.woff2` | `fonts/archivo-OFL.txt` | https://github.com/google/fonts/tree/main/ofl/archivoblack |
| Body, captions, contact links, credit, article code | IBM Plex Mono Regular / 400 | `fonts/plex-mono-regular.woff2` | `fonts/plex-OFL.txt` | https://github.com/google/fonts/tree/main/ofl/ibmplexmono |

All three are distributed under the SIL Open Font License 1.1, with their copyright notices and complete licenses retained alongside the fonts. WOFF2 files were converted from the upstream `Anton-Regular.ttf`, `ArchivoBlack-Regular.ttf`, and `IBMPlexMono-Regular.ttf`; Archivo Black and IBM Plex Mono are subsets retaining Latin characters and the punctuation used by this site. Anton's original full character set is retained. No fonts are fetched from a third-party host at runtime.

Horizontal CSS adjustments to display lettering reproduce the approved render's measured proportions. This adjusts real text rather than replacing it with an image or applying faux bold. Body copy remains at its natural font proportions.
