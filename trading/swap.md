---
description: Swap any coin with SOL or with another coin.
---

# Velvet Swap

**Swap** (in the menu) swaps any coin, straight through its locked pool. Coins show up there once their curve sells out.

* **SOL to a coin, or a coin to SOL**: one swap through the coin's pool.
* **Coin to coin**: the first coin is sold for SOL and that SOL buys the second coin, in **one transaction**. Either both legs go through or neither does.

Pick the coins, type an amount, and the box shows what you'll get, the **minimum received** after [slippage](buying-and-selling.md#slippage), the price impact, the pool fee and the route. If the price moves past your slippage before the swap lands, it's cancelled and nothing is spent.

Each pool trade pays the 0.35% [pool fee](../how-it-works/bonding.md#pool-fees); a coin-to-coin swap pays it once per leg. Every pool's liquidity is locked for good: see [Bonding](../how-it-works/bonding.md).
