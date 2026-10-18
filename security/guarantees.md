---
description: The rules Velvet's on-chain program enforces for every coin.
---

# What the program guarantees

Velvet runs on a Solana program (a smart contract). These rules are written into its code, and every transaction on Velvet has to pass them. No admin or creator can skip them.

## The coin

* **The program deploys every coin.** It creates the mint, writes the name and logo link on-chain, and mints exactly **1,000,000,000** tokens.
* **The name, ticker and logo link are locked.** They're stored in the coin itself and nobody, not the creator and not Velvet, can change them.
* **No more can ever be minted.** The mint authority is switched off in the same transaction that creates the coin.
* **No freeze.** The coin has no freeze authority, so nobody can lock your tokens.
* **Nothing hidden in the token.** Coins are Token-2022 tokens whose only extras are their name, ticker and logo link: no transfer fees, no transfer hooks, no permanent delegate. Velvet Pools refuses any coin with other extras.

## The launch

* **The curve is locked while the line is open.** Nobody can buy before the doors open, not even the creator.
* **One price for the line.** The whole line is filled as one buy, and each wallet's share is exactly proportional to its SOL.
* **No bonding during the cover charge.** Nothing can finish the curve and move a coin to its pool until the cover charge is over.
* **Big lines unlock gradually.** When a line puts more than 30 SOL into the curve, 25% unlocks at open and the rest over an hour.
* **Refunds are guaranteed.** If the line misses the guest-list minimum, every lamport committed can be claimed back.
* **The creator's buy is limited and visible.** At most 3% of the supply (about 1.9 SOL), inside the launch transaction, at the start price, and locked if the creator chose to.
* **Free launches can't be forged.** The program checks the creator's signature on-chain against the exact coin being created.

## Trading

* **Fees are capped.** The program will never charge more than its hard limits, whatever the settings say.
* **3% per wallet while bonding.** No line commit, opening buy or curve buy can give a wallet more than 30M tokens.
* **Slippage protection.** Every trade states the worst price it accepts; if the price moved further, the trade fails and nothing is spent.

## Bonding

* **Liquidity goes into the coin's Velvet Pools pool automatically** when the curve sells out, with the 30% reserve, at exactly the curve's last price.
* **The liquidity is locked forever.** Velvet Pools has no withdraw, and only Velvet's program can open a pool, one per coin.
* **Recycled fees are locked too:** LP from fees sent back into the pool is burned.

## Money that isn't yours to take

* The SOL on a bonding curve can only leave through trades, refunds and bonding.
* Velvet's treasury only receives the fees listed in [Fees](../how-it-works/fees.md).

You can check all of this: the program's source code is public and the deployed program is a [verified build](verified-build.md) of it.
