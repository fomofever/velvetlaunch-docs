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

Velvet Pools is Velvet's own swap program, built for bonded Velvet coins. It's based on Raydium's open-source CP-Swap (constant product, the same `x × y = k` pricing), with everything a launchpad pool doesn't need taken out:

* **No LP tokens and no withdraw.** There's nothing to lock or unlock, because the liquidity can never leave the pool, by the creator, by Velvet, or by anyone.
* **Only Velvet can open a pool**, one per coin, at an address fixed by the coin's mint. Nobody can set up a fake pool in advance to block or front-run bonding.
* **Classic SPL tokens only**, and the coin can never be frozen.

Its source is public alongside the launchpad's, and the deployed program is a [verified build](../security/verified-build.md).

## After bonding

* The trade box on the coin page trades through the pool. Nothing changes for you; [slippage](../trading/buying-and-selling.md) works the same.
* The **3% wallet limit lifts**.
* Wallets and apps can only trade the coin once they support Velvet Pools, so the coin page is the place to trade it.

## Pool fees

Every pool trade pays **0.35%**, taken in SOL:

| Share | Goes to |
| --- | --- |
| **0.20%** | Stays in the pool, so its liquidity grows with every trade |
| 0.05% | The coin's holder pool |
| 0.05% | **The creator's wallet**, paid automatically |
| 0.05% | Velvet |

Velvet collects the creator, holder and Velvet shares regularly; the program does the split.

## Coins that bonded to Raydium

Coins that bonded before Velvet Pools stay in their **Raydium** CPMM pools, with **100% of the LP locked** in Raydium's own locker, permanently. Their share of Raydium's 0.25% trading fee is still collected and split **25% creator · 25% holders · 50% Velvet**, and a quarter of Velvet's part is paired with the coin side and **deposited back into the pool**, with those LP tokens burned (shown as **Fees → liquidity** in the trades list).
