# CHANGELOG

## Version 0.0.2

### Marketplace

- Prices suggestion to sell a loot are now multiple of the lootbox price :
  - /4 for common
  - /2 for uncommon
  - /1 for rare
  - x2 for mythic
  - x3 for mythic
  - x5 for legendary
  - x9 for legendary
  - x15 for legendary

To be noted that the player can choose any price he wants regarless of the loot rarity he is selling, but he can't input his own price to keep the GUI and the experience simple.

One can still input his own price using the smart contract directly, and that will probably be possible from the desktop version.

### Difficulty

We replaced the previous Easy / Medium / Hard difficulty system by a more granular one based on a matrix of 2 metrics :

- Lootbox price
- Spread in odds between common and legendary assets

We now use levels of difficulty as follow :

- LV1 : ~0.05 USD / lootbox and x2 in spread, meaning legendaries are twice less frequent than commons
- LV2 : LV1 x 1.1 USD / lootbox and LV1 x 1.5 in spread
- LV3 : ...

Those values will be fine tuned each season to get the right steps between levels of difficulties.

For 0.0.2, all collections are at setup at LV1 and only 4 collections are activated.

### Mainnet only

0.0.1 was running on the testnet, but due to the nature of the game it made it obvious that having no resources limitation broke everything.
We choose to migrate to mainnet only and gif players lootboxes instead so that they can try the game on our bankroll, without having to pay if they dont want to continue testing.