# Robey B2B dealer portal: design handover

This package contains the design of the new Robey B2B portal (headless on Shopify Plus with B2B). Three things are authoritative, in this order.

## 1. The prototype: `prototype-responsive.html`

Open the file in Chrome, Safari or Edge. It is a single 7 MB file with every image embedded; only the Inter typeface is loaded from Google Fonts, so offline you will see a system font instead.

- Resize the window: mobile (below 768 px), tablet portrait (768 to 899), tablet landscape (900 to 1199) and desktop (1200 and up) all live in the same file. The indicator in the bottom-right corner tells you which breakpoint you are in.
- Press **B** (or click that indicator) for a navigation bar with all twenty-one screens.
- Everything that looks clickable works: menu, search with suggestions, filters, colour swatches on tiles and product pages, the size matrix (type quantities), the cart with cost summary, the account pages, the gallery view (click the large product photo).
- Quantities typed on a product page appear in the cart immediately; there is deliberately no "Add to cart" button.
- The data is sample data and not authoritative. The on-screen copy is Dutch: the portal is for Dutch dealers, and the wording is part of the design.

For phones: open the file on the phone itself, or use the device mode of the browser (Chrome: DevTools, toggle device toolbar).

## Reading values

The prototype is real HTML and CSS, so the browser's inspector is what Figma's inspect panel would be, except that you see the real values instead of an approximation: right-click an element, choose Inspect, and you get the spacing, font sizes, colours and hover behaviour per breakpoint. Classes are named `rb-<component>__<part>` (for example `rb-tegel__stalen`, `rb-mx__rij`; the component names are Dutch abbreviations, see the glossary in the dossier) and the values refer to the tokens in `code/tokens.css`. The complete stylesheet is also available as a separate file, `code/prototype-styles.css`, for reading.

## 2. The tokens and base components: `code/`

- `tokens.css`: every colour, size, radius and shadow as a custom property (`--robey-color-gold`, `--robey-radius-cell`, …). Import directly.
- `tokens.json`: the same values as data, with the role of each token.
- `componenten.css`: the parts where guessing goes wrong, such as the size cell with all its states (`.robey-cell`), buttons, labels and prices.
- `voorbeeld.html`: a sample page that uses only those two stylesheets, to check the import.
- `prototype-styles.css`: the complete stylesheet of the prototype, for reading only; do not adopt it.

## 3. The build dossier: `dossier.html`

Everything you cannot read off a screen: behaviour, models (cart, stock and preorder, availability per size), breakpoints, canonical copy, and the open questions for you (Data questions) and for Robey (Open decisions). Read "What is authoritative" and "Stack and principles" first, then per component what you are building.

`dossier-archief.html` is the full design history with dates and rejected alternatives. Only for when you want to know why something is the way it is; not needed to build.

## What to adopt and what not

Adopt: every value, the structure of each component, the behaviour and the copy. Do not adopt: the code of the prototype. It is generated design code with a single DOM; the portal gets components with props and data from the Storefront and Customer Account APIs.

## Questions

Dennis Odijk, Robey Sportswear.
