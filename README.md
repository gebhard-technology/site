# site

Gebhard Technology LLC website. Plain HTML and one stylesheet, no build step and no dependencies.

## Previewing locally

Open `index.html` in a browser. Every link is relative, so the whole site works
straight from disk, with no server running.

To preview it the way it is served in production instead:

    python3 -m http.server 8000

Then visit http://localhost:8000.

## Layout

| Path | What it is |
| --- | --- |
| `index.html` | Main page |
| `styles.css` | Styles for the main page and the blog |
| `blog/` | Blog index and posts |
| `brand/` | Logo lockups and the social card, from the logo kit |
| `fonts/` | Outfit, self-hosted so there is no third-party request |
| `getting-ready/`, `snow-pup-sleeps/`, `daily-routines/` | App pages, each self-contained with its own styles |

The app pages are deliberately styled on their own and do not share `styles.css`.

## Brand

The site uses the horizontal logo lockup in the nav, as the logo kit specifies,
swapping to the reversed version in dark mode. Colors are defined once as custom
properties at the top of `styles.css`:

| | Hex |
| --- | --- |
| Blue | `#1F4FA8` |
| Green | `#2E9B6E` |
| Ink | `#14212B` |
| Light blue | `#8FB4F5` |
| Light green | `#7FD6AE` |

Headings use Outfit, the brand typeface, served from `fonts/` rather than Google
Fonts so the site stays self-contained. Body text uses the system font stack.

### Page palette

The page uses only the blue and green from the logo, over ink text on white.

| Role | Light | Dark |
| --- | --- | --- |
| Background | `#FFFFFF` | `#101B24` |
| Text (ink) | `#14212B` | `#E9EEF2` |
| Headline and post headings (green) | `#2E9B6E` | `#7FD6AE` |
| Links and buttons (blue) | `#1F4FA8` | `#8FB4F5` |

The green is 3.48:1 on white, which clears WCAG AA for large text but not for
small. It is used on the headline and on blog post headings, both of which are
large enough. Smaller headings stay ink and the uppercase section labels stay
gray, so nothing on the page sits below AA.
