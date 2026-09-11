# Homepage Flow Fix — v4.3.7

The homepage previously ended visually around the “Submit your story” placeholder because the main content wrapper was closed too early and stray closing div tags existed before `<main>`.

## Fix
- Removed the stray `</div></div>` before `<main>`.
- Moved the closing `</main>` to after the Community, Newsletter, and 7 Day Login sections.
- Footer remains outside `<main>`.
- Homepage now continues naturally through Community → Newsletter → 7 Day Login → Footer.
