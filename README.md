# Sandcaller

A pixel-art desert toy in one self-contained HTML file. Cross an endless sea of dunes at sunset, plant a thumper, and try to climb onto the giant sandworm it calls.

Open `index.html` in a recent browser (it also works from `file://`). WebGL2 required.

**Controls** (in-game text is in French)
- ZQSD / WASD / arrows: move · Shift: run · mouse: look (click to capture)
- E: plant the thumper / hook onto the worm · Space: jump / jump off the worm
- Tab: wide view · M: sound (off by default) · touch: joystick + on-screen buttons

**Two ways the worm arrives** (decided by the terrain around the thumper):
- On top of a big dune it surfaces and arrives horizontally, half out of the sand, slowing down. Get within reach of its body and press E to throw grappling hooks, then climb onto its back.
- On a small dune or low ground it strikes from below: only its open mouth rises, in a funnel of sliding sand. It swallows the thumper, and you too if you are too close (it spits you back out).

**Tech:** dunes are generated in Web Workers as a 1024 m seamlessly tiling height field and ray-marched per pixel in WebGL2 at about 340 px tall. Sand displacement is dynamic (bulge and furrow). The image uses a strict palette with 4×4 Bayer dithering, a 1 px outline pass and heat shimmer. The interface is Canvas 2D; sound is synthesised with Web Audio. Internal resolution drops automatically if frames get slow (`?fixedres` disables this).
