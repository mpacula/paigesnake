# Paige's Snake

A simple, ad-free 3D snake game for iPad. No accounts, no persistence: open and play.

**Play:** https://mpacula.github.io/paigesnake/

Everything is a static site (one HTML file plus Three.js), so there is no build step.

## Features

- Two worlds: forest and beach, generated fresh every game
- Smooth third-person movement over rolling terrain
- Configurable number of CPU snakes (0 to 10)
- Eat snacks (apples, bananas, popsicles) to grow
- Bump another snake's body with your head to eat it; it turns into snacks
- Works offline once loaded (service worker); add it to the iPad home screen for a full-screen icon

## Controls

- Touch the left or right side of the screen to turn
- Touch both sides at once to go fast
- Keyboard: arrow keys or A/D to turn, Shift/Space/Up to go fast

## Developing

Serve the folder over HTTP (ES modules don't load from `file://`):

```
python3 -m http.server 8000
```

`index.html?play=forest&cpu=4` (or `play=beach`) skips the menu, which is handy while iterating.
Bump `CACHE` in `sw.js` when you want to force clients to refetch assets.
