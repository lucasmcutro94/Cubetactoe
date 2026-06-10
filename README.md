# Cube Tac Toe

Tic Tac Toe played on the surface of a 3×3 Rubik's Cube. The cube has a black body
and all-white stickers, and is fully rotatable so you can inspect every side.

## Run it

The game loads three.js as an ES module from a CDN, which browsers block over
`file://`. Serve the folder over HTTP instead:

```bash
cd "Cube Tac Toe"
python3 -m http.server 8000
```

Then open <http://localhost:8000> in your browser. (Any static server works —
e.g. `npx serve` if you prefer Node.)

## Rules

- **Player 1 is X**, **Player 2 is O**. X moves first.
- On your turn:
  1. **Place** your mark on any empty white sticker (click it).
  2. **Make exactly one cube move** using the buttons.
- Win by getting **3 of your marks in a row** (row, column, or diagonal) on a
  **single face**.
- **Victory is only checked after your rotation finishes** — never the instant you
  place a mark. And on your turn, **only your own** line can win; if your move happens
  to complete the opponent's line, it's ignored until their turn.

## Controls

- **Drag** empty space — rotate / inspect the whole cube.
- **Scroll / pinch** — zoom.
- **Click a sticker** — place your mark (only during the place phase).
- **Move buttons** — perform your required cube move:
  - **Face moves:** `U U' D D' L L' R R' F F' B B'` (a prime `'` = the same face the
    other way).
  - **Slice moves:** `M M' E E' S S'` (the three middle layers).
- **Reset game** — clear all marks and start over with X.

## Notes

- All 18 moves are standard quarter-turns. Because every sticker is white, marks are
  your only landmarks — they travel with the stickers as the cube turns.
- Single self-contained file: [`index.html`](index.html).
