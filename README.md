# Paige's Snake

A simple, ad-free 3D snake game for iPad. No accounts, no persistence: open and play.

**Play:** https://mpacula.github.io/paigesnake/

Everything is a static site (one HTML file plus Three.js), so there is no build step.

## Features

- Three worlds: forest, beach and space (snakes wear space suits there), generated fresh every game
- Smooth third-person movement over rolling terrain
- Configurable number of CPU snakes (0 to 10)
- Eat snacks (apples, bananas, popsicles) to grow
- Bump another snake's body with your head to eat it; it turns into snacks
- Lava pools (1 or 2 per world) set the snake on fire and shrink it; stay out
- A rare unicorn snack turns the snake into a rainbow snake with a unicorn head
- Music: synthesized in the browser with Web Audio, no audio files. Normal play
  is a chiptune "Ode to Joy" (Beethoven); space opens with the fanfare from Strauss's
  "Also sprach Zarathustra" and settles into an ambient synth loop; unicorn mode
  switches to a bell-and-harp "Twinkle, Twinkle, Little Star". The tunes are public domain and the
  arrangements are original, so there is nothing to license. Toggle with the
  speaker button or the Music checkbox in the menu
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

`index.html?play=forest&cpu=4` (or `play=beach`, `play=space`) skips the menu, which is handy while iterating.
Add `&at=pool` to start next to a lava pool, `&burn=1` to start on fire, `&unicorn=1` to start in unicorn mode, `&nomusic=1` to skip audio.
Bump `CACHE` in `sw.js` when you want to force clients to refetch assets.
