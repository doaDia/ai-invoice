# AI Invoice — TagihAI for Small Sellers

**PayPal AI Hackathon 2026 entry** — build what's next with PayPal and AI.

Small sellers describe a sale in plain words (Indonesian or English), AI turns it
into a professional invoice, and the buyer pays through PayPal.

## What it does

1. **Type a sale in plain language** — e.g. `Jual 10kg sayur ke Warung Bu Siti
   Rp150.000` or `Sold 2 boxes of eggs to Toko Berkah, Rp55.000 per box`.
2. **AI parses it into an invoice** — buyer, line items, quantities, prices,
   totals. The invoice is fully editable before sending.
3. **Pay the invoice with PayPal** — real PayPal Sandbox checkout buttons.
   IDR totals are converted to USD at a clearly shown fixed demo rate
   (16,000 IDR = 1 USD). After approval the app shows a
   "Paid (PayPal Sandbox)" confirmation with the order ID.
4. **Extras** — an AI-drafted payment reminder message (ready to paste into
   WhatsApp), save invoices to local history, share an invoice as a
   self-contained link, and print a clean invoice.

## How to run

No build step, no API keys, no backend. Open `ai-invoice.html` in a browser,
or serve the folder with any static server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/ai-invoice.html
```

## Tools used

- **PayPal** — PayPal JavaScript SDK, Sandbox environment. The demo uses
  PayPal's documented sandbox demo client ID (`sb`). To use your own
  sandbox account, replace `client-id=sb` in the SDK script tag with your
  own sandbox client ID from [developer.paypal.com](https://developer.paypal.com).
- **AI** — [Pollinations](https://pollinations.ai) free text API (no key
  required). It parses the seller's plain-language sale description into
  structured invoice JSON (`buyer`, `items`, `currency`, `total`, `notes`).
  If the AI call fails, the app shows an error and lets the seller fill in
  the invoice manually — it never invents line items.

## Live demo

Hosted demo URL is listed on the Devpost submission. (This repo is a single
static file, so it can also be served directly from GitHub Pages.)

## License

MIT — see [LICENSE](LICENSE).
