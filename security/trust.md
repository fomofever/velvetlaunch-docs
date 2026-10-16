---
description: The few things Velvet's own servers do, and the limits the program puts on them.
---

# What you trust Velvet for

Almost everything on Velvet is enforced by the program (see [What the program guarantees](guarantees.md)). Here's what's left, and what stops it going wrong.

## The hourly hold-streak payout

Working out each holder's streak needs to look at history the program doesn't keep, so Velvet's server calculates the payouts and sends them. The program caps what that server can do. It can:

* only pay **current holders of that coin**;
* never pay out **more than the coin's holder pool holds**;
* never pay a wallet **more than 4× its share of the supply** for that payout;
* only pay **once per payout window**.

It can never touch the bonding curve's SOL, refunds, or locked liquidity. The worst a faulty payout server could do is pay a coin's holders unevenly or late, within those caps.

## Things Velvet's servers do automatically, but anyone could

These steps are permissionless: the program decides what happens, and Velvet's servers just make sure someone sends the transaction promptly.

* Opening the doors when a line's timer ends.
* Moving a coin to Raydium when its curve sells out.
* Collecting the locked liquidity's pool fees.

If Velvet's servers went down, anyone could send these transactions and get exactly the same result.

## The website

The site shows you prices, charts and the board, and builds the transactions you sign. Your wallet shows what you're signing. Velvet never holds your keys or your funds.

The site also stores coin logos and metadata, and the list of free launches waiting for a first buyer. If it were down, existing coins would keep working: they're on-chain, and trade on Raydium once bonded.

## Settings

Fees and limits live in an on-chain config that only the Velvet admin key can change, and only after a public **timelock**. See [Settings and the timelock](timelock.md).

## The program itself

The program can be upgraded by its upgrade authority (Velvet). An external audit is planned before mainnet. You can always check that the deployed program matches its public source: see [Verified build](verified-build.md).
