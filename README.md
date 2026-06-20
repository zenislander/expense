# Receipt Ledger

A simple, private expense tracker that runs entirely in your phone's browser. Snap a photo of a receipt and it reads the merchant, date, total, tax, and line items automatically, then files the expense under the right category. No app store, no account, no server — your data lives only on your own device.

Built as a single `index.html` file, so it's easy to host and share.

## What it does

- **Scan receipts with your camera** — take a photo (or pick one from your gallery) and the details are extracted for you. You confirm or tweak before saving.
- **Add expenses manually** — for cash or anything without a receipt.
- **Monthly dashboard** — see total spent this month and a breakdown by category.
- **By-month view** — per-month totals broken down by category, with optional budget tracking.
- **Search and filter** — find expenses by merchant, note, or category; filter by this month / last month / all time.
- **Custom categories** — rename the built-in ones or add your own.
- **Budgets** — set a monthly cap per category and see your progress (and overages) in the By-month view.
- **Backup and restore** — export everything to JSON (full backup) or CSV (opens in Excel), and import a JSON backup to restore or move to a new phone.

## Before you start: you need a Claude API key

This app reads receipts by sending the photo to Anthropic's Claude AI. That requires an API key, and **each person needs their own** — keys are personal and tied to billing.

1. Go to <https://console.anthropic.com/settings/keys> and sign in (or create an account).
2. Create a new API key and copy it. It looks like `sk-ant-...`.
3. The first time you tap **Scan receipt**, the app will ask you to paste it in. It's saved only in your own browser — never in this file or shared with anyone.

**Cost:** each receipt scan is a small charge to your own Anthropic account — typically a fraction of a cent per scan. Adding expenses manually, viewing, editing, and exporting are all free (no API call). You can check your usage anytime at the console.

**Privacy:** the API key and all your expenses are stored locally in your browser (`localStorage`). Nothing is uploaded to GitHub or any server I control. Receipt photos are sent to Anthropic only at the moment you scan, to read the text.

## How to use it

The easiest way is to open the hosted version (see the link your friend shared, or host it yourself below).

1. Open the page in **Chrome, Firefox, Safari, or another normal browser** (not an in-app browser like the one inside Instagram or Gmail).
2. Tap **Scan receipt** → your phone's camera/gallery chooser opens → pick or take a photo of the receipt.
3. The first time, paste in your Claude API key when asked.
4. Review the extracted details, adjust the category if needed, and **Save**.
5. **Important — install it to your Home screen** so your data persists reliably:
   - **Android (Chrome):** menu (⋮) → *Add to Home screen*
   - **iPhone (Safari):** Share button → *Add to Home Screen*
   - Launch it from that icon from then on. (If you open it as a one-off file each time instead, the browser may treat each visit as a new site and your saved entries can disappear.)

### Backing up your data

Your expenses live only on your device, so back them up:

- Open **Settings** (the ⚙ icon, top-right) → **Export JSON** to save a full backup. Keep it in Google Drive, email it to yourself, etc.
- **Export CSV** gives you a spreadsheet-friendly file.
- To restore or move to a new phone: Settings → **Import JSON**, then choose *Merge* or *Replace all*.

If you clear your browser's site data, switch browsers, or lose the phone without a backup, the data is gone — so export every now and then.

## Host your own copy (free)

This is just one HTML file, so it's easy to put online at a stable web address.

### Option A — GitHub Pages

1. Fork or copy this repo to your own GitHub account.
2. Make sure the file is named **`index.html`** in the repo root.
3. Repo **Settings → Pages → Source: "Deploy from a branch" → Branch: `main` / root → Save**.
   - Note: on a free GitHub account, the repo must be **public** for Pages to work. That's fine here — the file contains no secrets (your API key is only ever stored in your browser, never in the file).
4. Wait about a minute; your site appears at `https://YOURNAME.github.io/REPO/`.
5. Open that URL on your phone and add it to your Home screen.

### Option B — Netlify Drop (no account needed to try)

1. On a computer, go to <https://app.netlify.com/drop>.
2. Drag `index.html` onto the page.
3. You get an instant URL like `https://something.netlify.app`. Open it on your phone and add to Home screen.

## Browser support

Works on all major mobile and desktop browsers — Chrome, Firefox, Safari, Edge, Samsung Internet, Brave. A few notes:

- **Install to Home screen** for reliable data storage, especially on iPhone (Safari can clear storage for sites you haven't opened in a while if they aren't installed).
- **Avoid private/incognito mode** — browsers wipe local storage when you close a private tab.
- **Avoid in-app browsers** (links opened inside other apps) — file pickers and storage can misbehave there.

## A note on what this is and isn't

This is a lightweight personal tool, not a polished commercial product. Your data is stored only in your browser with no automatic cloud backup or cross-device sync — exporting is your backup. If you want those things, the data would need to move to a proper backend with a database, which is a bigger project.

## License

Free to use and share. No warranty — use at your own discretion, and keep your API key private.
