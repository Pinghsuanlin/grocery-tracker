# Groceries

A phone-friendly price tracker for groceries and household shopping. This repository holds only the app; all data lives in the private `grocery-log` repository.

App link (after GitHub Pages is on): https://pinghsuanlin.github.io/grocery-tracker/

## Setup (once)

1. **Fill `grocery-log` (private).** Add file → Upload files → drag in everything from the `grocery-log` folder (`items.json`, `stores.json`, `mappings.json`, `purchases.csv`, `README.md`, `.gitignore`) → Commit.
2. **Fill `grocery-tracker` (public).** Upload `index.html`, `manifest.webmanifest`, `icon-180.png`, `icon-512.png`, `README.md` → Commit.
3. **Turn on GitHub Pages.** `grocery-tracker` → Settings → Pages → Deploy from a branch → `main` / root → Save.
4. **Give your token access.** GitHub → profile picture → Settings → Developer settings → Fine-grained tokens → open each phone's token → Edit → Repository access: add `grocery-log` (keep `gym-log`) → Save. Permissions stay Contents: Read and write.
5. **On each phone:** open the app link in Safari, paste the same token you use for the gym app, choose who uses the phone, tap Connect and sync, then Share → Add to Home Screen.

## Finding your way

- **Tabs at the bottom:** Home · Items · Prices · Shops.
- **Home:** search for an item, or tap **Add a price** / **Add a receipt**.
- **Add a price:** enter the item, shop and price and the verdict appears straight away. Then **Save as bought**, **Save as noted**, or just go back without saving.
- **Item pages:** best price, by shop, by brand, price over time (tap a dot for its price), then all prices. Type pages (e.g. Milk) show each type separately and never mix them.
- **Shops:** which shop is cheapest on top, your shops below (tap one to edit).

## Using it

- **Fair comparisons:** verdicts use the last 12 months of prices when there are at least 3, so inflation doesn't make today's prices look expensive. Each shop has a country (Spain unless you choose otherwise when adding it); prices are only compared within the same country, and item pages have a switch when an item was bought in more than one.
- **Safety checks:** a price 3× above or below your usual for that item asks "Save anyway?" (usually a typo, or g vs kg). Saving a receipt that's already saved (same shop and date, same total or mostly the same lines), or the same purchase twice, asks first.
- **Count spending from:** Settings → Spending sets the date spending starts; prices before it count as noted only. Stored in `grocery-log/settings.json`, shared by both phones; your data isn't changed.
- **Categories:** household is split into Cleaning & laundry, Paper & disposables and Kitchenware (pots, pans, serving ladles…). Asian supermarkets are marked as Asian shops. Both are applied to your data files automatically on the next sync, keeping any items or shops you've added or renamed.
- **Shops screen:** Home → Shops lists every shop by country; tap one to change its name, kind, country or receipt words.
- **Import a file:** Settings → Import purchases from a file adds rows from a CSV in the app's format (e.g. an old log). Rows already in your data are skipped.
- **Fast for years:** new prices go into one file per year (`purchases/2026.csv`); the original `purchases.csv` stays and is still read. Saving only touches this year's file, and syncing only downloads files that changed, so speed stays the same however much history you keep. The offline copy is kept in the browser's IndexedDB storage, which has plenty of room. Open the app from its Home Screen icon so the phone keeps that copy.

- **Is this a good price?** At the shelf, pick the item and type the price and size (or the weight and €/kg). The tag shows the unit price and a verdict against your own history: *Best price yet*, *Great deal* (within 5% of your best), *Good* (cheaper than 75% of your purchases), *Typical*, or *Expensive* (pricier than 75%). Tap *Log this purchase* to save it.
- **Items, types and subtypes:** items like Milk, Cheese or Yogurt have types (whole, semi-skimmed; cured, fresh; Greek…). Pick the item, then the type, or add a new type in two taps. Prices are compared within the same type; when a type has fewer than 3 prices, the app compares with the whole item and says so. Item pages show prices by type, shop and brand.
- **Brands and own label:** an optional brand on each purchase, detected from product and receipt names where possible; own-label brands (Hacendado, Alipende, Auchan, BM, Kirkland…) are ticked automatically. Item pages show how own label compares with branded.
- **Choosing a shop:** the list shows only *your shops*: the ones you've used, most used first. To find another, type its name: it finds shops the app already knows (Lidl, Dia, Carrefour…) or offers to add what you typed. Pick the kind (Supermarket is pre-selected) and tap **Add shop**. Amazon, Amazon Fresh and Too Good To Go are included.
- **Your shops (Settings):** reorder or remove shops in the list. Shops you pick from a search or add go to the end automatically. Removing a shop from the list doesn't delete it or its prices. The list is saved in `grocery-log/settings.json`, shared by both phones; without a connection it's kept on the phone and saved at the next sync.
- **Surprise bags (Too Good To Go):** log what you paid and the value shown in the app; the app shows your savings and keeps bags out of the price comparisons.
- **New items:** type the name in any language and tap Add. The form shows the name, the category (guessed: mango, 芭樂 or caqui → Fruit) and how prices are compared (per kg, litre or piece); change any of them if the guess is wrong. If the name clearly matches a group in the same category ("flat peaches" → Peaches, "leche sin lactosa" → Milk), a tick box offers to group it so prices are compared within the group; otherwise nothing is asked. The full group list, other languages and receipt names are under More details. **Add item** is instant: the item is ready to use straight away and uploads in the background, or at the next sync if you're offline.
- **Log a price:** choose *Bought it* or *Just noting the price*. Noted prices count in every comparison but not in what you've spent; All prices can show bought, noted or both. Then shop, item, pack size or weight, price, offer (2×1, 3×2, 2ª unidad al 50% or 70%, % off) and currency. The offer is worked into the effective price.
- **Add from a receipt:** take a photo of the receipt, tap the iPhone's text icon, Copy All, and paste it into the app. It finds the shop, date, lines and weighed items, checks the lines add up to the receipt total, and suggests an item for each line. Confirm or change each one; the app remembers your choices per shop, so the next receipt from the same shop fills itself in. A missing pack size is asked for, never guessed.
- **Compare shops:** how each shop's typical prices compare with your average, on items you've bought at more than one shop, plus the cheapest shop for each item.
- **Currencies:** EUR, USD, GBP, TWD and JPY. Prices are converted at the daily reference rate for the purchase date (free source: fawazahmed0 currency-api, available from 2 March 2024). You can type a rate instead, e.g. your card's rate.
- **Edit or delete** a purchase from its item page. GitHub keeps every earlier version of the data.

## Planned

- **Typical weight per piece:** for items sold sometimes per piece and sometimes per kg (avocado about 200 g, lettuce, melon, pineapple), so per-piece purchases get a unit price, marked as approximate.
- **Tags alongside the subtype:** organic, Iberian, DOP, lactose-free and so on, so combinations don't need their own subtype.
- **Shopping list:** this week's list, with the cheapest shop for it based on your prices.
- **Shrinkflation alert:** a warning when the same product comes back in a smaller pack (e.g. 500 g → 450 g).

Decided against: comparing by drained weight (peso escurrido), since it's rarely clear on labels; net weight is used consistently instead.
