---
description: What happens when the curve sells out, Velvet Pools, and the locked liquidity.
---

# Bonding

When a coin's bonding curve sells out (about **100 SOL** raised), the coin **bonds**: it moves to its own pool in **Velvet Pools** and trades there from then on.

## What happens

1. The curve stops. No more curve trades.
2. A one-time **0.25 SOL** bonding fee goes to Velvet, paid from the curve.
3. The program creates the coin's Velvet Pools pool with the rest of the curve's SOL and the **30% of the supply** kept aside for it, **priced exactly where the curve ended**. Any of that 30% not needed to match the curve's last price is **burned**, so nobody can buy cheaper right after bonding.
4. The liquidity is **locked forever**: Velvet Pools has no way to withdraw it.

Anyone can send this transaction once the curve is full, and Velvet does it automatically within moments. The program decides where everything goes; whoever sends the transaction can't change it. A coin can't bond while its [cover charge](cover-charge.md) is still on.

<figure><img src="../.gitbook/assets/coin-bonded.png" alt="A bonded coin"><figcaption><p>A bonded coin trades on its pool</p></figcaption></figure>

## Velvet Pools

Velvet Pools is Velvet's own swap program, built for bonded Velvet coins. It uses constant-product pricing (`x × y = k`), with everything a launchpad pool doesn't need taken out:

* **No LP tokens and no withdraw.** There's nothing to lock or unlock, because the liquidity can never leave the pool, by the creator, by Velvet, or by anyone.
* **Only Velvet can open a pool**, one per coin, at an address fixed by the coin's mint. Nobody can set up a fake pool in advance to block or front-run bonding.
* **Plain tokens only**: never frozen, with no transfer fees or hooks.

Its source is public alongside the launchpad's, and the deployed program is a [verified build](../security/verified-build.md).

## After bonding

* The trade box on the coin page trades through the pool. Nothing changes for you; [slippage](../trading/buying-and-selling.md) works the same.
* The **3% wallet limit lifts**.
* Trade it from the coin page or [Velvet Swap](../trading/swap.md).

## Pool fees

Every pool trade pays **0.35%**, taken in SOL:

| Share | Goes to |
| --- | --- |
| **0.20%** | Stays in the pool, so its liquidity grows with every trade |
| 0.05% | The coin's holder pool |
| 0.05% | **The creator's wallet**, paid automatically |
| 0.05% | Velvet |

The program does the split.
