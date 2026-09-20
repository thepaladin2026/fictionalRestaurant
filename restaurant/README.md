# Bootstrap &amp; Grid System — Lagune

Responsive one-page site for a fictional restaurant, a *maquis* and wood-fire grill in Treichville, Abidjan. Built with Bootstrap 5 and its grid system, plus a custom stylesheet for the theme.

## Files

```
index.html               the page
style.css                custom styles on top of Bootstrap
screenshot-desktop.png   desktop view, 1440 px
screenshot-mobile.png    mobile view, 390 px
```

Open `index.html` in a browser. Bootstrap and the fonts come from a CDN, so the page needs an internet connection.

## How each requirement is covered

| Requirement | Where |
|---|---|
| Navigation bar, name left, links right | `.navbar` with `navbar-brand` and `justify-content-end` on the collapsing menu (Home, Menu, About Us, Contact) |
| Hero with a background image | `.hero`, `background-image` with a dark gradient laid over `images/hero.svg` |
| Heading and button centred in the hero | `text-center` plus `row justify-content-center` and `col-lg-8` |
| Menu grid, at least three items | `row g-4` with six `col-lg-4 col-md-6` cards |
| Each item has image, title, description, price | `card-img-top`, `card-title`, `card-text`, `.price` |
| About Us in two columns | `row align-items-center g-5` with two `col-lg-6`, image on the left, text on the right |
| Contact form with name, email, message, submit | `row g-3`, two `col-md-6` fields, a full-width textarea, submit button |
| Footer with copyright and social icons | `row align-items-center` with copyright on the left and Bootstrap Icons on the right |

## Grid classes used

`container`, `row`, `col-lg-4`, `col-md-6`, `col-lg-6`, `col-sm-4`, `col-md-12`, the gutter helpers `g-3` / `g-4` / `g-5`, and the alignment helpers `align-items-center` and `justify-content-center`. The menu therefore goes from three columns on desktop, to two on tablet, to one on phone without a single custom media query.

## Bootstrap customisation

Bootstrap was re-themed through its own CSS custom properties rather than with `!important` overrides:

- `--bs-body-font-family`, `--bs-body-bg` and `--bs-body-color` on `body` set the base typography and the sand background.
- `.btn-accent` is a custom button built by redefining `--bs-btn-bg`, `--bs-btn-hover-bg` and friends, so it behaves exactly like a native Bootstrap button.
- `--bs-navbar-brand-color`, `--bs-nav-link-color` and `--bs-card-border-radius` restyle the navbar and the cards.
- The form controls inside `.contact-form` are inverted to sit on the dark lagoon panel.

## Design choices

**Concept.** A grilled-fish maquis in Abidjan rather than a generic restaurant. That decision drove the colours, the dishes on the menu and the copy.

**Colour palette.** Lagoon green `#0c3234` for the navbar, hero, form and footer; a warm sand `#f6f5f0` for the page; gold `#e0a21b` for buttons, icons and badges; a single chilli red `#b8352f` reserved for the "Spicy" badge. The palette comes from the subject: lagoon water, grilled plantain, pepper sauce.

**Typography.** DM Serif Display for headings, the restaurant name and the prices; Karla for everything else. The serif gives the menu the feel of a printed card, the sans keeps the interface plain.

**Images.** All illustrations are hand-written SVG stored locally: six top-down plates for the menu, one flat-lay for the hero, one terrace scene for About Us. They stay sharp at any size and are only a few kilobytes each.

**Prices in F CFA** and street names from Treichville, because generic placeholder text makes a restaurant page feel like a template.

**Responsiveness.** Bootstrap's breakpoints handle the layout; `style.css` adds two media queries (991 px and 767 px) that only scale down the display type and the card images. Tested at 1440 px, 768 px and 390 px.

**Accessibility.** Every image has an `alt`, every form field has a `<label>` tied to it with `for`, the hero keeps white text above the AA contrast ratio thanks to the overlay and a text shadow, and card transitions are switched off under `prefers-reduced-motion`.
