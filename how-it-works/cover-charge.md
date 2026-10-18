---
description: The opening fee that makes flipping a launch expensive, and pays holders.
---

# The cover charge

When a coin's doors open, its trading fee starts high and falls fast:

| Time after the doors open | Fee on a curve trade |
| --- | --- |
| 0 seconds | 50% |
| about 30 seconds | about 25% |
| about 60 seconds and after | 1% (the normal fee) |

The fee falls in a straight line over **150 Solana slots**, which is about a minute. It applies to buys **and** sells, so dumping the line's tokens right away is as expensive as buying in at the open.

## Where it goes

* The normal **1%** is split as usual: a quarter to the coin's holders, the rest to Velvet.
* **Everything above 1% goes to the coin's holders**, through the [hold streak](../trading/hold-streak.md) pool.

So if someone pays a cover charge to flip the opening, the people holding the coin are the ones who get paid for it.

## No bonding during the cover charge

A coin can't finish its bonding curve (and move to its pool, where there's no cover charge) until the cover charge is over. A buy that would complete the curve in that minute is refused. See [The line](the-line.md#a-full-line-cant-bond-in-the-first-minute).

## VIPs pay half

Wallets with a **VIP** [Velvet Pass](../trading/velvet-pass.md) pay half of the cover charge above the normal fee: 25.5% instead of 50% right at the open. The normal 1% is never discounted.

## See it before you trade

The trade box shows **Cover charge now** on every coin, and the trade button warns you when the cover charge is above 10%. Wait a minute and you pay the normal fee.

<figure><img src="../.gitbook/assets/trade-box.png" alt="Cover charge in the trade box" width="420"><figcaption><p>The current fee is always shown in the trade box</p></figcaption></figure>
