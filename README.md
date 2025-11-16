# Jewelry Store (Static) - Repo Contents

This repository contains a static storefront (`index.html`) and a GitHub Actions workflow that generates `products.json` from a Google Sheet published as CSV.

## Setup steps
1. Create Google Sheet with a sheet/tab named `Products` and headers:
	`id,title,price_display,amount,desc,image,payment_link,visible`
2. Publish the `Products` sheet as CSV (File → Publish to the web → choose 'Products' sheet → format CSV) and copy the export URL.
3. Add the export CSV URL to GitHub Secrets as `SHEET_CSV_URL`.
4. Push these files to the `main` branch of the repo.
5. Wait for the Actions workflow to run. After success, `products.json` will be created in repo root.
6. Enable GitHub Pages (Settings → Pages → Source: main / root) to serve the site.

## Notes
- Images should be public direct links (Cloudinary, Imgur, or raw.githubusercontent.com).
- Payment links are created from your payment gateway (Razorpay / Cashfree / PayU) and placed in the `payment_link` column.
- Orders are handled manually (payment confirmation email → update orders sheet → message customer).

---

If you want, I can:
- Create a ZIP with these files for you to download; or
- Create a ready-to-paste repo (I can prepare the exact `git` commands to run locally).