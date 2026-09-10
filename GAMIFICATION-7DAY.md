# EXOTICS 7-Day Login Gamification

## Purpose
A lightweight engagement loop for newsletter members:

`NEWSLETTER → DAILY CHECK-IN → 7-DAY STREAK → REWARD THRESHOLD → REWARD (COMING SOON)`

## Current behavior
- The section exists on the homepage as `#daily-login`.
- Check-in is locked until the newsletter form reports a successful signup.
- Each calendar day can contribute one check-in.
- Consecutive days increment the streak.
- A missed day resets the streak to Day 1.
- Each completed day awards 10 local XP.
- Day 7 reaches the reward threshold.
- The reward catalog and claim flow remain **COMING SOON**.

## Prototype storage
The current static prototype stores state in browser `localStorage`:
- `exotics_newsletter_subscribed_v1`
- `exotics_daily_login_v1`

This is intentionally not treated as a secure membership or reward system.

## Production architecture
When the account/reward backend is ready, move the source of truth server-side:

`Newsletter Provider → Account Identity → Daily Check-in API → Streak Ledger → Reward Service`

The backend should own:
- member identity
- verified newsletter status
- one-check-in-per-day enforcement
- timezone policy
- streak calculation
- XP ledger
- reward eligibility
- reward claim / redemption
- anti-abuse and replay protection

The browser should only display the server-authoritative result.
