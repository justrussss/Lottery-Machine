# Lottery Machine

A 3D lottery machine that picks names at random. Add your names, press **Draw a name**, and watch the balls get blown around inside a glass globe until one is sucked into a tube, carried around the machine and dropped onto the results shelf.

It runs entirely in the browser as a single HTML file. There is no build step and nothing to install.

## What it's for

Use it anywhere you'd normally draw names out of a hat:

- raffles and giveaways
- picking who goes first, or who presents next
- classroom or team draws
- choosing winners on a stream or in a meeting

Each name is drawn once. Names that have already been picked stay on the shelf until you reset the draw, so nobody is picked twice.

## How to use it

1. Open `Lottery Machine.html` in a modern browser (it needs WebGL).
2. Add names in the **Names** panel. Separate several names with commas, or add them one at a time. Up to 60 names, 24 characters each.
3. Press **Draw a name** (or hit **Space**).
4. The sign above the machine shows the winner once the ball lands on the shelf. Press draw again for the next one.

| Control | What it does |
| --- | --- |
| **Draw a name** | Spins the globe, opens the exit and sends one ball through the tube |
| **Mix balls** | Keeps the balls tumbling without drawing |
| **Reset draw** | Puts every ball back in the globe |
| **Intensity** | How hard the air jets and spin are |
| **Build-up** | How many seconds the balls mix before the exit opens |
| Drag / scroll / pinch | Orbit and zoom the camera |

On small screens the names list opens from the **Names** button.

## How it works

- Rendered with [three.js](https://threejs.org/) (r128, loaded from a CDN).
- The balls are simulated in 2D inside the globe: gravity, ball-to-ball and wall collisions, air jets from the base, and the spinning drum. They are drawn in 3D with random depth, so they tumble as they move.
- The winner is chosen by which ball reaches the exit first after the gate opens, so the result comes from the simulation, not a pre-picked random number.
- The exit tube, globe, shelf and stage are generated in code. There are no image or model files.

## Requirements

- A browser with WebGL.
- An internet connection, because three.js and the Figtree font load from cdnjs and Google Fonts.

## Notes

The pick is decided by a physics simulation driven by `Math.random()`. It is fine for casual draws, but it is not a certified random-number generator, so don't use it where an audited draw is required.
