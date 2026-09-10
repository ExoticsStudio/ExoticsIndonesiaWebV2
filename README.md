# Exotics Indonesia — Read-Only Content Architecture

## Data flow

Google Sheets -> Sync Worker -> Cached JSON -> CDN/Static Hosting -> Browser

The browser is read-only. It does not POST, PUT, PATCH, or DELETE content.

## Frontend routes

- `/`
- `/games`
- `/news`
- `/news/{slug}`
- `/reviews`
- `/guides`
- `/featured`
- `/community`
- `/merch`
- `/store`
- `/about`

## Cached data

- `data/news-latest.json` — listing metadata only
- `data/reviews-latest.json` — latest review cards
- `data/guides-latest.json` — latest guide cards
- `data/articles/{slug}.json` — full article detail

## Google Sheets

Google Sheets remains the content source of truth. A server-side/edge sync process should fetch the published CSV periodically and regenerate the cached JSON files.

Recommended sheet columns for NEWS:

`id, slug, title, image_url, published_at, category, excerpt, content, author, status`

Only rows with `status=published` should be exposed.

## Important

Do not fetch the complete spreadsheet from the browser on every page load. Keep listing payloads small and fetch full article content only on the article page.

The current HTML contains the cinematic UI and a Google Sheets read-only configuration placeholder. The cache files in this package are starter examples for the production sync layer.
