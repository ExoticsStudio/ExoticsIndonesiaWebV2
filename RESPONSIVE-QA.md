# Exotics Responsive QA

## Supported viewport classes

- 320×568 — small phone
- 360×800 — Android/iPhone class
- 390×844 — modern phone
- 430×932 — large phone
- 768×1024 — tablet portrait
- 1024×768 — tablet landscape / small laptop
- 1280×800 — laptop
- 1440×900 — desktop
- 1920×1080 — large desktop
- 2560×1440 — ultrawide / high-resolution desktop

## Rules

- No horizontal page overflow.
- Text wraps safely.
- Cards use fluid grids.
- Images never force viewport width.
- Navigation collapses on narrow screens.
- Modal/dialog content remains inside viewport.
- Buttons and touch controls target at least 44px on touch devices.
- Landscape phones receive a shorter hero.
- Reduced-motion preference remains respected.
- Print layout remains readable.

## Final production QA

Before launch, test real devices/browsers:
- iOS Safari
- Android Chrome
- Desktop Chrome
- Desktop Safari
- Firefox
- Edge

Also test:
- 200% browser zoom
- slow network
- reduced motion
- keyboard-only navigation
- long Indonesian titles
- long English titles
- missing images
- very long URLs
- empty/loading/error states
