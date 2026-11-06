# S2.5 Mobile 2.5D Short Engine (starter MVP)

## What this is
A free, browser-based Three.js starter renderer designed for Android Chrome. It creates a procedural 3D street/house set, places a simple cartoon character in it, animates a few basic actions, overlays captions, and records the canvas to WebM using the browser's MediaRecorder API.

No API key, paid API, server, or Claude Pro subscription is required. Three.js is loaded from jsDelivr, so the page needs internet access.

## Important limitations
- This is a starter engine, not the complete proprietary renderer shown in the tutorial.
- It does not generate new 3D sets or character rigs from text. The scene is procedural and currently generic.
- It does not generate narration. You can upload an audio file, subject to Android browser audio-capture support.
- Android Chrome generally exports WebM, not guaranteed MP4. Convert WebM to MP4 in Canva if needed.
- Rendering can be slow or interrupted if Android runs out of memory, the tab is backgrounded, or the phone sleeps.
- No AI image/video APIs are called.

## Run it on Android
A browser module page should be served over HTTPS or localhost; opening index.html directly as a file may fail because of browser module/CORS restrictions.

### Easiest free hosting: GitHub Pages
1. Create a new public GitHub repository named `s2-5-mobile-engine`.
2. Upload `index.html` to the repository root.
3. Open repository Settings → Pages.
4. Under Build and deployment, choose Deploy from a branch; select `main` and `/root`; Save.
5. Wait for GitHub Pages to publish the HTTPS page.
6. Open the published URL in Chrome on Android.

GitHub Pages is free for public repositories. Repository/account UI may differ slightly on mobile.

## Use it
1. Open the page and tap Preview.
2. Edit the scene JSON or ask Claude using `CLAUDE_PROMPT.txt`.
3. Paste Claude's JSON into the scene-plan box and tap Load scene plan.
4. Optionally upload narration audio.
5. Tap Render WebM and keep the tab open until finished.
6. Download the WebM file. Convert to MP4 in Canva if required.

## JSON format
[
  {"duration": 4, "caption": "SHORT CAPTION", "narration": "Voice line.", "action": "brick"}
]

Supported actions: brick, look, point, explain, count, sad, end.
