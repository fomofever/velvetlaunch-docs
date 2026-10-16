---
description: Short answers to common questions.
---

# FAQ

<details>

<summary>Is this real money?</summary>

Not yet. Velvet currently runs on Solana **devnet**, where SOL is free test money. USD values on the site use today's real SOL price for reference only. On mainnet, trades use real SOL: only trade what you can afford to lose.

</details>

<details>

<summary>Why wait in a line instead of buying right away?</summary>

Because bots are faster than people. With a line, being first is worthless: everyone in it pays the same price, so the opening belongs to the community instead of snipers. See [The line](../how-it-works/the-line.md).

</details>

<details>

<summary>Can I launch with no SOL?</summary>

Yes. Choose **Free** on the launch page and just sign a message. Your coin waits on the board until someone gets in line; their transaction puts it on-chain and pays the ≈0.022 SOL setup. Your signature only works for that exact coin, once, and expires after 7 days. See [Free launches](../launching/free-launches.md).

</details>

<details>

<summary>Can the creator rug the liquidity?</summary>

No. Bonded coins have 100% of their Raydium LP locked in Raydium's own locker, permanently. Before that, the SOL sits in the program's curve, which only pays out through trades by its rules.

</details>

<details>

<summary>Can more tokens be minted?</summary>

No. Every coin has a fixed 1B supply, and the mint authority is switched off in the launch transaction.

</details>

<details>

<summary>Why can't I buy more than 3%?</summary>

While a coin is bonding, no wallet can buy past 3% of the supply on the curve, so one whale can't scoop the coin. The limit lifts once the coin is on Raydium. See [Buying and selling](../trading/buying-and-selling.md#the-3-limit-while-bonding).

</details>

<details>

<summary>Why was my fee so high?</summary>

You traded in the first minute after the doors opened, when the [cover charge](../how-it-works/cover-charge.md) applies. It starts at 50% and falls to 1% within about a minute, and everything above 1% goes to the coin's holders. The trade box always shows the current fee.

</details>

<details>

<summary>Why did my payout not show up yet?</summary>

You need to hold through a full hour before your balance counts, and payouts run about once an hour. Your streak and multiplier show on each coin page once you hold. See [Hold streak payouts](../trading/hold-streak.md).

</details>

<details>

<summary>What's the ATH × number?</summary>

How far the coin's all-time high got above the line price, the price everyone in the opening line paid. The bar on the coin page shows where the price is now between the two.

</details>

<details>

<summary>What does Bonding / Bonded mean?</summary>

**Bonding**: the coin trades on Velvet's bonding curve. **Bonded**: the curve sold out and the coin now trades on its Raydium pool, with locked liquidity.

</details>

<details>

<summary>Can I burn tokens?</summary>

Yes, from the coin page (🔥 Burn tokens under the trade box). Burned tokens are destroyed for good. When the creator burns, the coin gets a 🔥 Dev burned badge. See [Burning tokens](../trading/burning.md).

</details>

<details>

<summary>My wallet won't connect. What do I do?</summary>

Make sure the wallet is set to the same network as the site (devnet, for now), then refresh the page and try again. If a browser extension wallet still won't connect, try another supported wallet or your phone's wallet app.

</details>

<details>

<summary>What do I have to trust Velvet for?</summary>

Almost nothing: the program enforces the line, the curve, the fees, refunds, bonding and the LP lock. The one part Velvet runs is the hourly hold-streak payout, and the program caps it. See [What you trust Velvet for](../security/trust.md).

</details>

<details>

<summary>Is Velvet audited?</summary>

Not yet. It has its own test suite, a fuzzing campaign and two security reviews behind it, and an external audit is planned before mainnet. The deployed program is a [verified build](../security/verified-build.md) of its public source.

</details>

<details>

<summary>Is Velvet Launch related to Velvet Capital?</summary>

No. Velvet Launch (velvetlaunch.xyz) is an independent Solana launchpad. It has no connection to Velvet Capital or velvet.capital, and no token of theirs is involved here.

</details>
