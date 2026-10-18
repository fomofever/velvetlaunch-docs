---
description: How Velvet's settings can change, and why changes are slow on purpose.
---

# Settings and the timelock

Velvet's fees and limits live in one on-chain **config** account, read by the program on every transaction.

## Changes have to wait

The config can't be changed instantly. A change is first **proposed** on-chain, where anyone can see it, and can only be **applied** after a timelock:

| Network | Timelock |
| --- | --- |
| Mainnet | **48 hours** |
| Devnet (testing) | 1 hour |

That gives everyone time to see a change coming before it takes effect.

## Hard limits

Some limits are written into the program's code, so no config change can ever go past them, even after the timelock:

| | Hard limit |
| --- | --- |
| Normal trading fee | 2% at most (currently 1%) |
| Cover charge | 50% at most |
| Holders' share of the normal fee | never more than the fee itself |
| Bonding fee | 2 SOL at most (currently 0.25 SOL) |
| Line length | 3,000 slots at most (about 20 minutes) |
| Cover charge length | 3,000 slots at most |
| Wallet limit while bonding | 3% of supply, for line commits, opening buys and curve buys (fixed in code) |
| Timelock | 30 days at most |
| Big-line unlock | at least 10% claimable at open, the rest over at most 7 days |
| VIP discount | fixed in code |
| Permanent storage fee | 0.001 SOL per coin at most (currently 0.0001 SOL). Because it's capped this low, the admin can change it without the timelock |

## What a change affects

* **The curve** is copied into each coin when it's created, so a new curve only applies to coins launched after the change.
* **Fees and limits** are read on every transaction, so once a change is applied it covers all coins.

## Current settings

The **How it works** page on velvetlaunch.xyz always shows the live values, read straight from the config. On mainnet:

| Setting | Value |
| --- | --- |
| Normal fee | 1% (¼ to holders) |
| Cover charge | 50% → 1% over 150 slots (≈1 minute) |
| Line length | 10 to 750 slots (≈4 s to 5 min) |
| Line commit limit | 5 SOL per wallet, and never more than buys 3% of the supply (about 1.9 SOL) |
| Creator opening buy | up to 2 SOL, and never more than 3% of the supply (about 1.9 SOL) |
| Guest-list minimum | up to 100 SOL |
| Creator lock | up to 30 days |
| Curve | 70% of supply, bonds at ≈100 SOL |
| Bonding fee | 0.25 SOL |
| Pool fee | 0.35%: 0.20% stays in the pool · 0.05% each to holders, the creator and Velvet (fixed in code) |
| Big-line unlock | lines over 30 SOL: 25% at open, the rest over 1 hour |
