---
description: The few things Velvet does for you, and the limits the program puts on them.
---

# What you trust Velvet for

Almost everything on Velvet is enforced by the program (see [What the program guarantees](guarantees.md)). Here's what's left, and what stops it going wrong.

## The hourly hold-streak payout

Velvet works out each holder's streak and sends the hourly payouts. The program caps what a payout can do. It can:

* only pay **current holders of that coin**;
* never pay out **more than the coin's holder pool holds**;
* never pay a wallet **more than 4× its share of the supply** for that payout;
* only pay **once per payout window**.

A payout can never touch the bonding curve's SOL, refunds, or locked liquidity. Even if something went wrong, the most that could happen is a coin's holders being paid unevenly or late, within those caps.

## Things Velvet does automatically, but anyone could

These steps are permissionless: the program decides what happens, and Velvet just makes sure the transaction is sent promptly.

* Opening the doors when a line's timer ends.
* Moving a coin to Raydium when its curve sells out.
* Collecting the locked liquidity's pool fees.

Anyone can send these transactions and get exactly the same result.

## The website

The site shows you prices, charts and the board, and builds the transactions you sign. Your wallet shows what you're signing. Velvet never holds your keys or your funds.

Coin logos and metadata are stored permanently on **Arweave**, so a coin's name, logo and links keep working in every wallet and explorer even if Velvet's site is gone. Existing coins never depend on the site: they're on-chain, and trade on Raydium once bonded.

## Settings

Fees and limits live in an on-chain config that only the Velvet admin key can change, and only after a public **timelock**. See [Settings and the timelock](timelock.md).

## The program itself

The program can be upgraded by its upgrade authority (Velvet). An external audit is planned before mainnet. You can always check that the deployed program matches its public source: see [Verified build](verified-build.md).
