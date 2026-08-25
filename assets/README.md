# Brand assets

| File | Used for | Notes |
|---|---|---|
| `logo.png` | Header mark, footer mark, favicon, apple-touch-icon | 256x256 RGBA. The PS monogram keyed to transparency so it composites on the page's near-black without a visible backing square. |
| `og.jpg` | Open Graph / Twitter link preview | 1200x630, the ratio link previews expect. Centre-cropped from `banner.png`. |
| `masthead.jpg` | Full-bleed masthead above the hero | 1672x941, the banner re-encoded as JPEG at quality 0.85. 96 KB against 1.27 MB for the PNG. Cropped by CSS `object-fit`, not baked in, so the framing can be retuned without regenerating the file. |
| `banner.png` | Source art | The original 1672x941 banner, kept for future use. Not referenced by the page. |
| `logo-source.png` | Source art | The original 1254x1254 monogram, opaque on a #1c1c1c backing. Kept as the master; `logo.png` is derived from it. Not referenced by the page. |

## Regenerating the derived files

`logo.png` is the monogram with its dark backing converted to an alpha
channel: per pixel, alpha is the pixel's luminance rescaled between the
background and foreground levels, and the colour is flattened to the
monogram's off-white. That keeps the antialiased edges clean against any
dark background, rather than fringing against the original #1c1c1c.

`masthead.jpg` is the full banner re-encoded, no crop: the framing is done
in CSS so it can adapt per breakpoint.

`og.jpg` is a centre crop of `banner.png` to 1.905:1, then JPEG at quality
0.88. PNG was 981 KB for the same image; JPEG is 59 KB with no visible
loss on this artwork.

If either source file is replaced, regenerate the derived file rather than
pointing the page at the source. The monogram at full size is 972 KB, which
is far too heavy for a 28 px header mark and a favicon.
