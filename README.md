# 8-Bit Brewing Co. — GitHub Pages Site

## 📁 Folder Structure

```
your-repo/
├── index.html              ← Main site file
├── assets/
│   ├── fonts/
│   │   ├── 8bit-font.woff2   ← Your custom font (primary)
│   │   ├── 8bit-font.woff    ← Fallback format
│   │   └── 8bit-font.ttf     ← Fallback format
│   ├── bg.gif               ← Animated background (full bleed)
│   ├── logo.gif             ← Animated logo (navbar, ~200×80px)
│   ├── mascot.gif           ← Beer ghost character (navbar + footer)
│   ├── cursor.gif           ← Gold coin cursor (32×32px, 10 frames)
│   └── shop/
│       ├── hoodie.jpg       ← Product images (replace placeholders)
│       ├── pint-glass.jpg
│       ├── tee.jpg
│       └── ...
```

## 🚀 GitHub Pages Setup

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Source: **Deploy from branch → main → / (root)**
4. Your site will be live at: `https://yourusername.github.io/repo-name`

## 🖼 Asset Specs

| Asset       | Size          | Notes                                  |
|-------------|---------------|----------------------------------------|
| bg.gif      | Full browser  | Compress — target under 3MB            |
| logo.gif    | ~200×80px     | Transparent background                 |
| mascot.gif  | ~100×100px    | Transparent, 8–12 frames recommended   |
| cursor.gif  | **32×32px**   | 10 frames, 100ms per frame = 1 second  |

## ⚡ Cursor GIF Optimization

The gold coin cursor should be exactly **32×32px**.  
To optimize your cursor.gif run:

```bash
# Install gifsicle
brew install gifsicle   # macOS
# or
sudo apt install gifsicle  # Linux

# Optimize
gifsicle -O3 --colors 32 cursor.gif -o cursor-opt.gif
```

Or use **ezgif.com → GIF Optimizer** online (free, no install).

## 🛍 Shopify Integration

Two options:

### Option A — Link to Shopify store (what's in the demo)
Just update the Shopify URLs in `index.html`:
```html
href="https://your-store.myshopify.com"
```
Or use your custom domain: `https://shop.8bitbrewingco.com`

### Option B — Embed Shopify Buy Button (recommended for max conversion)
1. In Shopify Admin → **Sales Channels → Buy Button**
2. Generate embed code for each product
3. Replace the `.shop-card` placeholder divs with the Shopify embed `<div id="product-component-...">` tags
4. Add the Shopify Buy Button JS snippet before `</body>`

```html
<script type="text/javascript">
/*<![CDATA[*/
(function () {
  var scriptURL = 'https://sdks.shopifycdn.com/buy-button/latest/buy-button-storefront.min.js';
  // ... Shopify auto-generates this for you
})();
/*]]>*/
</script>
```

## 🎮 Easter Egg

The Konami Code (↑↑↓↓←→←→BA) is baked in.
Shows a "+30 LIVES — Free Round On Us 🍺" screen.
Great for the pitch — guaranteed wow moment.

## 🎨 Customization

All colors are CSS variables at the top of `index.html`:
```css
--gold:      #FFB800;   /* Primary accent */
--gold-dim:  #c48a00;   /* Shadow/depth */
--gold-glow: #ffe066;   /* Hover highlight */
--black:     #000000;
--dark:      #0a0a0a;   /* Section backgrounds */
```

## 📋 Checklist Before Pitch

- [ ] Drop in `bg.gif`, `logo.gif`, `mascot.gif`, `cursor.gif`
- [ ] Add font files to `assets/fonts/`
- [ ] Update address & phone in Contact section
- [ ] Update hours in Contact section
- [ ] Update Shopify store URL
- [ ] Add real product images to `assets/shop/`
- [ ] Update beer names/descriptions if needed
- [ ] Update food menu prices
- [ ] Test on mobile
- [ ] Push to GitHub Pages and grab the live URL

---
Built for 8-Bit Brewing Co. — Murrieta, CA 🍺
