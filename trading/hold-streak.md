---
description: How holders are paid every hour, and how the streak multiplier works.
---

# Hold streak payouts

Every coin on Velvet has a **holder pool** of SOL. Every hour, the pool pays part of itself to the coin's holders, straight to their wallets. You don't need to claim or stake anything: just hold.

## Where the pool's SOL comes from

* **0.25%** of every curve trade (a quarter of the 1% fee), and of the line when it settles.
* **The whole cover charge** above the normal fee, paid by people who trade right after the doors open.
* After the coin bonds, **0.05%** of every pool trade.

See [Fees](../how-it-works/fees.md) for the full picture.

## How your share is worked out

Each hour, the pool pays out about **1/24 of itself**, so a burst of trading keeps paying holders for around a day instead of all going out at once. (Small pools are paid out whole.)

That payout is shared by **balance × streak multiplier**:

| You've held for | Multiplier |
| --- | --- |
| Just started | 1× |
| 1 day | 2× |
| 1 week | 2.5× |
| 1 month or more | 3× |

The multiplier climbs smoothly between those points. It doubles over the first day, when flipping is most tempting, then keeps creeping up for a month.

## What resets your streak

* **Selling any amount** resets your streak to the start.
* **Burning** tokens does not reset it.
* Only balance you held through the **whole hour** counts for that hour's payout.

Your streak, multiplier and the time of the next payout show on each coin page once you hold the coin.

{% hint style="info" %}
**Why didn't my payout show up yet?** You need to hold through a full hour before your balance counts, and payouts run about once an hour. Very small shares roll over into the next payout.
{% endhint %}

## Who runs the payouts

Velvet sends the hourly payouts, and the program limits what a payout can do: it can only pay current holders of that coin, never more than the pool holds, and never far more than a wallet's share. It can't touch curve funds, refunds or locked liquidity. See [What you trust Velvet for](../security/trust.md).
