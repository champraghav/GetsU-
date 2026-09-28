# Product photos

Real photos go here. Any product without one falls back to a designed
stand-in (a category-tinted plate with an icon), so nothing breaks while a
photo is missing — but a real photo converts far better than a stand-in.

Currently photographed: `protein-bar-chocolate.jpg`, `pancake-premix.jpg`.
Still needs one: **High-Protein Oats**.

## Adding a photo to an existing product

1. Save the image here, named after the product, e.g. `high-protein-oats.jpg`.
   - Square or portrait works best (the card crops to a 1:1 box).
   - JPG, ideally under 300KB so the page stays fast.
2. In `index.html`, find the `products` array (search for `LAUNCH CATALOG`)
   and add an `image` line to that product:

   ```js
   image: 'images/products/high-protein-oats.jpg',
   ```

3. Commit and push. The card, cart and product page all pick it up.

## Adding a whole new product

Copy an existing entry in the `products` array and give it a new `id`.
Notes on the fields that matter:

- `category` must match a `key` in the `CATEGORIES` array just above
  (`breakfast` or `snacks` today). Add a new entry there first if you need
  a new one, or the label and icon won't resolve.
- `price` / `original` drive the "Save X%" badge automatically — it is
  calculated, never typed in, so it can't contradict the prices shown.
- `nutrition` is **optional**. Leave it off until you have verified figures
  for that product; the page then shows a "we're finalising the panel,
  it's on the pack" note instead of numbers. Declared nutrition is
  regulated under the FSSAI labelling rules, so never publish a panel you
  cannot back up with a lab report or the printed pack.
- `allergens` — use the exact string `'None'` when there are none. Anything
  else is rendered as a "Contains …" warning.
- `badge` is deliberately empty on every product. Only use it for something
  factual (`'New'`). Avoid `'Best Seller'` or `'Popular'` until sales data
  actually supports it — the site publicly pledges not to invent customer
  signals.

## Before adding claims

A chip like `'20g protein per bar'` is a labelling claim. Make it match the
declared panel and the pack:

- per **serving** vs per **100 g** changes the number — say which.
  The premix chip reads `20g protein / 100g` because 7 g in a 35 g serving
  is 20 g per 100 g; quoting "20g protein" next to a 7 g panel reads as a
  contradiction to anyone who checks.
- comparative claims ("25% more protein", "60% less sugar") need a stated
  basis for the comparison. Without one they don't belong on the page.
