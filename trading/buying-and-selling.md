---
description: Trading a coin on the bonding curve or in its pool, and the 3% wallet limit.
---

# Buying and selling

Once a coin's doors open, you trade it from the box on the right of its coin page (below the chart on a phone).

<figure><img src="../.gitbook/assets/coin-bonding.png" alt="A coin page while bonding"><figcaption><p>A bonding coin: chart on the left, trade box on the right</p></figcaption></figure>

## How to trade

1. Pick **Buy** or **Sell**.
2. Enter an amount: SOL when buying, tokens when selling. The quick buttons fill in common amounts.
3. Check **You get (est.)**, the **cover charge now** and your **slippage**.
4. Press the button and approve in your wallet.

<figure><img src="../.gitbook/assets/trade-box.png" alt="The trade box" width="420"><figcaption><p>The trade box</p></figcaption></figure>

<figure><img src="../.gitbook/assets/coin-mobile.png" alt="A coin page on a phone" width="320"><figcaption><p>On a phone, the trade box sits below the chart</p></figcaption></figure>

## Where the trade happens

* **Bonding** coins trade on Velvet's [bonding curve](../how-it-works/bonding-curve.md). The price moves with every buy and sell.
* **Bonded** coins trade in their **Velvet Pools** pool. The same box routes your trade there, so nothing changes for you.

## The 3% limit while bonding

While a coin is bonding, no wallet can buy past **3% of the supply** (30,000,000 tokens) on the curve. The trade box shows how much more you can buy under **Wallet limit while bonding**. The program checks this on every curve buy, so one whale can't scoop up the coin before it bonds. The same limit applies to [line commits](getting-in-line.md#the-3-limit-in-the-line) and the creator's [opening buy](../launching/opening-buy.md).

Tokens in your wallet count toward it, and so do tokens you're still owed: your unclaimed share from the line and, for the creator, the opening-buy bag that's still locked. Waiting to claim doesn't get you around it. A buy that would take you over the limit is rejected, and nothing is spent. The limit lifts once the coin bonds.

## The cover charge

Right after the doors open, the fee starts at **50%** and falls to the normal **1%** within about a minute. Everything above 1% goes to the coin's holders. The trade box always shows the fee you'd pay right now. See [The cover charge](../how-it-works/cover-charge.md).

## Slippage

Prices can move between the moment you press the button and the moment your trade lands. Slippage is the most the price can move against you before the trade is cancelled instead. The default is 3%.

Tap **Slippage** in the trade box to change it: pick 0.5%, 1%, 3%, 5% or 10%, or type your own between 0.1% and 50%. Your choice is remembered in your browser.

* **Above 10%**, the box warns you that you may get a much worse price.
* **Below 0.5%**, it warns that the trade may fail if the price moves.
* **Take initials out** never uses slippage: it always returns at least your exact initials, or doesn't go through.

## Your trades

The **Trades** list on the coin page shows every buy and sell, plus the coin's milestones: launched, doors open, bonded and 🔥 burns. On the chart, trades by the creator are marked **D** and your own trades **Y**.
