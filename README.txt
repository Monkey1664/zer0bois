ZeroBois - front-end prototype (3 burn-to-play games)

Open zerobois-home.html in a browser (needs internet for fonts + three.js CDN).
Keep all files in this one folder; pages link to each other by file name.

FILES
- zerobois-home.html .............. landing page, links to the 3 games
- burn-royale TEST.html ........... Burn Royale (dice-style burn game)
- burn-royale-coinflip.html ....... Coin Flip
- send-it-to-zero.html ............ Send It To Zer0 (odometer/reel game)
- *-how-it-works.html, burn-royale-odds-reference.html .. rules/odds pages
- burn-royale-sound-settings.html . sound settings page

HOW IT'S BUILT
Each page is a single self-contained HTML file: CSS, images (base64) and all
JavaScript are inline. Search the <script> blocks for:
- computeSplit()  -> every wager: 95.5% to pot, 4% to ignite_pool (team), 0.5% destroyed
- payout cap      -> a win pays at most 40% of the pot
- burnStepTick / stepBurnAmount -> bet-amount bar logic
- token config (TOKENS) -> SOL / JUP / MockJUP settings
RTP is roughly 93-95% across the games (checked by simulation).

WHAT IS MOCKED (needs real Solana work)
- Wallet connect is a fake menu - no wallet adapter / signing.
- Outcomes use browser Math.random() - needs verifiable randomness (e.g. VRF) on-chain.
- Pot and balances live in browser localStorage - needs an on-chain program
  holding the pot, taking burns/wagers and paying out.
- No backend, audit or licensing.
