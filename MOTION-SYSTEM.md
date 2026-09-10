# Exotics Futuristic Motion System

## Direction

Cinematic + tactical + industrial futurism.

The goal is to make the interface feel alive without turning the website into generic RGB cyberpunk.

## Motion layers

1. Ambient scan texture
2. Cursor-reactive ambient light on pointer devices
3. Section reveal on scroll
4. Staggered card entrance
5. Cinematic image zoom on hover
6. Tactical light sweep across cards
7. Button scan/sweep
8. HUD status pulse
9. Hero scan line
10. Ad placeholder signal sweep
11. Loading shimmer

## Accessibility

`prefers-reduced-motion: reduce` disables decorative motion and keeps content immediately visible.

## Performance rule

Animations should use transform/opacity where possible. Do not introduce continuous heavy canvas/WebGL effects unless profiling proves the device budget allows them.
