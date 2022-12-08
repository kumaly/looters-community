## Disclaimer

This is a work in progress, anything you read here might change in the future.

## Dont want to read ? Watch a short video instead !

This is a short clip showing the current state of the project in version 0.0.4 :)

[Video on Youtube](https://www.youtube.com/watch?v=hAAXdMUUA1Q).

## How to try out the pre alpha of the game

Follow this [HOWTO](./HOWTO.md).

## Community

Join us on [Discord](https://discord.gg/ceXWjBQtZe).

Ask us for free looboxes to open !

# Overview

Looters is a EVM blockchain game where you buy and open lootboxes to collect loots with 5 levels of rarity.

Each time a player buys a lootbox, 90% of the coins collected stays in the smart contract, we call it the Pot (like in Poker).

Once a player has collected one of each loot from the collection, they can call the claim function on the smart contract and collect the current Pot, burning _that_ loot in the process.

After the Pot has been claimed, every lootbox purchase will fill it up and the game continues until the end of the current season.

From the 10% that doesn't go into the Pot, 50% goes into the Grand Prize for the current Season and 50% to the team.

# Strategy

The game is designed to engage players to compete, collaborate and trade the loots they have in duplicate for other loots they need in order to claim the Pot at the lowest cost possible.

The loots can be transferred between accounts like a regular NFT and the smart contract integrates a marketplace.

The contract is heavily optimized for low gas fees, you will be surprised :)

Like in poker, to win at this game players has to be both lucky and strategic.

# Lootboxes

There are 5 types of lootbox :

- Common : 5 random loots from common to legendary
- Uncommon : 4 random loots from uncommon to legendary
- Rare : 3 random loots from rare to legendary
- Mythic : 2 random loots from mythic to legendary
- Legendary : 1 random legendary loot

# Actions on the Smart Contract

## Buying a common lootbox

This is the main action a player can do.
The other rarities of lootboxes cannot be bought, they have to be crafted or won.
Lootboxes can be bought in bulk, from 1 to 99 to save even more gas fees.

## Crafting a lootbox

If the player has each loot of a given rarity like common, he can fuse them into a lootbox of the superior rarity like uncommon.

A player can only have a maximum of 9 of a given loot (like common #1), using crafting they can recycle duplicates and increase the odds of finding better loots with a lootbox of a higher rarity.

## Opening a lootbox

Most lootboxes are opened when bought, but a player can won free lootboxes too.
Blockchains operators can also buy lootboxes to distribute on their communication channels, to incentivize players to try the collections on their chain.

## Transfering loots

Trading loots with other players is a good way to complete the collection without opening more lootboxes.

## Creating and Taking offers

Using the integrated marketplace, players can buy and sell their loots directly.
While a lot more convenient than a Transfer, there is a 10% fee, half of which goes into the Grand Prize.

## Claiming the Pot

When players calls that action, one of each loot in their collection is burned and the whole balance of the smart contract (aka the Pot) is sent to their account.

# Collections

The game includes multiple themed collections, each one with a different smart contract deployed on a specific blockchain for the current season.

# Drop Odds and Difficulty

Each collection has a drop table that show the odds to get a particular loot. This is stored inside the smart contract and we do not use an oracle.
That information is also available to the player inside the app for transparency.

Collections are organised in 4 levels of difficulty with the following characteristics :

- Easy : 15 to 35 loot variations and commons are 2x more frequent than legendaries
- Medium : 36 to 55 variations, 2x more expensive per lootbox and commonw are 4x more frequent than legendary
- Hard : 56 to 71 variations, 4x more expensive and 8x the frequency
- Insane : 72 variations, 8x more expensive and 16x the frequency

Different players profiles will like more or less each difficulty, depending on how they like to play with their luck and collaborate with others and of course depending on their bankroll.

# Fees

Each time a lootbox is sold or a market offer is taken, 10% of the amount is collected as fees and distributed that way :

- 4% for the season leaderboard
- 1% for the season events (gifted lootboxes)
- 5% for The Looters team

# Seasons

The game is organized by seasons of 15 days that start when the smart contracts are deployed.
Players have the whole season to compete for the Pots and earn points into the Leaderboard for a chance to win the Grand Prize.

Once the season is over, all the smart contracts are "self destroyed" to avoid players buying more lootboxes or trying to sell old season loot to new players.

The remaining coins in the Pots are collected and used to airdrop free lootboxes for the next season.

We then start a new season with collections deployed on different blockchains and new collections are introduced.

## Season Leaderboard

Opening lootboxes and trading loot to win the Pot is the core loop of the game, but the real goal is to earn points and take the tops spots of the Season Leaderboard.

During the season, 5% of all coins used to buy lootboxes or take offers are added to the Grand Prize.

At the end of the season, the top 10% of the player will share that Prize with a payout structure similar to a Poker tournament (a large chunk for the winner, and less and less as we go down the list of players).

To be noted that at the current stage of development the Grand Prize is managed by the looters team, because it aggregates coins from multiple chains and will require more work to make it decentralised.

We expect the leaderboard to be the main focus of players competing in hard and insane difficulties.

## How players get points in the leaderboard

TBD.

# EVM

## Vanilla EVM

The game is designed to run on vanilla EVM, without the use of external services like and oracle because most of them do not work on smaller EVM chains.

We decided that having the randomizer inside the smart contract, even if not the best solution, was the most suited to run on as many chains as possible.

Our game doesn't store huge amounts of coins like a DeFi app does, and all drops are public so anyone can check that the odds are correct.

Development is all about trade-offs right :)

## Currency for Collections

The game does not have its own coin, for each blockchain it runs on it uses the native coin of that blockchain.

For smaller chains that's a good thing, because players will have to set up the chain in Metamask and hold some of its coins to engage with some collections in the game.

As players can win lootboxes for any collection, they'll want to open them and do that setup work :)

Also to be noted that players gets more points in the Leaderboard if they participates in all collections on all chains, so no one is left behind.

The Pot of a collection is also paid in the native coin of the chain.

## Currency for the Grand Prize

The Grand Prize is filled up with coins from many chains but will be paid in one currency only to make things simpler and cost effective.

For each season, one blockchain will have the oportunity to sponsor the season and be the one used for the Grand Prize payout on the most actives and engaged players of the game.
