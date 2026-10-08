# Robot Spy

A 3D hide-and-seek game, made for phones and tablets.

A crowd of robots walks the streets of a neon city at night. The WANTED poster shows the robot you're looking for. Find it and tap it before the time runs out.

- Drag to pan, pinch to zoom in on the crowd, and rotate the city to look behind towers. Hidden robots glow blue through walls.
- A wrong tap costs 5 seconds.
- **Scan** marks the rough area of the target for 10 seconds, at the cost of 10 seconds.

**Play:** https://tb-x.github.io/robot-spy/

## Running locally

It is one `index.html` plus the sound clips in `assets/`, with no build step. [three.js](https://threejs.org/) 0.169 loads from jsDelivr. Serve the folder over HTTP, for example:

```bash
python -m http.server 5203
```

Then open http://localhost:5203. Opened straight from disk the game still works, but the browser won't load the clips: you hear the built-in synthesized sounds, and the spoken lines and the city background are silent.

## Sound knobs

At the top of the sound section in `index.html`:

- `CLIP_VOL` and `VOICE_VOL`: how loud the sound effects and the spoken lines are (0 to 1).
- `CITY_VOL`: how loud the neon-city background is during a search.
- `CLIP_TRIM`: per-clip volume trims that even out the clips. Lower a number if a sound is too loud.
- `ASSET_V`: bump it after replacing any file in `assets/`, so phones don't keep the old one.

## Audio credits

Voices and sounds: [elevenlabs.io](https://elevenlabs.io). All clips were made on 2026-10-08 with an ElevenLabs **free** plan, so they may only be used non-commercially and must credit ElevenLabs. They are not covered by any licence on this game's code.

- **Spoken lines** (`assets/say-*.mp3`, 12 clips): voice "Roger", model Eleven Multilingual v2. A briefing per level, the wrong-tap and "so close" lines, two "found it" lines, the scan hint, the five-seconds warning and the time's-up line.
- **Sound effects** (`assets/sfx-*.mp3`, 6 clips): ElevenLabs Sound Effects. Error buzzer, success jingle, radar scan, power-down, power-up chime, and the looping neon-city background.

The button tap and the last-five-seconds tick are still synthesized in the browser.
