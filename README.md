# Alder-Vision

> Standalone HTML audio/MIDI visualisers.

Each file is a self-contained generative visual. Open any HTML directly in a browser (Chromium recommended), grant microphone access, and it runs.

## Structure

```
Alder-Vision/
└── *.html    # Standalone recipe exports — one file per recipe
```

## Recipe Format

Each HTML contains:
- The compiled recipe (JS + GLSL, inlined)
- A `<script id="recipe-source" type="text/plain">` block with the original `active.js` source
- A JSDoc header with `@recipe`, `@engine`, `@tags`, `@description`, and `@controls` metadata

## Browsing Recipes

Search by tag, engine, or description:

```bash
grep -l "@tags.*particles" ~/Projects/Alder-Vision/*.html
grep -l "@engine three" ~/Projects/Alder-Vision/*.html
```

## Loading a Visualiser

Use the `/remix` skill in the admin Claude instance — it scans this folder, lists visualisers, and writes the selected source to `active.js`.

## Requirements

- Chromium (Chrome/Edge) — Web MIDI and Web Audio APIs
- Microphone permission for audio-reactive recipes
- MIDI device optional (visuals run without it)
