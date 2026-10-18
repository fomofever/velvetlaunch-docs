---
description: Check that the program running on Solana is built from the public source code.
---

# Verified build

Velvet's program source code (the launchpad and Velvet Pools) is public at [**github.com/fomofever/velvet-program**](https://github.com/fomofever/velvet-program).

A **verified build** proves that the program deployed on Solana was built from exactly that code, with nothing added. It uses Solana's standard [verified builds](https://solana.com/docs/programs/verified-builds) process:

1. The program is built inside a fixed Docker image, so the same source always produces the same bytes.
2. The hash of that build is compared with the hash of the program deployed on-chain.
3. A verification record is written on-chain, linking the program to the repository and the exact commit.

## Current status

| | Launchpad | Velvet Pools |
| --- | --- | --- |
| Program ID | `8f9XtMzn9J8vapxoLoypKUjNta64jhjfr18WMVCn5yAk` | `VPkPeiAg7LheTtDdBByCmXewabF9zF6yK5YYLmfPjWb` |
| Library name | `fairlaunch` | `velvet_pools` |
| Network | Solana devnet | Solana devnet |
| Source commit | [`057f0b0`](https://github.com/fomofever/velvet-program/commit/057f0b0241e34853f6a94424752efd42dd318e27) | [`057f0b0`](https://github.com/fomofever/velvet-program/commit/057f0b0241e34853f6a94424752efd42dd318e27) |
| Executable hash | `a33ea9a786e1526db758a790cc6113249cc8f33dd6f4aad42fee95d97cb9feb1` | `b6c934233e852de5ed57e96459b284450a27aa256adfbd1eb4aeb9f5a052824d` |
| On-chain verification record | `RtuQouMuxb8P8h75L5GFHAB7ocKETzPK4u1XZ96yEty` | written by the same process |

On mainnet, the build will also be submitted to OtterSec's public verifier, which gives the program a **Verified** badge on Solana explorers.

## Check it yourself

With Docker and [`solana-verify`](https://github.com/Ellipsis-Labs/solana-verifiable-build) installed:

```sh
git clone https://github.com/fomofever/velvet-program
cd velvet-program
git checkout 73c142f996b3e8482c8a25538bbf5f2173ac9763
solana-verify build --library-name fairlaunch
solana-verify get-executable-hash target/deploy/fairlaunch.so
solana-verify get-program-hash -u devnet 8f9XtMzn9J8vapxoLoypKUjNta64jhjfr18WMVCn5yAk
```

The last two hashes should match. For Velvet Pools, check out its commit above and use `--library-name velvet_pools`, `target/deploy/velvet_pools.so` and its program ID.

Velvet Pools is based on Raydium's open-source [CP-Swap](https://github.com/raydium-io/raydium-cp-swap) (Apache-2.0); its license is kept in the source and changed files are marked.

## Audit status

The program has its own test suite, a fuzzing campaign and two security reviews behind it. **It has not been externally audited yet.** An external audit is planned before mainnet, and its report will be linked here.
