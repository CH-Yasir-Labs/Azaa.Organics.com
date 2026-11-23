# Azaa Organics

A responsive, no-build storefront for Azaa Organics. It includes a product catalog with honey and ghee flavors and size/price options, farm eggs, mustard oil, dry fruits, category and price filters, search, best-seller sorting, a cart, wishlist, WhatsApp ordering, contact messages and a local admin dashboard.

## Run locally

Admin sign-in uses the browser's Web Crypto API. Serve the folder on `localhost` instead of opening `index.html` directly:

```powershell
python -m http.server 8000
```

Then open `http://localhost:8000`.

To open admin, click **Admin Login** five times. On first use, create a local admin account. If an account already exists, choose **Create new account** on the sign-in form to replace its password. This five-click gate is only hidden navigation, not secure authentication: anyone can create an account in their own browser. The verifier, admin data, and product changes are stored only in that browser and are not shared with visitors or other devices. A backend is required for secure access and a shared product catalog. The admin can manage orders and customer messages, add/edit/remove products, and add/rename categories. When adding or editing a product, optional pack options use the format `250 ml:1500, 500 ml:2800`. Upload 2–3 product photos; changing pack sizes uses the matching photo when available. Orders do not collect payment.

## Data and deployment

This version is a **local demo**. The browser stores products, categories, cart, wishlist, orders, messages and the admin verifier in `localStorage`. That data exists only in the current browser profile on the current device. It is not a shared database, is not synchronized to the admin on another device, and can be cleared with browser data.

The static site can be hosted on GitHub Pages, but doing so does not change those limitations. Do not use this demo to collect real customer information or treat its client-side admin panel as secure. A production launch needs a hosted database and server-side authentication/authorization.

## Publish on GitHub Pages

1. Create a GitHub repository and upload these project files to its root.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/(root)`, then save.
4. Open the Pages URL GitHub provides after its deployment finishes.

## Store details

- Contact: [azaaorganics@gmail.com](mailto:azaaorganics@gmail.com)
- WhatsApp orders: [0307 6158708](https://wa.me/923076158708)
- Designer credit: Choudhary Yasir
- Logo: `azaa-organics-logo.png`

Honey flavors include 250 ml and 500 ml packs plus 1 liter and 1 kg options at Rs. 2,800. Desi ghee is Rs. 3,000 per kg, eggs are available only in 1-dozen packs at Rs. 400 per dozen, almonds are Rs. 2,000 per kg, and mustard oil starts at Rs. 350 for a 250 ml bottle. Product prices and sizes can be edited in Admin.

A flat Rs. 250 delivery charge is added to each order and included in the checkout, WhatsApp order summary and saved order total.

Honey and ghee use separate flavor-labeled photos in the project root (`azaa-honey-*.jpg` and `azaa-ghee-*.jpg`), and mustard oil uses `azaa-mustard-oil-labeled.jpg`. The logo, `azaa-organics-logo.png`, is also in the project root. Include these files when pushing the site to GitHub. Other starter product photos are loaded from Unsplash; upload real product photos in Admin to replace starter images. The social links currently point to each platform's homepage; replace them with the business profile URLs. Update product details in `app.js` and links in `index.html` as needed.
