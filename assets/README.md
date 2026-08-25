# Brand assets

The site references two files from this directory. Add them here before deploying.

| File | Used for | Notes |
|---|---|---|
| `logo.png` | Header mark, footer mark, favicon, apple-touch-icon | Square. The PS monogram. A transparent background is preferred so the mark sits flush on the page's near-black; a solid black square also works but may show a faint edge. 512x512 or larger. |
| `banner.png` | Open Graph / Twitter social card image | The wide "Passionet Studio" banner. 1200x630 is the ideal crop for link previews. |

Both are optional in the sense that the page degrades cleanly without them:
the logo mark is painted as a CSS background, so a missing file leaves the
wordmark intact rather than showing a broken-image icon. Social previews
simply fall back to text-only until `banner.png` exists.
