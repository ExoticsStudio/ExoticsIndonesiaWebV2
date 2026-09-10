# Changelog

## 4.3.4 — 2026-09-10

### UX / Cinematic Loading
- Changed the loading overlay to a visual-only cinematic gimmick.
- Removed wording that could imply a real database loading/synchronization process.
- Updated deep-scan copy to clearly communicate that it is a visual system effect, not a live backend scan.
- Preserved reduced-motion behavior and the existing transition system.

## 4.3.3 — 2026-09-10

### Content Refresh
- Removed legacy sample news, reviews, guides, and generic genre cards from the visible homepage dataset.
- Replaced demo content with a refreshed 2026 game-release dataset covering January–September 2026.
- Added Grand Theft Auto VI as an upcoming headline item with the official November 19, 2026 release date; it remains outside the Jan–Sep release set because its launch is in November.
- Added Game Universe data with per-game Steam destination where a Steam listing/search is available.
- Added 2026 review and Game Guide placeholders based on current-release titles.
- Updated database scan counters to reflect the new dummy dataset.
- Kept Google Sheets / GET-only editorial architecture unchanged.

### Sources
- Rockstar Games official GTA VI pages for release date and platforms.
- GameSpot's 2026 release schedule for January–September 2026 release-date seed data.
- Sony/PlayStation official announcement for MARVEL Tōkon: Fighting Souls.

This build uses dummy/editorial seed data until the real Google Sheets feed is connected.

## 4.3.5
- Removed the cinematic page-loading overlay temporarily.
- Internal navigation now transitions directly without the loading gimmick.
- Other futuristic HUD/scan visuals remain available where applicable.
