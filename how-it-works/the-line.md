---
description: Why every coin opens with a line, and how one price for everyone stops snipers.
---

# The line

## The problem: sniping

On most launchpads, a new coin can be bought the moment it exists, and the first buyer gets the lowest price. Bots watch for new coins and buy in the same block they're created, then sell into everyone who arrives a few seconds later. The people the coin was made for end up paying the bots.

## Velvet's answer: a line with one price

Every Velvet coin opens with a **line**:

1. **The curve is locked.** While the line is open, nobody can buy the coin at all.
2. **Everyone commits SOL.** Anyone can join, at any point while the line is open, up to about 1.9 SOL per wallet (3% of the supply at the starting price).
3. **The doors open together.** When the timer ends, the program adds up every commit and runs it through the [bonding curve](bonding-curve.md) as **one single buy**.
4. **Everyone pays the same price.** Each wallet gets tokens in proportion to the SOL it put in. Whoever joined first and whoever joined in the last second pay exactly the same average price.

Since being first is worth nothing, there's nothing to snipe. A bot in the line is just another buyer at the same price as you.

## Big lines unlock gradually

When a line puts **more than 30 SOL** into the curve, its tokens don't all arrive at once:

* **25%** of every spot can be claimed as soon as the doors open;
* the other **75% unlocks steadily over 1 hour**. Claim whenever you like: each claim sends whatever has unlocked so far.

A big line opens at a much higher price than it paid, so without this a full line could dump on everyone the moment the doors open. Lines of 30 SOL or less open fully unlocked. The coin page shows how much of your spot has unlocked and a countdown to the rest, and your position counts the locked part as yours.

## A full line can't bond in the first minute

While the [cover charge](cover-charge.md) is on, nothing can finish the bonding curve. If a line is big enough to fill the whole curve, it stops just short of it and the unused SOL is refunded to everyone in the line, pro-rata, with the same **Claim**. A buy that would finish the curve during that minute is refused (the trade box tells you to buy a little less or wait). Once the cover charge is over, the next buy completes the curve and the coin bonds as usual. This way nobody can skip the cover charge by bonding the coin straight away.

## Right after the doors open

The next defence is the [cover charge](cover-charge.md): for about a minute after the doors open, trading costs much more than normal (starting at 50%), and the extra goes to the coin's holders. Flipping the opening becomes expensive, and holders get paid when someone tries.

## The creator can't jump the line either

If the creator wants their own coin, they can make an [opening buy](../launching/opening-buy.md) inside the launch transaction, at the starting price, limited to 3% of the supply (about 1.9 SOL) and shown publicly. It can be locked so it unlocks slowly. There are no hidden dev wallets buying in the first block, because nobody can buy in the first block.

## Line settings

| Setting | Range |
| --- | --- |
| Line length | about 4 seconds to 5 minutes (10 to 750 Solana slots) |
| Commit limit | about 1.9 SOL per wallet: whatever buys 3% of the supply at the starting price |
| Guest-list minimum | none, up to 100 SOL. Below it, everyone is refunded. |
| Big-line unlock | lines over 30 SOL: 25% at open, the rest over 1 hour |

## Who opens the doors?

When the timer ends, anyone can send the transaction that settles the line, and Velvet does it automatically. Settling only follows the program's rules: nobody can change the price or the shares.
