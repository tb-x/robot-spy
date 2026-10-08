# Robot Spy

A 3D hide-and-seek game, made for phones and tablets.

A crowd of robots walks the streets of a neon city at night. The WANTED poster shows the robot you're looking for. Find it and tap it before the time runs out.

- Drag to pan, pinch to zoom in on the crowd, and rotate the city to look behind towers. Hidden robots glow blue through walls.
- A wrong tap costs 5 seconds.
- **Scan** marks the rough area of the target for 10 seconds, at the cost of 10 seconds.

**Play:** https://tb-x.github.io/robot-spy/

## Running locally

It is a single `index.html` with no build step. [three.js](https://threejs.org/) 0.169 loads from jsDelivr. Serve the folder over HTTP, for example:

```bash
python -m http.server 5203
```

Then open http://localhost:5203. All sounds are synthesized in the browser.
