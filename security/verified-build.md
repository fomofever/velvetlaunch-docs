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
| Source commit | [`73c142f`](https://github.com/fomofever/velvet-program/commit/73c142f996b3e8482c8a25538bbf5f2173ac9763) | [`ad4ea16`](https://github.com/fomofever/velvet-program/commit/ad4ea16b40b0694c3719f79bd2155f2a2c6f3fdb) |
| Executable hash | `cb0c3423b924960443e0477f328a2ebbf144fcadad0986055e34e8cddb0cae4a` | `9aefa0e9a3faf96c0d2ff30343cc8bc0ae36b45d8115d100ee56177d0c8c9a48` |
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
