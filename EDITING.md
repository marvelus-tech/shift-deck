# Editing the SHIFT deck

Everything you need to change is at the top of `index.html`, in two blocks. You don't need to touch the layout code or styles below them.

## 1. CONFIG: client details and prices
- `clientName`: shown on the cover ("Prepared for ...").
- `contactName`, `contactEmail`, `contactPhone`, `bookingLink`: shown on the last slide. Placeholders in square brackets, like `[contact email]`, stay as plain text and their links do nothing until you replace them.
- `prototypeUrl`: the "View live prototype" button.
- Prices: `introPrice`, `introLength`, `retainerPrice`, `monthlyBase`, `monthlyUnit`, `monthlyNote`, `currency`, and the `fleetTiers` list (each row is `["cars", "price"]`, with an optional third item for a small note, e.g. `["6 to 10 cars", "+$25/month", "Most popular"]`). Keep the ranges from overlapping.
- Standard prices: `retainerStandard` and `monthlyStandard` appear struck through beside the current price. Set either to `""` to hide its strikethrough. `dealLabel` (default "Launch pricing") is the small tag above any discounted price; set it to `""` to hide it.

## 2. SLIDES: all slide text
- One `{ ... }` block per slide, in order. Change the words inside the quotes.
- Wrap words in `*stars*` to show them in the accent blue.
- `{clientName}`, `{retainerPrice}` and any other CONFIG name in curly braces is replaced with the CONFIG value.
- `type` picks the layout. Leave it as is, or copy a whole block to make another slide with the same layout.
- To remove a slide, delete its whole `{ ... },` block. The counter and progress bar update on their own.

## Copy rules
No em or en dashes (use "to" or commas). Keep each slide to one idea.

## Publishing
Copy `index.html` and the `assets/` folder to any static host. For the current site, copy them into `publish/`, then commit and push (GitHub Pages rebuilds in about a minute).

Maintainer note: `src/index.src.html` is the source. `python3 src/build.py https://marvelus-tech.github.io/shift-deck/` turns it into `index.html`. If you edit `index.html` directly, copy the same changes into the source, or the next build will overwrite them.
