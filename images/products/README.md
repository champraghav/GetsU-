# Product photos

Drop real product photos here to have them replace the placeholder icons
on the site.

## How to add a photo for a product

1. Save the image in this folder, named after the product, e.g.
   `protein-bar-chocolate.jpg` or `pancake-premix.jpg`.
   - Square images work best (the site crops to a 1:1 box either way).
   - JPG or PNG, ideally under 300KB so the site stays fast.
2. Open `index.html`, find the `products` array (search for
   `PRODUCTS DATABASE`), and add an `image` field to that product, e.g.:

   ```js
   { id: 2, name: 'Protein Bar — Chocolate Delight', category: 'snacks',
     price: 99, original: 129, features: [...], badge: 'Best Seller',
     image: 'images/products/protein-bar-chocolate.jpg' },
   ```

3. Save, commit, and push. The product card and cart will show the photo
   automatically. Any product without an `image` field keeps using the
   existing line-icon placeholder — nothing breaks if a photo is missing
   or the path is wrong, it just falls back to the icon.
