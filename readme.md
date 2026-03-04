# Anagram Solver

A clean, fast, browser-based anagram solver. No server required — runs entirely in the browser as a single HTML file.

🔗 **Live site:** [niz8.github.io/Anagram](https://niz8.github.io/Anagram/)

-----

## Features

- Unscramble any set of letters into valid words
- Up to **3 wildcard** characters (`?` or spacebar)
- **Advanced options:** filter by starting letters, ending letters, or exclude specific letters
- Results grouped by word length
- Light / dark mode (auto-detects system preference)
- Word list powered by the [Collins Scrabble Words dictionary](https://github.com/redbo/scrabble/blob/05748fb060b6e20480424b9113c1610066daca3c/dictionary.txt) (~178k words), with a compact fallback if the fetch fails
- Fully responsive — works on mobile and desktop

-----

## Usage

1. Type your letters into the main input
1. Press **space** or `?` to insert a wildcard
1. Optionally expand **Advanced Options** to filter results
1. Hit **Find Words** or press Enter

-----

## Version History

### v1.6.0

- Switched dictionary fetch to local `dictionary.txt` (same directory) — eliminates all CORS issues
- Removed all CSS custom properties (variables) — replaced with hardcoded values for maximum browser compatibility
- Removed Google Fonts dependency entirely — uses system fonts only
- Restored Scrabble-style letter tile logo with staggered animation
- Dark mode now uses `.dark` class on `<body>` and `<html>` instead of `data-theme` attribute

### v1.5.1

- Fixed CORS error on dictionary fetch by switching from `raw.githubusercontent.com` to `cdn.jsdelivr.net` (jsDelivr), which serves files with proper CORS headers

### v1.5.0

- Replaced handwritten word list with live fetch from Collins Scrabble Words dictionary (~178k words)
- Added compact fallback word list in case dictionary fetch fails
- Added version number to footer

### v1.4.0

- Fixed broken tile logo on mobile (tiles were overflowing and rendering incorrectly)
- Removed Google Fonts dependency — switched to system fonts (Georgia, system monospace) for reliability
- Replaced tile logo with simple text-based logo
- Fixed button colour not rendering on mobile
- Expanded fallback word list to ~2,300 words, adding common missing words (mouth, tooth, house, chair, etc.)
- Profanity/slur audit — confirmed word list is clean

### v1.3.0

- Fixed dark mode not covering full screen (was only applying to central card)
- Added `html` background transition so viewport edges go dark correctly

### v1.2.0

- Reverted starts/ends pool inflation fix (it introduced a worse bug — double-counting prefix/suffix letters)
- Restored correct logic: starts/ends are **filters only**, not added to the tile pool
- Fixed broken solving when starts/ends fields were used with basic inputs

### v1.1.0

- Diagnosed and fixed core anagram solving bug: starts/ends letters were being double-subtracted from the pool, causing valid words to be rejected
- Added space-as-wildcard input (pressing space inserts `?`)
- Added wildcard dot counter indicator (3 dots show how many wildcards are used)
- New color theme: warm off-white background, sage green accents, millennial grays
- Added dark mode toggle with system preference auto-detection
- Replaced text logo with Scrabble-style letter tile logo

### v1.0.0

- Initial release
- Single HTML file anagram solver
- Embedded word list (~1,750 words)
- Wildcard support (up to 3 `?` characters)
- Advanced options: starts with, ends with, exclude letters
- Results grouped by word length with animation
- Dark theme (initial version was dark-only)
- Vibecoded disclaimer footer

-----

## Tech

- Vanilla HTML, CSS, JavaScript — zero dependencies
- Single file deployment
- Dictionary: [redbo/scrabble dictionary.txt](https://github.com/redbo/scrabble/blob/05748fb060b6e20480424b9113c1610066daca3c/dictionary.txt)
- Hosted on GitHub Pages

-----

> ⚡ **Vibecoded** — built with vibes and AI assistance. Word results may be incomplete or incorrect. Use at your own risk. Not responsible for Scrabble disputes, crossword catastrophes, or general wordplay mayhem.