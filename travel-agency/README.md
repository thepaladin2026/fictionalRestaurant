# Bootstrap Components — Harmattan

Landing page for a fictional travel agency running small-group trips across West Africa from an office in Abidjan. Built around Bootstrap 5 components.

## Files

```
index.html               the page
style.css                custom styles on top of Bootstrap
images/                  4 SVG illustrations (hero and three destinations)
screenshot-desktop.png   desktop view, 1440 px
screenshot-mobile.png    mobile view, 390 px
```

Open `index.html` in a browser. Bootstrap and the fonts come from a CDN, so the page needs an internet connection.

## How each requirement is covered

| Requirement | Where |
|---|---|
| Navbar, logo left, links right | `.navbar` with a `navbar-brand` (compass icon plus name) and a collapsing menu: Home, Destinations, Tours, Contact |
| Hero with background image, heading, subheading, call to action | `.hero` section, `background-image` over `images/hero.svg`, centred `col-lg-8` |
| Destinations grid, at least three | `row g-4` with three `col-lg-4 col-md-6` |
| Cards with image, title, description, "Learn More" | Bootstrap `card`, `card-img-top`, `card-title`, `card-text` and an outline button |
| Tours as an accordion, each with title, description, "View Details" | `.accordion` with four `accordion-item` blocks and `data-bs-parent` so only one opens at a time |
| Contact form: name, email, destination of interest, message | `form-control`, `form-select`, `form-label` inside a `row g-3` |
| Footer with copyright and social icons | `row align-items-center` plus Bootstrap Icons |

## Bootstrap components used

Navbar with `collapse` and `navbar-toggler` (burger menu below 992 px), the grid system, cards, badges, buttons, the accordion, form controls including a select, Bootstrap Icons, and the spacing and flex utilities (`d-flex`, `gap-*`, `mt-auto`, `sticky-top`).

**A note on the jumbotron.** The brief mentions it, but the jumbotron component was removed in Bootstrap 5. The documented replacement is a section built from utility classes, which is exactly what the `.hero` section does here: a padded full-width block with a background, a display heading, a lead paragraph and a button.

## Bootstrap customisation

Everything is re-themed through Bootstrap's own CSS custom properties, never with `!important`:

- `--bs-body-font-family`, `--bs-body-bg`, `--bs-body-color` on `body`.
- `.btn-sun` and `.btn-outline-night` are custom buttons made by redefining `--bs-btn-bg`, `--bs-btn-hover-bg` and the matching border and colour variables, so they keep native Bootstrap behaviour.
- `--bs-accordion-active-bg`, `--bs-accordion-btn-focus-box-shadow` and `--bs-accordion-border-radius` restyle the accordion.
- `--bs-navbar-brand-color` and `--bs-nav-link-color` restyle the navbar; `--bs-btn-border-radius: 999px` makes every button a pill.

## Design choices

**Concept.** Rather than generic stock destinations, the agency sells three real routes: the Assinie sandbar, the hills around Man, and the Adrar in Mauritania. Concrete places made the descriptions, the tour lengths and the prices specific instead of filler.

**Colour palette.** Night indigo `#2d2a55` for the navbar, hero overlay and footer; a warm off-white `#faf7f4` for the page; sunset orange `#e8875a` for every call to action and for the "View Details" links. Indigo and sunset orange are the two ends of the harmattan sky the agency is named after.

**Typography.** A single family, Outfit, in four weights. One geometric sans across the whole page keeps a travel brand looking modern without the display-serif cliché.

**Images.** Four hand-written SVG landscapes: a sunset over water for the hero, a beach, green mountains with a waterfall, and desert dunes. They are a few kilobytes each and stay sharp on any screen.

**Rounded shapes.** Pill buttons, 14 px cards and 12 px accordion corners, which reads softer and friendlier than the square restaurant project.

**Responsiveness.** Bootstrap's breakpoints do the layout work; `style.css` adds two media queries (991 px and 767 px) that scale the display type and make the hero button full width on phones. Tested at 1440 px, 768 px and 390 px.

**Accessibility.** Every image has an `alt`, every field has a `<label>`, the burger button has an `aria-label`, focus rings are visible on the form, and card transitions are disabled under `prefers-reduced-motion`.
