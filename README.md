# 🏆 Southern Kitchen Fantasy Server League

Turn a restaurant shift into a fantasy sports season. Draft your servers onto teams, hand everyone a randomized bingo board of menu items, and rack up points for every upsell, big check, and fast ticket — all from a single HTML file with no install required.

**[▶ Live demo](https://claude.ai/artifact/51iePC3nL4AjMK7x2bYQqd)**

## Features

- **⚙️ Setup** — create teams and add servers (or leave them Solo, no team required).
- **🎯 Draft Room** — join a team by typing a name right there, rate each server's Sales / Upselling / Speed / Accuracy / Guest Experience (1–5 stars, just for fun), and remove players who've left.
- **📝 Scorekeeper** — every server gets their own randomized 25-square (5×5) bingo board drawn from the menu. Tap a square each time you sell that item — selling it again stacks more points. Complete a row, column, or diagonal for a bonus, be the first to get a Bingo for a Clutch bonus, and fill the whole card for the big one.
  - **⏱️ Ticket Time Bonus** — every board includes a timing bonus square. Toggle **Rush Hour** (20-minute goal) vs **Normal Hours** (12-minute goal) and ring it up whenever a ticket beats the clock.
  - **🔀 New Board** — redeal a fresh randomized board anytime; one is also dealt automatically at the start of each shift.
- **🏆 League** — live team standings, an MVP leaderboard, and a history of every completed shift.
- **💬 Live Chat** — chat in real time with whoever else has the page open right now (nothing is saved once everyone closes it).
- **📋 Rules** — a plain-English rundown of how scoring works, built into the app.

## How to use it

1. Open the app (live demo link above, or `fantasy_server_league_v2.html` locally).
2. **Setup:** add your teams and servers.
3. **Draft:** assign teams, set skill ratings, or let people join themselves.
4. **Scorekeeper:** pick a server and start ringing up sales as the shift happens.
5. **End Shift** when the shift wraps — it logs the results and deals everyone a fresh board for next time.
6. Check **League** to see standings, crown an MVP, and look back at shift history.

## Customizing the menu

The scoring pool lives in one array near the top of the `<script>` block:

```js
const REAL_TASKS=[
 ["Item Name", pointValue],
 ...
];
```

Edit the names and point values to match your own menu, then save. No build step, no dependencies — it's a single self-contained HTML file.

## Tech

- Vanilla HTML, CSS, and JavaScript — no frameworks, no build step.
- Game state (teams, players, scores, shift history) is saved to the browser's `localStorage`, per device/browser.
- Live chat uses an ephemeral real-time channel between everyone with the page open — it isn't saved and doesn't sync your scoreboard data across devices.

## Data & privacy

Everyone who opens the app keeps their own local copy of the league (teams, players, scores). It's not a shared live scoreboard across devices — if your team opens it on separate phones, each phone has its own save. Use **New Season** (top right) to wipe everything and start fresh.

## License

Use it, tweak it, run your own league with it.
