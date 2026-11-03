# Feeless Arcade

A single-file hub page linking out to the whole collection of free, Nano (XNO) themed browser games — a grid of game cards plus donation cards for XNO and BTC. No build step, no backend.

## How it works

- Each game card's **Play** button links out to that game's `xno.click` short link (a one-tap human-check page, not an ad) — this is what earns a small amount per visit.
- A small **"skip the short link"** link underneath each card goes straight to the game's GitHub Pages URL, for anyone who'd rather not go through the short link, or in case a short link is still propagating.
- The full game list — name, tagline, emoji, direct URL, short URL — lives in the `GAMES` array near the top of the `<script>` block in `index.html`. To add, remove, re-order or re-link a game, edit that array; nothing else needs to change.
- The **Support this project** section at the bottom shows your XNO address and your BTC address, each with a QR code (built with `nano:`/`bitcoin:` URIs), a copy button and an "Open in wallet" button. There's no payment verification here (unlike the supporter unlock inside each individual game) — it's just a simple, always-visible way to tip either coin.

## Deploy on GitHub Pages

1. Create a new repository, for example `feeless-arcade` (or `game-hub`).
2. Upload `index.html` and `README.md` to the root of the repository.
3. Open **Settings > Pages**, set the source to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
4. After a minute the hub is live at `https://nanorekin.github.io/<repo-name>/`.

Once it's live, you may want to link to it from each individual game (and/or set it as the "homepage" in each repo's GitHub settings) so players can discover the rest of the collection.

## Updating the game list

To add a 15th game later, add a new entry to the `GAMES` array in `index.html`:

```js
{ emoji: "🎮", name: "New Game", tag: "A one-line description.", direct: "https://nanorekin.github.io/new-game/", short: "https://xno.click/NewGame" }
```

Reorder entries in the array to change the order they appear in the grid (currently newest-built first).

## Wallets

- **XNO:** `nano_3a7e3irpbpxbh1n7dk9u3cm9tnd97q1unjxn67ni9gijoxfmzguitx1xgc9u` (same address used across every individual game's tip card)
- **BTC:** `bc1q06lvnx6csg52yf2t29arx6k8xlk3hjnneht5ye`

To change either address, edit the `XNO_ADDRESS`/`BTC_ADDRESS` constants near the top of the script in `index.html`.
