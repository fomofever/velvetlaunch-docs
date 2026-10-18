---
description: Swap any bonded coin with SOL or with another bonded coin.
---

# Velvet Swap

**Swap** (in the menu) trades any coin that has bonded, straight through its locked pool.

* **SOL to a coin, or a coin to SOL**: one swap through the coin's pool.
* **Coin to coin**: the first coin is sold for SOL and that SOL buys the second coin, in **one transaction**. Either both legs go through or neither does.

Pick the coins, type an amount, and the box shows what you'll get, the **minimum received** after [slippage](buying-and-selling.md#slippage), the price impact, the pool fee and the route. If the price moves past your slippage before the swap lands, it's cancelled and nothing is spent.

## Which pools

| Pool | Fee | Shown as |
| --- | --- | --- |
| Velvet Pools (coins bonding now) | 0.35% | the coin's logo |
| Raydium (coins that bonded earlier) | 0.25% | the coin's logo with a small Raydium badge |

A coin-to-coin swap pays both pools' fees, one per leg. Every pool's liquidity is locked for good: see [Bonding](../how-it-works/bonding-to-raydium.md).
