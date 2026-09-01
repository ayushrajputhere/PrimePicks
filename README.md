# Prime Picks — How to use this website

## ⚠️ Fixed in this update
- **Search bar** — was decorative only (no working code behind it), now fully functional on both pages — click the ⌕ icon, live search opens across all products.
- **Font looking cheap** — leftover markdown code-fences (` ```html ` / ` ``` `) were sitting inside `category.html` and `css/style.css`, which broke the page's rendering mode. Removed them, and added the missing bold font-weights (800/900) that weren't being loaded, which were also making text render as fake/blurry-bold.
- **Slow to add products** — added `product-generator.html`, a small local tool: fill a form, click generate, copy the JSON, paste into `products.json`. No manual typing of JSON needed anymore.

## 0. Fastest way to add a product now
Open `product-generator.html` in your browser (just double-click it, no hosting needed) → fill the form → click **Generate JSON** → click **Copy to clipboard** → paste it into `data/products.json` (inside the square brackets, with other products).

## 1. Naya product kaise add karein (manual method, still works)

Sab products ek hi file me hain: `data/products.json`

Har product ek block hai jaisa niche hai. Bas isko copy karo, apne product ki
details daalo, aur file me kahin bhi (comma ke saath) paste kar do:

```json
{
  "id": "p009",
  "category": "tech",
  "name": "Product ka naam",
  "description": "1-2 line description — kya khaas hai isme.",
  "image": "https://.....jpg",
  "price": "₹999",
  "originalPrice": "₹1,499",
  "discount": "33% off",
  "availability": "In Stock",
  "buyLink": "https://www.amazon.in/dp/XXXXXXXXXX?tag=YOUR-AFFILIATE-TAG-21"
}
```

**Zaroori cheezein:**
- `id` — har product ka unique naam (p009, p010, ...)
- `category` — inme se ek hi likhna: `home-decor`, `gaming`, `tech`, `kitchen`
- `buyLink` — **yeh sabse important hai**. Amazon product page pe jao, apna
  affiliate link generate karo (SiteStripe se), aur wahi yaha paste karo.
  Har link me apna Associate tag hona chahiye (`tag=yourtag-21`), warna
  commission nahi milega.
- `image` — product ki photo ka URL. Amazon ki apni image URL use mat karo
  (copyright issue ho sakta hai) — apni khichi photo host karo, ya royalty-free
  source (Unsplash/Pexels) se lo, ya koi image-hosting site (imgur, cloudinary)
  pe upload karke uska link daalo.

Save karo, upload karo — product turant category page pe dikhne lagega.
Koi naya HTML page banane ki zaroorat nahi.

**Naya category chahiye ho to:** `category.html` file me `CATEGORY_META`
object me ek naya entry add karo, aur `index.html` me ek naya category card
add karo. (Bata dena, main bhi kar sakta hun.)

## 2. Website hosting — free aur best tareeka

### Option A — GitHub Pages (recommended, sabse reliable, free forever)
1. github.com pe free account banao (agar nahi hai).
2. Naya repository banao — naam kuch bhi (e.g. `PrimePicks`).
3. Is folder ke saare files (index.html, category.html, css/, data/) us
   repository me upload kar do — GitHub website pe "Add file → Upload files"
   se seedha drag-drop kar sakte ho, koi git command nahi chahiye.
4. Repository ke **Settings → Pages** me jao, "Branch: main" select karo, Save.
5. 1-2 minute me tumhari site live ho jayegi is URL pe:
   `https://your-username.github.io/PrimePicks/`
6. Baad me apna khud ka domain bhi free me connect kar sakte ho GitHub
   Pages ke "Custom domain" setting se (domain kharidna padega, hosting
   free rahegi).

### Option B — Netlify (sabse easy, drag-and-drop, free)
1. netlify.com pe free account banao.
2. "Add new site → Deploy manually" pe jao.
3. Is poore folder ko zip karke seedha drag-drop kar do.
4. Site turant live ho jayegi ek free `.netlify.app` URL pe.
5. Product update karna ho to bas naya zip banao aur dobara drag-drop kar do
   (ya Netlify ko GitHub se connect kar do for auto-updates).

**Meri recommendation:** Shuru me Netlify se try karo (sabse fast, 2 min me
live), aur jab site grow karne lage aur regular updates karne lage, GitHub
Pages pe shift kar lena — usme version history bhi milti hai aur free custom
domain connect karna easier hai.

## 3. Pinterest pe kaise use karein
Pin banate waqt "Destination link" me category page ka live URL daalo,
jaise: `https://your-site.com/category.html?cat=home-decor`
Isse Pinterest se aane wala traffic seedha us category ke saare products
dekhega, sirf ek product nahi.

