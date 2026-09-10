# Sync Worker contract (example)

The sync worker is intentionally kept separate from the browser.

1. Fetch the published Google Sheets CSV.
2. Parse rows.
3. Keep only `status=published`.
4. Generate:
   - `data/news-latest.json`
   - `data/reviews-latest.json`
   - `data/guides-latest.json`
   - `data/articles/{slug}.json`
5. Publish those files to static hosting/CDN.
6. Run every 5–15 minutes.

The browser only GETs the generated JSON.

No browser credentials for Google Sheets are required when the sync layer is server-side.
