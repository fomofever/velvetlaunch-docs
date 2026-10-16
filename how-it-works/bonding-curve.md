---
description: How a coin is priced before it bonds, and the 70/30 split.
---

# The bonding curve

After the doors open, a coin trades on Velvet's **bonding curve**: a formula in the program that sets the price from how many tokens have been sold. Buying pushes the price up, selling brings it down, and there's always someone to trade with (the curve itself).

## The 70/30 split

Every coin has a fixed supply of **1,000,000,000 tokens**, split in two at launch:

| Share | Tokens | What it's for |
| --- | --- | --- |
| **70%** | 700,000,000 | Sold on the bonding curve (including the line and any opening buy) |
| **30%** | 300,000,000 | Kept aside for the Raydium pool when the coin bonds |

When all 700M curve tokens are sold, about **100 SOL** has gone in and the coin [bonds to Raydium](bonding-to-raydium.md). The 30% goes into the pool with that SOL, at the price where the curve ended, so there's no jump when it moves.

## The shape of the curve

Velvet uses a constant-product curve (the same idea as most decentralised exchanges) with virtual reserves:

* virtual SOL × virtual tokens = constant
* it starts at **75 virtual SOL** and **1,225M virtual tokens**

That gives:

| | Price per token | Market cap (1B supply) |
| --- | --- | --- |
| Start | ≈0.000000061 SOL | ≈61 SOL |
| When it bonds | ≈0.00000033 SOL | ≈333 SOL |

The price rises about **5.4×** from the first token to the last token on the curve. Early buyers get more tokens per SOL, and every buy moves the price a little more than the last.

{% hint style="info" %}
These are Velvet's mainnet settings. Settings live in an on-chain config that can only change after a public timelock; see [Settings and the timelock](../security/timelock.md). Every coin keeps the curve it launched with.
{% endhint %}

## Why 70/30?

A bigger pool share means deeper liquidity on Raydium after bonding: the coin starts its DEX life with 30% of the supply and about 100 SOL in a locked pool, so trades move the price less and the chart is harder to crash.

## The limits while bonding

* **3% per wallet:** no curve buy can take a wallet above 30M tokens. See [Buying and selling](../trading/buying-and-selling.md#the-3-limit-while-bonding).
* **Fees:** 1% per trade, with the [cover charge](cover-charge.md) just after the open.
* **Liquidity:** the SOL on the curve stays in the program's account. It only leaves through trades by the curve's rules, or into the Raydium pool when the coin bonds. Nobody can withdraw it.
