# Alder-Vision

> Recipe archive for [Joe-No](https://github.com/Alder-Dice/Joe-No) — a local terminal-driven living art engine.

Each file is a standalone HTML export of a generative visual recipe. Recipes are self-contained: open any HTML directly in a browser (Chromium recommended), grant microphone access, and the visuals run.

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

## Importing a Recipe into Joe-No

Use the `/remix` skill in the Joe-No admin Claude instance — it scans this folder, lists recipes, and writes the selected source to `active.js`.

## Requirements

- Chromium (Chrome/Edge) — Web MIDI and Web Audio APIs
- Microphone permission for audio-reactive recipes
- MIDI device optional (visuals run without it)
