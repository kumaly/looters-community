# CHANGELOG

## Version 0.0.5

Reworked the way datas from the blockchain are updated, stored and called from the app.
Leaderboard and collections listing datas should now refresh properly.

Improved some pages for desktop display, still a lot to do there.

Updated the estimated gas inside the app using following values:

```
export const GAS_LOOTBOX = {
  REGISTER: 20_000,
  BUY: 55_000,
  BUY_AND_OPEN: 55_000,
  BUY_AND_OPEN_EXTRA: 20_000,
  CLAIM: 80_000,
  CRAFT: 55_000,
  CRAFT_AND_OPEN: 55_000,
  GIFT: 55_000,
  OFFER_CANCEL: 35_000,
  OFFER_CREATE: 55_000,
  OFFER_CREATE_EXTRA: 20_000,
  OFFER_TAKE: 55_000,
  OPEN: 55_000,
  TRANSFER: 40_000,
  TRANSFER_EXTRA: 3_000,
};
```

EXTRA is what is multiplied by the quantity -1, so to open 3 lootboxes you pay 2x the extra and 1x the base.
REGISTER is what is added if the receiver of the operation has never used the smart contract, for example if you transfer a loot to a friend to get him started or the first time you buy a lootbox.

Notifications are disabled in that version until we redo that module with the new datas format.

## Version 0.0.4

Leaderboard has been activated, refresh rate is around every minute but you have to pull the page to refresh like in most mobile apps.

Points are credited that way :

- Each variation with 1+ loot in your inventory
  - 1 point / common \* collection level
  - 3 points / uncommon \* collection level
  - 5 points / rare \* collection level
  - 7 points / mythic \* collection level
  - 10 points / legendary \* collection level
- Each claim of a collection : points of all variations \* 1.5

Play screen has been updated to, it now show your progression per collection and how much there is in the pot.
Refresh rate is also around 1 min and you also have to pull to refresh.

Inside a collection, the app connects directly to the RPC right now, so the refresh rate is 1s there.

We also removed the coin logo on the collection vignettes has the app is now single chain.

## Version 0.0.3

Integration of collection from LV1 to LV8 with gradual increase of price and difficulty.

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

For 0.0.2, all collections are setup at LV1 and only 4 collections are activated.

### Mainnet only

0.0.1 was running on the testnet, but due to the nature of the game it made it obvious that having no resources limitation broke everything.
We choose to migrate to mainnet only and gift players lootboxes instead so that they can try the game on our bankroll, without having to pay if they dont want to continue testing.
