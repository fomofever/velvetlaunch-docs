---
description: The program, Velvet Pools, config and Raydium addresses Velvet uses.
---

# Addresses

{% hint style="warning" %}
Velvet currently runs on **Solana devnet**. Mainnet addresses for the treasury and config will be added here at launch. Always check you're on **velvetlaunch.xyz** before connecting your wallet.
{% endhint %}

## Velvet

| | Address |
| --- | --- |
| Launchpad program | [`8f9XtMzn9J8vapxoLoypKUjNta64jhjfr18WMVCn5yAk`](https://explorer.solana.com/address/8f9XtMzn9J8vapxoLoypKUjNta64jhjfr18WMVCn5yAk?cluster=devnet) |
| Config (devnet) | [`1US82nyGuVex3o6ngeeHgiXVkwFrVqLRjsHpwfzt6fT`](https://explorer.solana.com/address/1US82nyGuVex3o6ngeeHgiXVkwFrVqLRjsHpwfzt6fT?cluster=devnet) |
| Treasury (devnet) | [`Ev7cPd4cU34oixKSiT4RE2LxhU4oCm5ocMh8R2Y5z8qe`](https://explorer.solana.com/address/Ev7cPd4cU34oixKSiT4RE2LxhU4oCm5ocMh8R2Y5z8qe?cluster=devnet) |
| Velvet Pools program | [`VPkPeiAg7LheTtDdBByCmXewabF9zF6yK5YYLmfPjWb`](https://explorer.solana.com/address/VPkPeiAg7LheTtDdBByCmXewabF9zF6yK5YYLmfPjWb?cluster=devnet) |
| Program source | [github.com/fomofever/velvet-program](https://github.com/fomofever/velvet-program) |

The programs will use the same addresses on mainnet. Each coin's pool address is derived from its mint, so there's exactly one per coin.

## Coin addresses

Every coin's mint address is created by the program, and every one ends in **`vLvt`**, for example `6kA4…vLvt`. The program enforces this: it refuses to create a coin at any address that doesn't end in `vLvt`. To be sure a coin was launched on Velvet, open it on velvetlaunch.xyz: the site only lists coins created by Velvet's program.

## Raydium (mainnet, coins that bonded earlier)

| | Address |
| --- | --- |
| CPMM program | `CPMMoo8L3F4NbTegBCKVNunggL7H1ZpdTHKxQB5qKP1C` |
| AMM config (0.25% fee) | `D4FPEruKEHrG5TenZ2mpDGEfu1iUvTiqBxvpU8HLBvC2` |
| LP locker | `LockrWmn6K5twhz3y9w1dQERbmgSaRkfnTeTKbpofwE` |

## Raydium (devnet, coins that bonded earlier)

| | Address |
| --- | --- |
| CPMM program | `DRaycpLY18LhpbydsBWbVJtxpNv9oXPgjRSfpF2bWpYb` |
| AMM config | `5MxLgy9oPdTC3YgkiePHqr3EoCRD9uLVYRQS2ANAs7wy` |
| LP locker | `DRay25Usp3YJAi7beckgpGUC7mGJ2cR1AVPxhYfwVCUX` |
