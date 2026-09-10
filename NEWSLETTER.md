# Exotics Newsletter

## Architecture

Newsletter subscriptions are intentionally **separate from the Google Sheets content system**.

```text
Visitor
  ↓
Newsletter form
  ↓
Newsletter endpoint / email marketing provider
  ↓
Subscriber list
  ↓
Email campaigns
```

The website does not POST newsletter subscribers into the editorial Google Sheet.

## Endpoint

Configure the production endpoint before enabling live signup:

```js
window.EXOTICS_NEWSLETTER_ENDPOINT = "https://YOUR-ENDPOINT.example/subscribe";
```

The endpoint should accept:

```json
{
  "email": "user@example.com",
  "language": "en",
  "source": "exotics-website"
}
```

Expected response: HTTP 2xx on success.

## Provider

The frontend is provider-agnostic. A production deployment can connect this endpoint to an email marketing provider or a small serverless function.

Do not put provider API secrets in `index.html`.

## Privacy / consent

Before production launch, add:
- privacy policy link
- explicit consent wording if legally required
- unsubscribe mechanism handled by the email provider
- abuse/rate limiting
- bot protection where necessary
- double opt-in if required by the selected provider/jurisdiction

## Current UI behavior

If no endpoint is configured, the form does **not** send data anywhere and shows a bilingual `COMING SOON` message.
