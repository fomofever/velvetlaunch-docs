---
description: Check that the program running on Solana is built from the public source code.
---

# Verified build

Velvet's program source code is public at [**github.com/fomofever/velvet-program**](https://github.com/fomofever/velvet-program).

A **verified build** proves that the program deployed on Solana was built from exactly that code, with nothing added. It uses Solana's standard [verified builds](https://solana.com/docs/programs/verified-builds) process:

1. The program is built inside a fixed Docker image, so the same source always produces the same bytes.
2. The hash of that build is compared with the hash of the program deployed on-chain.
3. A verification record is written on-chain, linking the program to the repository and the exact commit.

## Current status

| | |
| --- | --- |
| Program ID | `8f9XtMzn9J8vapxoLoypKUjNta64jhjfr18WMVCn5yAk` |
| Network | Solana devnet |
| Source commit | [`1893155`](https://github.com/fomofever/velvet-program/commit/1893155450bdf258c489a8c92cc15625ee6fca0d) |
| Executable hash | `10f9d02134bacd6057edfdee0505829ccc5d8d9002f2dc7cea64c6189b5809a6` |
| On-chain verification record | `RtuQouMuxb8P8h75L5GFHAB7ocKETzPK4u1XZ96yEty` |

On mainnet, the build will also be submitted to OtterSec's public verifier, which gives the program a **Verified** badge on Solana explorers.

## Check it yourself

With Docker and [`solana-verify`](https://github.com/Ellipsis-Labs/solana-verifiable-build) installed:

```sh
git clone https://github.com/fomofever/velvet-program
cd velvet-program
git checkout 1893155450bdf258c489a8c92cc15625ee6fca0d
solana-verify build --library-name fairlaunch
solana-verify get-executable-hash target/deploy/fairlaunch.so
solana-verify get-program-hash -u devnet 8f9XtMzn9J8vapxoLoypKUjNta64jhjfr18WMVCn5yAk
```

The last two hashes should match.

## Audit status

The program has its own test suite, a fuzzing campaign and two security reviews behind it. **It has not been externally audited yet.** An external audit is planned before mainnet, and its report will be linked here.
