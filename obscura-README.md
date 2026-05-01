# OBSCURA — A Daily Decryption

A daily cryptogram puzzle. Decode the day's encrypted quote — but the cipher is written in **abstract glyphs that change every dawn**, so what you decoded yesterday teaches you nothing about today's symbols. Single HTML file. Zero dependencies. Drops onto GitHub Pages.

## Why this isn't just another Wordle clone

Wordle is letter-position deduction over a 5-letter target. OBSCURA is whole-quote substitution decryption, with a few twists:

- **The cipher looks alien.** Each day, 26 hand-designed geometric glyphs are mapped to letters in a fresh random permutation. The encoded quote appears as a sequence of symbols — not letter-substituted text. You learn the alphabet from scratch each day.
- **Real cryptanalysis tools.** The built-in **Frequency** panel shows how often each glyph appears in today's cipher, with the English-language baseline (E 12.7%, T 9.1%, A 8.2%…) right below. That's how human codebreakers actually solve substitution ciphers, and the game gives you the same advantage.
- **Tension via limits.** 5 errors and 3 reveals per day. Wrong letter assignments cost an error; the Reveal button uncovers a glyph for free.
- **Glyph siblings.** Tap any glyph to see every other instance of the same symbol light up — pattern-spotting is the core skill.
- **Daily reset, deterministic.** Everyone everywhere gets the same quote and the same glyph set today. Tomorrow at local midnight, fresh puzzle.
- **Streak tracking and shareable results** in the spirit of the daily-puzzle format.

## Features

- 92 quotes from philosophers, writers, and proverbs — variety in length and difficulty (8–20 unique letters per puzzle).
- 26 hand-coded SVG glyphs designed for visual distinctness.
- Procedural daily seed: same puzzle for everyone, different mapping every day.
- Persistent progress: today's state, lifetime stats, current and best streak — all in `localStorage`.
- Full keyboard support, on-screen letter bank, and touch-friendly tap-to-select.
- Mobile-responsive layout.
- Live countdown to the next puzzle.

## Deploy to GitHub Pages

1. Create a new GitHub repository (public).
2. Drop `index.html` (and optionally this `README.md`) into the repo root.
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)`**.
4. Wait ~30 seconds. Live at `https://<your-username>.github.io/<repo-name>/`.

No build step. No framework. No `package.json`.

## Run locally

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

Or just double-click `index.html`.

## How to play

1. Each glyph stands for one letter. Same glyph, same letter, throughout the puzzle.
2. **Tap a glyph** to select it, then type or click a letter to assign it.
3. Right → every instance reveals at once. Wrong → costs one of your 5 errors.
4. Use **⌬ Frequency** to see which glyphs are most common (those are usually E, T, A, O…).
5. Use **✦ Reveal** to uncover a glyph for free (you have 3 per day).
6. Solve before you exhaust your errors. New puzzle at local midnight.

## Tech

- Vanilla HTML / CSS / JS in one file.
- Glyphs drawn as inline SVG from compact path arrays.
- Seeded PRNG (mulberry32) makes the daily puzzle deterministic.
- Two Google Fonts loaded for the dark-academia aesthetic (Cormorant Garamond + Inter + JetBrains Mono).
- No external libraries, no API keys, no build tools.

## License

Do whatever you want with it. Have fun.
