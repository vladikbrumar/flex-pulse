# Flex Pulse

A tracker for Amazon Flex drivers, built as a Telegram Mini App.

- Guided block steps from leaving home to getting back, with a whole-trip timer and a route timer
- Miles by leg: home to station, station to last stop, last stop to home
- True cost per mile from your car (owned, loan or lease), including depreciation
- Surge vs base per station, and how far ahead each block was grabbed
- Expenses, a mileage view and a tax-year summary
- Saved gate, building and locker codes by address

## How it runs
`index.html` is the whole app: plain HTML, CSS and JavaScript, no build step. GitHub Pages serves it, and the Telegram bot opens it as a Mini App.

## Data
Each user's data is saved on their phone and backed up to their own Telegram account (Telegram CloudStorage). There's no server, and nobody else can see another user's data.

## Publishing an update
Replace `index.html` and commit to `main`. Pages redeploys in about a minute, and users get it the next time they open the app.
