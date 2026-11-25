# The Last House — Three.js Horror Animation

A browser-based, five-minute cinematic horror sequence with a haunted forest/house environment, animated rain and mist, a ghost reveal, Hinglish narration cues, and procedurally generated ambient audio.

## Run locally

1. Install Node.js (LTS).
2. Open a terminal in this folder.
3. Run:

```bash
npx serve .
```

4. Open the local URL printed by the server (usually http://localhost:3000) in Chrome or Edge.
5. Press **Play film**. The browser requires a user click before audio can start.

Three.js is loaded from jsDelivr via an import map, so an internet connection is required.

## Controls

- **Play film** — starts the 5-minute timeline and browser Hindi voice narration.
- **Pause / Restart** — pauses or resets the film.
- **Sound** — mutes/unmutes generated ambience and effects.
- **Record video** — records the WebGL canvas and generated audio to a WebM file. Press again to stop and save.

## Export MP4

Browsers commonly record MediaRecorder output as WebM, not MP4. Convert the saved file with FFmpeg:

```bash
ffmpeg -i the-last-house-horror.webm -c:v libx264 -pix_fmt yuv420p -c:a aac -b:a 192k -movflags +faststart the-last-house-horror.mp4
```

For a clean full-length recording:
1. Use desktop Chrome/Edge, close other tabs, and set browser zoom to 100%.
2. Start recording, then press Play film.
3. Let the full five-minute timeline finish.
4. Stop recording and convert the WebM using the command above.

## Audio notes

The drone, wind bed, stings, and whispers are synthesized in the browser using Web Audio API. The narration uses the device/browser Hindi speech voice (availability and voice quality vary by operating system). For a polished Hinglish voice, replace browser TTS with your own recorded narration or a licensed TTS voice, then mix it with the sound bed in an editor.

## Current creative scope

This is a working real-time 3D prototype, not a pre-rendered studio film. The environment, camera path, rain, fog, ghost, lights, and audio are generated at runtime. You can extend it with original GLB character/house models, higher-quality textures, recorded Foley, and custom voice acting.
