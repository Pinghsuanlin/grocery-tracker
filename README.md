# Groceries

A phone-friendly price tracker for groceries and household shopping. This repository holds only the app; all data lives in the private `grocery-log` repository.

App link (after GitHub Pages is on): https://pinghsuanlin.github.io/grocery-tracker/

## Setup (once)

1. **Fill `grocery-log` (private).** Add file → Upload files → drag in everything from the `grocery-log` folder (`items.json`, `stores.json`, `mappings.json`, `purchases.csv`, `README.md`, `.gitignore`) → Commit.
2. **Fill `grocery-tracker` (public).** Upload `index.html`, `manifest.webmanifest`, `icon-180.png`, `icon-512.png`, `README.md` → Commit.
3. **Turn on GitHub Pages.** `grocery-tracker` → Settings → Pages → Deploy from a branch → `main` / root → Save.
4. **Give your token access.** GitHub → profile picture → Settings → Developer settings → Fine-grained tokens → open each phone's token → Edit → Repository access: add `grocery-log` (keep `gym-log`) → Save. Permissions stay Contents: Read and write.
5. **On each phone:** open the app link in Safari, paste the same token you use for the gym app, choose who uses the phone, tap Connect and sync, then Share → Add to Home Screen.

## Using it

- **Is this a good price?** At the shelf, pick the item and type the price and size (or the weight and €/kg). The tag shows the unit price and a verdict against your own history: *Best price yet*, *Great deal* (within 5% of your best), *Good* (cheaper than 75% of your purchases), *Typical*, or *Expensive* (pricier than 75%). Tap *Log this purchase* to save it.
- **Log a purchase:** shop, item, pack size or weight, price, offer (2×1, 3×2, 2ª unidad al 50% or 70%, % off) and currency. The offer is worked into the effective price.
- **Add from a receipt:** take a photo of the receipt, tap the iPhone's text icon, Copy All, and paste it into the app. It finds the shop, date, lines and weighed items, checks the lines add up to the receipt total, and suggests an item for each line. Confirm or change each one; the app remembers your choices per shop, so the next receipt from the same shop fills itself in. A missing pack size is asked for, never guessed.
- **Compare shops:** how each shop's typical prices compare with your average, on items you've bought at more than one shop, plus the cheapest shop for each item.
- **Currencies:** EUR, USD, GBP, TWD and JPY. Prices are converted at the daily reference rate for the purchase date (free source: fawazahmed0 currency-api, available from 2 March 2024). You can type a rate instead, e.g. your card's rate.
- **Edit or delete** a purchase from its item page. GitHub keeps every earlier version of the data.
