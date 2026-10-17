---
description: Reading a coin's chart, its timeframes and the indicator lines.
---

# The chart

Every coin page has a live chart built from the coin's own on-chain trades: the opening line, every curve trade and, after bonding, every trade in its pool.

## The controls

| Control | What it does |
| --- | --- |
| **Price / MCap** | Price per token, or market cap (price × the 1B supply). |
| **USD / SOL** | USD uses today's SOL price. |
| **Line / Candles** | A simple price line, or open-high-low-close candles with volume bars underneath. |
| **Timeframe** | 1, 15 or 30 seconds; 1, 5, 15 or 30 minutes; 1, 4 or 12 hours; 1 or 7 days; or the whole history. |
| **Reset** (↺) | Puts the scale and view back to default after you zoom or drag. Live trades never undo your zoom. |

The chart starts at the coin's launch. Minutes with no trades show as faint flat candles, so time runs evenly. A long history opens on the most recent trading; drag left to scroll back to the launch.

## Indicators

Open **Indicators** to turn these on or off (your choice is remembered):

* **Dev trades**: a **D** on each of the creator's buys and sells.
* **Your trades**: a **Y** on your own buys and sells (connect your wallet).
* **Bonding line**: the price or market cap where the coin bonds, as a dashed gold line. For a bonded coin it's the level where it bonded, with a **Bonded** marker on that candle.
* **Your average entry**: the average price your buys filled at.
* **Your average exit**: the average price your sells filled at.
* **Your initials**: the level where what you hold is worth 2× what you still have in, so you can see when you'll be able to [take your initials out](your-position.md#take-initials-out). Shown until you get there.

Your entry, exit and initials lines only appear while you have a position open (tokens in your wallet, or a line spot not yet claimed). Sell everything and they go away; your next buy starts them fresh, counting only that new position (see [rounds](your-position.md#rounds-selling-out-starts-fresh)).

Lines far outside the current view are named under the chart instead (for example "Bonds at $35.0K, 5.1× from here"), so they never squash the candles.

{% hint style="info" %}
The entry and exit lines show fill prices, without fees, so they sit on the candles where you traded. Your profit and loss, fees included, is in [Your position](your-position.md).
{% endhint %}
