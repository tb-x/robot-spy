# Robot Spy

A 3D hide-and-seek game, made for phones and tablets.

A crowd of robots walks the streets of a neon city at night. The WANTED poster shows the robot you're looking for. Find it and tap it before the time runs out.

- Drag to pan, pinch to zoom in on the crowd, and rotate the city to look behind towers. Hidden robots glow blue through walls.
- A wrong tap costs 5 seconds.
- **Scan** marks the rough area of the target for 10 seconds, at the cost of 10 seconds.
- 🏠 in the corner goes back to the list of all games.

**Play:** https://tb-x.github.io/robot-spy/

## Running locally

It is one `index.html` plus the sound clips in `assets/`, with no build step. [three.js](https://threejs.org/) 0.169 loads from jsDelivr. Serve the folder over HTTP, for example:

```bash
python -m http.server 5203
```

Then open http://localhost:5203. Opened straight from disk the game still works, but the browser won't load the clips: you hear the built-in synthesized sounds, and the spoken lines are silent.

During a search a little spy tune plays. It's made in the browser as the game runs, so it never repeats exactly, gets a bit faster in the last 10 seconds, and dips while the voice is talking. The sound button mutes it with everything else.

## Play offline (add to Home Screen)

On iPhone or iPad, open the game in Safari, tap **Share → Add to Home Screen**, then open it once from the new icon while online. After that it starts full screen and works without internet. Changes I publish arrive on their own: the next online launch downloads them and the one after shows them.

(How: `manifest.webmanifest` gives the icon and full-screen mode; `sw.js`, a service worker, keeps a copy of every file the game uses, including three.js, the font and the sound clips.)

## Sound knobs

At the top of the sound and music sections in `index.html`:

- `CLIP_VOL` and `VOICE_VOL`: how loud the sound effects and the spoken lines are (0 to 1).
- `CLIP_TRIM`: per-clip volume trims that even out the clips. Lower a number if a sound is too loud.
- `MUSIC_VOL`: how loud the music is; `MUSIC_DUCK`: how far it dips under the voice.
- `MUSIC_BPM` and `MUSIC_HURRY`: the tempo, and how much faster it gets in the last 10 seconds.
- `ASSET_V`: bump it after replacing any file in `assets/`, so phones don't keep the old one.

## Audio credits

Voices and sounds: [elevenlabs.io](https://elevenlabs.io). All clips were made on 2026-10-08 with an ElevenLabs **free** plan, so they may only be used non-commercially and must credit ElevenLabs. They are not covered by any licence on this game's code.

- **Spoken lines** (`assets/say-*.mp3`, 12 clips): voice "Roger", model Eleven Multilingual v2. A briefing per level, the wrong-tap and "so close" lines, two "found it" lines, the scan hint, the five-seconds warning and the time's-up line.
- **Sound effects** (`assets/sfx-*.mp3`, 5 clips): ElevenLabs Sound Effects. Error buzzer, success jingle, radar scan, power-down and power-up chime.

The music, the button tap and the last-five-seconds tick are synthesized in the browser.
