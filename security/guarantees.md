---
description: The rules Velvet's on-chain program enforces for every coin.
---

# What the program guarantees

Velvet runs on a Solana program (a smart contract). These rules are written into its code, and every transaction on Velvet has to pass them. No server, admin or creator can skip them.

## The coin

* **The program deploys every coin.** It creates the mint, writes the name and logo link on-chain, and mints exactly **1,000,000,000** tokens.
* **No more can ever be minted.** The mint authority is switched off in the same transaction that creates the coin.
* **No freeze.** The coin has no freeze authority, so nobody can lock your tokens.

## The launch

* **The curve is locked while the line is open.** Nobody can buy before the doors open, not even the creator.
* **One price for the line.** The whole line is filled as one buy, and each wallet's share is exactly proportional to its SOL.
* **Refunds are guaranteed.** If the line misses the guest-list minimum, every lamport committed can be claimed back.
* **The creator's buy is limited and visible.** At most 3% of the supply (about 1.9 SOL), inside the launch transaction, at the start price, and locked if the creator chose to.
* **Free launches can't be forged.** The program checks the creator's signature on-chain against the exact coin being created.

## Trading

* **Fees are capped.** The program will never charge more than its hard limits, whatever the settings say.
* **3% per wallet while bonding.** No line commit, opening buy or curve buy can give a wallet more than 30M tokens.
* **Slippage protection.** Every trade states the worst price it accepts; if the price moved further, the trade fails and nothing is spent.

## Bonding

* **Liquidity goes to Raydium automatically** when the curve sells out, with the 30% reserve, at the curve's last price.
* **100% of the LP is locked in Raydium's locker**, permanently. Nobody can withdraw it.
* **Recycled fees are locked too:** LP from fees sent back into the pool is burned.

## Money that isn't yours to take

* The SOL on a bonding curve can only leave through trades, refunds and bonding.
* Velvet's treasury only receives the fees listed in [Fees](../how-it-works/fees.md).

You can check all of this: the program's source code is public and the deployed program is a [verified build](verified-build.md) of it.
