# Flex Pulse

A tracker for Amazon Flex drivers, built as a Telegram Mini App.

- Guided block steps from leaving home to getting back, with a whole-trip timer and a route timer
- Miles by leg: home to station, station to last stop, last stop to home
- True cost per mile from your car (owned, loan or lease), including depreciation
- Surge vs base per station, and how far ahead each block was grabbed
- Expenses, a mileage view and a tax-year summary
- Booked blocks, and how many hours you can still book this week and today
- Areas you were sent to (several per block), which areas and routes pay best, and a map of them
- Saved gate, building and locker codes by address
- English and Ukrainian, with a short first-launch guide and 1-minute setup

## How it runs
`index.html` is the whole app: plain HTML, CSS and JavaScript, no build step. GitHub Pages serves it, and the Telegram bot opens it as a Mini App.

## Data
Each user's data is saved on their phone and backed up to their own Telegram account (Telegram CloudStorage). There's no server, and nobody else can see another user's data.

## Publishing an update
Replace `index.html` and commit to `main`. Pages redeploys in about a minute, and users get it the next time they open the app.

## Map
The area map draws on OpenStreetMap tiles (© OpenStreetMap contributors) through Leaflet. Area names are looked up on OpenStreetMap Nominatim only after the user agrees; addresses are never sent. Without internet the app shows a simple drawing instead.

## Old version
`/flex-pulse/classic/` is v0.17, frozen. It shares the same data as the main app (same origin and storage), and the `ocr/`, `places/` and `zips/` folders. Only its three data paths point one level up (`../ocr/`, `../places/`, `../zips/`). Settings has an "Open the old version (v0.17)" link.

### Rolling back
From the mildest step:
1. Settings -> App -> Design -> Classic (one tap, done by the user).
2. Automatic: if the new design crashes, the app switches to Classic and says so.
3. Settings -> "Open the old version (v0.17)": same data, frozen code.
4. Owner: in BotFather, set the Mini App / menu button URL to `https://vladikbrumar.github.io/flex-pulse/classic/`. Everyone gets v0.17 on their next open; switching back is the same edit.
5. Owner/dev: `git revert` the v0.18 commit. The `classic/` folder can stay.
